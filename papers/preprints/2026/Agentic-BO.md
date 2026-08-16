# Agentic Bayesian Optimization through Surrogate-Augmented Autoresearch

- **作者：** Paul Brunzema, Louis Tiao, Nhat Le, Kevin De Angeli, Yao Xuan, Djordje Gligorijevic
- **来源：** arXiv，2026-07-31
- **状态：** 🔵 Preprint
- **相关性：** 9.9/10
- **方向：** Agentic BO / LLM Agent / BO Backend
- **论文：** https://arxiv.org/abs/2608.00316

## Motivation

传统 BO 的优势来自 uncertainty-aware search，但领域先验通常很难编码进 kernel、surrogate 或问题结构。LLM 能从自然语言、代码和文档中获得丰富的非结构化先验，但现有 LLM-BO 方法往往把 LLM 固定在 surrogate、acquisition 或 candidate generation 某一个角色；如果直接把控制权全部交给 LLM，又可能失去 BO 的系统化探索能力。

## 主要创新点

1. **Agentic Bayesian Optimization 范式**：LLM agent 成为 BO loop 的中央决策者，而 Bayesian backend 继续提供不确定性建模和可靠搜索基础。
2. **Sara agent + lenz backend**：agent 可以配置问题、调用 BO backend、选择并提交 evaluation，还可以根据新证据修改优化策略。
3. **动态修改整个 BO 问题**：agent 可以收紧搜索边界、切换 acquisition function、针对性追加 evaluation，甚至根据新要求重新定义问题。
4. **自然语言先验 + Bayesian uncertainty**：把 LLM 的非结构化知识与 BO 的 uncertainty-aware search 结合。

## 解决的问题

解决“LLM 太灵活但缺乏 BO 的可靠搜索机制”和“传统 BO 很可靠但难以利用非结构化领域先验”之间的矛盾。

## 为什么值得重点关注

这是目前很值得跟踪的 **Agentic BO** 路线：不是把 LLM 塞进 BO 的某个组件，而是让 agent 负责高层 orchestration，同时保留 BoTorch/BO backend 的统计基础。

## 对研究的启发

可以把 BO 看成一个可调用的 optimization tool，让 Agent 负责任务理解、策略切换、预算管理和动态重构；这比单纯让 LLM 预测 candidate 更接近“Agent + BO”。
