# Agent Wait-Resume Tester / 智能体等待恢复测试师

把智能体在等待 CI、部署、审批和 webhook 时的暂停与恢复，变成可重放的验收包。

## 适用触发词

- “让 Agent 等 CI 完成后再继续”
- “测试 webhook 重复回调会不会重复执行”
- “design a safe wait-and-resume flow for an agent”

## 流程

等待点与终态 → 事件合同 → 恢复与人工关口 → 测试矩阵 → 干运行 → 验收包

## 输入与输出

输入可以是状态图、任务配置、日志样本或事件说明。输出包括状态迁移表、事件合同、重放矩阵、证据字段和 PASS/FAIL/CHECK 结论。

## 示例

输入：`CI 成功后让代码审查 Agent 恢复，但同一个回调不能创建两次审查。`

输出会要求 `run_id`、`event_id`、当前状态、重复事件处理和可观察日志断言，并给出正常、重复、乱序、超时、拒绝五类测试。

## 安装

将本目录复制到 Claude Code 的 skills 目录，例如：

`~/.claude/skills/agent-wait-resume-tester/SKILL.md`

本地中文目录名只用于本机归档；安装目录使用 `agent-wait-resume-tester`。

## 发布

建议仓库名：`agent-wait-resume-tester`。发布前先阅读 `smoke-test.md`；通过后可用 GitHub CLI 创建新的公开仓库并推送，绝不覆盖已有仓库或强推。

## 文件树

```text
agent-wait-resume-tester/
├── SKILL.md
├── README.md
├── smoke-test.md
└── publish-checklist.md
```
