# 来源与致谢

本仓库的全部文字为**新撰写**，未复制任何第三方仓库的正文。下列来源提供了思路、结构或事实依据，一并致谢。

## 一、方法论的公开来源（可直接核对）

| 内容 | 来源 | 状态 |
|---|---|---|
| 读者处理文本的七条预期（主谓相邻、重音位置、旧先于新等） | Gopen & Swan, *The Science of Scientific Writing*, American Scientist 78(6):550–558, 1990 | 正式 |
| 系统论文的结构与常见病（原创性、现实性、教训、选择、语境、呈现六维） | Levin & Redell, *How (and How Not) to Write a Good Systems Paper*, ACM SIGOPS OSR, 1983 | 正式 |
| 措辞模糊、增量词汇、过度强调等写作病灶 | Lipton & Steinhardt, *Troubling Trends in Machine Learning Scholarship*, 2018（arXiv:1807.03341） | 预印 |
| 二项比例的精确区间 | Clopper & Pearson, *The Use of Confidence or Fiducial Limits Illustrated in the Case of the Binomial*, Biometrika 26:404–413, 1934 | 正式 |
| 比例的近似区间 | Wilson, *Probable Inference, the Law of Succession, and Statistical Inference*, JASA 22:209–212, 1927 | 正式 |
| 经验分布的均匀收敛界（DKW 不等式） | Dvoretzky, Kiefer & Wolfowitz, *Asymptotic Minimax Character of the Sample Distribution Function*, Annals of Mathematical Statistics 27:642–669, 1956 | 正式 |
| AI 参与研究的失败模式清单 | Lu et al., *Towards end-to-end automation of AI research*, Nature 651:914–919, 2026（doi:10.1038/s41586-026-10265-5，**CC-BY 4.0**） | 正式 |
| 双关联（bisociation） | Koestler, *The Act of Creation*, 1964 | 正式（专著） |
| 结构映射（structure-mapping） | Gentner, *Structure-Mapping: A Theoretical Framework for Analogy*, Cognitive Science 7(2):155–170, 1983 | 正式 |
| 三类创造力（探索型 / 组合型 / 变革型） | Boden, *The Creative Mind: Myths and Mechanisms*, 2nd ed., 2004 | 正式（专著） |
| 两面神思维（Janusian thinking） | Rothenberg, *The Emerging Goddess*, 1979 | 正式（专著） |
| 矛盾矩阵与发明原理 | Altshuller, TRIZ（俄文原版 1946–1985；英文综述见 *Engineering of Creativity*, 2000） | 正式（专著） |

> `ai-failure-modes.md` 的七类划分依据 Nature 论文的 Limitations 与附录自述。该文为 CC-BY 4.0，允许改编与再分发，已注明出处。

## 二、参考过的开源技能项目

写作方法论在组织方式上参考了下列项目的公开实践（**未复制其正文，未运行其安装器**）：

| 项目 | 参考之处 |
|---|---|
| `Master-cai/Research-Paper-Writing-Skills` | 引言的反向推理结构、段落清晰度检查、reverse outlining、输出契约的组织形式 |
| `hanlulong/econ-writing-skill` | 三视角审稿法、百分制自评、场所匹配决策、反 AI 腔清单 |
| `Imbad0202/academic-research-skills` | 诚信门禁的检查问题设计（其许可证为 CC-BY-NC 4.0；本仓库未复制其文本） |
| `Orchestra-Research/AI-Research-SKILLs` | 六维严谨性评分的维度划分、选题透镜、认知创意框架的分类、段落级章节蓝图 |
| `K-Dense-AI/scientific-agent-skills` | 四条不可协商规则（保密/不编造/证据绑定/科学忠实）、证据编号与核验流程 |

**说明**：这些项目各自适用不同许可证（MIT / CC-BY-NC 4.0 等）。本仓库只借用了**方法论层面的思路**——方法、流程、检查清单属于思想而非表达，不受版权保护——正文表述、示例、结构编排均为独立撰写。其中唯一来自 CC-BY-NC 项目的部分（AI 失败模式清单），其事实基础已直接回溯到 CC-BY 4.0 的 Nature 原文并据此重写，因此本仓库整体可按 MIT 分发。

若你认为某处与你享有版权的作品构成实质性相似，请开 issue 指出具体文件与段落，我们会核对并改写或删除。

## 三、本仓库的原创部分

- 四级证据标记体系（`[正式]/[预印]/[自算]/[推断]` + `[待核]` 占位）与"三条硬规则"的合并表述
- 统计报告规范（区间优先、二值化阈值敏感性、无效运行单列、可复现四件套）
- 相关工作查重流程（多词系检索法）与差距矩阵的"每行必须落到贡献"自检
- 4 部分论证报告模板与配套的写作自查清单
- 项目知识底稿模板（术语表 / 已核实数字 / 竞品边界 / 待核清单四段结构）
- 症状路由表与"三道闸"的编排
- 全部中文表述
