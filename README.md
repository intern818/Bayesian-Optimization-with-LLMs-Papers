# 贝叶斯优化 × LLM 最新研究论文

> 追踪与整理贝叶斯优化及其与 LLM、Agent 等技术结合的最新研究论文。

本项目面向 Bayesian Optimization（BO）及其与 Large Language Models（LLMs）、Agent、多智能体和相关基础模型技术结合的研究方向，持续追踪高质量会议论文以及 arXiv、OpenReview 上值得关注的前沿工作。

## 研究范围

重点关注以下方向：

- Bayesian Optimization（BO）
- LLM-guided / LLM-assisted Bayesian Optimization
- LLM × Bayesian Optimization
- Agentic Bayesian Optimization
- Multi-Agent Bayesian Optimization
- LLM 作为 BO surrogate、prior、acquisition 或搜索策略
- BO 与 LLM 推理、规划、候选生成结合
- BO 与模型剪枝、量化、压缩结合
- BO 用于 LLM / Foundation Model 的训练、调优与后训练
- Multi-objective / constrained / high-dimensional BO 与 LLM、Agent 的结合
- 其他具有明确研究价值的 BO × LLM / Agent 交叉方向

## 论文优先级

### 🏆 第一优先级：高质量会议论文

优先整理已经正式录取或发表的高水平会议论文，包括但不限于：

- ICML
- NeurIPS
- ICLR
- AAAI
- ACL
- EMNLP
- KDD
- IJCAI
- CVPR / ICCV / ECCV
- AISTATS
- UAI
- COLT

会议质量作为重要参考，但不会机械地只按照 CCF 分类筛选。

### 🧪 第二优先级：前沿预印本

持续从以下来源发现尚未正式录取、但具有较高研究价值的工作：

- arXiv
- OpenReview

预印本需要经过相关性、创新性和研究价值筛选，不进行简单的关键词堆积。

## 相关性评分

每篇最终收录论文按照 0–10 分进行相关性与研究价值综合评分：

- **9–10：核心论文** —— BO 与 LLM / Agent 深度结合，或对该方向具有明显推动作用
- **8–8.9：高度相关** —— 方法与 BO × LLM / Agent 有较强联系
- **7–7.9：值得关注** —— 对 BO、LLM 或 Agent 的某一关键技术方向具有明显价值
- **<7：通常不进入每日重点推送**

评分不会只根据标题，而会结合摘要、方法、实验和论文定位进行判断。

## 论文状态

- 🏆 Accepted / Published：已录取或正式发表
- 🟡 Under Review：正在审稿
- 🔵 Preprint：预印本
- ❌ Rejected：已拒稿
- ⚪ Withdrawn：已撤稿

## 项目结构

```text
Bayesian-Optimization-with-LLMs-Papers/
├── README.md
├── papers/
│   ├── accepted/
│   │   └── 2026/
│   │       ├── ICML/
│   │       ├── NeurIPS/
│   │       ├── ICLR/
│   │       ├── AAAI/
│   │       ├── ACL/
│   │       └── EMNLP/
│   └── preprints/
│       └── 2026/
├── daily/
├── metadata/
│   └── papers.json
└── rss/
    └── feed.xml
```

## 每日更新

项目计划通过自动化任务每日检索和整理最新论文：

1. 优先检查高水平会议中的 BO 相关论文；
2. 从 arXiv 和 OpenReview 补充最新前沿工作；
3. 进行论文去重和投稿状态判断；
4. 判断论文与 BO、LLM、Agent 等方向的实际相关性；
5. 对论文进行质量与相关性评分；
6. 生成中文摘要、研究贡献、与 BO/LLM 的关系及值得关注的原因；
7. 更新 GitHub 论文库和每日论文速报；
8. 进一步生成 RSS Feed，方便通过 RSS 阅读器订阅。

## 目标

希望将本项目逐渐建设为一个 **Bayesian Optimization × LLM Research Radar**，帮助研究者持续发现高质量论文、追踪新兴研究方向，并观察 BO 与 LLM / Agent 结合的发展趋势。
