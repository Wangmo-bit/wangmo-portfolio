# 数据模型

所有数据以 JSON 文件存储在 `src/content/` 目录下，构建时读取。

## 作品数据 — projects.json

```json
[
  {
    "id": "cyberlife",
    "name_zh": "赛博生活",
    "name_en": "CyberLife",
    "tagline_zh": "赛博朋克风格的订阅会员管理工具",
    "tagline_en": "Cyberpunk-style subscription manager",
    "description_zh": "详细介绍...",
    "description_en": "Detailed description...",
    "status": "developing",
    "theme_color": "#00F0FF",
    "icon": "cyberlife-icon.png",
    "platform": "iOS",
    "screenshots": ["cyberlife-01.png", "cyberlife-02.png"],
    "tech_stack": ["Swift 6", "SwiftUI", "SwiftData", "CloudKit"],
    "links": {
      "appstore": "",
      "github": ""
    },
    "order": 1
  }
]
```

### status 枚举

| 值 | 中文显示 | 英文显示 |
| --- | --- | --- |
| `released` | 已上架 | Released |
| `developing` | 开发中 | In Dev |
| `coming_soon` | 即将推出 | Coming Soon |

## 媒体报道 — press.json

```json
[
  {
    "title_zh": "独立开发者王墨：用赛博朋克重新定义订阅管理",
    "title_en": "Indie dev Mo Wang redefines subscription management",
    "source": "少数派",
    "url": "https://...",
    "date": "2026-03-15"
  }
]
```

- 按 `date` 倒序排列
- 数组为空时隐藏整个板块

## 个人信息 — profile.json

```json
{
  "name_zh": "王墨",
  "name_en": "Mo Wang",
  "domain": "wangmo.tech",
  "bio_zh": "用代码和产品思维创造有趣的工具。\n相信好的产品能让日常多一点秩序感和仪式感。",
  "bio_en": "Building delightful tools with code and product thinking.\nBelieving great products bring order and ritual to everyday life.",
  "tags_zh": ["梅乾资本创始人", "养了三只猫", "热爱游戏", "热爱产品"],
  "tags_en": ["Founder of Dry Capital", "Cat dad ×3", "Gamer", "Product nerd"],
  "email": "wangmodream@qq.com",
  "social": {
    "jike": "https://...",
    "xiaohongshu": "https://...",
    "github": "https://github.com/..."
  }
}
```

## 图片资源约定

| 目录 | 内容 | 命名规则 |
| --- | --- | --- |
| `src/assets/avatar/` | 头像 | `avatar.jpg` |
| `src/assets/projects/` | 作品截图 | `{project-id}-{nn}.png` |
| `src/assets/icons/` | 作品图标 | `{project-id}-icon.png` |
| `public/` | favicon、OG image | `favicon.svg`, `og.png` |

图片要求：

- 截图建议宽度 1200px，PNG 或 WebP
- Astro `<Image />` 组件会自动生成响应式尺寸和 WebP
- 概念图（Coming Soon 作品）可用占位图，后续替换
