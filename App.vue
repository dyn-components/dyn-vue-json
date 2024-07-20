<script setup lang="tsx">
import DynComponent from "./src/index.ts";

const jsonData = {
  name: "John",
  age: 30,
  address: {
    city: "New York",
    postalCode: "10001",
  },
  hobbies: ["reading", "travelling"],
  isActive: true,
  data: [1, 2, 3],
  test: null,
};
</script>

<template>
  <DynComponent :data="jsonData" />
</template>

<style lang="scss" scoped></style>
