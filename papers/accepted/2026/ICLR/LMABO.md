# Adaptive Acquisition Selection for Bayesian Optimization with Large Language Models

- **中文标题：** 基于大语言模型的贝叶斯优化自适应采集函数选择
- **作者：** Giang Ngo, Dat Phan-Trong, Dang Nguyen, Sunil Gupta, Svetha Venkatesh
- **会议：** ICLR 2026
- **状态：** 🏆 Poster
- **相关性：** 9.6/10
- **方向：** LLM-guided BO / Acquisition Function Selection
- **论文：** https://openreview.net/pdf/cd4e0de0695b84a802957344631556dd16862f10.pdf

## Motivation

BO 的 acquisition function 决定下一步评估哪里，但不存在对所有问题都最优的固定 acquisition function。甚至在同一个优化过程中，最优策略也可能随着预算、当前 surrogate 和搜索进展不断变化。

传统 adaptive portfolio 方法主要依据历史 function value 或 acquisition 的历史表现，难以同时利用预算、采样分布、GP lengthscale 等更加丰富的状态信息。

## 主要创新点

1. **LMABO**：把 acquisition function selection 重新定义成一个由 LLM 完成的在线决策问题。
2. **结构化状态表示**：每次 BO 迭代把完整的优化状态序列化后交给 LLM，包括搜索进展、预算、surrogate 等信息。
3. **LLM 作为 zero-shot strategist**：不要求专门训练一个 acquisition-selection policy，而是直接利用预训练 LLM 的优化知识进行策略选择。
4. **动态选择 acquisition function**：LLM 从多个 acquisition function 组成的 portfolio 中，根据当前优化状态选择下一步策略。

## 解决的问题

解决 BO 中“一个 acquisition function 无法适应所有阶段和所有任务”的问题，同时避免人工设计复杂的动态选择规则。

## 与 BO 的关系

LLM 不负责替代 GP 或 acquisition function，而是站在更高一级：**决定当前应该使用哪个 acquisition function。**

## 与 LLM 的关系

LLM 被定位成在线 optimization strategist，利用上下文理解和推理能力综合多个状态变量。

## 值得关注的原因

这篇论文非常适合用来理解“LLM 作为 BO 高层控制器”的范式。它与简单的 LLM candidate generation 有明显区别：LLM 决策的是 BO 的**策略层**。

## 关键启发

可以进一步推广为让多个 LLM experts 分别负责不同 acquisition strategy，再由一个 meta-agent 根据当前 BO 状态动态融合专家意见。