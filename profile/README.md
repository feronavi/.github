<div align="center">

# Feronavi

### Project work for people and AI agents, in one place.

An open-source, self-hosted workspace for planning work, building shared knowledge, and delivering projects. Bring your team and agents into the same workflows, with permissions and an audit trail.

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

## One workspace, shared by your team and agents

- **Project delivery:** organize requests, work items, iterations, releases, and project knowledge in one self-hosted platform.
- **Built-in RAG:** ask across projects or focus on one project; answers include references back to source material.
- **Full MCP server:** let compatible agents discover tools, read project context, perform permission-checked actions, and verify the results.
- **CRDT document collaboration:** edit documents together in real time, resolve concurrent changes, and recover local edits after a short disconnect.
- **Open interfaces:** connect MCP clients and integrate through the platform's versioned OpenAPI endpoints.

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

### 面向团队与 Agent 的项目协作空间

Feronavi 是开源、自托管的项目协作平台。团队与 Agent 共用项目上下文，在同一套权限和审计规则下推进工作。

- **内置 RAG：**跨项目检索，回答带来源引用。
- **完整 MCP Server：**Agent 可发现工具、读取上下文、执行有权限约束的业务操作，并复读核验结果。
- **CRDT 实时协作：**多人同时编辑文档，自动合并并支持短暂离线恢复。
- **开箱部署：**使用 GHCR 预构建镜像与 Docker Compose，无需本地编译。

[查看中文 README 与部署说明](https://github.com/JasperPengC/feronavi#top) ·
[MCP 接入指南](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp)
