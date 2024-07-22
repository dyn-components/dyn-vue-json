# json


[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 目录

- [介绍](#介绍)
- [安装](#安装)
- [快速开始](#快速开始)
- [属性说明](#属性说明)
- [事件](#事件)
- [方法](#方法)
- [自定义样式](#自定义样式)
- [示例](#示例)
- [贡献指南](#贡献指南)
- [维护者](#维护者)
- [许可证](#许可证)
- [致谢](#致谢)

## 介绍

简要介绍该组件的功能和用途。

## 安装

```bash
pnpm add dyn-components --save-dev
```

修改 vite.config.js

```ts
import viteDynComponents from "dyn-components/vite-plugin-dyn-components";

export default defineConfig({
  viteDynComponents()
})
```

## 快速开始

```vue
<template>
  <dyn-json :data="{}"></dyn-json>
</template>
```
