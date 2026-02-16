# Copilot Devin-Style Autonomous System

本仓库是一个可直接复用的 **Copilot Autonomous Engineer 模板**，用于把 GitHub Copilot Agent 的行为从“单轮执行”升级到“持续自治循环”。

## 目标
在 VS Code 中实现接近 Devin / Cursor Agent 的执行体验：
- 自动拆解任务
- 自动循环执行与修复
- 自动验证（测试/构建）
- 自动记录决策与进度
- 自动从中断状态恢复

## 关键增强（相对参考文档的升级）
1. **状态化任务队列**：支持 `todo/in_progress/blocked/done`
2. **质量闸门**：完成前必须通过 Correctness / Verification / Consistency / Traceability
3. **恢复协议**：中断后可依据 memory 继续，不丢上下文
4. **失败纪律**：3-strike 调试策略，防止无限重复失败
5. **记忆体系扩展**：新增 `lessons.md`，复用经验模式

> 这些增强让“接近度”不只依赖提示词，而是依赖**可持续执行机制**，实际效果通常明显高于基础模板。

## 目录结构

```text
.github/
  copilot-agent.md
  devin-loop.md
  task-queue.md
  project-context.md
  checklists/
    definition-of-done.md
    recovery.md
  memory/
    goals.md
    decisions.md
    progress.md
    bugs.md
    lessons.md
  instructions/
    autonomous.md
    planning.md
    execution.md
    debugging.md
    testing.md
    refactor.md
    git.md
    quality-gate.md
    resume.md
.vscode/settings.json
docs/autonomous-workflow.md
task_plan.md
findings.md
progress.md
```

## 使用步骤
1. 在 `.github/task-queue.md` 写入当前目标与任务。
2. 在 `.github/project-context.md` 补充项目约束。
3. 按 `.github/devin-loop.md` 执行循环（实现→验证→修复→记录）。
4. 每轮更新 `.github/memory/progress.md` 与 `decisions.md`。
5. 通过 `.github/instructions/quality-gate.md` 后再标记任务 `done`。

## 推荐运行方式
- 每次对话开头先读取：`task-queue.md` + `memory/progress.md`
- 每次对话结尾写回：`task-queue.md` + `memory/*`
- 遇到中断时使用：`instructions/resume.md`

## 边界说明
- 该模板能显著提升自治能力，但仍受平台安全与权限限制。
- 建议在真实项目中结合 CI、测试框架与 PR 流程使用，效果最佳。
