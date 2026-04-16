# Evals — 黄金案例回归测试

10 个覆盖多运动/多级别/多伤病/多训练阶段的测试案例。用于：
- 重构前后验证行为一致
- 新增规则后检查是否破坏老逻辑
- 接新贡献者的 PR 前跑一遍

## 如何运行（手动）

1. 打开 Claude Code（或粘贴 SKILL.md 到其他 LLM）
2. 输入 `cases.md` 里每个 case 的 `Input` 块
3. 让教练输出诊断 + 周计划
4. 按该 case 的 `Must have` / `Must not have` 条目逐条打勾
5. 任何一项不通过 = 回归，查根因

## 如何运行（半自动）

有 Claude API key 时用 `run.sh`（待实现）：
- 批量跑 10 个 case，产物存 `evals/output/`
- 用 `grep -E` 按 pattern 检查 assertions
- 输出 pass/fail 报告

## 通过标准

首次基线建立：运行 10 个 case，记录实际输出作为 baseline。
之后每次重构：输出必须包含所有 `Must have` 条目，不包含任何 `Must not have` 条目。
允许的差异：措辞、组数微调、顺序——只要 P0/P1 分配一致、禁忌执行一致、诊断标签一致。
