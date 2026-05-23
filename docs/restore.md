# Restore

## 恢复全局规则

将 `codex/AGENTS.md` 的内容合并到本机：

```text
~/.codex/AGENTS.md
```

建议手动合并，避免覆盖本机已有规则。

## 恢复 subagents

将以下文件复制到：

```text
~/.codex/agents/
```

文件：

- `codex/agents/planner.toml`
- `codex/agents/worker.toml`
- `codex/agents/reviewer.toml`

## 恢复配置

`codex/config.example.toml` 是脱敏示例，不建议直接覆盖本机 `~/.codex/config.toml`。

推荐做法：

1. 备份现有 `~/.codex/config.toml`。
2. 手动合并 model、reasoning、sandbox、agents、features 等稳定配置。
3. 本机路径、project trust、MCP 本地路径由本机重新生成或手动填写。

## 恢复 Vault

将 `vault/` 内容复制到：

```text
D:\vault\
```

如已有 Vault，优先合并 `profiles/` 和模板，不要覆盖真实项目状态。
