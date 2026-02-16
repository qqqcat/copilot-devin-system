# Decisions Log

## Template
- Date:
- Decision:
- Why:
- Impact:
- Revisit Trigger:

## 2026-02-16
- Decision: 使用状态化任务队列（todo/in_progress/blocked/done）。
- Why: 静态清单无法支撑持续执行与恢复。
- Impact: 提升续跑能力与过程透明度。
- Revisit Trigger: 若项目规模非常小，可降级为简单 checklist。

## 2026-02-16
- Decision: 引入质量闸门与 3-strike 失败协议。
- Why: 减少重复失败与“假完成”。
- Impact: 提高稳定性，降低回归风险。
- Revisit Trigger: 若任务是一次性 PoC，可简化闸门。
