# Spec: Management System Development & Maintenance Specification (.kiro Standard)

## 1. 概述与目标 (Overview & System Scope)
本规范约束管理系统开发与维护的三个核心子项目架构：
1. **Core Admin Portal (后台管理系统系统端)**: 基于 Vue 3 + Pinia + Element Plus/Ant Design 的前端管理界面。
2. **API Gateway & Services (后台服务与接口网关)**: 基于 Node.js/TypeScript (Fastify/NestJS) 的业务中台。
3. **DevOps & Maintenance Automation (运维与自动化部署系统)**: 基于 Docker/CI/CD 的部署与状态监控维护模块。

---

## 2. 三项目模块架构规范 (System Architecture)

```text
root/
├── .kiro/
│   ├── rules.md                         # Kiro 全局交互行为准则
│   └── specs/
│       └── management-system-dev-ops.spec.md  # 本核心规范文档
├── apps/
│   ├── admin-web/                       # 项目 1：后台管理系统前端
│   ├── api-server/                      # 项目 2：后端服务与 API 网关
│   └── devops-scripts/                  # 项目 3：运维部署与监控脚本
```