---
titleCn: 策略选择的社会学解读：LOL职业联赛BP同构现象的定性比较分析
titleEn: "A Sociological Reading of Strategic Choice: QCA of Ban/Pick Isomorphism in LoL Professional Leagues"
subtitleCn: 基于制度同构理论与fsQCA方法的电竞组织行为研究
subtitleEn: "Esports Organizational Behavior Research Based on Institutional Isomorphism Theory and fsQCA"
time: 2024
typeCn: 学术研究，这是我最好玩的小组作业
typeEn: Academic Research
roleCn: 研究者
roleEn: Researcher
documents:
  - type: paper
    titleCn: 论文
    titleEn: Research Paper
    descCn: 审稿中
    descEn: Under review
    file: ./docs/lol-qca/paper.pdf
    status: pending


---

## 项目概述

### 研究问题

《英雄联盟》职业联赛的Ban/Pick（以下简称BP）环节是比赛开始前的策略博弈阶段，双方各自禁用与选用五名英雄，直接决定团队阵容的强度、风格与战术布局。随着职业电竞赛事体系的成熟，一个持续引发行业讨论的现象逐渐显化：各支队伍的BP选择呈现高度趋同，固定的英雄组合与禁用模式反复出现，形成所谓"版本答案"。这种同构化趋势在提高平均竞技水准的同时，也压缩了战术创新空间，引发了关于比赛观赏性与策略多样性的广泛争议。

本研究关注的核心问题是：职业联赛中BP策略的同构现象是如何发生的？哪些条件组合构成了导致同构的因果路径？不同赛区的队伍是否通过相同的路径走向策略趋同？

### 理论视角

研究的理论锚点是DiMaggio与Powell于1983年在《美国社会学评论》发表的经典论文"The Iron Cage Revisited: Institutional Isomorphism and Collective Rationality in Organizational Fields"。该文提出了组织场域中制度同构的三种变迁机制——强制性同构（coercive isomorphism）、模仿性同构（mimetic processes）、规范性同构（normative pressures），用以解释为何处于同一场域中的组织会随时间推移而在结构和行为上趋于相似。这篇文章是社会学领域被引用最多的论文之一，迄今已累计超过67000次引用。

将这一理论框架迁移至电竞场域具有内在的适切性。职业联赛构成了一个典型的组织场域：各战队作为组织单元共享同一套竞赛规则、面对相同的版本环境、受到相似的绩效评价体系约束。在这一场域中，BP策略的同构化过程可以对应到三种机制——版本更新带来的强制性约束迫使队伍调整英雄池，面对不确定性时对高胜率队伍的策略模仿构成模仿性同构，教练团队职业化所形成的行业共识则推动了规范性同构。

### 研究方法

本研究采用定性比较分析法（Qualitative Comparative Analysis, QCA）作为核心分析工具。QCA是基于布尔代数的集合论组态分析方法，通过考察前因条件与结果之间的充分与必要子集关系，识别多重并发因果路径。相较于传统线性回归以变量独立性为前提假设的分析范式，QCA能够处理多因并发的复杂因果关系和殊途同归的多重因果路径，被视为社会科学近年来最重要的方法创新之一。

选择QCA有明确的方法论理由。BP策略同构化的背后逻辑并非单一线性因果关系，而是各队伍在不同条件下做出类似策略选择的多种可能性路径。某些队伍可能因版本更新而趋向选择热门英雄，另一些队伍可能因模仿高胜率队伍策略而做出相似决策，还有队伍出于对教练团队职业化建议的遵循而选择标准化的安全BP。QCA能够通过布尔代数的逻辑操作对前因条件进行组合，识别出不同条件组态如何共同影响结果，在处理"不同路径导致相同结果"这一问题上具有独特优势。

### 数据来源与变量操作化

数据来源于Kaggle平台上的LPL 2024 Summer、LCK 2024 Summer、LEC 2024 Summer三个赛区的比赛记录数据集，涵盖比赛队伍、比赛时间、英雄禁用与选取、击杀比分、比赛胜负等维度。数据处理与分析使用Python 3.9完成，QCA分析使用Tosmana软件执行fsQCA。

变量操作化过程借鉴扎根理论的思路，从制度同构的三种机制出发，逐步将抽象理论概念转化为可观测的经验指标：

**强制性同构变量（Version_dependency）**——度量队伍的Pick/Ban是否受当前版本强势英雄的约束。具体操作为：根据OP.GG职业联赛英雄胜场数据确定当前版本的强势英雄池，检查每支队伍的英雄选禁是否落入该范围。若队伍的BP英雄与版本强势英雄高度吻合，则编码为受版本强制性约束影响。

**模仿性同构变量（High_winrate_team_imitation）**——度量队伍是否模仿高胜率队伍的BP策略。通过胜率数据判断联赛中的高胜率队伍，再比较其他队伍的Pick/Ban英雄与高胜率队伍的相似程度。若BP选择与高胜率队伍策略高度相似，则编码为存在模仿行为。

**规范性同构变量（Professional_standardization）**——度量队伍的BP策略是否符合职业化形成的行业标准。以OP.GG职业联赛出场率前20位英雄作为"安全BP"的操作定义，检查队伍是否选择了这些行业公认的常规英雄。

**结果变量（Formulaic_BP）**——BP策略的公式化程度。此处引入了一个跨学科的量化方案：使用自然语言处理领域的TF-IDF（Term Frequency-Inverse Document Frequency）算法对每场比赛每支队伍的BP数据进行向量化，将英雄名类比为文本中的词项，将单场BP类比为一篇文档，将整个赛季的比赛集合类比为语料库。在此基础上计算不同比赛间BP向量的余弦相似度，再通过sigmoid函数将相似度平滑映射到1-10的分数区间，得到BP公式化评分。

TF-IDF的引入具有方法论上的合理性：TF衡量特定英雄在某场比赛中的出现频率，IDF衡量该英雄在整个赛季比赛集合中的出现频率的倒数，两者结合能够降低那些在所有比赛中普遍出现的英雄的权重，突出特定比赛中具有辨识度的英雄选择，从而更准确地反映每支队伍BP策略的独特性或趋同性。sigmoid函数的使用则确保了相似度到评分的映射是平滑非线性的，避免小幅相似度变化导致极端评分波动，使得分体系具备足够的弹性与稳定性。

### 结果发现

QCA分析覆盖了LPL、LCK、LEC三个赛区共37支队伍的数据。结果显示，导致BP策略高度同构化的因果路径并非单一。

从数据分布来看，LPL赛区队伍普遍呈现较高的BP公式化评分和较高的平均相似度，多数队伍在三个前因条件上同时满足（如EDG、TT、JDG、TES、BLG等），表明LPL赛区的同构现象受到强制性、模仿性和规范性三重机制的叠加驱动。LCK和LEC赛区的队伍则呈现出更多样化的条件组态——部分队伍（如FNC）在仅满足模仿性和规范性条件的情况下同样达到高公式化评分，而另一些队伍（如T1、GEN、G2）尽管具备高胜率或较强的版本适应能力，BP公式化程度反而较低，暗示这些队伍在策略选择上保持了一定的自主性。

QCA的核心优势在结果解读中得到体现：它揭示了"殊途同归"的多重因果路径——通往BP同构化的条件组合存在多种可能，单一变量的有无并不能决定结果，条件之间的组态效应才是关键。这一发现从方法论层面印证了将QCA引入电竞组织行为研究的适用性。

### 研究意义

本研究的贡献体现在三个层面。在理论层面，将组织社会学的制度同构理论引入电竞研究领域，为理解职业联赛中策略趋同现象提供了系统性的分析框架，拓展了制度同构理论的经验应用场景。在方法层面，将TF-IDF文本向量化方法创造性地应用于非文本数据（BP英雄组合）的相似性度量，并将QCA组态分析引入电竞策略研究，展示了跨学科方法整合的可能性。在实践层面，研究结果为赛事组织者理解策略同质化的成因提供了参考，也为教练团队在"遵循版本共识"与"保持策略独立性"之间的决策权衡提供了经验依据。

## Project Overview

### Research Question

The Ban/Pick (hereafter BP) phase in League of Legends professional leagues constitutes a pre-match strategic contest in which both teams ban and select five champions each, directly determining team composition strength, playstyle, and tactical orientation. As professional esports ecosystems have matured, a persistent phenomenon has attracted sustained industry discussion: BP choices across teams exhibit high levels of convergence, with fixed champion combinations and ban patterns recurring as so-called "meta answers." While this isomorphic tendency raises the average level of competitive play, it simultaneously compresses the space for tactical innovation, generating widespread debate regarding match watchability and strategic diversity.

The core questions of this study are: How does BP strategy isomorphism occur in professional leagues? Which combinations of conditions constitute the causal paths leading to isomorphism? Do teams across different regional leagues converge through identical paths?

### Theoretical Perspective

The theoretical anchor is the seminal paper by DiMaggio and Powell published in the *American Sociological Review* in 1983, "The Iron Cage Revisited: Institutional Isomorphism and Collective Rationality in Organizational Fields." The paper proposes three mechanisms of institutional isomorphic change within organizational fields — coercive isomorphism, mimetic processes, and normative pressures — to explain why organizations operating within the same field tend to become increasingly similar in structure and behavior over time. This article ranks among the most cited publications in sociology, with over 67,000 citations accumulated to date.

Transferring this theoretical framework to the esports field carries inherent analytical fitness. Professional leagues constitute a typical organizational field: teams as organizational units share a common set of competition rules, face identical patch environments, and are subject to similar performance evaluation systems. Within this field, the isomorphic process of BP strategies maps onto the three mechanisms — patch updates impose coercive constraints forcing teams to adjust champion pools, strategy imitation of high-win-rate teams under uncertainty constitutes mimetic isomorphism, and the industry consensus formed through coaching staff professionalization drives normative isomorphism.

### Methodology

This study employs Qualitative Comparative Analysis (QCA) as the core analytical tool. QCA is a set-theoretic configurational analysis method based on Boolean algebra that examines sufficient and necessary subset relationships between antecedent conditions and outcomes to identify multiple concurrent causal paths. Compared to traditional linear regression paradigms that assume variable independence, QCA can handle complex causal relationships involving multiple concurrent factors and equifinal causal paths, and has been regarded as one of the most important methodological innovations in social science in recent years.

The selection of QCA rests on explicit methodological grounds. The logic behind BP strategy isomorphism is not a single linear causal relationship, but rather multiple possible paths through which teams make similar strategic choices under different conditions. Some teams may gravitate toward popular champions due to patch updates; others may make similar BP decisions by imitating high-win-rate teams; still others may opt for standardized safe BPs in compliance with professionalized coaching recommendations. QCA's capacity to combine antecedent conditions through Boolean algebraic operations and identify how different condition configurations jointly affect outcomes offers a distinctive advantage in addressing the problem of "different paths leading to the same result."

### Data Sources and Variable Operationalization

Data were sourced from three Kaggle datasets: LPL 2024 Summer, LCK 2024 Summer, and LEC 2024 Summer, covering match teams, match timing, champion bans and picks, kill scores, and match outcomes. Data processing and analysis were conducted in Python 3.9, with QCA analysis performed using Tosmana software for fsQCA.

Variable operationalization drew on grounded theory logic, translating the three abstract institutional isomorphism mechanisms into observable empirical indicators:

**Coercive Isomorphism Variable (Version_dependency)** — measures whether a team's Pick/Ban is constrained by the current patch's dominant champions. Operationally, the dominant champion pool was determined using OP.GG professional league champion win data, and each team's bans and picks were checked for overlap with this pool.

**Mimetic Isomorphism Variable (High_winrate_team_imitation)** — measures whether a team imitates the BP strategies of high-win-rate teams. High-win-rate teams were identified through win rate data, and other teams' Pick/Ban champions were compared for similarity.

**Normative Isomorphism Variable (Professional_standardization)** — measures whether a team's BP strategy conforms to professionalized industry standards. The top 20 champions by appearance rate in OP.GG professional league data served as the operational definition of "safe BP."

**Outcome Variable (Formulaic_BP)** — the degree of BP strategy formulaicity. A cross-disciplinary quantification approach was introduced: TF-IDF (Term Frequency-Inverse Document Frequency) from natural language processing was used to vectorize each team's BP data per match, treating champion names as word terms, individual match BPs as documents, and the entire season's match collection as a corpus. Cosine similarity between BP vectors across matches was then computed, and sigmoid functions were applied to smoothly map similarity scores onto a 1–10 scoring interval.

The introduction of TF-IDF carries methodological justification: TF measures the frequency of a specific champion's appearance in a given match, while IDF measures the inverse frequency of that champion across the entire season, together reducing the weight of universally appearing champions and highlighting distinctive selections, thereby more accurately reflecting the uniqueness or convergence of each team's BP strategy. The sigmoid function ensures that the mapping from similarity to score is smooth and nonlinear, preventing minor similarity fluctuations from producing extreme score variations.

### Findings

QCA analysis covered 37 teams across the LPL, LCK, and LEC regions. Results demonstrated that the causal paths leading to high BP strategy isomorphism are not singular.

In terms of data distribution, LPL teams generally exhibited higher BP formulaicity scores and average similarity values, with most teams satisfying all three antecedent conditions simultaneously (e.g., EDG, TT, JDG, TES, BLG), indicating that isomorphism in the LPL is driven by the superimposed effects of all three mechanisms. LCK and LEC teams presented more diversified condition configurations — some teams (e.g., FNC) achieved high formulaicity scores while satisfying only mimetic and normative conditions, whereas others (e.g., T1, GEN, G2) maintained lower BP formulaicity despite possessing high win rates or strong patch adaptation capabilities, suggesting that these teams preserved a degree of strategic autonomy.

The core advantage of QCA was demonstrated in result interpretation: it revealed equifinal multiple causal paths — multiple condition combinations can lead to BP isomorphism, and the presence or absence of a single variable cannot determine the outcome; configurational effects among conditions are what matter. This finding methodologically validates the applicability of QCA to esports organizational behavior research.

### Contributions

This study contributes at three levels. Theoretically, it introduces institutional isomorphism theory from organizational sociology into esports research, providing a systematic analytical framework for understanding strategic convergence in professional leagues and extending the empirical application scope of isomorphism theory. Methodologically, it creatively applies TF-IDF text vectorization to non-text data (BP champion combinations) for similarity measurement and introduces QCA configurational analysis to esports strategy research, demonstrating the potential of interdisciplinary method integration. Practically, the findings offer reference for tournament organizers seeking to understand the causes of strategic homogenization, and provide empirical grounding for coaching teams navigating the trade-off between "following meta consensus" and "maintaining strategic independence."

## 文档清单

文档在front matter中定义。

## 时间线

- **2024 前期**：确定研究选题，完成文献综述，系统梳理DiMaggio与Powell（1983）制度同构理论及QCA方法论文献
- **2024 中期（数据准备）**：从Kaggle获取LPL、LCK、LEC三个赛区2024夏季赛数据集；基于扎根理论思路完成三个前因条件变量的操作化设计
- **2024 中期（数据处理）**：使用Python完成数据清洗与预处理；实现TF-IDF向量化、余弦相似度计算与sigmoid映射，生成BP公式化评分；完成变量编码与校验
- **2024 中后期**：使用Tosmana软件执行fsQCA分析，识别充分条件与必要条件，提取多重因果路径；完成结果解读与跨赛区比较
- **2024 后期**：撰写研究论文与汇报PPT，完成研究答辩

## Timeline

- **Early 2024**: Defined research topic; completed literature review systematically covering DiMaggio & Powell (1983) institutional isomorphism theory and QCA methodological literature
- **Mid 2024 (Data Preparation)**: Obtained LPL, LCK, and LEC 2024 Summer season datasets from Kaggle; completed operationalization design for three antecedent condition variables following grounded theory logic
- **Mid 2024 (Data Processing)**: Completed data cleaning and preprocessing in Python; implemented TF-IDF vectorization, cosine similarity computation, and sigmoid mapping to generate BP formulaicity scores; completed variable coding and validation
- **Mid-Late 2024**: Executed fsQCA analysis using Tosmana software; identified sufficient and necessary conditions; extracted multiple causal paths; completed result interpretation and cross-regional comparison
- **Late 2024**: Authored research paper and presentation slides; completed research defense

## 技能标签

- 制度同构理论【精通】
- QCA定性比较分析【精通】
- Python数据分析【精通】
- TF-IDF与NLP基础【良好】
- 扎根理论（变量操作化）【良好】
- 学术论文写作【良好】
- 社会学理论应用【良好】
- Tosmana / fsQCA软件【良好】
- 数据可视化【良好】

## Skills

- Institutional Isomorphism Theory [Advanced]
- QCA Qualitative Comparative Analysis [Advanced]
- Python Data Analysis [Advanced]
- TF-IDF & NLP Fundamentals [Intermediate]
- Grounded Theory (Variable Operationalization) [Intermediate]
- Academic Paper Writing [Intermediate]
- Sociological Theory Application [Intermediate]
- Tosmana / fsQCA Software [Intermediate]
- Data Visualization [Intermediate]

## 相关链接

- [LPL 2024 Summer 数据集 (Kaggle)](https://www.kaggle.com/)
- [LCK 2024 Summer 数据集 (Kaggle)](https://www.kaggle.com/)
- [LEC 2024 Summer 数据集 (Kaggle)](https://www.kaggle.com/)
- [DiMaggio & Powell (1983) 原文](https://www.jstor.org/stable/2095101)

## Links

- [LPL 2024 Summer Dataset (Kaggle)](https://www.kaggle.com/)
- [LCK 2024 Summer Dataset (Kaggle)](https://www.kaggle.com/)
- [LEC 2024 Summer Dataset (Kaggle)](https://www.kaggle.com/)
- [DiMaggio & Powell (1983) Original Paper](https://www.jstor.org/stable/2095101)
