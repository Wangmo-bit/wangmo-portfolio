# 开发环境

## 快速上手

```bash
# 克隆仓库
git clone git@github.com:YOUR_USERNAME/wangmo-portfolio.git
cd wangmo-portfolio

# 安装依赖
pnpm install

# 本地开发
pnpm dev

# 构建
pnpm build

# 预览构建产物
pnpm preview
```

## 工具版本要求

| 工具 | 最低版本 | 说明 |
| --- | --- | --- |
| Node.js | 18.x | 推荐 20.x LTS |
| pnpm | 8.x | 包管理器 |
| Git | 2.x | 版本控制 |

## 技术栈

| 项目 | 选型 | 版本 |
| --- | --- | --- |
| 框架 | Astro | 4.x |
| 样式 | Tailwind CSS | 3.x |
| 语言 | TypeScript | 5.x |
| 构建产物 | 纯静态 HTML/CSS/JS | — |

## 部署

- **平台**：GitHub Pages
- **域名**：wangmo.tech
- **CI/CD**：GitHub Actions — 推送 main 分支自动构建部署
- **HTTPS**：GitHub Pages 自动签发证书

## 项目结构

```
wangmo-portfolio/
├── src/
│   ├── layouts/          # 页面布局
│   ├── components/       # 组件
│   ├── pages/            # 页面路由
│   │   ├── index.astro   # 中文首页
│   │   └── en/
│   │       └── index.astro  # 英文首页
│   ├── content/          # 内容数据（JSON/MD）
│   │   ├── projects.json # 作品数据
│   │   └── press.json    # 媒体报道数据
│   ├── styles/           # 全局样式
│   └── assets/           # 图片资源
├── public/               # 静态资源（favicon 等）
├── docs/                 # 项目文档
├── astro.config.mjs      # Astro 配置
├── tailwind.config.mjs   # Tailwind 配置
├── tsconfig.json         # TypeScript 配置
├── package.json
├── CLAUDE.md
└── PRD.md
```
