# Review Protocol

## Goal

把方案审核拆成“输入归一 → 独立审稿 → 交叉质询 → 综合判定 → 修改清单”。审核目标是提升方案的可信度、说服力和可执行性。

## Phase 1: Review packet

从用户输入中抽取：

```markdown
## Review Packet
- Title:
- Audience:
- Use case:
- Desired action:
- Core claim:
- Argument chain:
  1. Premise:
  2. Inference:
  3. Conclusion:
- Evidence used:
- Explicit assumptions:
- Hidden assumptions:
- Constraints:
```

缺失信息用“默认假设”标记，不要擅自当作事实。

## Phase 2: Independent review

分别执行 5 个视角：

1. 严谨逻辑学家
2. 演化经济学家
3. 证据与数据审计员
4. 目标用户 / 决策者代理
5. 红队反方审稿人

每个视角只基于原文和 review packet 判断。不要读取其他视角结论后再形成意见。

每个审稿人必须返回：

```markdown
## Reviewer: <role>

### Verdict
- 结论：Pass / Revise / Fail
- 置信度：High / Medium / Low

### Critical issues
1. 问题：
   - 证据：引用方案原句或段落
   - 原因：为什么是问题
   - 影响：会导致什么误判
   - 修改建议：怎么改

### Evidence gaps
- Claim:
- Required source type:
- Acceptable evidence:

### Best preserved parts
- 只保留真正值得保留的部分，不写客套话。
```

## Phase 3: Cross-examination

综合时执行：

- 多个审稿人共同指出的问题 → 高优先级。
- 单个审稿人指出但影响严重的问题 → 高优先级但标记为“单一视角高风险”。
- 审稿意见冲突 → 按证据强度、目标受众、使用场景仲裁。
- 风格偏好 → 降级处理，不进入 Top 问题，除非影响理解或转化。
- 无来源事实 → 不判定真假，只判定“证据不足”。

## Phase 4: Final synthesis

最终报告不得堆叠 5 个审稿人原文。必须改写成用户可执行的修改报告：

1. 先给最终 verdict。
2. 再给 Top 3-5 问题。
3. 每个问题都包含：原文证据、为什么严重、怎么改。
4. 再给按维度的详细审核。
5. 最后给发布前 checklist。

## Anti-collusion rules

- 不用“大家都认为”代替证据。
- 不因多个角色重复同一观点就自动判定正确，仍需检查原文证据。
- 不允许审稿角色互相迁就。
- 红队反驳必须构造最强反方，不做稻草人。
- 保留部分必须具体，不能写“结构清晰”“观点有价值”这类空话。
