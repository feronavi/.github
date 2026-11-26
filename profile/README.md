<div align="center">

# Feronavi

### 让团队与 Agent，一起推进项目。

开源、自托管的项目协作平台，连接需求、知识与交付。多人一起写文档，项目知识随问随用，Agent 直接参与业务执行。

[![License](https://img.shields.io/badge/license-AGPL--3.0-blue)](https://github.com/JasperPengC/feronavi/blob/main/LICENSE)
[![Container](https://img.shields.io/badge/GHCR-0.3.0-2496ED?logo=docker&logoColor=white)](https://github.com/orgs/feronavi/packages/container/package/feronavi-app)
[![MCP](https://img.shields.io/badge/MCP-Server-5B6EE1)](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp)
[![RAG](https://img.shields.io/badge/RAG-Built--in-168B78)](https://github.com/JasperPengC/feronavi#rag)
[![CRDT](https://img.shields.io/badge/CRDT-Real--time%20docs-805AD5)](https://github.com/JasperPengC/feronavi#collaboration)

[快速开始](https://github.com/JasperPengC/feronavi#get-started) ·
[MCP 接入](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp) ·
[使用文档](https://feronavi.com/zh/docs/overview/) ·
[变更日志](https://github.com/JasperPengC/feronavi/blob/main/CHANGELOG.md) ·
[正式版本](https://github.com/JasperPengC/feronavi/releases)

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

## 快速部署

使用 Docker Compose 安装正式版本 **0.3.0**，无需安装 Node.js 工具链或从源码编译。本版新增需求变更、正式测试与发布证据，安装产物见[版本发布页](https://github.com/JasperPengC/feronavi/releases/tag/v0.3.0)。

```bash
mkdir feronavi && cd feronavi
curl -fL https://raw.githubusercontent.com/JasperPengC/feronavi/v0.3.0/compose.yaml -o compose.yaml
(umask 077; test -e .env || echo "DB_PASSWORD=$(openssl rand -hex 24)" > .env)
docker compose pull
docker compose up -d --wait
```

访问 `http://127.0.0.1:3000/setup` 创建首个组织和管理员。本版应用镜像支持并验证了 `linux/amd64`；其他架构尚未完成验收。

**容器镜像：**[`feronavi-app:0.3.0`](https://github.com/orgs/feronavi/packages/container/package/feronavi-app) · [`feronavi-db:16-0.2.0`](https://github.com/orgs/feronavi/packages/container/package/feronavi-db)

缓存采用官方 `valkey/valkey:8-alpine`，由 Compose 作为独立 `cache` 服务启动；应用与 worker 共用应用镜像，数据库镜像内不打包 Valkey。

配套 MCP 桥接包为 `feronavi-mcp@0.1.1`，工具定义与权限来自服务端。

准备升级到 0.3.0 时，请先确认目标产物已发布，再阅读[升级说明](https://github.com/JasperPengC/feronavi/blob/main/UPGRADING.md)。配置、MCP 客户端和 API 说明请参阅[产品介绍与部署指南](https://github.com/JasperPengC/feronavi)。

## 社区

本项目在 [LINUX DO](https://linux.do) 社区推广。

---

### 立即开始

使用 GHCR 预构建镜像和 Docker Compose 开箱部署，无需安装 Node.js 或本地编译工具链。

[查看产品 README 与部署说明](https://github.com/JasperPengC/feronavi#top) ·
[MCP 接入指南](https://github.com/JasperPengC/feronavi/tree/main/packages/feronavi-mcp)
