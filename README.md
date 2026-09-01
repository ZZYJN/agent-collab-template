# 多 Agent 协作项目模板

人类 + 多 AI agent（Claude Code / Codex 等）协作开发的项目模板：开箱即得一套经过两轮独立 AI 交叉审计的协作规范、研发流程、文档模板和 git 钩子。

## 用法（新项目三步）

1. 在 GitHub 点 **Use this template** 创建新仓库（比 fork 干净：没有历史包袱、没有上游关联），clone 到本地；
2. 全局替换 `<项目名>`，补齐 `AGENTS.md` 的「项目概述」；
3. 启用钩子：`git config core.hooksPath scripts/hooks`。然后正常开工——所有 agent 会自动读到规范。

## 里面有什么

| 文件 | 作用 |
|---|---|
| [AGENTS.md](AGENTS.md) | 根规范：角色分工、核心原则、并发与 git 纪律（Codex 原生读取；Claude Code 经 CLAUDE.md 导入） |
| [docs/workflow.md](docs/workflow.md) | 流程：变更分级、文档状态机、派工与评审协议、机器门禁触发器 |
| [docs/templates/](docs/templates/) | PRD / RFC / 任务书模板（含追溯字段与人工闸门记录） |
| [docs/decisions/](docs/decisions/) | ADR 模板 + 三条奠基决策（为什么单一信息源 / 角色制 / 规范分层） |
| [scripts/hooks/](scripts/hooks/) | commit-msg 钩子：强制提交者身份前缀 |

## 设计要点

- **文件是唯一共享记忆**：agent 之间不共享上下文，一切靠仓库文件对齐；
- **人管批准，agent 管执行，机器管强制**：人只守 PRD / RFC 两道闸门 + 敏感动作签核，其余交给流程与钩子/CI；
- **写者不当查者**：一个 agent 实现，另一个 agent 依据文档独立评审；
- **流程绑定角色而非厂商**：换模型、换 CLI，不换流程。

规范定稿前经过两轮独立 AI 交叉审计与修订（审计报告归档于源项目仓库的 docs/reviews/）。
