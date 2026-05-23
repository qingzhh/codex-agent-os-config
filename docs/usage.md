# Usage

## 日常任务模板

```text
请按我的 Codex Agent OS 执行本任务。

使用：
- Profile: D:\vault\profiles\codex-workflow.md
- Project State: D:\vault\projects\project-template.md

要求：
- planner 作为 workflow manager 判断复杂度
- planner/reviewer 只读，禁止改文件
- worker 严格按 plan 最小改动
- reviewer 检查 correctness / regression / edge cases
- subagent 完成即 disposable
- fresh context > long history
- 完成前必须验证
- 有长期价值时再更新 Vault
- 输出中文、简洁
```

## Profile 选择

- 字幕任务：`D:\vault\profiles\subtitle-workflow.md`
- 前端 React：`D:\vault\profiles\frontend-react.md`
- Python 研究：`D:\vault\profiles\python-research.md`
- MCP 开发：`D:\vault\profiles\mcp-dev.md`
- Codex 工作流：`D:\vault\profiles\codex-workflow.md`

## 记忆写入规则

- 只记录长期有价值的信息。
- 优先追加 checkpoint，不重写全文。
- 不写入长日志、临时推理、大段 diff、构建产物或未验证结论。
- `projects/` 只保存项目状态、风险和下一步。
- `profiles/` 只保存跨项目能力模板。
