# VividMap 官网

VividMap 工作室的官网，一个站点内含两款 App：**ChronosMap**（时间地图）与
**云迹 / yunji**（把照片变成活的旅行地图）。视觉与交互沿用 ChronosMap 官网
的设计语言（浅色蓝调、Inter 字重对比、设备截图网格、手机框路线插画、sticky
模糊导航），在其上扩展了工作室首页与云迹页。

## 结构

| 文件 | 页面 |
|------|------|
| `index.html` | 工作室首页：双 App 入口门户卡 + 隐私承诺 |
| `chronosmap.html` | ChronosMap 产品页 |
| `yunji.html` | 云迹产品页 |
| `privacy.html` | 隐私政策（工作室通用，覆盖两款 App） |
| `support.html` | 支持 / FAQ |
| `site.css` | 样式（ChronosMap 基础 + 合并站扩展） |
| `site.js` | ChronosMap 的 i18n 引擎与原有 9 语言翻译（未改动核心） |
| `studio-i18n.js` | 注入工作室首页 / 云迹 / 品牌名的多语言文案，并把隐私/支持改写为工作室通用版 |
| `reveal.js` | 滚动显现 + 导航滚动态（渐进增强，无 JS 时内容默认可见） |
| `assets/` | 两款 App 的图标与设备/界面截图 |

## 命名

| 语言 | 名称 |
|------|------|
| 简体中文 | 云迹 |
| 繁體中文 | 雲跡 |
| 日本語 | 雲跡 |
| 한국어 | 운적 |
| 其他 | yunji |

站点默认英文，右上角可在 9 种语言间切换；其中 en / zh-Hans / zh-Hant 提供
工作室首页与云迹页的完整文案，其余语言的工作室/云迹文案回退英文（ChronosMap
原有内容仍各自本地化），品牌名按上表逐语言显示。

## 本地预览

```bash
# 直接双击 index.html 即可（纯静态，无需服务器；无 JS 时内容也完整可见）
open index.html

# 或起一个静态服务器
python3 -m http.server 8080   # 访问 http://localhost:8080
```

## 设计说明

- 首页以「双图标漂浮卡 + 漂浮地名胶囊」开场，而非居中标题三段式；门户卡用
  不等高的截图与悬浮抬升做微交互。
- 滚动显现、导航滚动态、卡片悬浮、漂浮胶囊动画均带 `prefers-reduced-motion`
  降级；`.reveal` 采用 `.js` 门控，保证无 JS / 爬虫环境下内容默认可见。
- 云迹页沿用 ChronosMap 的 `device-shot` / `phone-frame` / `route-line` 组件，
  保持两页视觉一致。
