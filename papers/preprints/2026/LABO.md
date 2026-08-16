# LABO: LLM-Accelerated Bayesian Optimization through Broad Exploration and Selective Experimentation

- **作者：** Zhuo Chen, Xinzhe Yuan, Jianshu Zhang, Jinzong Dong, Ruichen Zhou, Yingchun Niu, Tianhang Zhou, Yu Yang Fredrik Liu, Yuqiang Li, Nanyang Ye, Qinying Gu
- **来源：** arXiv，2026-05-21
- **状态：** 🔵 Preprint
- **相关性：** 9.5/10
- **方向：** LLM-Accelerated BO / Cheap Surrogate / Scientific Discovery
- **论文：** https://arxiv.org/abs/2605.22054

## Motivation

科学实验通常昂贵且数据稀缺，而 LLM 的预测成本远低于真实实验。已有 LLM-BO 方法通常把 LLM 直接嵌入 sampling 或 surrogate pipeline，却没有充分利用“LLM 便宜、真实实验昂贵”这一成本差异。

## 主要创新点

1. **LLM 作为低成本探索器**：允许 LLM 对搜索空间进行大范围、低成本预测。
2. **动态 gating criterion**：根据不确定性动态决定一个候选点应该由 LLM 预测，还是付出真实实验成本。
3. **单一 BO loop 中融合两类反馈**：LLM prediction 与真实 experimental observation 被放进同一个优化循环。
4. **理论分析**：给出 cumulative regret bound，用理论形式解释廉价 LLM evaluation 对样本效率的帮助。

## 解决的问题

核心问题是：如何在昂贵真实实验和廉价但不完美的 LLM 预测之间进行合理的预算分配。

## 与 BO 的关系

BO 负责最终的 uncertainty-aware decision making，而 LLM 相当于一个低成本的信息来源。

## 为什么值得关注

它提供了一种非常实用的思路：**不要只讨论“LLM 能不能替代实验”，而是让 LLM 尽可能便宜地探索，把真正昂贵的 evaluation 留给最值得验证的区域。**

## 对研究的启发

这条路线可以进一步和 multi-agent、expert ensemble、LLM prior 融合：多个 LLM expert 负责廉价预测/探索，再由 BO 根据不确定性决定何时调用真实 oracle。