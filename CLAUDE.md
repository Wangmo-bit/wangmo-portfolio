# 王墨的赛博分身

个人作品集网站 — 展示作品、个人介绍、社交平台链接。
**域名**：wangmo.tech
**目前开发版本：v1.0**
PRD：`PRD.md`

## 技术栈

Astro / Tailwind CSS / TypeScript / GitHub Pages / GitHub Actions
纯静态站，零后端，零三方 UI 库

## 当前状态

文档已完成，即将开始 M0。
进度追踪：`docs/05-implementation-plan.md`（checkbox 任务清单）

| 里程碑 | 内容 |
| --- | --- |
| M0 | 项目骨架：Astro + Tailwind + GitHub Pages 部署流水线 |
| M1 | 核心页面：左右分栏 + 个人介绍 + 作品卡片 |
| M2 | 作品详情：截图轮播 + Coming Soon 状态 + 主题色联动 + 动效 |
| M3 | 中英双语：i18n 路由 + 语言切换 |
| M4 | 媒体报道 + SEO + Open Graph |

| M5 | 响应式打磨 + 上线 |

## 关键文档

- `docs/01-dev-environment.md` — 开发环境 + 项目结构
- `docs/02-tech-architecture.md` — 技术架构设计
- `docs/03-design-system.md` — 设计系统：配色、字体、动效
- `docs/04-data-model.md` — 数据模型：JSON 结构定义
- `docs/05-implementation-plan.md` — 实施计划与任务清单
- `docs/08-ui-interaction-specs/` — UI 交互稿（含可交互 HTML mockup）

## UI 文案规则

- 默认中文，英文版单独维护
- 中英文案质量对等，英文不是机翻
- i18n 在 M3 阶段实现

## 协作规则

- 修改文件前先读，理解现有代码再动手
- 只做被要求的事，不顺手重构，不加多余注释，不引入未要求的依赖
- 按依赖关系分批开发，每批 2-3 个任务，一批一个 commit
- 每批完成后：勾掉 `docs/05-implementation-plan.md` 对应 checkbox，简报（做了什么、改了哪些文件、需要决策的问题）
- PRD 与文档有出入时以 PRD 为准，告知并更新文档
- 架构决策分叉时给选项 + 推荐，不自行拍板
- 需要引入新三方库时先说明理由
