# 技术架构

## 架构概览

纯静态站点，零后端。Astro 在构建时将内容数据 + 组件模板编译为静态 HTML，部署到 GitHub Pages。

```
内容数据 (JSON/MD)
       ↓
Astro 构建 (SSG)
       ↓
静态 HTML/CSS/JS
       ↓
GitHub Pages (CDN)
       ↓
用户浏览器
```

## 核心决策

### 为什么选 Astro

- **零 JS 默认**：构建出的页面默认不包含 JavaScript，加载极快
- **Islands 架构**：只有需要交互的组件才加载 JS（如语言切换、滚动联动）
- **内容驱动**：原生支持 Markdown/JSON 作为内容源
- **静态输出**：`astro build` 生成纯 HTML，往哪丢都行

### 不用框架组件库

- 页面简单（单页），不需要 React/Vue 的组件化能力
- 交互用原生 JS + Astro Islands 足够
- 减少构建体积和复杂度

## 关键模块

### 1. 布局系统

- `MainLayout.astro`：根布局，包含 head meta、全局样式
- 桌面端左右分栏通过 CSS Grid/Flexbox 实现
- 移动端通过媒体查询切换为上下布局

### 2. 主题色联动

- 右栏滚动时通过 Intersection Observer 检测当前可见的作品卡片
- 读取卡片的 `data-theme` 属性
- 通过 CSS 自定义属性 `--current-theme` 更新左栏背景渐变
- 过渡动画通过 CSS transition 实现（1.2s cubic-bezier(0.4, 0, 0.2, 1)）

### 3. 国际化 (i18n)

- 路由级别：`/`（中文）、`/en/`（英文）
- 内容数据包含 `_zh` 和 `_en` 字段
- 构建时生成两套静态页面
- 语言切换 = 页面跳转（`/` ↔ `/en/`）
- 首次访问根据 `navigator.language` 自动重定向

### 4. 内容管理

- 作品数据：`src/content/projects.json`
- 媒体报道：`src/content/press.json`
- 个人信息：`src/content/profile.json`
- 添加作品 = 编辑 JSON + 放入截图 → 推代码 → 自动部署

### 5. 图片优化

- 使用 Astro 内置 `<Image />` 组件
- 自动生成 WebP 格式
- 自动生成响应式 srcset
- 懒加载（loading="lazy"）

## 性能目标

| 指标 | 目标 |
| --- | --- |
| Lighthouse Performance | > 90 |
| First Contentful Paint | < 1s |
| Total Bundle Size | < 200KB（不含图片） |
| 图片 | WebP + 懒加载 |
