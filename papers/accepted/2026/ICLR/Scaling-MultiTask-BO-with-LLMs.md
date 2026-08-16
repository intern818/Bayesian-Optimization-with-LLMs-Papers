# Scaling Multi-Task Bayesian Optimization with Large Language Models

> 注：本文件与 BOLT 论文对应；仓库中保留一个主条目即可，后续自动化会通过 arXiv/OpenReview ID 去重。

- **会议：** ICLR 2026 Poster
- **相关性：** 9.7/10
- **核心标签：** Multi-Task BO、LLM Transfer、Warm Start
- **OpenReview：** https://openreview.net/forum?id=5X7g7gYxjX

## 一句话理解

把大量历史 BO 任务中的优质解“蒸馏”给 LLM，让 LLM 为新任务提供初始化，而不是让 Multi-Task GP 无限膨胀。

## 最值得看的点

核心价值不在于让 LLM 完整接管 BO，而在于把 LLM 当作跨任务经验迁移器；这是一种非常干净的“LLM prior + BO refinement”架构。