# conversation-memory-manager · 对话记忆管家

中文 | [English](#english)

## 中文

把对话本身当作**可版本化管理的资产**：AI 助手长任务对话逐单元 markdown 归档、1-5 分重要性自动评分、用户终审保留清单、主线/支线类 Git 分离、节点级上下文回溯重建。

### 解决什么问题

| 痛点 | 对策 |
|---|---|
| 上下文一压缩，对话原文永久消失 | 压缩前抢救式转录，归档即真相源 |
| 任务越聊越长，上下文越来越臃肿 | 主线/支线分离；恢复时默认只拉主线 |
| 记忆该留该删说不清 | 五分制自动评分 + 用户终审清单 |

### 安装

```bash
npx skills add zzh112212/conversation-memory-manager -g -y
```

### 快速上手（对 AI 说）

- 「归档这轮 / 记住这轮」→ 单元立刻落盘，强制 5 分
- 「记忆清单」→ 生成终审清单，勾选文件或口头报编号定去留
- 「字体调试那几轮开支线」→ 独立归档独立评分，收尾三选一（合并/归档/删除）
- 「回溯到定部署方案的节点」→ 生成重建简报，恢复当时上下文，后续内容封存不删

记忆库在项目根 `.memory/`：`manifest.md` 总索引 + `mainline/` 主线 + `branches/` 支线 + `archive/` 留尸区（删除不物理清除）+ `rollbacks/` 回溯简报。git 可用时自动启用独立记忆仓库（只在 `.memory/` 内 `git init`，绝不碰你的项目 `.git`）。

### 技能套装（可选联动，单装完整可用）

- **input-triage** — 输入分诊（管进来的东西）
- **context-continuity** — 任务状态接力（管任务进行到哪）
- **conversation-memory-manager** — 对话存留（管说过什么，本技能）

## English

Version your conversation as an asset: per-unit markdown archival, 1-5 importance scoring, user-approved retention checklists, mainline/branch git-like separation, and node-level context rollback — for AI coding assistants on long tasks.

```bash
npx skills add zzh112212/conversation-memory-manager -g -y
```

Say things like "archive this turn", "memory checklist", "branch off the font-debugging rounds", or "roll back to the node where we picked Vercel". Memory lives in `.memory/` at the project root. Works standalone; integrates optionally with `input-triage` and `context-continuity`.

## 版本 / Version
- v1.2（2026-09-30）：终审/支线收尾组件优先——弹窗点选 + 一次确认回传替代逐条输入（新增 references/widget-checklist.md）；evals +1
- v1.1（2026-09-30）：新增「应答进行中」自指单元规范（F1）；清单格式自检硬门槛（F3）；evals 新增 2 例（自指单元、清单格式自检）
- v1.0（2026-09-29）：首发

## License

MIT
