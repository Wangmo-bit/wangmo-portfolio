# 作品详情交互稿

## 触发方式

- 点击作品卡片 → 卡片原地展开为详情视图
- 展开动画：卡片高度向下展开（约 0.3s ease-out）
- 再次点击或点击关闭按钮 → 收起

## 展开后布局

### 桌面端

```
+-----------------------------------------------+
|                                                 |
|   ┌────────┐   作品名称              [✕ 收起]  |
|   │        │   一句话描述                       |
|   │  图标   │   [状态标签]                      |
|   │        │                                    |
|   └────────┘                                    |
|                                                 |
|   详细介绍文字（2-3 段）                         |
|                                                 |
|   ── 截图预览 ──                                |
|                                                 |
|   ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐     |
|   │      │  │      │  │      │  │      │     |
|   │ 截图1 │  │ 截图2 │  │ 截图3 │  │ 截图4 │     |
|   │      │  │      │  │      │  │      │     |
|   └──────┘  └──────┘  └──────┘  └──────┘     |
|                                                 |
|   ◄ 可横向滚动查看更多截图 ►                     |
|                                                 |
|   ── 技术栈 ──                                  |
|                                                 |
|   [Swift]  [SwiftUI]  [SwiftData]              |
|                                                 |
|   [查看详情 →]  (外链到 App Store / GitHub)      |
|                                                 |
+-----------------------------------------------+
```

### 移动端

- 点击卡片 → 全屏模态弹出（从底部滑入）
- 顶部吸顶关闭按钮
- 截图横向滑动轮播
- 下滑手势关闭

## 截图轮播

### 桌面端

- 截图横排，可横向滚动
- 截图尺寸：固定高度 300px，宽度按比例
- Hover 截图轻微放大（scale 1.02）
- 可选：点击截图全屏查看（lightbox）

### 移动端

- 全宽轮播，左右滑动
- 底部圆点指示器
- 截图尺寸：宽度 100%，高度自适应

### Coming Soon 作品

- 截图区域替换为单张概念图
- 概念图上叠加半透明遮罩 + "Coming Soon" 文字
- 不显示技术栈和外链

## 作品数据结构

每个作品需要的数据字段：

```
name_zh: 赛博生活
name_en: CyberLife
tagline_zh: 赛博朋克风格的订阅会员管理工具
tagline_en: Cyberpunk-style subscription manager
status: developing / coming_soon / released
theme_color: #00F0FF
icon: cyberlife-icon.png
description_zh: 详细介绍...
description_en: Detailed description...
screenshots: [img1.png, img2.png, ...]
tech_stack: [Swift, SwiftUI, SwiftData]
links:
  appstore: (url)
  github: (url)
```
