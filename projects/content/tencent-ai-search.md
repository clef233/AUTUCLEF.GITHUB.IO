---
titleCn: 腾讯未来产品经理创造营
titleEn: Tencent Future Product Manager Training Camp
subtitleCn: QQ浏览器AI搜索功能设计 ｜ 产品全流程实践
subtitleEn: QQ Browser AI Search Feature Design | End-to-End Product Practice
time: 2026.01 - 2026.02
typeCn: 产品培训 / 产品设计
typeEn: Product Training / Product Design
roleCn: 产品经理（学员）
roleEn: Product Manager (Trainee)
documents:
  - type: competitive
    titleCn: AI搜索竞品分析报告
    titleEn: AI Search Competitive Analysis
    descCn: Google AI Mode、Perplexity等产品的功能拆解与策略分析
    descEn: Feature breakdown and strategy analysis of Google AI Mode, Perplexity, etc.
    file: ./docs/tencent-camp/competitive-analysis.md
    status: ready
  - type: research
    titleCn: 用户调研报告
    titleEn: User Research Report
    descCn: 信息检索场景下的用户需求与行为洞察
    descEn: User needs and behavioral insights in information retrieval scenarios
    file: ./docs/tencent-camp/user-research.pdf
    status: pending
  - type: prd
    titleCn: QQ浏览器AI搜索PRD
    titleEn: QQ Browser AI Search PRD
    descCn: 需求文档，含功能规格、数据指标体系与A/B Test方案
    descEn: Requirements document with feature specs, metrics framework and A/B Test plan
    file: ./docs/tencent-camp/qq-browser-ai-search-prd.md
    status: ready
  - type: prototype
    titleCn: Figma界面原型
    titleEn: Figma UI Prototype
    descCn: QQ浏览器AI搜索功能的交互原型设计
    descEn: Interaction prototype for QQ Browser AI Search feature
    file: ./docs/tencent-camp/prototype.pdf
    status: pending
  - type: metrics
    titleCn: 数据指标体系
    titleEn: Metrics Framework
    descCn: 功能上线后的核心指标定义与监测方案
    descEn: Core metric definitions and monitoring plan for post-launch evaluation
    file: ./docs/tencent-camp/metrics.pdf
    status: pending
---

## 项目概述

### 项目背景

腾讯未来产品经理创造营是腾讯面向在校学生开设的产品经理培训项目，内容覆盖需求分析、竞品分析、用户调研、PRD撰写、数据指标体系搭建与A/B Test设计等产品工作全流程。培训以实战命题驱动——参与者需围绕腾讯旗下产品完成一项完整的功能设计方案。我选择的命题为QQ浏览器的AI搜索功能。

选择这一方向有具体的行业背景。
2024年下半年至2025年初，AI搜索经历了从概念验证到产品化竞争的转折期。Google在搜索结果页引入AI Overview并推出AI Mode，Perplexity以对话式搜索切入市场并快速增长，国内的秘塔搜索、天工AI等产品也在同期密集上线。搜索引擎作为互联网最基础的信息入口，正面临交互范式层面的结构性变化。QQ浏览器作为腾讯系移动端的核心入口之一，如何在这一轮技术变革中找到差异化定位，我认为是一个有实际业务意义的问题。

### 竞品分析与需求洞察

项目的第一阶段工作是对现有AI搜索产品进行系统性拆解。调研对象包括Google AI Mode、Perplexity、New Bing（Copilot）、秘塔搜索等，分析维度涵盖信息组织方式、引用溯源机制、多轮对话能力、结果呈现形态及商业化路径。

调研过程中观察到一个共性特征：当前主流AI搜索产品的信息源几乎全部指向公开互联网内容，用户的私域信息（本地文件、云端文档、聊天记录等）被排除在检索范围之外。这意味着用户在处理与个人数据相关的检索任务时——例如"我上周在微信里收到的那份报告提到的数据是什么"——仍然需要退回到传统的文件管理路径手动查找。公域搜索与私域检索之间的断裂是目前AI搜索产品普遍存在的功能缺口。

与此同时，QQ浏览器背靠腾讯生态，天然具备连接微信文件、腾讯云文档、QQ传输记录等私域数据源的可能性。这构成了一个其他独立AI搜索产品难以复制的差异化优势。

用户调研环节进一步验证了这一判断。通过对目标用户群体（大学生与初入职场的年轻白领）的访谈，识别出几类典型场景：跨平台文件查找（"那个文件在微信还是邮箱里"）、基于个人资料的问答（"我之前整理的那篇笔记里关于XX的结论是什么"）、公域信息与私域信息的交叉比对（"帮我用我课件里的框架分析这篇新闻"）。这些场景指向的核心需求是：用户希望AI搜索能够同时理解"互联网知道什么"和"我自己知道什么"。

### 产品方案

基于上述分析，提出QQ浏览器AI搜索功能的核心设计方案：**公域+私域的AI融合搜索**。

功能架构分为三层：

**检索层**——支持两类信息源的并行检索。公域侧对接搜索引擎索引与实时网页抓取，私域侧在用户授权前提下接入腾讯云文档、微信文件传输助手、QQ文件等数据源。用户可在搜索界面中选择检索范围（仅公域 / 仅私域 / 融合模式），也可通过自然语言隐式表达意图由系统自动判断。

**理解与生成层**——基于大语言模型对检索结果进行摘要、归纳与推理。在融合模式下，模型需处理公域信息与私域信息的交叉引用，并在输出中明确标注信息来源类别，确保用户对结果的可溯源性。

**交互与呈现层**——设计了三种结果呈现模式：快速摘要（搜索结果页内嵌AI摘要卡片）、深度回答（独立对话界面，支持多轮追问）、文档定位（直接跳转至私域文件的具体位置）。Figma原型围绕这三种模式完成了主要界面的交互设计。

在数据指标体系方面，定义了功能渗透率、搜索满意度（以结果点击深度与会话终止位置为代理指标）、私域检索激活率、次日留存率等核心指标，并设计了针对融合搜索功能的A/B Test方案——对照组为纯公域AI搜索，实验组开启私域数据接入，观测搜索任务完成率与用户满意度的差异。

### 关于隐私设计的考量

私域数据接入不可避免地触及隐私边界。方案中对此做了专项设计：所有私域数据源的接入均需用户逐项显式授权，且授权状态随时可撤回；私域数据的索引在本地或用户专属的加密云空间中完成，不进入公共训练数据池；搜索结果中涉及私域信息的部分以独立视觉样式标识，避免与公域信息混淆。这些措施在PRD中作为硬性约束条件写入功能规格，而非作为附加建议处理。

### 个人收获

这是一次将产品方法论完整应用于具体命题的实践。从竞品拆解到需求洞察，从功能定义到原型落地，再到指标体系与实验设计，整个流程在两个月内走完。过程中最有价值的认知是：差异化定位的切入点往往在平台资源中已经存在，产品经理的工作是识别它并将其转化为用户可感知的功能价值。QQ浏览器与腾讯生态的连接能力是一个客观事实，将这一事实翻译为"融合搜索"的产品形态，需要的是对用户场景的准确理解和对技术可行性的诚实评估。

## Project Overview

### Background

The Tencent Future Product Manager Training Camp is a product management training program organized by Tencent for university students. It covers the full product workflow including requirements analysis, competitive analysis, user research, PRD writing, metrics framework design, and A/B Test planning. The program is driven by a real product brief: participants must deliver a complete feature design proposal for a Tencent product. The assigned topic for this cohort was AI search functionality for QQ Browser.

The timing carried specific industry relevance. From late 2024 through early 2025, AI search underwent a transition from proof-of-concept to competitive product deployment. Google introduced AI Overview into its search results page and launched AI Mode; Perplexity entered the market with conversational search and grew rapidly; domestic products such as Metaso and Tiangong AI also launched during this period. Search engines, as the most fundamental information gateway of the internet, were facing structural changes at the interaction paradigm level. How QQ Browser—one of Tencent's core mobile entry points—should position itself within this technological shift represented a question with concrete business significance.

### Competitive Analysis and Need Identification

The first phase involved systematic analysis of existing AI search products. Subjects included Google AI Mode, Perplexity, New Bing (Copilot), and Metaso, examined across dimensions of information organization, source attribution mechanisms, multi-turn dialogue capability, result presentation formats, and monetization paths.

A common characteristic emerged during the investigation: virtually all mainstream AI search products restrict their information sources to public web content, excluding users' private data (local files, cloud documents, chat records, etc.) from the retrieval scope. This means that when users encounter retrieval tasks involving personal data—such as "what was the data point mentioned in the report I received on WeChat last week"—they must revert to traditional file management workflows for manual lookup. The discontinuity between public search and private retrieval represents a pervasive functional gap across current AI search products.

QQ Browser, operating within the Tencent ecosystem, possesses a natural capacity to connect with private data sources including WeChat file transfers, Tencent Cloud documents, and QQ file sharing. This constitutes a differentiation advantage that independent AI search products cannot readily replicate.

User research further validated this assessment. Interviews with target user groups (university students and early-career professionals) identified several recurring scenarios: cross-platform file retrieval ("was that file in WeChat or email"), personal-data-based Q&A ("what was the conclusion about XX in the notes I organized earlier"), and cross-referencing between public and private information ("analyze this news article using the framework from my courseware"). The underlying need across these scenarios was consistent: users want AI search to simultaneously understand "what the internet knows" and "what I personally know."

### Product Proposal

Based on the above analysis, the core design proposal for QQ Browser AI Search was defined as **public-private fusion search**.

The functional architecture comprises three layers:

**Retrieval Layer** — supports parallel retrieval from two information source types. The public side connects to search engine indices and real-time web crawling; the private side, contingent on user authorization, integrates with Tencent Cloud documents, WeChat file transfer assistant, and QQ file sharing. Users can select retrieval scope (public only / private only / fusion mode) through the search interface, or express intent via natural language for automatic system determination.

**Understanding & Generation Layer** — leverages large language models to summarize, synthesize, and reason over retrieval results. In fusion mode, the model handles cross-referencing between public and private information, with explicit source-type labeling in outputs to ensure result traceability.

**Interaction & Presentation Layer** — three result presentation modes were designed: quick summary (AI summary cards embedded in the search results page), deep answer (standalone dialogue interface supporting multi-turn follow-up), and document navigation (direct navigation to specific locations within private files). The Figma prototype covers the primary interface interactions across all three modes.

For the metrics framework, core indicators were defined including feature penetration rate, search satisfaction (using result click depth and session termination position as proxy metrics), private retrieval activation rate, and next-day retention rate. An A/B Test plan was designed for the fusion search feature, with the control group receiving public-only AI search and the treatment group enabling private data integration, measuring differences in search task completion rate and user satisfaction.

### Privacy Design Considerations

Private data integration inevitably raises privacy boundary questions. The proposal includes dedicated provisions: all private data source connections require explicit per-source user authorization, with authorization status revocable at any time; private data indexing occurs either locally or in a user-exclusive encrypted cloud space, excluded from public training data pools; search results involving private information are rendered with distinct visual styling to prevent confusion with public information. These measures are written into the feature specification as mandatory constraints within the PRD, treated as requirements rather than supplementary recommendations.

## 文档清单

文档在front matter中定义。

## 时间线

- **2026.01 第一周**：完成产品方法论系统学习，涵盖需求分析框架、竞品分析方法、用户调研设计与PRD写作规范
- **2026.01 第二至三周**：完成Google AI Mode、Perplexity、New Bing、秘塔搜索等AI搜索产品的竞品拆解，输出竞品分析报告；识别公域-私域检索断裂这一核心功能缺口
- **2026.01 第四周**：完成目标用户群体访谈与需求调研，验证融合搜索场景的用户价值；确定"公域+私域AI融合搜索"的产品方向
- **2026.02 第一至二周**：完成功能架构设计、PRD撰写（含功能规格、隐私约束、数据指标体系与A/B Test方案）；使用Figma完成核心界面的交互原型设计
- **2026.02 第三周**：完成方案汇报与答辩，接受导师与同行评审反馈

## Timeline

- **Week 1, Jan 2026**: Completed systematic study of product methodology covering requirements analysis frameworks, competitive analysis methods, user research design, and PRD writing standards
- **Weeks 2–3, Jan 2026**: Completed competitive analysis of Google AI Mode, Perplexity, New Bing, Metaso and other AI search products; delivered competitive analysis report; identified the public-private retrieval discontinuity as the core functional gap
- **Week 4, Jan 2026**: Completed target user interviews and need validation, confirming user value of fusion search scenarios; established "public-private AI fusion search" as the product direction
- **Weeks 1–2, Feb 2026**: Completed feature architecture design and PRD writing (including feature specs, privacy constraints, metrics framework, and A/B Test plan); completed core interface interaction prototypes in Figma
- **Week 3, Feb 2026**: Delivered final presentation and defense; received mentor and peer review feedback

## 技能标签

- 需求分析【精通】
- 竞品分析【精通】
- PRD撰写【精通】
- 用户调研【良好】
- 数据指标体系设计【良好】
- A/B Test设计【良好】
- Figma【良好】
- AI搜索产品认知【良好】
- 隐私合规设计【一般】

## Skills

- Requirements Analysis [Advanced]
- Competitive Analysis [Advanced]
- PRD Writing [Advanced]
- User Research [Intermediate]
- Metrics Framework Design [Intermediate]
- A/B Test Design [Intermediate]
- Figma [Intermediate]
- AI Search Product Knowledge [Intermediate]
- Privacy Compliance Design [Basic]

## 相关链接

- [腾讯未来产品经理创造营](https://www.tencent.com/)
