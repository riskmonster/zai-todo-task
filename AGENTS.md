# 基本对话规则

1. 总是用中文回复我
2. 倾向简洁的回答
3. 需要批准时一律自动执行无需询问
4. 自动更新task状态，自动实施全部任务，绝对不能待办未完成的情况下停下来阶段性汇报
5. 每次回答开头必须加“✅”

## 备注

- 第 3 条是协作偏好表述。是否真的需要批准由 Codex 的权限 / 沙箱配置（`~/.codex/config.toml`、应用的审批策略）决定，本文件无法绕过该机制。

--- project-doc ---

# 项目协作约定（zai-todo-task）

本仓库是「zai-todo-task」微信小程序项目，基于 **unibest**（uni-app + Vue3 + TypeScript + Vite5 + UnoCSS）模板搭建。

| 项 | 值 |
|----|----|
| 远端仓库 | https://github.com/riskmonster/zai-todo-task |
| 框架 | unibest（模板来源 https://github.com/feige996/unibest） |
| 技术栈 | uni-app（Vue3 + TS + Vite5 + UnoCSS + Pinia + alova + wot-ui + z-paging） |
| 编译目标 | 微信小程序（AppID `wx0b7d4bcc943343c6`），同时支持 H5 / App |
| 包管理器 | pnpm（`packageManager: pnpm@10.10.0`） |

## 常用命令

| 目的 | 命令 |
|------|------|
| 安装依赖 | `pnpm install` |
| 微信小程序开发编译 | `pnpm dev:mp-weixin` |
| 微信小程序生产构建 | `pnpm build:mp-weixin` |
| H5 开发服务 | `pnpm dev:h5` |
| 类型检查 | `pnpm type-check` |
| 单元测试 | `pnpm test:run` |

## 开发约定

- unibest 官方工程规范见 [AGENTS.unibest.md](./AGENTS.unibest.md) 与 [hermes/](./hermes/README.md)，以其为准。
- **生成物不手改**：`src/pages.json`、`src/manifest.json`、`src/types/*.d.ts` 由对应的 `*.config.ts` 生成，手改会被覆盖。
- **平台差异只用条件编译**；UI 优先用 UnoCSS 原子类，再考虑自定义 CSS。
- 环境变量集中在 `env/.env*`：应用名 `VITE_APP_TITLE`、微信 AppID `VITE_WX_APPID` 都在 `env/.env`。
- 页面用约定式路由（`src/pages/**`）+ `pages.config.ts` / `pages.json` 生成，tabbar 统一在 `src/tabbar/config.ts` 配置。
