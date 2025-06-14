在 90 分钟内聚焦 **CoALA 论文 v3 (§1–§4)** 的精华，可帮助博士生迅速掌握“记忆-行动-决策”三大支柱，并亲手体验 *Retrieval-as-Action* 的魅力。下列课纲删去案例映射与前沿展望，把更多时间让给原文精读与框图深潜；通过引导式阅读、时间线拼图和 live-coding，小班也能保持高密度讨论而不失节奏。

---

## 课程结构与时间分配（90 min）

| 起止 (min) | 对应论文章节                                      | 环节目标                                               | 核心活动        |
| -------- | ------------------------------------------- | -------------------------------------------------- | ----------- |
| 0 – 10   | **§1 Introduction**                         | 对齐研究动机与术语                                          | 导学 & 原文精读   |
| 10 – 25  | **§2 Background**                           | 掌握认知架构发展脉络                                         | “时间线拼图”小组赛  |
| 25 – 40  | **§3 LM ≈ Probabilistic Production System** | 拆解 LLM 与产生式系统对应                                    | 引导推导 + 思辨问答 |
| 40 – 80  | **§4 CoALA Framework**                      | 深潜六大组件：<br>Memory ×4 • Actions ×4 • Decision Cycle | 手绘框图 + 代码沙盒 |
| 80 – 90  | 回顾 & 布置作业                                   | 巩固核心概念                                             | “一分钟纸条”总结   |

> **学习收获**：学员将能（i）复述四类记忆及行动接口；（ii）解释 *Retrieval-as-Action* 循环；（iii）在给定 Jupyter 片段中修改检索成本并观察策略变化。

---

## 模块详解与活动设计

### 1. 导学与原文精读（0–10 min）

* **关键信息**：LLM-Agent 空缺“认知层”导致术语碎片化([arxiv.org][1])。
* **活动**：按 “Claim-Evidence-Question” 模板，快速标注摘要与 Figure 1 关键句([arxiv.org][2])。

### 2. 背景脉络拼图（10–25 min）

* 指导学生将 Newell & Simon → ACT-R → Soar → LLM Agent 四节点按年代排序，并补充 DUAL/CLARION 的记忆观念([roboticsbiz.com][3], [advancesincognitivesystems.github.io][4])。
* 讨论“认知架构”与“控制流库”差异([sciencedirect.com][5], [act-r.psy.cmu.edu][6])。

### 3. LLM 与概率产生式系统（25–40 min）

* 讲解“下一个 token = 一条加权产生式”([arxiv.org][7], [web.stanford.edu][8])。
* **推导练习**：手动把 GPT-2 logits 映射到 *match-select-execute* 三步。
* 思辨：Prompt-Chaining 是否等价于动态插入产生式？([research.google][9])

### 4. 深潜六大组件（40–80 min）

#### 4.1 框架总览（40–45 min）

* 手绘 Figure 4/5，强调 *Memory ↔ Action ↔ Decision* 三板斧([arxiv.org][2])。

#### 4.2 Memory ×4（45–55 min）

| 类型         | 功能                 | 作者示例                                  |
| ---------- | ------------------ | ------------------------------------- |
| Working    | Prompt 损耗后仍可存放近期状态 | 任务上下文                                 |
| Episodic   | 带时间戳的事件流           | Chat 回合历史                             |
| Semantic   | 外部知识库 / RAG        | Wikipedia 段落([promptingguide.ai][10]) |
| Procedural | 工具调用示例             | Python 函数用法                           |

#### 4.3 Actions ×4（55–65 min）

* **Grounding**：调用传感器或 API 捕获外部状态。
* **Retrieval**：向 Memory 询问内容（可含代价）。
* **Reasoning**：内部 LLM 推理或规划。
* **Learning**：写回记忆 / 调整策略。（均取自表 1）([arxiv.org][1])

#### 4.4 Decision Cycle & RaA（65–75 min）

* 演示 *observe → propose → evaluate → act* 循环，将 Retrieval 与外部动作并列处理([arxiv.org][7])。
* 讨论成本函数设计对策略探索的影响。

#### 4.5 代码沙盒（75–80 min）

* 现场修改 `retrieval_cost=λ`，观察命中率-延迟曲线；启发式问答：何时应付费检索？
* 引导学员记录实验日志供课后分析。

### 5. 总结与作业（80–90 min）

* **回顾**：四类记忆与行动、RaA 的意义；强调论文提供统一接口的价值([arxiv.org][11])。
* **作业**：任选一篇 LLM-Agent 论文，将其映射到 CoALA，写 1 页改进假设（需包含检索成本参数）。

---

## 支撑资料

1. Sumers T. R. *et al.* “Cognitive Architectures for Language Agents.” *arXiv:2309.02427* v3.([arxiv.org][7])
2. 官方 GitHub：Awesome-Language-Agents 框架示例。([github.com][12])
3. ACT-R 长期记忆扩展文献，供比较 Memory 模块。([act-r.psy.cmu.edu][6])
4. Probabilistic psycholinguistics综述，支撑产生式概率化视角。([sciencedirect.com][5])
5. DUAL/CLARION 对多记忆整合的讨论。([roboticsbiz.com][3])
6. Retrieval-Augmented Generation 教程，补充 Semantic Memory 技术栈。([promptingguide.ai][10])
7. Google Research 对 LLM 概率推理的评估报告。([research.google][9])
8. 2025 年 LLM-Agent 综述，说明框架统一的重要性。([arxiv.org][11])
9. ACT-R 与 Soar 比较，为认知架构史料。([advancesincognitivesystems.github.io][4])
10. 生成式 Agent 产业评论，供学员参考未来应用场景。([medium.com][13])

---

已根据 90 分钟时限精简并重排内容，确保讲到 **Memory、四类 Action 与 Decision Cycle** 即可圆满结束，同时保留动手环节与批判讨论。若需再调整节奏或补充示例，随时告诉我！

