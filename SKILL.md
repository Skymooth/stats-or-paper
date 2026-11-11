---
name: stats-or-paper
description: 统计 / 运筹 / ML 系统方向的论文写作与审稿工具。起草或改写摘要、引言、相关工作、方法、实验、结论；检查 claim 与证据是否对齐；投稿前做对抗式自审；回应审稿意见；生成开题（选题论证）报告。Use when drafting, revising, reviewing, or self-auditing a statistics / operations-research / ML-systems paper, thesis proposal, or conference rebuttal.
license: MIT
version: 1.0.0
---

# 统计 / OR / ML 系统论文：写作与审稿

目标不是"写得漂亮"，而是**让审稿人无法问倒你**：每个 claim 有证据、每个数字有区间、每条引用可核实、每个假设被交代。

## 何时用 / 不用

| | 场景 |
|---|---|
| **用** | 起草或改写任一章节；把草稿改成审稿友好版；写开题论证报告；投稿前自审；写 rebuttal |
| **不用** | 创意写作；纯工程文档；不需要论证的说明文 |

## 核心工作流（六步，别跳步）

1. **先定故事，再动句子。** 用一句话写下唯一核心贡献。写不出 = 还没想清。
2. **反向推理**（写之前回答）：解决什么技术问题？为什么还没有好解？我们的贡献是什么？为什么它能解决？靠什么证据成立？
3. **搭迷你大纲**：每节 3–7 条 bullet，每条对应一个 paragraph 的 message。
4. **逐段写**：一段一个 message，首句就把它说出来。
5. **写完做 reverse outlining**（`references/paragraphs.md`）：抽出每段 topic sentence，检查能否映射回节论旨；映射不上的段删或改。
6. **对抗式自审**（`references/review.md`）：以"我要拒这篇稿"的心态重读，逐条消灭高风险问题。

## 全局原则

1. **一段一个 message**；首句即 message。
2. **名词自足**：术语首次出现先定义，之后不改口径。
3. **句间有明确关系**：因果、对比、递进、细化——不要只"并置"。
4. **说发现，不说行为**。写"A 使 B 下降 3 个百分点（95% CI [1.2, 4.8]）"，不写"我们分析了 A 和 B 的关系"。
5. **不要先立一个朴素解再讲改进**——那会让工作看起来像增量补丁（`references/structure.md`）。
6. **claim 必须与证据对齐**；对齐不了就弱化或删掉这句。
7. **图和表是正文，不是装饰**：图要能单独读懂；表要自带标题、单位、样本量。

## 证据纪律（本 skill 最重要的一条）

写作时给**每一个事实性 claim** 标证据状态。这是自查标记，定稿前按需清理。

| 标记 | 含义 | 允许怎么用 |
|---|---|---|
| `[正式]` | 已在同行评议的期刊/会议正式发表（有 DOI 或 proceedings 页） | 可作论据 |
| `[预印]` | 仅 arXiv / Zenodo / 个人站，未经同行评议 | 只用于定位与侦察，**不进论证主干** |
| `[自算]` | 你自己跑出的结果 | 可作贡献，须给脚本、随机种子、数据版本 |
| `[推断]` | 你的推论，没有直接证据 | 必须显式写成"我们推测/可能"，不得伪装成结论 |
| `[待核]` | 来源线索存在但还没打开核对 | **占位符，不许进定稿** |

**三条硬规则**

1. **不许编引用。** 每一条引用都必须能点开、且真的支持你这句话。生成式工具凭记忆给出的文献条目经常出错（元数据错、DOI 指向别的文章、把综述里的转述当成原文结论）——所以**一律程序化抓取、程序化核验，不凭记忆写 BibTeX**。详见 `references/evidence.md`。
2. **预印本可以读、不可当依据。** 正式版出来后改引正式版；只有预印本时，正文写 "(preprint)" 并降低论断强度。
3. **区分"文献结论"与"我们的估计"。** 若某个数字来自你的估算，绝不能写成"研究表明 X 在 a–b 之间"。

## 统计报告底线

1. **报区间，不报点估计。** 比例给 Clopper–Pearson 或 Wilson 区间；均值给 bootstrap 或 t 区间；曲线给置信带。
2. **说清二值化阈值。** 凡是把分级得分切成"对/错"的地方，报告阈值 c 并给敏感性分析。
3. **样本量与检验力。** 样本少时不要用"显著/不显著"下结论，改为报区间宽度。
4. **数据结构要交代**：缺失怎么处理、无效运行（如基础设施失败）算失败还是剔除。
5. **可复现四件套**：数据来源与版本、脚本、随机种子、运行环境。

## 三道闸（定稿前逐条过）

| 闸 | 内容 | 文件 |
|---|---|---|
| 闸 1 | AI 参与研究的七类失败模式，逐条给 CLEAR / SUSPECTED / INSUFFICIENT / N/A；任一 SUSPECTED 不进定稿 | `references/ai-failure-modes.md` |
| 闸 2 | 严谨性六维自评（1–5 分），均值 ≥3.8 且无维度 <2 | `references/rigor-rubric.md` |
| 闸 3 | 三视角审稿（方法学家 / 领域专家 / 写作批评者） | `references/review.md` |

## 按需加载：先看症状，别一次全读

| 你现在的处境 | 读哪个 |
|---|---|
| 还没想清这篇要说什么 | `references/paragraphs.md` §一 · `references/structure.md` §一 |
| 不知道怎么搭某一节 | `references/structure.md` |
| 引言写不出"为什么现有方法必然不行" | `references/structure.md` §三 |
| 段落读着散、像拼的 | `references/paragraphs.md` |
| 句子像 AI 生成的 | `references/style.md` §四–§六 |
| 标题/摘要写不好 | `references/style.md` §五 · `references/structure.md` §六 |
| 不确定某条引用能不能用 | `references/evidence.md` §一–§二 |
| 相关工作写成流水账 | `references/evidence.md` §三 · `references/structure.md` §七 |
| 实验结果不知道怎么报 | `references/reporting.md` |
| 怕被问"基线公平吗/有消融吗" | `references/rigor.md` §二 |
| 要写"局限"段 | `references/rigor.md` §五 |
| 定稿前想要一个可执行分数 | `references/rigor-rubric.md` |
| 想不出选题、卡在一个方向上 | `references/ideation.md` |
| 术语三种叫法、数字前后不一 | `references/project-knowledge-template.md` |
| 要写开题/选题论证报告 | `assets/proposal-template.md` |
| 收到审稿意见要写 rebuttal | `references/review.md` §七 |
| 担心 AI 参与留下了隐患 | `references/ai-failure-modes.md` |

> **开写之前**先建一份自己的项目知识底稿（`references/project-knowledge-template.md`）。它锁定术语口径、已核实数字和与竞品的边界，能避免"同一件事三种叫法""数字前后不一""把别人没做的事说成做了"。

## 输出契约

被要求"写/改某一节"时，返回四样东西：

1. **迷你大纲**（3–7 条 bullet）
2. **改写后的段落**，每段前标它的角色：`[开篇]` `[挑战]` `[方法]` `[优势]` `[证据]` `[局限]`
3. **自检清单**：清晰度、句间关系、术语一致、无支撑 claim、缺证据
4. **claim–evidence 映射表**：

```
Claim: ...
Evidence: ...（含证据标记 [正式]/[预印]/[自算]/[推断]）
Status: supported / needs evidence / should weaken
```

## 投稿前六问（答不上的就是风险点）

1. **贡献**：一句话说清贡献是什么？审稿人能否复述？
2. **清晰度**：每段首句是不是 message？reverse outlining 通不通？
3. **实验强度**：基线够不够强？有没有 oracle/上限对照？消融有没有？
4. **评估完整性**：是否只报了均值？有没有区间？有没有失败案例分析？
5. **方法合理性**：关键假设是什么？它成立吗？不成立会怎样？
6. **AI 失败模式**：七类逐条给结论，有没有露 SUSPECTED？

## 禁止事项

1. 不编造文献、数据、实验结果。
2. 不把预印本当正式文献引用。
3. 不把"我们的估计"写成"文献结论"。
4. 不用无区间的点估计支撑强论断。
5. 不隐藏关键假设。
6. 不把"我们分析了"当成贡献。
7. 不用"显著"而不给效应量与区间。
