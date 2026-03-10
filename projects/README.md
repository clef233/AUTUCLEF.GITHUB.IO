# 项目详情页使用说明 (动态模板版)

## 📁 新文件结构

```
projects/
├── project-detail.html          # [唯一模板文件] 动态渲染项目内容
├── content/                     # [Markdown内容目录] 存放所有项目数据
│   ├── tencent-ai-search.md     # 腾讯AI搜索项目数据
│   ├── ocr-document-tool.md     # OCR工具项目数据
│   ├── lora-polarization.md     # LoRA研究项目数据
│   ├── esports-strategy.md      # 电竞研究项目数据
│   └── your-new-project.md      # [新增]你的新项目
├── docs/                        # 文档存放目录
│   ├── tencent-prd.pdf          # PRD文档
│   ├── tencent-competitive.pdf  # 竞品分析
│   └── ...
└── README.md                    # 本文件
```

## 🚀 工作原理

1. **单一模板**: `project-detail.html` 是唯一的模板文件，包含所有UI组件
2. **URL参数**: 通过 `?project=xxx` 参数指定要显示的项目
3. **动态加载**: JavaScript 自动加载对应 Markdown 文件并渲染
4. **内容分离**: 所有项目内容存储在 `content/*.md` 文件中

## ✨ 如何添加新项目

只需**三步**：

### 1. 创建 Markdown 文件

在 `content/` 文件夹创建 `[你的项目ID].md` 文件：

```markdown
---
title: your-project-id
titleCn: 项目中文名
titleEn: Project English Name
subtitleCn: 项目副标题
titleEn: Project Subtitle
time: 2024.01 - 2024.06
type: 项目类型
typeEn: Project Type
role: 你的角色

# 文档清单配置
documents:
  - type: prd
    titleCn: PRD文档
    titleEn: PRD Document
    descCn: 产品需求文档
    descEn: Product requirements
    file: ./docs/[项目]-prd.pdf
    status: ready          # ready 或 pending
  - type: competitive
    titleCn: 竞品分析
    titleEn: Competitive Analysis
    file: ./docs/[项目]-competitive.pdf
    status: pending
  - type: prototype
    titleCn: Figma原型
    titleEn: Figma Prototype
    file: https://figma.com/...
    status: ready
  - type: paper
    titleCn: 论文
    titleEn: Paper
    file: ./docs/[项目]-paper.pdf
    status: ready
---

## 项目概述

使用 Markdown 格式撰写项目描述。

支持：
- **加粗**
- *斜体*
- [链接](url)
- 列表

### 背景
项目背景描述...

### 目标
项目目标描述...

## 文档清单

（此章节标题保留，内容由 YAML front matter 的 documents 字段自动生成）

## 时间线

使用列表格式记录里程碑：

- **2024.01.01**: 项目启动
- **2024.02.01**: 完成第一阶段
- **2024.03.01**: 项目上线

## 技能标签

使用列表格式记录技能（支持等级标注）：

- 【精通】技能名称
- 【良好】技能名称
- 【一般】技能名称

## 设计展示

（可选）使用链接格式展示图片：

- [图片描述](../images/screenshot1.jpg)
- [图片描述](../images/screenshot2.jpg)

## 相关链接

（可选）使用链接格式：

- [GitHub仓库](https://github.com/...)
- [在线演示](https://demo.com)
```

### 2. 上传文档

将相关文档放入 `docs/` 文件夹：
- PRD文档：`[项目ID]-prd.pdf`
- 竞品分析：`[项目ID]-competitive.pdf`
- 论文：`[项目ID]-paper.pdf`
- 其他文档...

### 3. 更新作品集页面

在 `../portfolio.html` 中添加新的项目卡片：

```html
<div class="portfolio-item" data-category="product">
  <a href="projects/project-detail.html?project=your-project-id" style="text-decoration: none; color: inherit;">
    <div class="portfolio-image">
      <span class="lang-cn">中文标题</span>
      <span class="lang-en">English Title</span>
    </div>
  </a>
  <div class="portfolio-content">
    <span class="portfolio-category">Category</span>
    <a href="projects/project-detail.html?project=your-project-id" style="text-decoration: none; color: inherit;">
      <div class="portfolio-title">项目名称</div>
    </a>
    <div class="portfolio-desc lang-cn">中文描述...</div>
    <div class="portfolio-desc lang-en">English description...</div>
    <div class="portfolio-links">
      <a href="projects/project-detail.html?project=your-project-id">
        📄 <span class="lang-cn">查看详情</span><span class="lang-en">Details</span>
      </a>
    </div>
  </div>
</div>
```

## 📄 支持的文档类型

| 类型标识 | 图标 | 中文名 | 英文名 |
|---------|-----|-------|-------|
| prd | 📋 | PRD文档 | PRD Document |
| competitive | 🔍 | 竞品分析 | Competitive Analysis |
| prototype | 🎨 | 原型设计 | Prototype |
| architecture | 🗺️ | 思维导图 | Architecture |
| metrics | 📊 | 数据报告 | Metrics Report |
| research | 👥 | 用户调研 | User Research |
| paper | 📄 | 论文 | Paper |
| thesis | 📚 | 毕业论文 | Thesis |
| presentation | 📽️ | 演示文稿 | Presentation |

## 🎨 自定义模板样式

如需修改模板样式，编辑 `project-detail.html` 中的 `<style>` 部分。

## 🔧 技术细节

- **Markdown解析**: 使用 [marked.js](https://marked.js.org/) 库
- **YAML Front Matter**: 支持标准YAML格式配置
- **双语支持**: 通过 `lang-cn` / `lang-en` 类实现
- **URL参数**: `?project=xxx` 指定项目ID

## 💡 提示

1. **状态管理**: 文档配置中的 `status` 字段控制显示状态 (`ready` 或 `pending`)
2. **外部链接**: 支持 Figma、GitHub 等外部链接
3. **PDF预览**: 点击 `ready` 状态的文档卡片可在页面内预览
4. **图片懒加载**: 设计展示区域的图片使用懒加载优化性能

## 🗑️ 删除旧文件

新架构不再需要以下旧文件（可安全删除）：

```bash
# 旧文件（可删除）
projects/tencent-ai-search.html
projects/ocr-document-tool.html
projects/lora-polarization.html
projects/esports-strategy.html
projects/project-template.html
```

---

**最后更新**: 2026年3月
