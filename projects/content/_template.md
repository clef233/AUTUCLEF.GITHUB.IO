---
# 项目基本信息
# 项目ID（文件名应与此一致）
title: project-template

# 项目标题
titleCn: 项目中文名称
titleEn: Project English Name

# 项目副标题
subtitleCn: 项目简短描述
subtitleEn: Project short description

# 项目时间
time: 2024.01 - 2024.06

# 项目类型
type: 产品设计
typeEn: Product Design

# 担任角色
role: 产品经理
documents:
  # PRD文档
  - type: prd
    titleCn: PRD文档
    titleEn: PRD Document
    descCn: 产品需求文档，包含功能定义、交互流程等
    descEn: Product requirements document with features and workflows
    file: ./docs/[项目ID]-prd.pdf
    status: pending    # pending = 待上传, ready = 已上传

  # 竞品分析
  - type: competitive
    titleCn: 竞品分析报告
    titleEn: Competitive Analysis
    descCn: 市场竞品对比研究
    descEn: Market competitive research
    file: ./docs/[项目ID]-competitive.pdf
    status: pending

  # 原型设计（可以是Figma链接）
  - type: prototype
    titleCn: Figma原型设计
    titleEn: Figma Prototype
    descCn: 高保真交互原型
    descEn: High-fidelity interactive prototype
    file: https://www.figma.com/file/xxxxx
    status: pending

  # 思维导图/架构图
  - type: architecture
    titleCn: 产品架构图
    titleEn: Architecture Diagram
    descCn: 系统架构与功能模块
    descEn: System architecture and modules
    file: ./docs/[项目ID]-architecture.png
    status: pending

  # 数据报告
  - type: metrics
    titleCn: 数据分析报告
    titleEn: Metrics Report
    descCn: 用户数据与核心指标分析
    descEn: User data and KPI analysis
    file: ./docs/[项目ID]-metrics.pdf
    status: pending

  # 用户调研
  - type: research
    titleCn: 用户调研报告
    titleEn: User Research
    descCn: 用户访谈与问卷分析
    descEn: User interviews and survey analysis
    file: ./docs/[项目ID]-research.pdf
    status: pending

  # 论文
  - type: paper
    titleCn: 研究论文
    titleEn: Research Paper
    descCn: 学术论文全文
    descEn: Full academic paper
    file: ./docs/[项目ID]-paper.pdf
    status: pending

  # 毕业论文
  - type: thesis
    titleCn: 毕业论文
    titleEn: Thesis
    descCn: 本科/硕士毕业论文
    descEn: Undergraduate/Master thesis
    file: ./docs/[项目ID]-thesis.pdf
    status: pending

  # 演示文稿
  - type: presentation
    titleCn: 项目答辩PPT
    titleEn: Presentation
    descCn: 项目答辩演示文稿
    descEn: Project defense slides
    file: ./docs/[项目ID]-presentation.pdf
    status: pending
---

## 项目概述

### 背景
在这里描述项目的背景信息：
- 为什么做这个项目？
- 解决了什么问题？
- 目标用户是谁？

### 目标
项目的主要目标：
- 目标1
- 目标2
- 目标3

### 我的职责
我在项目中担任的角色和具体工作：
- 职责1
- 职责2
- 职责3

### 成果
项目取得的成果（数据、奖项、影响力等）：
- 成果1
- 成果2

## 文档清单

（此章节标题必须保留，内容会自动从 YAML front matter 渲染）

## 时间线

使用以下格式记录项目里程碑：

- **YYYY.MM.DD**: 里程碑事件描述
- **2024.01.15**: 项目启动，完成需求调研
- **2024.02.01**: 完成产品原型设计
- **2024.03.15**: 项目上线/答辩/发布

支持的关键字标记：
- **加粗**：使用 `**文字**`
- [链接文字](https://example.com)

## 技能标签

列出项目中使用的技能（支持等级标注）：

- 【精通】产品需求分析
- 【精通】Figma原型设计
- 【良好】用户调研
- 【良好】数据分析
- 【一般】Python编程

等级说明：
- 【精通】：熟练掌握，能独立解决复杂问题
- 【良好】：能够独立完成常规工作
- 【一般】：了解基础，需要指导

## 设计展示

（可选章节）展示项目截图或设计稿：

使用以下格式：
- [图片说明文字](../images/图片文件名.jpg)
- [首页设计](../images/homepage-design.jpg)
- [核心功能界面](../images/feature-screenshot.jpg)

图片建议尺寸：800x600px，JPG或PNG格式

## 相关链接

（可选章节）项目相关的外部链接：

- [GitHub仓库](https://github.com/username/repo)
- [在线演示](https://demo.example.com)
- [项目文档](https://docs.example.com)

---

## 📋 Markdown 语法速查

### 文本格式
- **加粗**：`**文字**`
- *斜体*：`*文字*`
- ~~删除线~~：`~~文字~~`
- `代码`：`` `代码` ``

### 标题
```markdown
# 一级标题
## 二级标题
### 三级标题
```

### 列表
```markdown
- 无序列表项
- 另一个项目

1. 有序列表项
2. 另一个项目
```

### 链接和图片
```markdown
[链接文字](https://example.com)
![图片说明](图片路径.jpg)
```

### 引用
```markdown
> 这是一段引用文字
```

### 代码块
```markdown
```python
def hello():
    print("Hello World")
```
```

---

**提示**：复制此文件后，将 `project-template` 替换为你的项目ID，
并删除所有注释（以 `#` 开头的行）。
