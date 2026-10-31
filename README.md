# notion-widgets

给 Notion 用的一组极简小组件：**黑白色 · Material You 形态 · 自动深浅色 · 铺满容器**。

纯静态 HTML/CSS/JS，无构建步骤、无框架、**无任何 API key**。

## 组件

| 组件 | 地址 | 说明 |
|:--|:--|:--|
| 时钟 | `/clock/` | 实时时间 + 秒 + 日期 + 年内进度 |
| 天气 | `/weather/` | 大同 / 苏州可切换，数据来自 Open-Meteo |
| 倒计时 | `/countdown/` | 默认高考，支持自定义日期与标题 |
| 今日一句 | `/quote/` | 本地句池，一天一句，当天稳定不变 |

## 嵌入 Notion

1. 在 Notion 页面输入 `/embed`
2. 粘贴组件地址
3. 拖动 iframe 下缘调整高度（建议 200–300px）

## 参数

**主题强制**（所有组件）—— 页面配色和系统不一致时用：

```
?theme=dark
?theme=light
```

**倒计时自定义**：

```
/countdown/?date=2027-06-07&label=高考
/countdown/?date=2027-09-01&label=开学
```

**天气城市**：点组件里的「大同 / 苏州」切换，选择存在浏览器本地。
城市坐标在 `weather/index.html` 的 `CITIES` 里改。

## 设计规范

- 颜色：只有黑白灰，不出现任何色相
- 圆角：卡片 `28px` / 内部元素 `18px` / pill `999px`
- 间距：4px 基数
- 数字：等宽字体 + `tabular-nums`，切换数字时不跳动
- 深浅色：跟随系统 `prefers-color-scheme`，可用 `?theme=` 覆盖
- 所有尺寸用 `clamp()` + `vh/vw`，iframe 拉高拉矮都不会溢出或裁切

设计 token 全部集中在 `assets/base.css` 的 `:root`，改一处全局生效。

## 关于密钥

本仓库**不含任何 API key、token、密码**。

天气使用 [Open-Meteo](https://open-meteo.com/) 的免费公开接口，无需注册、无需密钥，
响应头 `access-control-allow-origin: *`，可直接在浏览器里请求。

## 许可

自用为主，随便改。
