---
name: proposal-review
description: |
  审核方案、提案、市场策略、增长方案、商业论证、课程大纲、活动策划和对外材料。用于用户要求“审核这份方案”“方案审稿”“框架审核”“内容审核”“数据来源审核”“review proposal”时。该 skill 通过多视角审稿 harness 检查逻辑链、事实证据、数据来源、结构说服力、反方质疑和可执行性，输出尖锐、可修改、可追责的审核报告。
disable-model-invocation: true
---

# Proposal Review

对用户提供的方案文本、文件路径、当前对话草稿或文档内容进行多视角审核。目标是发现会影响判断、说服和执行的硬伤，而不是润色语气。

## Load references

执行审核前读取：

- `references/review-protocol.md`
- `references/reviewer-roles.md`
- `references/evidence-standards.md`
- `references/scoring-rubric.md`
- `references/output-template.md`

## Intake

先归一输入，提取：

- 方案标题与目标
- 目标受众
- 使用场景：内部决策、客户提案、销售转化、课程宣传、增长实验、公开发布等
- 核心结论
- 关键论证链
- 数据、案例、引用、来源
- 明示假设与隐含假设
- 需要读者采取的行动

缺少受众、用途或成功标准时，按最合理默认值继续审核，并在报告开头标记“默认假设”。不要因输入不完整而中断，除非完全没有可审核正文。

## Harness

按 `review-protocol.md` 编排审核：

1. 生成 review packet。
2. 分别启动独立审稿视角：严谨逻辑学家、演化经济学家、证据与数据审计员、目标用户/决策者代理、红队反方审稿人。
3. 第一轮审稿不得互相读取意见。
4. 合成阶段区分共识问题、单一视角问题和冲突意见。
5. 按 `output-template.md` 输出最终报告。

如当前环境无法真正并行启动子 agent，则在同一响应中模拟隔离审稿：每个角色独立分析，先完成全部角色判断，再进入合成，不得边看边改前一个角色结论。

## Review rules

- 引用方案原句或段落定位问题。
- 区分硬伤、弱点、表达优化，不混为一谈。
- 不写泛泛表扬，不说“整体不错但可以优化”。
- 不补造数据，不把模型推断包装成事实。
- 对无来源事实标记来源缺口，而不是直接判真。
- 每个高优先级问题必须给出修改方向。
- 最终报告优先服务用户修改：先列 Top 问题，再给细节。

## Output

使用 `references/output-template.md`。默认中文输出，代码、变量名、英文专有名词保留英文。
