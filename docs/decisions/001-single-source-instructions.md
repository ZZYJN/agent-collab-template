# ADR-001: 代理指令文件采用 AGENTS.md 单一信息源

日期：2026-08-31 ｜ 提出者：[claude] ｜ 批准人：张焯元（基线批准时追认）｜ 状态：已采纳（部分表述被 ADR-003 收窄）

## 背景

本项目由 Claude Code 与 Codex 共同开发。Codex 原生读取 `AGENTS.md`（跨代理开放标准）；Claude Code 只读取 `CLAUDE.md`，不原生支持 `AGENTS.md`。若各维护一份规范，两份文件必然漂移。

## 决定

`AGENTS.md` 是唯一权威规范；`CLAUDE.md` 只包含 `@AGENTS.md` 导入和 Claude 专属补充区，不承载共同规范内容。

## 理由与被否掉的替代方案

- **符号链接（`ln -s AGENTS.md CLAUDE.md`）**：官方同样支持，但 Windows 上创建符号链接需要管理员权限或开发者模式，且部分工具对符号链接处理不一致。`@import` 是 Claude Code 官方文档的推荐方式，还保留了写 Claude 专属指令的位置。
- **维护两份独立文件**：必然漂移，直接否掉。

## 影响

- 修改规范只改 `AGENTS.md`；除 Claude 专属内容外，不往 `CLAUDE.md` 写任何规范。
- 未来接入其他支持 AGENTS.md 标准的代理（Cursor、Gemini CLI 等）零成本。
