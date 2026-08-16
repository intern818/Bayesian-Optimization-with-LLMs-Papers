# DASH: Decoupled Adaptive Surrogate - Acquisition Harness for Automated Bayesian Optimization

- **作者：** Changquan Zhao；Yuxiang Sun；Ruihao Zhu；Cheng Hua；Yulian He
- **来源：** arXiv
- **发布日期：** 2026-08-01
- **状态：** 🔵 预印本 / 尚未确认正式录取
- **类别：** LLM-enhanced AutoBO
- **相关性评分：** 9.4/10
- **arXiv：** https://arxiv.org/abs/2608.00641

## 核心内容

DASH 面向自动化贝叶斯优化，分别处理 surrogate selection 与 acquisition adaptation：根据预测可靠性、不确定性校准和排序一致性选择 surrogate，并通过两阶段 acquisition controller 动态调整 acquisition function 配额，最后由 LLM 进行候选选择。同时加入 knowledge-guided warm start 和结构化 memory。

## 与贝叶斯优化的关系

DASH 直接优化 BO 内部的 surrogate 和 acquisition 组件，目标是根据任务和优化阶段动态选择更合适的 BO 配置。

## 与 LLM / Agent 的关系

LLM 负责 acquisition 候选的最终选择，并与知识引导 warm start、memory 等机制结合，形成 LLM-enhanced AutoBO。

## 为什么值得关注

它与“让 LLM 参与 BO 内部组件选择”的研究路线高度相关。与直接让 LLM 生成候选点相比，这种方式更强调保留 BO 的统计优化结构，同时利用 LLM 的上下文决策能力。

## 局限与关注点

需要关注 LLM 最终决策是否稳定，以及 memory、warm start 和 acquisition controller 各模块之间是否存在较强的任务依赖。论文目前为预印本，应持续跟踪后续投稿状态。
