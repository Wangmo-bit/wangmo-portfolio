# 实施计划

## M0 — 项目骨架

- [ ] Astro 项目初始化 + TypeScript
- [ ] Tailwind CSS 集成 + 全局样式（配色变量、字体）
- [ ] GitHub 仓库创建
- [ ] GitHub Actions 部署流水线（推 main → 自动构建 → GitHub Pages）
- [ ] 域名 wangmo.tech 绑定 + HTTPS
- [ ] 验收：`pnpm dev` 可运行，推代码后自动部署

## M1 — 核心页面

- [ ] MainLayout 组件（head meta、全局结构）
- [ ] 桌面端左右分栏布局（CSS Grid/Flex）
- [ ] 左栏：头像 + 姓名 + 标签 + 简介 + 社交链接 + 邮箱
- [ ] 左栏：多层背景渐变 + 头像呼吸光效
- [ ] 右栏：作品卡片组件（图标、名称、描述、状态标签）
- [ ] 作品数据从 projects.json 读取渲染
- [ ] 语言切换按钮（UI 占位，功能 M3 实现）
- [ ] 验收：桌面端完整布局可查看

## M2 — 作品详情 + 截图

- [ ] 卡片点击展开详情（描述、技术栈、链接）
- [ ] 截图横向滚动条
- [ ] Coming Soon 作品概念图 + 遮罩样式
- [ ] 主题色联动：Intersection Observer 检测当前作品 → 更新左栏 --current-theme
- [ ] 卡片 hover 效果（上浮、边框、阴影）
- [ ] 页面加载动画（staggered fade-in）
- [ ] 验收：交互完整，主题色联动流畅

## M3 — 中英双语

- [ ] i18n 路由结构：`/`（中文）、`/en/`（英文）
- [ ] profile.json / projects.json / press.json 双语字段
- [ ] 语言切换按钮跳转对应路由
- [ ] 首次访问自动检测浏览器语言
- [ ] localStorage 记住用户选择
- [ ] 验收：两套页面内容完整，切换流畅

## M4 — 媒体报道 + SEO

- [ ] 媒体报道板块组件
- [ ] press.json 数据渲染，空数据时隐藏
- [ ] 报道链接可点击跳转（新标签页）
- [ ] SEO：title、description、keywords meta 标签
- [ ] Open Graph 标签（微信/Twitter 分享卡片）
- [ ] favicon + apple-touch-icon
- [ ] robots.txt + sitemap.xml
- [ ] 验收：分享链接有预览卡片，SEO 标签完整

## M5 — 响应式 + 打磨上线

- [ ] 移动端布局（上下结构、精简头部、左边框色条）
- [ ] 平板端适配
- [ ] 截图/图片资源替换为真实素材
- [ ] 个人信息/作品描述文案定稿
- [ ] Lighthouse 性能测试 > 90
- [ ] 跨浏览器测试（Chrome、Safari、Firefox）
- [ ] 验收：wangmo.tech 正式上线，三端体验完整
