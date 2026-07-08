# FICO Markdown 原始资料第一轮整理 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 按 LLM WIKI 思想，先整理 `raw/fico/article/202607/` 下 4 个 Markdown 原始资料，建立来源页、必要实体页/概念页、资料清单和日志。

**Architecture:** 原始文件保持不动；在 `wiki/fico/sources/` 建立每篇资料的来源页，在 `wiki/fico/entities/` 和 `wiki/fico/concepts/` 中只创建原文明确支撑的页面；同步更新 `wiki/index.md`、`wiki/fico/overview.md` 和 `wiki/log.md`。

**Tech Stack:** Markdown, Obsidian wiki-links, YAML frontmatter.

## Global Constraints

- 不修改 `raw/` 中原始资料内容。
- 只处理以下 4 个文件：
  - `raw/fico/article/202607/ABAW 资产减值准备.md`
  - `raw/fico/article/202607/CO 分摊分配配置说明.md`
  - `raw/fico/article/202607/OKB9 成本要素默认成本中心配置.md`
  - `raw/fico/article/202607/主营业务成本科目是否勾选成本要素.md`
- 暂不处理 `.docx`、`.pdf`、`.xlsx`。
- 所有新增 wiki 页面正文使用中文。
- 页面使用最小 frontmatter：`module`、`kind`、`updated`、`source_count`、`tags`。
- 发现不确定内容时写“不确定”，不硬造。

---

### Task 1: 读取并理解 4 个 Markdown 原始资料

**Files:**
- Read: `raw/fico/article/202607/ABAW 资产减值准备.md`
- Read: `raw/fico/article/202607/CO 分摊分配配置说明.md`
- Read: `raw/fico/article/202607/OKB9 成本要素默认成本中心配置.md`
- Read: `raw/fico/article/202607/主营业务成本科目是否勾选成本要素.md`

**Interfaces:**
- Consumes: 4 个 Markdown 原始资料。
- Produces: 可用于创建来源页、实体页、概念页的事实要点。

- [ ] **Step 1: Read all four files**
- [ ] **Step 2: Identify source summaries**
- [ ] **Step 3: Identify explicit entities and concepts**

### Task 2: 创建 FICO raw 资料清单

**Files:**
- Create: `wiki/fico/sources/raw资料清单.md`

**Interfaces:**
- Consumes: 当前 raw 文件清单。
- Produces: 一页记录 raw/FICO 当前资料状态的索引页。

- [ ] **Step 1: Create raw source inventory page**
- [ ] **Step 2: Mark 4 Markdown files as first-round processed candidates**

### Task 3: 创建 4 个来源页

**Files:**
- Create: `wiki/fico/sources/ABAW 资产减值准备.md`
- Create: `wiki/fico/sources/CO 分摊分配配置说明.md`
- Create: `wiki/fico/sources/OKB9 成本要素默认成本中心配置.md`
- Create: `wiki/fico/sources/主营业务成本科目是否勾选成本要素.md`

**Interfaces:**
- Consumes: Task 1 读取结果。
- Produces: 每篇原始资料对应的 wiki 来源页。

- [ ] **Step 1: Create each source page from the source template**
- [ ] **Step 2: Include raw path, key takeaways, related entities, related concepts, and follow-up actions**

### Task 4: 创建必要实体页和概念页

**Files:**
- Create only when supported by source content:
  - `wiki/fico/entities/ABAW.md`
  - `wiki/fico/entities/OKB9.md`
  - `wiki/fico/concepts/资产减值准备.md`
  - `wiki/fico/concepts/CO 分摊分配.md`
  - `wiki/fico/concepts/成本要素默认成本中心.md`
  - `wiki/fico/concepts/主营业务成本科目与成本要素.md`

**Interfaces:**
- Consumes: Task 3 来源页。
- Produces: 初步实体页与概念页。

- [ ] **Step 1: Create pages only for explicitly supported topics**
- [ ] **Step 2: Add backlinks to the relevant source pages**

### Task 5: 更新入口与日志

**Files:**
- Modify: `wiki/index.md`
- Modify: `wiki/fico/overview.md`
- Modify: `wiki/log.md`

**Interfaces:**
- Consumes: Tasks 2-4 output pages。
- Produces: 可从入口找到第一轮整理成果，并记录本次维护动作。

- [ ] **Step 1: Add first-round FICO source links to relevant indexes**
- [ ] **Step 2: Append log entry using `wiki/templates/log-entry.md` format**

### Task 6: 验证

**Files:**
- Verify: all files above

**Interfaces:**
- Consumes: Tasks 1-5 outputs。
- Produces: 确认所有新增页面存在，入口链接可检索。

- [ ] **Step 1: Verify files exist**
- [ ] **Step 2: Verify key links and raw paths are present**
- [ ] **Step 3: Report completion**
