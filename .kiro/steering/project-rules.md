# Steering Directive: Code Style & Syntax Standards

## 1. Vue 3 & TypeScript 编码规范

### 1.1 组件书写规范 (SFC)
- 必须使用 `<script setup lang="ts">` 组合式 API 语法。
- 组件命名使用 **PascalCase**（如 `AmazonAdapterCard.vue`）。
- 模版中使用的属性必须声明明确的 TypeScript 类型，**严禁使用 `any` 类型**。

### 1.2 状态管理与 Composables
- 函数与自定义 Hook 统一使用 `use` 前缀小驼峰命名（如 `useAmazonApi`）。
- 业务状态统一优先使用 Pinia 管理，简单的局部响应式变量使用 `ref()` 或 `reactive()`。

### 1.3 代码格式化
- 缩进：空格 `2` 字符。
- 语句结尾：**不加分号**（Semicolonless 风格）。
- 字符串引用：统一优先使用单引号 `'`。

---

## 2. 示例规范代码 (Canonical Code Example)

```vue
<script setup lang="ts">
import { ref } from 'vue'

interface Props {
  asin: string
  active?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  active: false
})

const emit = defineEmits<{
  (e: 'update:active', value: boolean): void
}>()

const status = ref<'idle' | 'loading' | 'success'>('idle')
</script>

<template>
  <div class="adapter-item" :class="{ active: props.active }">
    <span>ASIN: {{ props.asin }}</span>
  </div>
</template>