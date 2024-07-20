<script lang="tsx" setup>
import './styles/index.scss'
import { onMounted, ref, watch } from "vue";
import { createElement, createJsonTree } from "./utils/index";

const props = defineProps({
  data: {
    type: Object,
    required: true,
  }
});

const rootRef = ref<HTMLElement>();

function addCopyButton(container: HTMLElement) {
	const button = createElement("button", "copy-button", "Copy");
	container.appendChild(button);
	button.addEventListener("click", () => {
		const jsonString = JSON.stringify(props.data, null, 2);
		navigator.clipboard.writeText(jsonString).then(() => {
			alert("JSON copied to clipboard");
		});
	});
}

onMounted(() => {
  watch(
    () => props.data,
    () => {
      const json = props.data;
      if (typeof json === "object" && json !== null) {
        const jsonObject = createElement("div", "json-object");
        rootRef.value!.innerHTML = "";
        rootRef.value!.appendChild(jsonObject);
        createJsonTree(json, jsonObject);
        addCopyButton(rootRef.value!);
      } else {
        rootRef.value!.innerHTML =
          typeof json === "string" ? json : JSON.stringify(json, null, 2);
      }
    },
    { immediate: true, deep: true }
  );
});
</script>

<template>
  <main ref="rootRef" class="dyn-component--vue dyn-json"></main>
</template>

<style lang="scss" scoped></style>
