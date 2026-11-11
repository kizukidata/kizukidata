# Kizuki

Apify Actors that turn public pages into rows with named fields: LinkedIn jobs and company pages, Google News, Telegram and YouTube channels, note articles, TikTok ads, YouTube captions, PDFs and web pages.

Kizuki is an independent developer on Apify Store. The Actors are unofficial and not affiliated with or endorsed by Apify, LinkedIn, Google, YouTube, Telegram, TikTok or note.

You pay for rows that carry data. A run that finds nothing has no per-row charge, and a row that only records a failure stays in the dataset so you can see what happened without being charged. Apify's run start fee applies to every run: USD 0.00005 per GB of memory (one event per GB, minimum one event). Each Actor's page shows its default memory.

- Site: [kizukidata.com](https://kizukidata.com)
- Actors on Apify Store: [apify.com/kizukidata](https://apify.com/kizukidata)
- Code examples: [kizukidata/examples](https://github.com/kizukidata/examples)
- X: [@kizukidata](https://x.com/kizukidata)
- Discord: [discord.gg/QdmUHkJSm8](https://discord.gg/QdmUHkJSm8)
- Contact: contact@kizukidata.com

## Actors

Prices are the Free tier, per returned row, from the Pricing tab of each Actor (November 2026). A higher Apify plan lowers the row price.

### Hiring

| Actor | One row is | Per row |
|---|---|---|
| [LinkedIn Jobs Scraper](https://apify.com/kizukidata/linkedin-jobs-feed) | a public LinkedIn job posting: title, company, location, posted date, pay range, seniority, applicants | $0.0012 |
| [LinkedIn Company Scraper & Change Monitor](https://apify.com/kizukidata/linkedin-company-monitor) | a company page, or with `onlyChanges` a company whose fields moved, with the old and new value | $0.0020 |

With `onlyNewItems` on jobs and `onlyChanges` on company pages, a daily run returns the postings and the profile changes since the previous run.

### News and channels

| Actor | One row is | Per row |
|---|---|---|
| [Google News Scraper](https://apify.com/kizukidata/google-news-feed) | an article: title, outlet, publication time, the outlet's own article URL | $0.0017 |
| [Telegram Channel Scraper](https://apify.com/kizukidata/telegram-channel-feed) | a public channel post: text, time, views, reactions, media | $0.0020 |
| [YouTube Channel Scraper](https://apify.com/kizukidata/youtube-channel-monitor) | a channel, a video or a comment | $0.0011 |

### Japan

| Actor | One row is | Per row |
|---|---|---|
| [note.com Scraper](https://apify.com/kizukidata/note-articles-feed) | a note.com article: title, likes, comments, hashtags, paid price | $0.0020 |

### Ads

| Actor | One row is | Per row |
|---|---|---|
| [TikTok Ads Library Scraper](https://apify.com/kizukidata/tiktok-ads-monitor) | an ad in the EU TikTok Ad Library, marked NEW, ACTIVE, SCALING or STOPPED against your previous run | $0.0018 |

### For LLMs and RAG

| Actor | One row is | Per row |
|---|---|---|
| [YouTube Transcript Scraper](https://apify.com/kizukidata/youtube-transcripts) | a video's captions: chapter-aware Markdown, timed segments, RAG chunks | $0.0020 |
| [PDF to Markdown Extractor](https://apify.com/kizukidata/pdf-to-markdown) | a PDF as page-numbered Markdown (`## Page N`) | $0.0022 |
| [URL to Markdown](https://apify.com/kizukidata/url-to-markdown) | a page's main content as Markdown, menus and footers dropped | $0.0014 |

Each Actor's page on Apify Store has its input fields, its output fields and its price. A scan without a text layer, a page that needs JavaScript, a blocked job page and an unknown channel are all reported with the reason and cost nothing per item.

<!-- Add newly published Actors here, one row each, same table shape. -->

## For AI agents (MCP)

Three bundles are listed in the official MCP Registry. Any client that accepts a remote MCP URL works: Claude Desktop, Claude Code, Cursor, VS Code. On the first connection your browser opens so you can sign in to Apify.

| Bundle | Actors in it | URL |
|---|---|---|
| Hiring Signals | `linkedin-jobs-feed`, `linkedin-company-monitor` | `https://mcp.apify.com?tools=kizukidata/linkedin-jobs-feed,kizukidata/linkedin-company-monitor` |
| News Monitoring | `google-news-feed`, `youtube-channel-monitor`, `telegram-channel-feed` | `https://mcp.apify.com?tools=kizukidata/google-news-feed,kizukidata/youtube-channel-monitor,kizukidata/telegram-channel-feed` |
| RAG Ingest | `youtube-transcripts`, `pdf-to-markdown`, `url-to-markdown` | `https://mcp.apify.com?tools=kizukidata/youtube-transcripts,kizukidata/pdf-to-markdown,kizukidata/url-to-markdown` |

For one Actor: `https://mcp.apify.com?tools=kizukidata/url-to-markdown`.

Registry names: `io.github.kizukidata/hiring-signals`, `io.github.kizukidata/news-monitoring`, `io.github.kizukidata/rag-ingest`.

Claude Code:

```bash
claude mcp add --transport http kizuki-rag "https://mcp.apify.com?tools=kizukidata/youtube-transcripts,kizukidata/pdf-to-markdown,kizukidata/url-to-markdown"
```

Claude Desktop and Cursor config files are in [kizukidata/examples/mcp](https://github.com/kizukidata/examples/tree/main/mcp). The server's `call-actor` tool starts a run and returns the run and dataset IDs; `get-dataset-items` reads the rows.

## From code

Every Actor takes a JSON input and returns JSON rows, so the same pattern covers all of them. Examples in curl, Python, JavaScript and n8n are in [kizukidata/examples](https://github.com/kizukidata/examples) (MIT).

```bash
curl -s -X POST "https://api.apify.com/v2/acts/kizukidata~url-to-markdown/run-sync-get-dataset-items?format=json" \
  -H "Authorization: Bearer $APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"urls": ["https://apify.com/kizukidata"], "maxItems": 1}'
```

## 日本語の要点

- Kizuki は Apify Store で公開データを 1 行 1 件の表にする Actor を作っています。公開中の Actor は、採用・ニュース・日本（note）・広告・LLM 向け（字幕・PDF・Web）に分けています。
- 値段は返した行だけ（Free の段、2026-11 の時点）。入力を処理して 0 件だったときは 1 件あたりの課金はありません。失敗だけを記録する行もデータセットに残りますが、課金されません。走らせるたびに Apify の起動料（1 GB ごとに USD 0.00005、1 GB 未満でも 1 回分。既定のメモリは各 Actor の頁）がかかります。
- MCP は 3 つのまとめを公式の MCP Registry に置いています。`https://mcp.apify.com?tools=...` の形で、使う Actor だけを AI エージェントに読み込ませられます。
- 非公式です。Apify・LinkedIn・Google・YouTube・Telegram・TikTok・note とは関係なく、承認も受けていません。
- 使い方の例（curl・Python・JavaScript・MCP・n8n）は kizukidata/examples にあります（MIT）。
