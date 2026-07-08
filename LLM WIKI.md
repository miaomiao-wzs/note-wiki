A pattern for building personal knowledge bases using LLMs.

This is an idea file, it is designed to be copy pasted to your own LLM Agent (e.g. OpenAI Codex, Claude Code, OpenCode / Pi, or etc.). Its goal is to communicate the high level idea, but your agent will build out the specifics in collaboration with you.

## The core idea

Most people's experience with LLMs and documents looks like RAG: you upload a collection of files, the LLM retrieves relevant chunks at query time, and generates an answer. This works, but the LLM is rediscovering knowledge from scratch on every question. There's no accumulation. Ask a subtle question that requires synthesizing five documents, and the LLM has to find and piece together the relevant fragments every time. Nothing is built up. NotebookLM, ChatGPT file uploads, and most RAG systems work this way.

The idea here is different. Instead of just retrieving from raw documents at query time, the LLM **incrementally builds and maintains a persistent wiki** — a structured, interlinked collection of markdown files that sits between you and the raw sources. When you add a new source, the LLM doesn't just index it for later retrieval. It reads it, extracts the key information, and integrates it into the existing wiki — updating entity pages, revising topic summaries, noting where new data contradicts old claims, strengthening or challenging the evolving synthesis. The knowledge is compiled once and then *kept current*, not re-derived on every query.

This is the key difference: **the wiki is a persistent, compounding artifact.** The cross-references are already there. The contradictions have already been flagged. The synthesis already reflects everything you've read. The wiki keeps getting richer with every source you add and every question you ask.

You never (or rarely) write the wiki yourself — the LLM writes and maintains all of it. You're in charge of sourcing, exploration, and asking the right questions. The LLM does all the grunt work — the summarizing, cross-referencing, filing, and bookkeeping that makes a knowledge base actually useful over time. In practice, I have the LLM agent open on one side and Obsidian open on the other. The LLM makes edits based on our conversation, and I browse the results in real time — following links, checking the graph view, reading the updated pages. Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase.

This can apply to a lot of different contexts. A few examples:

- **Personal**: tracking your own goals, health, psychology, self-improvement — filing journal entries, articles, podcast notes, and building up a structured picture of yourself over time.
- **Research**: going deep on a topic over weeks or months — reading papers, articles, reports, and incrementally building a comprehensive wiki with an evolving thesis.
- **Reading a book**: filing each chapter as you go, building out pages for characters, themes, plot threads, and how they connect. By the end you have a rich companion wiki. Think of fan wikis like [Tolkien Gateway](https://tolkiengateway.net/wiki/Main_Page) — thousands of interlinked pages covering characters, places, events, languages, built by a community of volunteers over years. You could build something like that personally as you read, with the LLM doing all the cross-referencing and maintenance.
- **Business/team**: an internal wiki maintained by LLMs, fed by Slack threads, meeting transcripts, project documents, customer calls. Possibly with humans in the loop reviewing updates. The wiki stays current because the LLM does the maintenance that no one on the team wants to do.
- **Competitive analysis, due diligence, trip planning, course notes, hobby deep-dives** — anything where you're accumulating knowledge over time and want it organized rather than scattered.

## Architecture

There are three layers:

**Raw sources** — your curated collection of source documents. Articles, papers, images, data files. These are immutable — the LLM reads from them but never modifies them. This is your source of truth.

**The wiki** — a directory of LLM-generated markdown files. Summaries, entity pages, concept pages, comparisons, an overview, a synthesis. The LLM owns this layer entirely. It creates pages, updates them when new sources arrive, maintains cross-references, and keeps everything consistent. You read it; the LLM writes it.

**The schema** — a document (e.g. CLAUDE.md for Claude Code or AGENTS.md for Codex) that tells the LLM how the wiki is structured, what the conventions are, and what workflows to follow when ingesting sources, answering questions, or maintaining the wiki. This is the key configuration file — it's what makes the LLM a disciplined wiki maintainer rather than a generic chatbot. You and the LLM co-evolve this over time as you figure out what works for your domain.

## Operations

**Ingest.** You drop a new source into the raw collection and tell the LLM to process it. An example flow: the LLM reads the source, discusses key takeaways with you, writes a summary page in the wiki, updates the index, updates relevant entity and concept pages across the wiki, and appends an entry to the log. A single source might touch 10-15 wiki pages. Personally I prefer to ingest sources one at a time and stay involved — I read the summaries, check the updates, and guide the LLM on what to emphasize. But you could also batch-ingest many sources at once with less supervision. It's up to you to develop the workflow that fits your style and document it in the schema for future sessions.

**Query.** You ask questions against the wiki. The LLM searches for relevant pages, reads them, and synthesizes an answer with citations. Answers can take different forms depending on the question — a markdown page, a comparison table, a slide deck (Marp), a chart (matplotlib), a canvas. The important insight: **good answers can be filed back into the wiki as new pages.** A comparison you asked for, an analysis, a connection you discovered — these are valuable and shouldn't disappear into chat history. This way your explorations compound in the knowledge base just like ingested sources do.

**Lint.** Periodically, ask the LLM to health-check the wiki. Look for: contradictions between pages, stale claims that newer sources have superseded, orphan pages with no inbound links, important concepts mentioned but lacking their own page, missing cross-references, data gaps that could be filled with a web search. The LLM is good at suggesting new questions to investigate and new sources to look for. This keeps the wiki healthy as it grows.

## Indexing and logging

Two special files help the LLM (and you) navigate the wiki as it grows. They serve different purposes:

**index.md** is content-oriented. It's a catalog of everything in the wiki — each page listed with a link, a one-line summary, and optionally metadata like date or source count. Organized by category (entities, concepts, sources, etc.). The LLM updates it on every ingest. When answering a query, the LLM reads the index first to find relevant pages, then drills into them. This works surprisingly well at moderate scale (~100 sources, ~hundreds of pages) and avoids the need for embedding-based RAG infrastructure.

**log.md** is chronological. It's an append-only record of what happened and when — ingests, queries, lint passes. A useful tip: if each entry starts with a consistent prefix (e.g. `## [2026-04-02] ingest | Article Title`), the log becomes parseable with simple unix tools — `grep "^## \[" log.md | tail -5` gives you the last 5 entries. The log gives you a timeline of the wiki's evolution and helps the LLM understand what's been done recently.

## Optional: CLI tools

At some point you may want to build small tools that help the LLM operate on the wiki more efficiently. A search engine over the wiki pages is the most obvious one — at small scale the index file is enough, but as the wiki grows you want proper search. [qmd](https://github.com/tobi/qmd) is a good option: it's a local search engine for markdown files with hybrid BM25/vector search and LLM re-ranking, all on-device. It has both a CLI (so the LLM can shell out to it) and an MCP server (so the LLM can use it as a native tool). You could also build something simpler yourself — the LLM can help you vibe-code a naive search script as the need arises.

## Tips and tricks

- **Obsidian Web Clipper** is a browser extension that converts web articles to markdown. Very useful for quickly getting sources into your raw collection.
- **Download images locally.** In Obsidian Settings → Files and links, set "Attachment folder path" to a fixed directory (e.g. `raw/assets/`). Then in Settings → Hotkeys, search for "Download" to find "Download attachments for current file" and bind it to a hotkey (e.g. Ctrl+Shift+D). After clipping an article, hit the hotkey and all images get downloaded to local disk. This is optional but useful — it lets the LLM view and reference images directly instead of relying on URLs that may break. Note that LLMs can't natively read markdown with inline images in one pass — the workaround is to have the LLM read the text first, then view some or all of the referenced images separately to gain additional context. It's a bit clunky but works well enough.
- **Obsidian's graph view** is the best way to see the shape of your wiki — what's connected to what, which pages are hubs, which are orphans.
- **Marp** is a markdown-based slide deck format. Obsidian has a plugin for it. Useful for generating presentations directly from wiki content.
- **Dataview** is an Obsidian plugin that runs queries over page frontmatter. If your LLM adds YAML frontmatter to wiki pages (tags, dates, source counts), Dataview can generate dynamic tables and lists.
- The wiki is just a git repo of markdown files. You get version history, branching, and collaboration for free.

## Why this works

The tedious part of maintaining a knowledge base is not the reading or the thinking — it's the bookkeeping. Updating cross-references, keeping summaries current, noting when new data contradicts old claims, maintaining consistency across dozens of pages. Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass. The wiki stays maintained because the cost of maintenance is near zero.

The human's job is to curate sources, direct the analysis, ask good questions, and think about what it all means. The LLM's job is everything else.

The idea is related in spirit to Vannevar Bush's Memex (1945) — a personal, curated knowledge store with associative trails between documents. Bush's vision was closer to this than to what the web became: private, actively curated, with the connections between documents as valuable as the documents themselves. The part he couldn't solve was who does the maintenance. The LLM handles that.


## Note

This document is intentionally abstract. It describes the idea, not a specific implementation. The exact directory structure, the schema conventions, the page formats, the tooling — all of that will depend on your domain, your preferences, and your LLM of choice. Everything mentioned above is optional and modular — pick what's useful, ignore what isn't. For example: your sources might be text-only, so you don't need image handling at all. Your wiki might be small enough that the index file is all you need, no search engine required. You might not care about slide decks and just want markdown pages. You might want a completely different set of output formats. The right way to use this is to share it with your LLM agent and work together to instantiate a version that fits your needs. The document's only job is to communicate the pattern. Your LLM can figure out the rest.


# LLM Wiki

一种利用大语言模型构建个人知识库的模式。

这是一个“想法文件”，设计初衷是让你将其复制粘贴到自己的 LLM 智能体（例如 OpenAI Codex、Claude Code、OpenCode / Pi 等）中使用。它的目标是传达高层次的想法，但具体的实现细节将由你的智能体与你协作完成。

## 核心理念

大多数人使用 LLM 处理文档的体验类似于 RAG（检索增强生成）：你上传一堆文件，LLM 在查询时检索相关片段，然后生成答案。这确实管用，但 LLM 每次都在从头重新发现知识，没有积累。当你问一个需要综合五份文档的微妙问题时，LLM 每次都不得不重新找到并拼凑相关片段——什么都没有沉淀下来。NotebookLM、ChatGPT 的文件上传功能，以及大多数 RAG 系统都是这样工作的。

这里的思路则不同。LLM 不再只是在查询时从原始文档中检索，而是 **增量式地构建并维护一个持久化的 wiki**——一个结构化的、相互链接的 Markdown 文件集合，位于你和原始资料之间。当你添加新资料时，LLM 不只是将其索引以供后续检索；它会阅读资料，提取关键信息，并将其整合到现有的 wiki 中——更新实体页面、修订主题摘要、记录新数据与旧主张之间的矛盾之处，强化或挑战正在演进的综合观点。知识被编译一次，然后_持续保持更新_，而不是每次查询时重新推导。

这就是关键差异：**wiki 是一个持久化、可复利增长的产物**。交叉引用已经在那里了；矛盾之处已经被标记了；综合观点已经反映了你读过的所有内容。每添加一份资料、每提出一个问题，wiki 都会变得更丰富。

你从不（或很少）亲自编写 wiki——LLM 负责编写和维护所有内容。你负责搜集资料、探索性工作和提出正确的问题；LLM 承担所有繁琐工作——摘要、交叉引用、归档和记账，这些才让知识库随时间推移真正有用。在实践中，我让 LLM 智能体在一侧打开，Obsidian 在另一侧打开。LLM 根据我们的对话进行编辑，我实时浏览结果——跟随链接、查看图谱视图、阅读更新后的页面。Obsidian 是 IDE，LLM 是程序员，wiki 是代码库。

这可以应用于许多不同场景。举几个例子：

- **个人**：追踪自己的目标、健康、心理、自我提升——整理日记、文章、播客笔记，随着时间推移构建出一幅关于自己的结构化图景。
    
- **研究**：在数周或数月内深入某个主题——阅读论文、文章、报告，增量构建一个包含不断演进论点的综合性 wiki。
    
- **阅读一本书**：每读一章就归档一章，为人物、主题、情节线索及其联系建立页面。读完后你就拥有一个丰富的伴读 wiki。想想那些粉丝维基，比如 [Tolkien Gateway](https://tolkiengateway.net/wiki/Main_Page)——成千上万个互相链接的页面，涵盖人物、地点、事件、语言，由志愿者社区历时多年建成。你在阅读时也可以个人建出类似的东西，而所有交叉引用和维护工作都由 LLM 完成。
    
- **商业/团队**：由 LLM 维护的内部 wiki，输入来源包括 Slack 讨论串、会议记录、项目文档、客户电话。可能有人类在流程中审查更新。wiki 保持最新，因为维护工作由 LLM 来做，而团队里没人愿意做这种事。
    
- **竞争分析、尽职调查、旅行规划、课程笔记、兴趣深潜**——任何需要随时间积累知识并希望有条理而非散落一地的场景。
    

## 架构

共有三层：

**原始资料**——你精心收集的源文档。文章、论文、图片、数据文件。这些是不可变的——LLM 从中读取，但从不修改它们。这是你的“事实来源”。

**Wiki**——一个由 LLM 生成的 Markdown 文件目录。包括摘要、实体页面、概念页面、比较、概述、综合观点。LLM 完全拥有这一层。它创建页面，在新资料到达时更新它们，维护交叉引用，并保持一切一致。你阅读它；LLM 编写它。

**模式（Schema）**——一个文档（例如 Claude Code 的 CLAUDE.md 或 Codex 的 AGENTS.md），它告诉 LLM wiki 的结构是什么、有哪些约定、在摄取资料、回答问题或维护 wiki 时应遵循哪些工作流程。这是关键的配置文件——它让 LLM 成为一个遵守纪律的 wiki 维护者，而不是一个泛泛的聊天机器人。你和 LLM 会随着时间推移，在摸索出适合你领域的方法后，共同演进这个文件。

## 操作

**摄取（Ingest）**。你将一份新资料放入原始资料集，并告诉 LLM 处理它。一个示例流程：LLM 读取资料，与你讨论关键收获，在 wiki 中编写一个摘要页面，更新索引，更新 wiki 中相关的实体和概念页面，并在日志中追加一条记录。一份资料可能触及 10–15 个 wiki 页面。我个人喜欢每次只摄取一份资料并保持参与——我会阅读摘要、检查更新，并引导 LLM 强调哪些内容。但你也可以同时批量摄取多份资料，减少监督。你可以自行开发适合自己风格的工作流程，并将其记录在模式中，以供未来会话使用。

**查询（Query）**。你向 wiki 提问。LLM 搜索相关页面，阅读它们，并综合生成带有引用的答案。答案可以根据问题采用不同形式——Markdown 页面、对比表格、幻灯片（Marp）、图表（matplotlib）、画布。一个重要洞见是：**好的答案可以归档回 wiki 中，成为新页面**。你要求做的对比、分析，或你发现的联系——这些都有价值，不应消失在聊天记录中。这样一来，你的探索性工作也会像摄取的资料一样，在知识库中复利增长。

**检查（Lint）**。定期让 LLM 对 wiki 进行健康检查。检查：页面之间的矛盾、被新资料取代的陈旧主张、没有入链的孤立页面、被提及但缺少独立页面的重要概念、缺失的交叉引用、可通过网络搜索填补的数据空白。LLM 擅长提出需要进一步调查的新问题和需要寻找的新资料。这能确保 wiki 随着增长保持健康。

## 索引与日志

两个特殊文件帮助 LLM（以及你）在 wiki 增长时导航。它们用途不同：

**index.md** 是面向内容的。它是 wiki 中所有内容的目录——每个页面都列有链接、一行摘要，以及可选的元数据（如日期或来源数量）。按类别组织（实体、概念、来源等）。LLM 在每次摄取后都会更新它。当回答查询时，LLM 首先读取索引来找到相关页面，然后深入阅读它们。这在中等规模（约 100 个来源，数百个页面）下效果出奇地好，并且避免了基于嵌入的 RAG 基础设施。

**log.md** 是按时间顺序的。它是一个只追加的记录，记录发生了什么以及何时发生——摄取、查询、检查。一个有用的小技巧：如果每条记录都以一致的前缀开头（例如 `## [2026-04-02] ingest | 文章标题`），日志就可以用简单的 Unix 工具解析——`grep "^## \[" log.md | tail -5` 就能得到最后 5 条记录。日志提供了 wiki 演进的时间线，并帮助 LLM 理解最近完成了哪些工作。

## 可选：CLI 工具

在某个时刻，你可能会想构建一些小工具，帮助 LLM 更高效地操作 wiki。对 wiki 页面进行搜索是最明显的需求——在规模较小时，索引文件就足够了，但随着 wiki 增长，你会需要真正的搜索功能。[qmd](https://github.com/tobi/qmd) 是一个不错的选择：它是一个针对 Markdown 文件的本地搜索引擎，具有混合 BM25/向量搜索和 LLM 重排序功能，且全部在本地运行。它既有 CLI（因此 LLM 可以调用它），也有 MCP 服务器（因此 LLM 可以将其作为原生工具使用）。你也可以自己构建更简单的方案——LLM 可以在需要时帮你“氛围编程”出一个简单的搜索脚本。

## 技巧与窍门

- **Obsidian Web Clipper** 是一个浏览器扩展，可将网页文章转换为 Markdown。对于快速将来源放入原始资料集非常有用。
    
- **在本地下载图片**。在 Obsidian 设置 → 文件和链接中，将“附件文件夹路径”设置为固定目录（例如 `raw/assets/`）。然后在设置 → 快捷键中，搜索“Download”找到“为当前文件下载附件”并绑定快捷键（例如 Ctrl+Shift+D）。裁剪文章后，按下快捷键，所有图片都会下载到本地磁盘。这是可选的，但很有用——它让 LLM 可以直接查看和引用图片，而不依赖可能失效的 URL。注意，LLM 不能原生地一次性读取带有内联图片的 Markdown——变通方法是让 LLM 先阅读文本，然后单独查看部分或全部引用的图片以获取额外上下文。这有点笨拙，但效果还不错。
    
- **Obsidian 的图谱视图**是查看 wiki 形态的最佳方式——什么连接了什么，哪些页面是枢纽，哪些是孤岛。
    
- **Marp** 是一种基于 Markdown 的幻灯片格式。Obsidian 有对应的插件。对于直接从 wiki 内容生成演示文稿很有用。
    
- **Dataview** 是一个 Obsidian 插件，可以对页面 frontmatter 运行查询。如果你的 LLM 在 wiki 页面中添加 YAML frontmatter（标签、日期、来源数量），Dataview 可以生成动态表格和列表。
    
- wiki 本质上就是一个 Markdown 文件的 git 仓库。你可以免费获得版本历史、分支和协作功能。
    

## 为什么这能奏效

维护知识库最繁琐的部分不是阅读或思考，而是“记账”——更新交叉引用、保持摘要最新、记录新数据与旧主张的矛盾、在数十个页面间保持一致性。人们放弃 wiki，是因为维护负担的增长速度快于其带来的价值。LLM 不会厌倦，不会忘记更新交叉引用，并且可以一次性处理 15 个文件。wiki 得以保持维护，因为维护成本几乎为零。

人类的工作是筛选资料、指导分析方向、提出好问题、思考这一切意味着什么。LLM 的工作是其他所有事。

这个想法在精神上与 Vannevar Bush 的 Memex（1945 年）有关联——一个私人的、精心策划的知识库，文档之间具有关联路径。Bush 的愿景比后来互联网实际变成的样子更接近这个想法：私密的、主动策划的，并且文档之间的联系与文档本身一样有价值。他无法解决的部分是“谁来维护”。而 LLM 恰好处理了这一点。

## 注记

本文档有意保持抽象。它描述的是想法，而非具体实现。确切的目录结构、模式约定、页面格式、工具——所有这些都取决于你的领域、你的偏好以及你选择的 LLM。上面提到的所有内容都是可选的、模块化的——选择有用的，忽略不需要的。例如：你的资料可能纯文本，那你根本不需要图片处理；你的 wiki 可能足够小，索引文件就够用，无需搜索引擎；你可能不关心幻灯片，只想要 Markdown 页面；你可能想要一套完全不同的输出格式。正确的使用方式是，将本文档分享给你的 LLM 智能体，然后一起协作，实例化一个适合你需求的版本。本文档的唯一任务就是传达模式。你的 LLM 能搞定其余部分。