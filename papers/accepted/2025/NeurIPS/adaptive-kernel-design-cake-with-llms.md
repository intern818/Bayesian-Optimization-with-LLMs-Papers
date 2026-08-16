# Adaptive Kernel Design for Bayesian Optimization Is a Piece of CAKE with LLMs

- **作者：** Richard Suwandi；Feng Yin；Juntao Wang；Renjie Li；Tsung-Hui Chang；Sergios Theodoridis
- **会议：** NeurIPS 2025 Main Conference Track
- **状态：** 🏆 已录取
- **类别：** LLM-guided Bayesian Optimization / LLM × BO
- **相关性评分：** 9.8/10
- **论文：** https://papers.nips.cc/paper_files/paper/2025/hash/c03a2610bca2712b984b331fd4f7bb6f-Abstract-Conference.html
- **代码：** https://github.com/richardcsuwandi/cake

## 核心内容

论文提出 CAKE（Context-Aware Kernel Evolution），利用 LLM 作为 GP kernel 的交叉与变异算子，在 BO 过程中根据观测数据自适应生成和改进 kernel。同时提出 BAKER，对候选 kernel 综合 Bayesian Information Criterion（BIC）和 Expected Improvement 进行排序。

## 与贝叶斯优化的关系

传统 BO 中 GP kernel 的选择通常固定或依赖启发式策略。CAKE 将 kernel 设计本身纳入 BO 的自适应优化过程，使 BO 可以随着观测数据变化动态调整其先验结构。

## 与 LLM / Agent 的关系

LLM 不只是用于生成候选点，而是直接参与 surrogate model 的结构设计：负责生成、变异和改进 GP kernel。这属于比较典型的 **LLM-enhanced BO** 路线。

## 为什么值得关注

这篇工作非常贴合“LLM 如何改变 BO 内部机制”这一问题。它把 LLM 从传统的自然语言接口或候选点生成器进一步推进到 **surrogate/kernel design** 层面，对研究 LLM 先验与 BO 结合很有参考价值。

## 局限与关注点

需要重点关注 LLM 生成 kernel 的可靠性、计算成本，以及不同 LLM backbone 对最终 BO 性能的影响。后续研究也可以进一步探索让多个 Agent 分工进行 kernel 设计、验证和选择。
