# Maximizing Intermediate Checkpoint Value in LLM Pretraining with Bayesian Optimization

- **作者：** Deyuan Liu；Zecheng Wang；Bingning Wang；Weipeng Chen；Chunshan Li；Zhiying Tu；Dianhui Chu；Dianbo Sui
- **会议：** ICML 2025
- **状态：** 🏆 已录取（Poster）
- **类别：** BO for LLM / LLM Training Optimization
- **相关性评分：** 9.1/10
- **OpenReview：** https://openreview.net/forum?id=UvwWrUV1JV

## 核心内容

论文研究如何利用中间训练 checkpoint，通过贝叶斯优化搜索 checkpoint merging 的最佳权重，从而更有效地利用 LLM 预训练过程中的中间模型状态。

## 与贝叶斯优化的关系

BO 被用于搜索 checkpoint merging 权重这一昂贵的黑盒优化空间，在有限实验预算下寻找更优的模型组合方案。

## 与 LLM / Agent 的关系

优化对象直接来自大型语言模型预训练过程，因此属于 **BO for LLM training / post-training** 方向，而不是让 LLM 参与 BO 算法内部决策。

## 为什么值得关注

它体现了 BO 的另一条重要路线：不是“LLM 帮助 BO”，而是“BO 帮助 LLM”。随着 LLM 训练和后训练成本持续增加，如何用少量昂贵实验优化训练策略、模型组合和超参数，是 BO 与 LLM 交叉的重要应用方向。

## 局限与关注点

后续可以关注搜索空间规模、单次评估成本、不同模型规模下的可迁移性，以及 BO 与其他黑盒优化方法的公平比较。
