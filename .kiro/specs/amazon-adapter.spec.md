# Spec: Kiro Amazon App Adapter (Vue 3)

## 1. 概述与目标 (Overview & Goals)
本规格定义了一个用于连接 Kiro AI 编辑器与亚马逊 API/应用服务接口的 Vue 3 适配器模块 (`KiroAmazonAdapter`)。该模块旨在统一管理 Kiro 插件与亚马逊后台数据交互（如商品检索、订单状态监控、AI 提示词转换以及 API 鉴权管理）。

## 2. 技术栈与标准 (Tech Stack & Standards)
- **前端框架**: Vue 3 (Composition API, `<script setup>`)
- **语言**: TypeScript (Strict Mode)
- **状态管理**: Pinia
- **HTTP 客户端**: Axios
- **响应式规范**: RFC-001 (Kiro Event Gateway Specification)

## 3. 核心架构与模块划分 (Architecture)

### 3.1 目录结构
```text
src/
├── adapters/
│   └── kiro/
│       ├── types/
│       │   └── amazon.ts       # 接口定义
│       ├── composables/
│       │   └── useKiroAmazon.ts# 核心逻辑 Composable
│       └── store/
│           └── kiroAmazon.ts  # Pinia 状态映射
```