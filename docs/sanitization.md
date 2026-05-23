# Sanitization

本仓库是脱敏备份，不是完整 `~/.codex` 镜像。

## 已排除

- `auth.json`
- token、key、cookie、凭据
- sqlite 状态库
- logs、sessions、cache、tmp
- 本机 runtime 路径
- 私有项目代码
- 私有项目状态
- 长命令输出和大段 diff

## 已保留

- 全局工作流规则
- subagent 模板
- Vault 规则
- profile 模板
- 项目状态模板
- 脱敏配置示例

## 发布前检查

建议在提交前运行：

```powershell
rg -n "gho_|ghp_|sk-[A-Za-z0-9]|Bearer|C:\\Users\\|AppData|\.sqlite|logs_2|state_5|session_index" .
```

如果有命中，确认是否属于说明文本；真实密钥或本机路径必须删除。
