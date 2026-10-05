# Skill: Amazon Adapter Spec Driver

## 1. 技能激活触发词 (Triggers)
当用户输入以下指令或涉及相关任务时，自动激活本技能：
- "适配亚马逊接口"
- "生成 Kiro Amazon Spec"
- "校验 Amazon API 规范"

## 2. 技能执行流程 (Workflow)

```mermaid
graph TD
    A[收到适配请求] --> B[读取 specs/kiro-amazon-adapter.spec.md]
    B --> C[验证 TypeScript 类型结构]
    C --> D[运行 Vitest 测试用例]
    D --> E[输出适配器结果报告]