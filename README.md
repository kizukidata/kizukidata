# Kizuki

Apify Actors that turn public pages and open data into rows with named fields: LinkedIn job and company pages, work-visa employer data, EU public tenders, news and social posts (Google News, Telegram, Bluesky, YouTube, WeChat Official Accounts), note.com articles, TikTok ads, podcast sponsors, public MCP server directories, and YouTube captions, PDFs and web pages as Markdown.

Kizuki is an independent developer on Apify Store. The Actors are unofficial and not affiliated with or endorsed by Apify, LinkedIn, Google, YouTube, Telegram, Bluesky, TikTok, note, Tencent, the MCP project, Smithery, the maintainers of the awesome-mcp-servers list, or any other site or public body whose data they read.

You pay for rows that carry data. A run that finds nothing has no per-row charge. A failure is not charged per row either: depending on the Actor, it shows up as a row with the reason, in the run's OUTPUT record, or in the run's status message. Apify's run start fee applies to every run: USD 0.00005 per GB of memory (one event per GB, minimum one event). Each Actor's page shows its default memory.

- Site: [kizukidata.com](https://kizukidata.com)
- Actors on Apify Store: [apify.com/kizukidata](https://apify.com/kizukidata)
- Code examples: [kizukidata/examples](https://github.com/kizukidata/examples)
- X: [@kizukidata](https://x.com/kizukidata)
- Discord: [discord.gg/QdmUHkJSm8](https://discord.gg/QdmUHkJSm8)
- Qiita (articles in Japanese): [@kizukidata](https://qiita.com/kizukidata)
- Contact: contact@kizukidata.com

## Actors

Prices are the Free-tier price per 1,000 returned rows, from each Actor's Pricing tab on 13 November 2026. A higher Apify plan lowers the row price.

### Hiring and work visas

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [LinkedIn Jobs Scraper](https://apify.com/kizukidata/linkedin-jobs-feed) | a public LinkedIn job posting: title, company, location, posted date, pay range, seniority, applicants | $0.33 |
| [LinkedIn Company Scraper & Change Monitor](https://apify.com/kizukidata/linkedin-company-monitor) | a company page, or with `onlyChanges` a company whose fields moved, with the old and new value | $1.29 |
| [UK Visa Sponsor Jobs Scraper](https://apify.com/kizukidata/uk-visa-sponsor-jobs) | a UK job ad from a company job board you name, matched to the Home Office sponsor register: visa routes, rating | $0.50 |
| [Canada LMIA Employers Scraper](https://apify.com/kizukidata/canada-lmia-employers) | an employer with a positive LMIA, by occupation, province and program stream, from Canada's open data | $0.65 |

For the two LinkedIn Actors, with `onlyNewItems` on jobs and `onlyChanges` on company pages, a daily run returns the postings and the profile changes since the previous run.

### Public tenders

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [EU Tenders Scraper (TED)](https://apify.com/kizukidata/eu-tenders) | an EU tender notice: buyer, CPV codes, deadline, estimated value when published, links to the notice | $0.80 |

### News and social

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [Google News Scraper](https://apify.com/kizukidata/google-news-feed) | an article: title, outlet, publication time, the outlet's own article URL | $1.36 |
| [Telegram Channel Scraper](https://apify.com/kizukidata/telegram-channel-feed) | a public channel post: text, time, views, reactions, media | $0.28 |
| [YouTube Channel Scraper](https://apify.com/kizukidata/youtube-channel-monitor) | a channel, a video or a comment | $0.24 |
| [Bluesky Monitor](https://apify.com/kizukidata/bluesky-monitor) | a Bluesky post found by keyword or account, or an account's follower counts with the change since the last run | $0.73 |
| [WeChat Article Scraper](https://apify.com/kizukidata/wechat-article-reader) | a WeChat Official Account article: title, account, author, publish time, the Original mark, full text, Markdown and image URLs | $1.60 |

### Japan

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [note.com Scraper](https://apify.com/kizukidata/note-articles-feed) | a note.com article: title, likes, comments, hashtags, paid price | $1.21 |

### Ads and sponsors

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [TikTok Ads Library Scraper](https://apify.com/kizukidata/tiktok-ads-monitor) | an ad in the EU TikTok Ad Library, marked NEW, ACTIVE, SCALING or STOPPED against your previous run | $0.33 |
| [Podcast Sponsors](https://apify.com/kizukidata/podcast-sponsors) | a sponsor named in a podcast episode's show notes: name, domain, promo code, the evidence line | $3.20 |

### For LLMs and RAG

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [YouTube Transcript Scraper](https://apify.com/kizukidata/youtube-transcripts) | a video's captions: chapter-aware Markdown, timed segments, RAG chunks | $1.00 |
| [PDF to Markdown Extractor](https://apify.com/kizukidata/pdf-to-markdown) | a PDF as page-numbered Markdown (`## Page N`) | $1.60 |
| [URL to Markdown](https://apify.com/kizukidata/url-to-markdown) | a page's main content as Markdown, menus and footers dropped | $0.33 |
| [MCP Server Registry Scraper](https://apify.com/kizukidata/mcp-server-directory) | a public MCP server merged from the MCP Registry, Smithery and awesome-mcp-servers: repository, package, transport, version, new or removed | $0.36 |

Each Actor's page on Apify Store has its input fields, its output fields and its price. A scan without a text layer, a page that needs JavaScript, a blocked job page and an unknown channel are all reported with the reason and cost nothing per item.

<!-- Add newly published Actors here, one row each, same table shape. -->

## For AI agents (MCP)

Seven bundles are listed in the official MCP Registry. Any client that accepts a remote MCP URL works: Claude Desktop, Claude Code, Cursor, VS Code. On the first connection your browser opens so you can sign in to Apify.

| Bundle | Actors in it | URL |
|---|---|---|
| Hiring Signals | `linkedin-jobs-feed`, `linkedin-company-monitor` | `https://mcp.apify.com?tools=kizukidata/linkedin-jobs-feed,kizukidata/linkedin-company-monitor` |
| News Monitoring | `google-news-feed`, `youtube-channel-monitor`, `telegram-channel-feed` | `https://mcp.apify.com?tools=kizukidata/google-news-feed,kizukidata/youtube-channel-monitor,kizukidata/telegram-channel-feed` |
| RAG Ingest | `youtube-transcripts`, `pdf-to-markdown`, `url-to-markdown` | `https://mcp.apify.com?tools=kizukidata/youtube-transcripts,kizukidata/pdf-to-markdown,kizukidata/url-to-markdown` |
| EU Tenders | `eu-tenders` | `https://mcp.apify.com?tools=kizukidata/eu-tenders` |
| Social Monitoring | `bluesky-monitor`, `telegram-channel-feed`, `note-articles-feed`, `wechat-article-reader` | `https://mcp.apify.com?tools=kizukidata/bluesky-monitor,kizukidata/telegram-channel-feed,kizukidata/note-articles-feed,kizukidata/wechat-article-reader` |
| Work Visa Data | `uk-visa-sponsor-jobs`, `canada-lmia-employers` | `https://mcp.apify.com?tools=kizukidata/uk-visa-sponsor-jobs,kizukidata/canada-lmia-employers` |
| MCP Server Directory | `mcp-server-directory` | `https://mcp.apify.com?tools=kizukidata/mcp-server-directory` |

For one Actor: `https://mcp.apify.com?tools=kizukidata/url-to-markdown`.

Registry names: `io.github.kizukidata/hiring-signals`, `io.github.kizukidata/news-monitoring`, `io.github.kizukidata/rag-ingest`, `io.github.kizukidata/eu-tenders`, `io.github.kizukidata/social-monitoring`, `io.github.kizukidata/work-visa-data`, `io.github.kizukidata/mcp-server-directory`.

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

- Kizuki は Apify Store で公開データを 1 行 1 件の表にする Actor を作っています。公開中の Actor は、採用とビザ・公共入札・ニュースと SNS（WeChat の公式アカウントの記事を含む）・日本（note）・広告とスポンサー・LLM 向け（字幕・PDF・Web・公開の MCP サーバーの一覧）に分けています。
- 課金は返した行の数で決まります（表は Free の段の 1,000 行あたり、2026-11-13 の時点。上の段のプランほど 1 行の値段は下がります）。入力を処理して 0 件だったときは 1 件あたりの課金はありません。失敗も 1 件あたりの課金はありません。失敗の理由は、Actor によって、データセットの行、run の OUTPUT の記録、run の状態の文のどれかに出ます。走らせるたびに Apify の起動料（1 GB ごとに USD 0.00005、1 GB 未満でも 1 回分。既定のメモリは各 Actor の頁）がかかります。
- MCP は 7 つのまとめを公式の MCP Registry に置いています。`https://mcp.apify.com?tools=...` の形で、使う Actor だけを AI エージェントに読み込ませられます。
- 非公式です。Apify・LinkedIn・Google・YouTube・Telegram・Bluesky・TikTok・note・Tencent・MCP のプロジェクト・Smithery・awesome-mcp-servers の管理者、そのほかデータを読む先のサイトや公的機関とは関係なく、承認も受けていません。
- 使い方の例（curl・Python・JavaScript・MCP・n8n）は kizukidata/examples にあります（MIT）。
