<div align="center">

# Feronavi

### 面向团队与 AI Agent 的项目协作空间

Feronavi 是一个开源、自托管的项目协作平台：把团队、知识和 Agent 放进同一套项目工作流，在权限、审计和可验证操作的约束下完成交付。

[![License](https://img.shields.io/badge/license-AGPL--3.0-blue)](https://github.com/JasperPengC/feronavi/blob/main/LICENSE)
[![Container](https://img.shields.io/badge/GHCR-0.2.0-2496ED?logo=docker&logoColor=white)](https://github.com/orgs/feronavi/packages/container/package/feronavi-app)
[![MCP](https://img.shields.io/badge/MCP-Server-5B6EE1)](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp)
[![RAG](https://img.shields.io/badge/RAG-Built--in-168B78)](https://github.com/JasperPengC/feronavi#rag)
[![CRDT](https://img.shields.io/badge/CRDT-Real--time%20docs-805AD5)](https://github.com/JasperPengC/feronavi#collaboration)

[Quick start](https://github.com/JasperPengC/feronavi#开始使用) ·
[MCP setup](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp) ·
[Documentation](https://github.com/JasperPengC/feronavi/tree/main/docs)

</div>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JasperPengC/feronavi/main/docs/screenshots/01-workbench-dark.png" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JasperPengC/feronavi/main/docs/screenshots/10-workbench-light.png" />
  <img src="https://raw.githubusercontent.com/JasperPengC/feronavi/main/docs/screenshots/10-workbench-light.png" alt="Feronavi project workspace" width="100%" />
</picture>

## 一个工作空间，连接团队与 Agent

- **项目交付：**在一个自托管平台内管理需求、工作项、迭代、发布和项目知识。
- **内置 RAG：**支持跨项目检索，也支持限定项目范围对话，回答带有来源引用。
- **完整 MCP Server：**兼容的 Agent 可以发现工具、读取项目上下文、执行权限校验后的操作，并复读核验结果。
- **CRDT 协同文档：**多人实时编辑，自动合并并在短暂断线后恢复本地变更。
- **开放接口：**通过版本化 OpenAPI 接口和 MCP 客户端接入现有自动化体系。

## Get started

Run the prebuilt containers with Docker Compose. No local Node.js toolchain or source compilation is required.

```bash
mkdir feronavi && cd feronavi
curl -fL https://raw.githubusercontent.com/JasperPengC/feronavi/v0.2.0/compose.yaml -o compose.yaml
(umask 077; test -e .env || echo "DB_PASSWORD=$(openssl rand -hex 24)" > .env)
docker compose pull
docker compose up -d --wait
```

Open `http://127.0.0.1:3000/setup` to create the first organization and administrator. The published application image supports `linux/amd64` and `linux/arm64`.

**Images:** [`feronavi-app:0.2.0`](https://github.com/orgs/feronavi/packages/container/package/feronavi-app) · [`feronavi-db:16-0.2.0`](https://github.com/orgs/feronavi/packages/container/package/feronavi-db)

Read the [full product overview and deployment guide](https://github.com/JasperPengC/feronavi) for configuration, upgrades, MCP clients, and API details.

---

### 立即开始

使用 GHCR 预构建镜像和 Docker Compose 开箱部署，无需安装 Node.js 或本地编译工具链。

[查看产品 README 与部署说明](https://github.com/JasperPengC/feronavi#top) ·
[MCP 接入指南](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp)
