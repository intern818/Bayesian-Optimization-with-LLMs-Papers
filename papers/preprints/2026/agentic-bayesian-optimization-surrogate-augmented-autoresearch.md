# Agentic Bayesian Optimization through Surrogate-Augmented Autoresearch

- **作者：** Paul Brunzema；Louis Tiao；Nhat Le；Kevin De Angeli；Yao Xuan；Djordje Gligorijevic
- **来源：** arXiv
- **发布日期：** 2026-07-31
- **状态：** 🔵 预印本 / 尚未确认正式录取
- **类别：** Agentic Bayesian Optimization
- **相关性评分：** 9.9/10
- **arXiv：** https://arxiv.org/abs/2608.00316

## 核心内容

论文提出 Agentic Bayesian Optimization，将 LLM Agent 置于 BO 循环的核心决策位置，而 Bayesian backend 负责提供不确定性感知的优化基础设施。Agent 可以配置问题、查询后端、选择并提交评估，并根据新证据动态调整优化策略，例如修改搜索边界、切换 acquisition function、定向提出评估，甚至重新定义优化问题。

论文实现了 Sara（surrogate-augmented autoresearch agent）和 lenz（模块化 BoTorch backend），并在合成和真实任务上进行实验。

## 与贝叶斯优化的关系

BO 不再只是被 LLM 调用的一种固定工具，而是成为 Agent 的不确定性优化后端。论文强调保留 BO 的系统性探索能力，同时允许 Agent 动态控制 BO 流程。

## 与 LLM / Agent 的关系

这是非常典型的 **Agentic BO**：LLM Agent 可以参与问题配置、候选评估、acquisition 选择、搜索边界调整和优化策略修改。

## 为什么值得关注

这篇工作代表了 BO × LLM 从“LLM 辅助某一个 BO 组件”向“LLM Agent 管理整个 BO loop”演进的趋势。对于 Multi-Agent BO、动态专家融合以及 LLM 控制 BO 流程等研究方向尤其值得关注。

## 局限与关注点

需要进一步研究 Agent 决策的稳定性、不同 LLM backbone 的影响、工具调用成本以及 Agent 自主修改 BO 策略时可能引入的偏差。
