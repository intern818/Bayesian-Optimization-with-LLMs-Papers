# Multi-Agent LLMs for Adaptive Acquisition in Bayesian Optimization

- **作者：** Andrea Carbonati, Mohammadsina Almasi, Hadis Anahideh
- **来源：** arXiv，2026-03-30
- **状态：** 🔵 Preprint
- **相关性：** 9.6/10
- **方向：** Multi-Agent LLM / Acquisition Strategy / BO
- **论文：** https://arxiv.org/abs/2603.28959

## Motivation

BO 中 exploration-exploitation 是核心矛盾，传统 BO 通过 acquisition function 显式控制，而 LLM optimizer 通常依赖 prompt 中隐式的历史信息推理，因此搜索行为不容易解释和控制。

作者进一步观察到：如果让一个 LLM 同时负责“策略选择”和“candidate generation”，容易出现 cognitive overload，导致搜索不稳定和过早收敛。

## 主要创新点

1. **多智能体分工**：把 exploration-exploitation 控制拆成 strategic policy mediation 与 tactical candidate generation 两个角色。
2. **Strategy Agent**：负责给不同搜索标准分配可解释权重，例如 informativeness、diversity、representativeness。
3. **Generation Agent**：根据 Strategy Agent 输出的搜索策略生成候选点。
4. **显式化搜索策略**：把原本隐藏在单个 LLM prompt 中的搜索政策变成可观察、可调节的中间变量。

## 解决的问题

解决单 Agent 同时进行“搜索策略推理 + 候选生成”造成的认知负担和搜索不稳定问题。

## 为什么值得关注

这篇论文与你关注的 Multi-Agent + BO 非常直接相关。它说明多智能体的价值不一定是“多个模型投票”，更可以是**将 BO 中不同层次的决策过程拆成不同 agent**。

## 对研究的启发

可以继续研究：多个 expert 分别学习不同 acquisition philosophy，再由一个 meta-agent 根据当前 BO state 动态融合，而不是简单平均多个 LLM 的答案。