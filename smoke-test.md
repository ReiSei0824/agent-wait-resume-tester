# Smoke Test — 2026-11-21

## 结构检查：通过

- `name` 为 `agent-wait-resume-tester`，仅含小写连字符。
- description 150 字符，以 `Designs` 开头，说明了触发情境。
- 五个必需章节齐全；工作流 6 步；Gotchas 6 条；无未填充占位符。
- README 的安装目录、仓库名、文件树与 skill name 一致，未把中文归档目录当作安装路径。

## 触发干运行：通过

| 触发语句 | 预期落点 | 结果 |
|---|---|---|
| `CI 绿了以后，Agent 总会重复跑一次，帮我验收恢复逻辑。` | 事件关联、幂等、重放矩阵 | PASS：输出状态表和重复事件断言。 |
| `Test an agent workflow that resumes after a deployment webhook.` | webhook 合同、乱序/过期测试、证据 | PASS：输出可执行验收包，不停在抽象建议。 |

## 结论

通过。此处为文本级干运行，不声称完成了真实 webhook 或生产调度器验证。
