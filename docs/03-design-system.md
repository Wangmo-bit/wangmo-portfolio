# 设计系统

## 视觉风格

赛博科技感，深色基底 + 霓虹色点缀。克制动效，氛围靠配色和光感传达。

## 配色

### 基础色

| Token | 色值 | 用途 |
| --- | --- | --- |
| `--bg-deep` | #07070c | 全局最深背景、左栏 |
| `--bg-elevated` | #0e0e16 | 右栏背景 |
| `--bg-card` | #13131f | 卡片、面板 |
| `--bg-card-hover` | #1a1a2a | 卡片 hover |
| `--text-primary` | #e8e8ed | 正文 |
| `--text-secondary` | #6b6b80 | 辅助文字 |
| `--text-tertiary` | #45455a | 最弱文字 |
| `--border` | #1e1e30 | 默认边框 |
| `--border-hover` | #2e2e48 | Hover 边框 |

### 作品主题色

| 作品 | 色值 | Token |
| --- | --- | --- |
| 赛博生活 | #00F0FF (Cyan) | `--theme-cyan` |
| 爪印档案 | #FF8C42 (暖橙) | `--theme-orange` |
| Lorebook | #8B5CF6 (紫罗兰) | `--theme-purple` |

### 主题色使用规则

- 左栏背景联动：主题色降饱和度，多层径向渐变叠加，opacity 0.08-0.20
- 卡片边框/标签：主题色 20-30% 混合边框色
- 头像光环：主题色呼吸动画
- 右侧光边：主题色 45% opacity

## 字体

| 用途 | 字体 | 备选 |
| --- | --- | --- |
| 英文标题/正文 | Space Grotesk | -apple-system, sans-serif |
| 中文 | Noto Sans SC | system-ui |
| 等宽/标签 | JetBrains Mono | monospace |

### 字号

| 层级 | 桌面 | 手机 |
| --- | --- | --- |
| 姓名 | 30px / 700 | 20px / 700 |
| 作品名 | 22px / 600 | 17px / 600 |
| 正文 | 14px / 400 | 13px / 400 |
| 辅助 | 12px / 400 | 11px / 400 |
| 标签/mono | 11px / 500 | 10px / 500 |

## 间距

基础单位 4px，常用间距：

| Token | 值 | 用途 |
| --- | --- | --- |
| xs | 4px | 紧凑间距 |
| sm | 8px | 标签间距 |
| md | 16px | 卡片内间距 |
| lg | 24px | 区块间距 |
| xl | 32px | 卡片外边距 |
| 2xl | 48px | 面板 padding |

## 圆角

| 元素 | 圆角 |
| --- | --- |
| 卡片 | 20px（桌面）/ 14px（手机） |
| 图标 | 16px（桌面）/ 12px（手机） |
| 标签胶囊 | 100px |
| 截图 | 10px（桌面）/ 8px（手机） |
| 社交按钮 | 12px（桌面）/ 10px（手机） |
| 语言切换 | 8px |

## 动效

### 左栏背景联动（核心）

- 触发：Intersection Observer 检测右栏当前可见作品
- 效果：多层渐变色平滑过渡
- 时长：1.2s cubic-bezier(0.4, 0, 0.2, 1)

### 头像呼吸光

- 背后径向渐变 + 外层描边同时呼吸
- 周期：4s ease-in-out
- 光晕缩放 scale 1.0 → 1.06

### 卡片 Hover

- translateY: -4px
- 边框亮度增强
- box-shadow 扩散
- 时长：0.35s

### 页面加载

- 左栏元素依次 fadeInUp（间隔 0.1s）
- 右栏卡片依次 slideInRight（间隔 0.15s）

### 克制原则

- 不用 3D、粒子、Canvas
- 不用打字机、故障闪烁、数字雨
- `prefers-reduced-motion` 时禁用所有动画

## 响应式断点

| 名称 | 范围 | 布局 |
| --- | --- | --- |
| 桌面 | ≥ 1024px | 左右分栏 |
| 平板 | 768-1023px | 窄左栏 + 右栏 |
| 手机 | < 768px | 上下布局 |
