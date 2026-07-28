# kotobasnap.github.io

Kotoba Snap 的公开页面：隐私政策与支持信息。由 GitHub Pages 提供。

应用源码在私有仓库 `goodboy0924/kotoba-snap-app`；本仓库**只存放需要公开可访问的文本**，不含任何应用代码。

## 页面

| 路径 | 内容 |
|---|---|
| `/` | 落地页，指向下列各页 |
| `/privacy/` | 隐私政策（简体中文） |
| `/privacy/en/` | Privacy Policy (English) |

仓库名等于组织名，所以这是组织的**主站**：路径里没有仓库名那一段，站内绝对链接一律以 `/` 开头。**不要写成 `/kotobasnap.github.io/...`** —— 那是项目站（`<org>.github.io/<repo>/`）的形式，在这里会 404。从旧站搬过来时改的正是这个。

## 与旧站的关系

2026-07-28 之前发布在 `goodboy0924/kotoba-snap-site`（`https://goodboy0924.github.io/kotoba-snap-site/`）。搬到组织站是为了让公开 URL 不带个人账号名。

**旧站保持在线，不下线。** 它的 URL 已经公开过，可能已被收藏或抓取；留着比制造一个死链好。商店 listing 与应用内入口一律指向本站。

## 与 app 仓库的关系

隐私政策的**草案与评审记录**在 app 仓库的 `docs/privacy/`（PR `goodboy0924/kotoba-snap-app#283`），行为审计依据在 `docs/隐私行为审计.md`。

**本仓库是已发布文本的唯一权威来源。** 修改流程：先在 app 仓库走评审，通过后同步到这里并更新「最后更新」日期；两边不一致时以这里为准。

同步时注意：app 仓库的 Markdown 用 `# 标题` 作正文首行，本站改用 front matter 的 `title` 渲染标题，因此同步要去掉 H1、补 front matter 与语言切换链接。**除此之外应逐字节一致** —— 2026-07-28 上线前的核对发现旧站停在评审前草案，差 109 行，其中含一条已被订正的不实表述（见 `goodboy0924/ai-app-project#70`）。副本会悄悄落后，同步后请实际 diff 一次。

## 本地预览

```bash
bundle exec jekyll serve
```

无自定义插件与主题 gem，GitHub Pages 直接构建即可。布局自包含（内联 CSS、无 webfont、无任何外部请求）—— 一个会向 CDN 发请求的隐私政策页面本身就是个笑话。

关联：`goodboy0924/ai-app-project#70`
