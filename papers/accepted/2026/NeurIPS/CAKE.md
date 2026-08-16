# Adaptive Kernel Design for Bayesian Optimization Is a Piece of CAKE with LLMs

- **中文标题：** 利用 LLM 自适应设计贝叶斯优化核函数：CAKE
- **作者：** Richard Suwandi, Feng Yin, Juntao Wang, Renjie Li, Tsung-Hui Chang, Sergios Theodoridis
- **会议：** NeurIPS 2025 主会
- **状态：** 🏆 已录取
- **相关性：** 9.8/10
- **方向：** LLM × BO / LLM 生成 GP Kernel
- **论文：** https://papers.nips.cc/paper_files/paper/2025/hash/c03a2610bca2712b984b331fd4f7bb6f-Abstract-Conference.html

## Motivation

BO 的效果高度依赖 Gaussian Process 的 kernel。传统方法通常固定 kernel，或者使用人工设计的 kernel 选择策略。当真实目标函数的结构与预设 kernel 不匹配时，BO 可能收敛缓慢甚至得到较差解。

作者的核心想法是：LLM 已经掌握大量数学、优化和代码知识，因此可以让 LLM 参与 kernel 的设计，而不是人为规定一个固定 kernel。

## 主要创新点

1. **CAKE（Context-Aware Kernel Evolution）**：让 LLM 充当 kernel 的 crossover 和 mutation 操作器，根据 BO 当前观察到的数据不断生成和修改 GP kernel。
2. **BAKER（BIC-Acquisition Kernel Ranking）**：结合 Bayesian Information Criterion（BIC）衡量模型拟合能力，并结合 Expected Improvement 判断当前优化价值，从多个候选 kernel 中选择更合适的一个。
3. **闭环 kernel 演化**：kernel 不再是 BO 开始前一次性确定，而是随着优化过程和观测数据持续演化。

## 解决的问题

传统 BO 中“kernel 选什么”高度依赖人工先验，而且一个 kernel 很难适用于不同任务。CAKE 尝试让 LLM 根据任务上下文和当前数据自动产生更加合适的 kernel 结构。

## 与 BO 的关系

这是比较直接的 **LLM-in-the-BO-loop** 方法，LLM 并没有取代 GP，而是改变 BO 中非常核心的 surrogate kernel 设计。

## 与 LLM 的关系

LLM 主要承担结构搜索角色，通过自然语言/代码形式生成 kernel，并进行 crossover / mutation。

## 值得关注的原因

这篇论文对你的研究尤其有参考价值：它不是简单让 LLM “推荐下一个点”，而是把 LLM 放到 BO 的**结构设计层**。这为“LLM 作为 BO expert / prior / algorithm designer”提供了一个很清晰的范式。

## 需要注意

重点关注 LLM 生成 kernel 的稳定性、计算开销以及不同模型之间的迁移能力。论文实验覆盖超参数优化、控制器调参和光子芯片设计等真实任务。