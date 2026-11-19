# Kizuki

Apify Actors that turn public pages and open data into rows with named fields: LinkedIn, Workday and ATS job boards, work-visa employer data, EU public tenders, company websites and tech stacks, YouTube channels, transcripts, Shorts, comments and creator contacts, Instagram posts and Reels, Threads, Reddit, Bluesky, Telegram, Google News, WeChat Official Accounts, note.com, Naver Blog, TikTok and Google ads, podcast sponsors, online stores' UCP profiles, public MCP server directories, and PDFs and web pages as Markdown.

Kizuki is an independent developer on Apify Store. The Actors are unofficial and not affiliated with or endorsed by Apify, LinkedIn, Workday, Google, YouTube, Meta, Instagram, Threads, Reddit, Telegram, Bluesky, TikTok, note, Naver, Tencent, the UCP project, the MCP project, Smithery, the maintainers of the awesome-mcp-servers list, or any other site or public body whose data they read.

You pay for rows that carry data. A run that finds nothing has no per-row charge. A failure is not charged per row either: depending on the Actor, it shows up as a row with the reason, in the run's OUTPUT record, or in the run's status message. Apify's run start fee applies to every run: USD 0.00005 per GB of memory (one event per GB, minimum one event). Each Actor's page shows its default memory.

- Site: [kizukidata.com](https://kizukidata.com)
- Actors on Apify Store: [apify.com/kizukidata](https://apify.com/kizukidata)
- Code examples: [kizukidata/examples](https://github.com/kizukidata/examples)
- X: [@kizukidata](https://x.com/kizukidata)
- Discord: [discord.gg/QdmUHkJSm8](https://discord.gg/QdmUHkJSm8)
- Qiita (articles in Japanese): [@kizukidata](https://qiita.com/kizukidata)
- Contact: contact@kizukidata.com

## Actors

Prices are the Free-tier price per 1,000 returned rows, from each Actor's Pricing tab on 19 November 2026. A higher Apify plan lowers the row price.

### Hiring and work visas

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [LinkedIn Jobs Scraper](https://apify.com/kizukidata/linkedin-jobs-feed) | a public LinkedIn job posting: title, company, location, posted date, pay range, seniority, applicants | $0.33 |
| [LinkedIn Company Scraper & Change Monitor](https://apify.com/kizukidata/linkedin-company-monitor) | a company page, or with `onlyChanges` a company whose fields moved, with the old and new value | $1.29 |
| [ATS Job Scraper](https://apify.com/kizukidata/ats-jobs) | an open job from Ashby, Greenhouse, Lever, Workable, SmartRecruiters or Recruitee boards with yearly pay and pay-transparency rule | $0.80 |
| [Workday Jobs Scraper](https://apify.com/kizukidata/workday-jobs-scraper) | an open job from a public Workday careers site (past the 2,000-job limit): salary range, yearly pay, closing date, locations, description, new and closed jobs | $0.10 |
| [UK Visa Sponsor Jobs Scraper](https://apify.com/kizukidata/uk-visa-sponsor-jobs) | a UK job ad from a company job board you name, matched to the Home Office sponsor register: visa routes, rating | $0.50 |
| [Canada LMIA Employers Scraper](https://apify.com/kizukidata/canada-lmia-employers) | an employer with a positive LMIA, by occupation, province and program stream, from Canada's open data | $0.65 |

With `onlyNewItems` on jobs and `onlyChanges` on company pages, a daily run returns the postings and the profile changes since the previous run.

### Company data, contacts and tech stacks

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [Website Tech Stack Detector](https://apify.com/kizukidata/website-tech-stack-detector) | a domain's CMS, shop platform, frameworks, analytics, ad pixel IDs, CDN, hosting, payments, mail host, DNS host and verified SaaS with evidence | $0.30 per 1,000 domains with a technology found |
| [Website Contact Scraper](https://apify.com/kizukidata/website-contact-intelligence) | a company domain's published emails, phones, social profiles, contact forms, booking links, DNS mail setup and ad pixels | $0.75 per 1,000 domains with a contact |
| [Google Maps Email & Contact Extractor](https://apify.com/kizukidata/google-maps-contact-enricher) | a Google Maps place enriched with website emails, phones, socials, contact forms, booking links and DNS mail setup | $0.75 per 1,000 domains with a contact |
| [YouTube Email Scraper](https://apify.com/kizukidata/youtube-creator-contact-scraper) | a YouTube creator's emails from the description, link-in-bio page and website, plus socials, contact forms, booking links and ad pixels | $2.40 per 1,000 channels with a contact |

### Public tenders

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [EU Tenders Scraper (TED)](https://apify.com/kizukidata/eu-tenders) | an EU tender notice: buyer, CPV codes, deadline, estimated value when published, links to the notice | $0.80 |

### YouTube

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [YouTube Channel Scraper & Monitor](https://apify.com/kizukidata/youtube-channel-monitor) | a channel, a video or a comment | $0.24 |
| [YouTube Comments Scraper](https://apify.com/kizukidata/youtube-comments-scraper) | a top or newest comment or reply row from videos, Shorts and channels | $0.20 |
| [YouTube Playlist Scraper](https://apify.com/kizukidata/youtube-playlist-chapters-scraper) | a playlist video with chapters, most replayed moments and an optional transcript | $0.50 ($1.50 per 1,000 transcripts) |
| [YouTube Shorts Scraper](https://apify.com/kizukidata/youtube-shorts-search) | a YouTube Short by keyword, channel or URL with view counts, hashtags and an optional transcript | $0.80 ($0.60 per 1,000 transcripts) |
| [YouTube Transcript Scraper](https://apify.com/kizukidata/youtube-transcripts) | a video's captions: chapter-aware Markdown, timed segments, SRT/VTT and RAG chunks | $1.50 |

### Social and news

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [Instagram Post & Reel Details Scraper](https://apify.com/kizukidata/instagram-post-reel-details) | a public Instagram post, carousel or Reel: caption, hashtags, likes, comments, audio, media URLs, Reel plays and creator stats (no login) | $1.10 |
| [Instagram Reels Transcript Scraper](https://apify.com/kizukidata/instagram-reels-transcript) | a public Instagram Reel's spoken transcript, hooks, audio details and engagement stats (no login) | $4.20 |
| [Threads Scraper](https://apify.com/kizukidata/threads-scraper) | a public Threads post, reply, repost or search result, or a public profile with followers and bio (no login) | $1.60 per 1,000 posts; $3.20 per 1,000 profiles |
| [Reddit Scraper](https://apify.com/kizukidata/reddit-scraper) | a public Reddit post by subreddit, URL, author or keyword, with optional comment trees | $0.80 ($0.60 per 1,000 comments) |
| [Reddit Comments Scraper](https://apify.com/kizukidata/reddit-comments-scraper) | a nested Reddit comment or LLM-ready Markdown thread | $0.60 ($0.80 per 1,000 posts) |
| [Reddit User & Subreddit Scraper](https://apify.com/kizukidata/reddit-user-subreddit-scraper) | a Reddit user's posts and comments, or a subreddit's rules and newest posts | $1.25 |
| [Google News Scraper](https://apify.com/kizukidata/google-news-feed) | an article: title, outlet, publication time, the outlet's own article URL | $1.36 |
| [Telegram Channel Scraper](https://apify.com/kizukidata/telegram-channel-feed) | a public channel post: text, time, views, reactions, media | $0.28 |
| [Bluesky Monitor](https://apify.com/kizukidata/bluesky-monitor) | a Bluesky post found by keyword or account, or an account's follower counts with the change since the last run | $0.73 |
| [WeChat Article Scraper](https://apify.com/kizukidata/wechat-article-reader) | a WeChat Official Account article: title, account, author, publish time, the Original mark, full text, Markdown and image URLs | $1.60 |

### Japan and Korea

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [note.com Scraper](https://apify.com/kizukidata/note-articles-feed) | a note.com article: title, likes, comments, hashtags, paid price | $1.21 |
| [Naver Blog Scraper](https://apify.com/kizukidata/naver-blog-feed) | a public Naver Blog post: title, publish time, Korean body text, original-size images, tags, comment and sympathy counts | $0.40 |

### Ads and sponsors

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [TikTok Ads Library Scraper](https://apify.com/kizukidata/tiktok-ads-monitor) | an ad in the EU TikTok Ad Library, marked NEW, ACTIVE, SCALING or STOPPED against your previous run | $0.33 |
| [TikTok Creative Center Scraper](https://apify.com/kizukidata/tiktok-creative-trends) | a top-performing TikTok ad or trending hashtag across 73 countries, with rank changes | $0.64 |
| [Google Ads Transparency Scraper](https://apify.com/kizukidata/google-ads-transparency-scraper) | a Google Ads Transparency Center creative with advertiser, format, copy, regions and EEA/US reach | $0.95 |
| [Podcast Sponsors](https://apify.com/kizukidata/podcast-sponsors) | a sponsor named in a podcast episode's show notes: name, domain, promo code, the evidence line | $3.20 |

### E-commerce and AI agents

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [UCP Profile Checker](https://apify.com/kizukidata/ucp-readiness) | an online store checked for a Universal Commerce Protocol (UCP) profile: version, capabilities, payment handlers, MCP endpoint, changes since the last run | $2.00 per 1,000 stores with a profile; other rows free |

### For LLMs and RAG

| Actor | One row is | Per 1,000 rows |
|---|---|---|
| [PDF to Markdown Extractor](https://apify.com/kizukidata/pdf-to-markdown) | a PDF as page-numbered Markdown (`## Page N`) | $1.60 |
| [URL to Markdown](https://apify.com/kizukidata/url-to-markdown) | a page's main content as Markdown, menus and footers dropped | $0.33 |
| [MCP Server Registry Scraper](https://apify.com/kizukidata/mcp-server-directory) | a public MCP server merged from the MCP Registry, Smithery and awesome-mcp-servers: repository, package, transport, version, new or removed | $0.36 |

Each Actor's page on Apify Store has its input fields, its output fields and its price. A scan without a text layer, a page that needs JavaScript, a blocked job page and an unknown channel are all reported with the reason and cost nothing per item.

<!-- Add newly published Actors here, one row each, same table shape. -->

## For AI agents (MCP)

Bundles are listed in the official MCP Registry. Any client that accepts a remote MCP URL works: Claude Desktop, Claude Code, Cursor, VS Code. On the first connection your browser opens so you can sign in to Apify.

| Bundle | Actors in it | URL |
|---|---|---|
| Company Signals | `website-tech-stack-detector`, `website-contact-intelligence`, `workday-jobs-scraper`, `youtube-creator-contact-scraper`, `google-ads-transparency-scraper` | `https://mcp.apify.com?tools=kizukidata/website-tech-stack-detector,kizukidata/website-contact-intelligence,kizukidata/workday-jobs-scraper,kizukidata/youtube-creator-contact-scraper,kizukidata/google-ads-transparency-scraper` |
| Social Video Intel | `instagram-reels-transcript`, `instagram-post-reel-details`, `youtube-shorts-search`, `youtube-comments-scraper`, `threads-scraper` | `https://mcp.apify.com?tools=kizukidata/instagram-reels-transcript,kizukidata/instagram-post-reel-details,kizukidata/youtube-shorts-search,kizukidata/youtube-comments-scraper,kizukidata/threads-scraper` |
| Hiring Signals | `linkedin-jobs-feed`, `linkedin-company-monitor`, `ats-jobs` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/linkedin-jobs-feed,kizukidata/linkedin-company-monitor,kizukidata/ats-jobs` |
| News Monitoring | `google-news-feed`, `youtube-channel-monitor`, `telegram-channel-feed` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/google-news-feed,kizukidata/youtube-channel-monitor,kizukidata/telegram-channel-feed` |
| RAG Ingest | `youtube-transcripts`, `pdf-to-markdown`, `url-to-markdown` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/youtube-transcripts,kizukidata/pdf-to-markdown,kizukidata/url-to-markdown` |
| EU Tenders | `eu-tenders` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/eu-tenders` |
| Social Monitoring | `bluesky-monitor`, `telegram-channel-feed`, `note-articles-feed`, `wechat-article-reader`, `naver-blog-feed` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/bluesky-monitor,kizukidata/telegram-channel-feed,kizukidata/note-articles-feed,kizukidata/wechat-article-reader,kizukidata/naver-blog-feed` |
| Work Visa Data | `uk-visa-sponsor-jobs`, `canada-lmia-employers` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/uk-visa-sponsor-jobs,kizukidata/canada-lmia-employers` |
| MCP Server Directory | `mcp-server-directory` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/mcp-server-directory` |
| UCP Profile Checker | `ucp-readiness` | `https://mcp.apify.com?tools=fetch-actor-details,kizukidata/ucp-readiness` |

For one Actor: `https://mcp.apify.com?tools=kizukidata/url-to-markdown`.

Registry names: `io.github.kizukidata/company-signals`, `io.github.kizukidata/social-video-intel`, `io.github.kizukidata/hiring-signals`, `io.github.kizukidata/news-monitoring`, `io.github.kizukidata/rag-ingest`, `io.github.kizukidata/eu-tenders`, `io.github.kizukidata/social-monitoring`, `io.github.kizukidata/work-visa-data`, `io.github.kizukidata/mcp-server-directory`, `io.github.kizukidata/ucp-readiness`.

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

- Kizuki は Apify Store で公開データを 1 行 1 件の表にする Actor を 36 本公開しています。用途ごとに、採用とビザ（LinkedIn・ATS・Workday・UK ビザ・カナダ LMIA）、企業データ・連絡先・技術構成（Website Tech Stack・Website Contact・Google Maps Contact・YouTube クリエイター連絡先）、公共入札（EU TED）、YouTube（チャンネル・コメント・プレイリスト・Shorts・字幕）、SNS とニュース（Instagram・Threads・Reddit・Google News・Telegram・Bluesky・WeChat）、日本と韓国（note・Naver Blog）、広告とスポンサー（TikTok・Google Ads・ポッドキャスト）、EC と AI エージェント（UCP）、LLM 向け（PDF・Web・MCP サーバー一覧）に分けています。
- 課金は返した行の数で決まります（表は Free の段の 1,000 行あたり、2026-11-19 の時点。上の段のプランほど 1 行の値段は下がります。技術構成・連絡先・UCP の確かめは該当データが見つかった行だけが対象です）。入力を処理して 0 件だったときは 1 件あたりの課金はありません。失敗も 1 件あたりの課金はありません。走らせるたびに Apify の起動料（1 GB ごとに USD 0.00005、1 GB 未満でも 1 回分。既定のメモリは各 Actor の頁）がかかります。
- MCP のまとめを公式の MCP Registry に置いています。`https://mcp.apify.com?tools=...` の形で、使う Actor だけを AI エージェントに読み込ませられます。
- 非公式です。Apify・LinkedIn・Workday・Google・YouTube・Meta・Instagram・Threads・Reddit・Telegram・Bluesky・TikTok・note・Naver・Tencent・UCP のプロジェクト・MCP のプロジェクト・Smithery・awesome-mcp-servers の管理者、そのほかデータを読む先のサイトや公的機関とは関係なく、承認も受けていません。
- 使い方の例（curl・Python・JavaScript・MCP・n8n）は kizukidata/examples にあります（MIT）。
