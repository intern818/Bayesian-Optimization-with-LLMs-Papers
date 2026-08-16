# Scaling Multi-Task Bayesian Optimization with Large Language Models

- **中文标题：** 利用大语言模型扩展多任务贝叶斯优化
- **作者：** Yimeng Zeng, Natalie Maus, Haydn Thomas Jones, Jeffrey Tao, Fangping Wan, Marcelo Der Torossian Torres, Cesar de la Fuente-Nunez, Ryan Marcus, Osbert Bastani, Jacob R. Gardner
- **会议：** ICLR 2026
- **状态：** 🏆 Poster
- **相关性：** 9.7/10
- **方向：** Multi-Task BO / LLM Transfer
- **论文：** https://openreview.net/pdf/cd4e0de0695b84a802957344631556dd16862f10.pdf

## Motivation

Multi-Task BO 的目标是利用过去任务的优化经验，加速新任务的优化。传统方法通常通过 multi-task GP、共享 kernel 或深度特征学习建立跨任务 surrogate，但当任务数量从几十扩展到几百、上千时，性能容易饱和。

作者希望回答一个问题：能否把大量历史 BO 经验压缩进 LLM，让 LLM 为新任务提供高质量初始化，而不需要构建一个越来越庞大的共享 surrogate？

## 主要创新点

1. **BOLT（Bayesian Optimization with LLM Transfer）**：不把 LLM 作为 BO surrogate，而是让 LLM 根据任务描述生成候选初始化点。
2. **Initialization-only Transfer**：测试任务阶段仍使用普通 single-task BO，LLM 主要负责提供初始候选，从而降低系统复杂度。
3. **持续微调闭环**：历史任务完成后，把 BO 找到的高质量解用于继续微调 LLM；更好的 BO 解又会产生更好的后续初始化。
4. **规模化跨任务迁移**：论文报告该方法可以扩展到约 1500 个任务，并避免共享 surrogate 在大量任务上的性能饱和。

## 解决的问题

传统 Multi-Task BO 在任务规模扩大后，跨任务建模越来越困难。BOLT 将“跨任务知识迁移”从 surrogate 建模问题转化成了 LLM 的生成与迁移问题。

## 与 BO 的关系

BO 本身仍然负责精细搜索和样本效率；LLM 主要负责 warm-start / initialization。

## 与 LLM 的关系

LLM 被训练成一个能够根据任务上下文产生优质候选解的“跨任务经验库”。

## 值得关注的原因

这篇论文对“LLM 是否应该直接替代 BO”这个问题给出了一个很有价值的答案：**不一定。LLM 可以只负责提供跨任务先验，而把不确定性建模和局部精细搜索继续交给 BO。**

## 关键启发

如果你的研究涉及多智能体、多专家或 LLM prior，这篇论文值得重点关注其“LLM 负责先验迁移 + BO 负责可靠优化”的模块化思想。