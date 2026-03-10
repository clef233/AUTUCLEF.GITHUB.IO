# 双语学术主页模板 (Bilingual Academic Homepage Template)

支持中英文一键切换的个人主页模板。

## ✨ 新特性

- 🌐 **一键切换**：页面右上角固定语言切换按钮
- 📱 **响应式设计**：语言切换按钮始终可见
- 🎨 **视觉反馈**：当前语言按钮高亮显示
- 📝 **双语内容**：中英文版本同时存在于同一页面

## 📁 文件结构

```
TEMPLATE_BILINGUAL/
├── index.html          # 主页面（包含所有内容和切换逻辑）
└── images/
    └── profile.jpg     # 个人照片
```

## 🚀 使用方法

### 1. 基础设置

1. 复制 `TEMPLATE_BILINGUAL/index.html` 到你的项目目录
2. 在 `images/` 文件夹添加你的照片（命名为 `profile.jpg`）
3. 修改个人信息部分的内容

### 2. 编辑内容

模板中的内容分为两类：

#### 纯中文内容（`.lang-cn`）
```html
<p class="lang-cn">中文内容</p>
```

#### 纯英文内容（`.lang-en`）
```html
<p class="lang-en">English Content</p>
```

#### 同时存在的内容
```html
<heading class="lang-cn">中文标题</heading>
<heading class="lang-en">English Title</heading>
```

### 3. 添加新内容

复制以下模板：

```html
<!-- 中文 -->
<p class="lang-cn">中文内容</p>

<!-- 英文 -->
<p class="lang-en">English content</p>
```

## 🎨 自定义样式

### 语言切换按钮样式

在 `<style>` 中修改：

```css
.lang-switcher {
  position: fixed;
  top: 20px;
  right: 20px;
  /* 修改位置、颜色等 */
}

.lang-btn {
  /* 修改按钮样式 */
}

.lang-btn.active {
  /* 修改激活状态 */
}
```

### 切换动画

修改 CSS 过渡时间：
```css
.lang-btn {
  transition: all 0.3s ease;  /* 修改这里 */
}
```

## 🔧 技术实现

### 工作原理

1. 所有元素都有 `lang-cn` 或 `lang-en` 类
2. 默认显示中文（`.lang-en { display: none; }`）
3. 点击英文按钮时，添加 `en-mode` 类到 body
4. CSS 规则自动切换显示：
   ```css
   body.en-mode .lang-cn { display: none; }
   body.en-mode .lang-en { display: block; }
   ```

### JavaScript 切换逻辑

```javascript
function switchLang(lang) {
  document.body.className = lang === 'en' ? 'en-mode' : '';
  // 更新按钮状态
  document.querySelectorAll('.lang-btn').forEach(btn => {
    btn.classList.remove('active');
  });
  event.target.classList.add('active');
}
```

## 📝 示例：唐盾的简历

本模板已预填充唐盾的完整简历内容：

- ✅ 个人基本信息（中英双语）
- ✅ 求职意向
- ✅ 工作经历（浙江大学计算社会科学中心）
- ✅ 教育背景（三亚学院社会学本科）
- ✅ 三个项目经历（含详细职责描述）
- ✅ 专业技能（带颜色等级标签）

## 🎯 特色功能

### 1. 技能等级标签

使用不同颜色区分熟练度：
```html
<span class="skill-tag level-advanced">精通</span>    <!-- 绿色 -->
<span class="skill-tag level-intermediate">良好</span> <!-- 蓝色 -->
<span class="skill-tag level-basic">一般</span>       <!-- 灰色 -->
```

### 2. 项目卡片样式

每个项目都有左侧边框高亮：
```html
<div class="project-card">
  <div class="project-title">项目名称</div>
  <div class="project-meta">时间 · 类型</div>
  <!-- 内容 -->
</div>
```

### 3. 联系信息盒子

统一格式的联系方式展示：
```html
<div class="contact-info">
  <p><span class="contact-label">标签：</span>内容</p>
</div>
```

## 📱 响应式提示

- 语言切换按钮固定在右上角
- 移动端会自动调整大小
- 建议在小屏幕上测试显示效果

## 🌟 优势

| 特性 | 说明 |
|-----|------|
| SEO友好 | 所有内容在HTML中，搜索引擎可索引 |
| 无刷新切换 | 瞬间完成语言切换，用户体验好 |
| 易于维护 | 中英文并排编辑，方便同步更新 |
| 无需后端 | 纯前端实现，可部署到任何静态托管 |

## 💡 提示

1. **内容同步**：修改中文时记得同步修改对应英文
2. **照片**：建议使用专业证件照，尺寸 400x400px
3. **链接**：GitHub、Demo 等链接中英文版本共用
4. **日期格式**：中文用 YYYY.MM，英文用 Month YYYY

## 🔗 参考

- 原始模板：[Jon Barron](https://jonbarron.info/)
- 部署平台：[GitHub Pages](https://pages.github.com/)

---

**最后更新**: 2024年
