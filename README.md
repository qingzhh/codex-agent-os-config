# Codex Agent OS Config

这是一个脱敏后的 Codex 配置备份与参考仓库，用于长期升级、迁移和分享。

## 包含内容

- `codex/AGENTS.md`：全局 Codex 工作流、context protection、Vault/Profile 分层规则。
- `codex/config.example.toml`：脱敏后的 Codex 配置示例。
- `codex/agents/`：planner、worker、reviewer 三个 subagent 模板。
- `vault/AGENTS.md`：Vault 长期记忆规则。
- `vault/profiles/`：跨项目能力模板。
- `vault/projects/`：项目状态模板和 Codex OS 示例状态。
- `docs/`：使用、恢复和脱敏说明。

## 不包含内容

- 认证文件、token、key、cookie。
- Codex 日志、session、SQLite 状态库、本地缓存。
- 本地项目代码、私有项目路径、个人项目状态。
- 构建产物、临时输出、大段 diff。

## 推荐使用方式

在 Codex 中使用：

```text
请按我的 Codex Agent OS 执行本任务。

使用：
- Profile: D:\vault\profiles\codex-workflow.md
- Project State: D:\vault\projects\project-template.md

流程：
- planner 作为 workflow manager 判断复杂度
- worker 按 plan 最小改动执行
- reviewer 只读审查 correctness / regression / edge cases
- 完成前必须验证
- 只有长期有价值的信息才写入 Vault
```

## 恢复思路

1. 先备份本机现有 `~/.codex`。
2. 只复制需要的文件，例如 `codex/AGENTS.md`、`codex/agents/*.toml`。
3. 根据本机环境手动合并 `codex/config.example.toml`，不要直接覆盖已有配置。
4. 将 `vault/` 内容复制或同步到 `D:\vault\`。

详细说明见 [docs/usage.md](docs/usage.md)、[docs/restore.md](docs/restore.md) 和 [docs/sanitization.md](docs/sanitization.md)。
