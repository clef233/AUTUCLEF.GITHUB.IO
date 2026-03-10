---
titleCn: 基于 OCR 的文档处理流程自动化工具
titleEn: OCR-Based Document Processing Automation Tool
subtitleCn: PDF/EPUB → TXT 可视化转换工具 ｜ 开源项目
subtitleEn: PDF/EPUB → TXT Visual Conversion Tool | Open Source
time: 2025.01 - 2025.02
typeCn: 开源工具
typeEn: Open Source Tool
roleCn: 独立开发者
roleEn: Solo Developer
documents:
  - type: head
    titleCn: 项目简介
    titleEn: Project Brief
    descCn: 项目背景、动机与核心功能说明
    descEn: Background, motivation and core features
    file: ./docs/ocr-tool/brief.pdf
    status: ready

---

## 项目概述

### 问题背景

在工作与日常信息处理中，将PDF或EPUB文档转换为可编辑纯文本是一项高频需求。研究者需要对文献做摘录、整理和二次加工，而现有的转换路径普遍存在操作门槛：命令行工具（如Tesseract）需要用户具备环境配置能力，多数GUI工具功能单一且无法区分文本型PDF与扫描型PDF的差异处理逻辑，EPUB格式的结构化解析则往往需要额外引入独立工具。对非技术背景的用户而言，完成一次完整的文档转换往往意味着在多个工具之间反复切换，流程碎片化程度较高。

### 解决方案

本项目基于Streamlit框架开发了一套可视化文档处理工具，将PDF文本提取、扫描型PDF的OCR识别、EPUB正文解析三项能力整合于统一界面。工具在PDF处理环节引入了双模式设计：对文本型PDF直接调用PyMuPDF进行文本与目录抽取，对扫描型PDF则通过Tesseract OCR执行中英文混合识别，并在处理过程中提供逐页进度反馈与异常提示。EPUB解析部分基于ebooklib与BeautifulSoup实现HTML内容的结构化抽取与纯文本导出。

在结果输出层面，工具对扫描型PDF同时保留OCR识别结果与原始文本提取结果，形成双输出对照机制。这一设计源于对OCR技术当前精度水平的判断——在复杂版式或低质量扫描件中，完全自动化的识别仍存在不可忽视的错误率，提供人工复核通道是保证输出质量的务实选择。该设计体现了工具在"辅助提效"与"完全替代"之间所取的边界。

### 项目成果

项目已完成GitHub开源发布与Streamlit云端部署，用户无需本地安装任何依赖即可通过浏览器使用全部功能。工具将原本分散于命令行与多个桌面应用的文档转换流程收敛为单一入口，为后续的内容整理、文本摘要或大语言模型二次处理提供了标准化的纯文本输入。

## Project Overview

### Problem Context

Converting PDF or EPUB documents into editable plain text is a recurring task in humanities and social science research, as well as in general information processing workflows. Researchers frequently need to excerpt, reorganize, and further process literature content. However, existing conversion paths impose considerable operational overhead: command-line tools such as Tesseract require environment configuration expertise, most GUI tools offer limited functionality without distinguishing between text-based and scanned PDFs, and structured EPUB parsing typically demands yet another standalone tool. For users without technical backgrounds, completing a single document conversion often involves switching between multiple disconnected tools.

### Approach

This project implements a visual document processing tool built on the Streamlit framework, consolidating PDF text extraction, scanned PDF OCR recognition, and EPUB content parsing into a unified interface. For PDF processing, the tool adopts a dual-mode design: text-based PDFs are handled directly via PyMuPDF for text and table-of-contents extraction, while scanned PDFs are processed through Tesseract OCR with Chinese-English bilingual recognition, accompanied by page-level progress feedback and exception alerts. EPUB parsing leverages ebooklib and BeautifulSoup to perform structured extraction from HTML content and export clean plain text.

At the output layer, the tool retains both OCR results and raw text extraction results for scanned PDFs, establishing a dual-output comparison mechanism. This design reflects a practical assessment of current OCR accuracy limitations—in documents with complex layouts or low scan quality, fully automated recognition still carries non-trivial error rates, and providing a manual review channel is a pragmatic measure for ensuring output reliability.

### Outcomes

The project has been open-sourced on GitHub and deployed on Streamlit Cloud, allowing users to access all features through a browser without local dependency installation. The tool consolidates a previously fragmented document conversion workflow into a single entry point, producing standardized plain-text output suitable for downstream content organization, summarization, or further processing by large language models.

## 文档清单

文档在front matter中定义。

## 时间线

- **2025.01 上旬**：明确项目目标与使用场景，完成PDF解析库（PyMuPDF、pdfplumber等）与OCR引擎（Tesseract、PaddleOCR等）的技术选型调研
- **2025.01 中旬**：完成PDF双模式处理核心逻辑开发，实现文本型PDF的文本提取与目录抽取，以及扫描型PDF的OCR识别链路
- **2025.01 下旬**：完成EPUB解析模块开发，基于ebooklib与BeautifulSoup实现结构化内容抽取；设计并实现双输出对照机制与结果预览功能
- **2025.02 初**：完成Streamlit界面集成、异常处理优化与临时文件管理；项目在GitHub开源发布，同步部署至Streamlit Cloud

## Timeline

- **Early Jan 2025**: Defined project objectives and usage scenarios; completed technical investigation of PDF parsing libraries (PyMuPDF, pdfplumber, etc.) and OCR engines (Tesseract, PaddleOCR, etc.)
- **Mid Jan 2025**: Developed core dual-mode PDF processing logic, implementing text extraction and TOC parsing for text-based PDFs, and OCR recognition pipeline for scanned PDFs
- **Late Jan 2025**: Completed EPUB parsing module based on ebooklib and BeautifulSoup; designed and implemented dual-output comparison mechanism and result preview functionality
- **Early Feb 2025**: Finalized Streamlit UI integration, exception handling optimization, and temporary file management; open-sourced on GitHub and deployed to Streamlit Cloud

## 技能标签

- Python【精通】
- Streamlit【精通】
- PyMuPDF【良好】
- Tesseract OCR【良好】
- ebooklib【良好】
- BeautifulSoup【良好】
- 需求分析【良好】
- Git / GitHub【良好】
- 技术选型调研【良好】

## Skills

- Python [Advanced]
- Streamlit [Advanced]
- PyMuPDF [Intermediate]
- Tesseract OCR [Intermediate]
- ebooklib [Intermediate]
- BeautifulSoup [Intermediate]
- Requirements Analysis [Intermediate]
- Git / GitHub [Intermediate]
- Technical Investigation [Intermediate]

## 相关链接

- [GitHub 仓库](https://github.com/clef233/pdf-epub-to-txt)
- [在线 Demo](https://pdf-epub-to-txt.streamlit.app/)

## Links

- [GitHub Repository](https://github.com/clef233/pdf-epub-to-txt)
- [Live Demo](https://pdf-epub-to-txt.streamlit.app/)
