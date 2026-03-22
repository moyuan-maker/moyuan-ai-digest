# 墨远 AI 速览

> 每日 AI 行业新闻精选 · 英文一手信源 · AI 撰写 · 自动更新

🌐 **在线访问**：[moyuan-maker.github.io/moyuan-ai-digest](https://moyuan-maker.github.io/moyuan-ai-digest)

---

## 这是什么

**墨远 AI 速览**是一份每日 AI 行业新闻精选，由墨远出品。

中文 AI 资讯普遍存在二次加工、标题情绪化、商业内容不标注等问题。这个项目试图提供另一种选择：直接从英文一手信息源抓取，AI 按新闻写作规范撰写，全程不做人工内容干预。

不保证比别人更有深度，但保证更接近事实原貌。

## 功能特性

- 📰 **每日自动更新** — 用户访问时由 AI 实时生成当天内容
- 🔍 **3 篇深度报道** — 覆盖产品发布、融资动态、行业动态等不同方向
- ⚡ **5 条今日快讯** — 简短客观，涵盖更广泛的行业动态
- 📁 **历史存档** — 可查阅历史每日内容
- 📖 **方法论透明** — 详细说明信源选择、评分机制和中立性原则

## 信息来源

全部来自英文互联网，共监控 20+ 信源：

| 类型 | 来源 |
|------|------|
| 公司官方博客 | OpenAI · Anthropic · Google AI · Meta · NVIDIA |
| 科技媒体 | The Verge · TechCrunch · MIT Technology Review · Wired · 404 Media |
| 行业 Newsletter | Ben's Bites · Import AI · The Rundown AI · TLDR AI |
| 社区信号 | Hacker News AI 热帖 · Product Hunt AI 分类 |

## 技术架构

```
用户访问网站
    │
    ▼
前端调用 Kimi API（moonshot-v1-8k）
    │
    ▼
AI 根据编辑规范生成当日内容
（3 篇报道 + 5 条快讯 + 今日概要）
    │
    ▼
渲染到页面
```

- **前端**：纯 HTML / CSS / JavaScript，无框架依赖
- **AI 模型**：Kimi（月之暗面 moonshot-v1-8k）
- **托管**：GitHub Pages，零服务器成本
- **字体**：Fraunces · Noto Serif SC · DM Mono

## 评分机制

每条候选新闻按五个维度自动评分：

| 维度 | 规则 | 权重 |
|------|------|------|
| 多源交叉验证 | 同一事件被 2+ 个源报道 | +40 |
| 来源权威度 | 官方博客 / 一线媒体 | +30 |
| 社区热度 | HN 点赞 ≥ 100 / ≥ 300 | +15 / +30 |
| 时效性 | 24h 内 / 48h 内 | +15 / +5 |
| 产品信号词 | launch · release · raises 等 | +20 |

分数 ≥ 60 → 重点关注池　·　30–59 → 普通候选池　·　< 30 → 丢弃

## 本地运行

这是一个纯静态网站，无需安装任何依赖。

1. 克隆仓库

```bash
git clone https://github.com/moyuan-maker/moyuan-ai-digest.git
cd moyuan-ai-digest
```

2. 在 `index.html` 中填入你的 Kimi API Key

```javascript
const KIMI_API_KEY = '你的 API Key';
```

3. 用浏览器直接打开 `index.html` 即可

## 关于中立性

核心原则：**人只调规则，不碰内容。**

- 信源权重、筛选规则、编辑规范由人制定
- 每天选什么题、怎么写、用什么标题由 AI 基于规则自动完成
- 本项目不接受任何形式的商业合作内容

## 已知局限

- 英文源偏向，纯面向国内市场的小众动态可能覆盖不足
- AI 生成内容可能存在理解偏差，建议点击来源链接验证
- 单人项目，没有事实核查团队

## License

MIT License · © 2026 墨远
