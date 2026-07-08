# 知识库初始化方案设计

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 初始化一个适合持续沉淀 SAP/FICO/ABAP 等主题资料的 Obsidian 知识库骨架，分离原始资料层与 LLM 维护层。

**Architecture:** 仓库保留 `raw/` 作为只读原始资料区，按 `主题/类型/年月` 组织；`wiki/` 作为知识沉淀区，按模块镜像完整骨架，统一维护 `entities`、`concepts`、`comparisons`、`sources`、`synthesis` 等目录。根目录的 `CLAUDE.md` 固化知识库维护规范，`wiki/index.md`、`wiki/log.md`、`wiki/overview.md` 提供全局入口与运行记录。

**Tech Stack:** Markdown, Obsidian, YAML frontmatter, Git.

## Global Constraints

- `raw/` 是原始资料层，只做归档与读取，不在这里维护总结或交叉引用。
- `wiki/` 是 LLM 维护层，负责总结、串联、纠错、交叉引用与持续更新。
- raw 目录规则统一为 `raw/<module>/<type>/<YYYYMM>/`。
- wiki 模块目录统一为 `wiki/<module>/{entities,concepts,comparisons,sources,synthesis}/`。
- 当前初始化覆盖 `fico`、`abap` 两个模块，并预留 `mm`、`pp`、`qm` 扩展规则。
- 维护文件采用 Markdown，页面可使用最小 YAML frontmatter 记录 `module`、`kind`、`updated`、`source_count`、`tags`。
- 全局入口文件固定为 `wiki/index.md`、`wiki/log.md`、`wiki/overview.md`。
- 不删除现有 `欢迎.md`，先保留作为可选入口。

---

### Task 1: Write knowledge-base rules

**Files:**
- Modify: `CLAUDE.md`
- Create: `chat_history/`

**Interfaces:**
- Consumes: 用户确认的知识库骨架规则、raw/wiki 分层约定、模块扩展规则。
- Produces: 仓库级维护规范，后续新增资料与 wiki 页面时必须遵守。

- [ ] **Step 1: Write the failing spec check**

No code test exists for this repository-level rule file. Verify manually that the final `CLAUDE.md` includes explicit sections for:
- `raw/<module>/<type>/<YYYYMM>/`
- `wiki/<module>/{entities,concepts,comparisons,sources,synthesis}/`
- `wiki/index.md`
- `wiki/log.md`
- `wiki/overview.md`
- `fico`, `abap`, `mm`, `pp`, `qm`

- [ ] **Step 2: Update the rule file**

Add a concise project-specific section to `CLAUDE.md` with the exact rules above, written in Chinese, and keep it aligned with the existing global instructions.

- [ ] **Step 3: Verify the file content**

Run:
```bash
grep -n "raw/<module>/<type>/<YYYYMM>/\|wiki/<module>/{entities,concepts,comparisons,sources,synthesis}/\|wiki/index.md\|wiki/log.md\|wiki/overview.md\|fico\|abap\|mm\|pp\|qm" CLAUDE.md
```
Expected: matching lines for all key rules.

- [ ] **Step 4: Commit**

```bash
git add CLAUDE.md
 git commit -m "docs: add knowledge base rules"
```

### Task 2: Create the wiki skeleton

**Files:**
- Create: `wiki/index.md`
- Create: `wiki/log.md`
- Create: `wiki/overview.md`
- Create: `wiki/shared/entities/.gitkeep`
- Create: `wiki/shared/concepts/.gitkeep`
- Create: `wiki/shared/comparisons/.gitkeep`
- Create: `wiki/shared/synthesis/.gitkeep`
- Create: `wiki/fico/entities/.gitkeep`
- Create: `wiki/fico/concepts/.gitkeep`
- Create: `wiki/fico/comparisons/.gitkeep`
- Create: `wiki/fico/sources/.gitkeep`
- Create: `wiki/fico/synthesis/.gitkeep`
- Create: `wiki/abap/entities/.gitkeep`
- Create: `wiki/abap/concepts/.gitkeep`
- Create: `wiki/abap/comparisons/.gitkeep`
- Create: `wiki/abap/sources/.gitkeep`
- Create: `wiki/abap/synthesis/.gitkeep`
- Create: `wiki/mm/entities/.gitkeep`
- Create: `wiki/mm/concepts/.gitkeep`
- Create: `wiki/mm/comparisons/.gitkeep`
- Create: `wiki/mm/sources/.gitkeep`
- Create: `wiki/mm/synthesis/.gitkeep`
- Create: `wiki/pp/entities/.gitkeep`
- Create: `wiki/pp/concepts/.gitkeep`
- Create: `wiki/pp/comparisons/.gitkeep`
- Create: `wiki/pp/sources/.gitkeep`
- Create: `wiki/pp/synthesis/.gitkeep`
- Create: `wiki/qm/entities/.gitkeep`
- Create: `wiki/qm/concepts/.gitkeep`
- Create: `wiki/qm/comparisons/.gitkeep`
- Create: `wiki/qm/sources/.gitkeep`
- Create: `wiki/qm/synthesis/.gitkeep`

**Interfaces:**
- Consumes: Repository rule file from Task 1.
- Produces: Physical directory structure that future ingests will use.

- [ ] **Step 1: Create the empty directory tree**

Create the module directories with `.gitkeep` files so Git preserves the structure. `wiki/shared/` is reserved for cross-module pages that do not belong to one SAP module.

- [ ] **Step 2: Write the global entry pages**

Use the following content for each file:

`wiki/index.md`
```markdown
---
kind: index
updated: 2026-07-06
tags: []
---

# Knowledge Base Index

- `[[overview]]` — how to use this knowledge base
- `[[log]]` — chronological maintenance log
- `[[wiki/fico/]]` — FICO module pages
- `[[wiki/abap/]]` — ABAP module pages
- `[[wiki/mm/]]` — MM module pages
- `[[wiki/pp/]]` — PP module pages
- `[[wiki/qm/]]` — QM module pages
```

`wiki/log.md`
```markdown
---
kind: log
updated: 2026-07-06
tags: []
---

# Maintenance Log

## 2026-07-06
- Initialized the wiki skeleton.
```

`wiki/overview.md`
```markdown
---
kind: overview
updated: 2026-07-06
tags: []
---

# Knowledge Base Overview

This vault follows a persistent wiki pattern:
- `raw/` stores immutable source material.
- `wiki/` stores maintained summaries, entity pages, concept pages, comparisons, and syntheses.
- `CLAUDE.md` defines how future sessions should maintain the structure.
```

- [ ] **Step 3: Verify the directory layout**

Run:
```bash
find wiki -maxdepth 3 -type d | sort
```
Expected: directories for `shared`, `fico`, `abap`, `mm`, `pp`, `qm`, each with the five module subdirectories.

- [ ] **Step 4: Verify the page content**

Run:
```bash
sed -n '1,120p' wiki/index.md && printf '\n---\n' && sed -n '1,120p' wiki/log.md && printf '\n---\n' && sed -n '1,120p' wiki/overview.md
```
Expected: frontmatter and links exactly match the skeleton above.

- [ ] **Step 5: Commit**

```bash
git add wiki
 git commit -m "docs: initialize wiki skeleton"
```

### Task 3: Create the raw intake skeleton

**Files:**
- Create: `raw/fico/article/202607/.gitkeep`
- Create: `raw/fico/pdf/202607/.gitkeep`
- Create: `raw/fico/web/202607/.gitkeep`
- Create: `raw/abap/article/202607/.gitkeep`
- Create: `raw/abap/pdf/202607/.gitkeep`
- Create: `raw/abap/web/202607/.gitkeep`
- Create: `raw/mm/article/202607/.gitkeep`
- Create: `raw/mm/pdf/202607/.gitkeep`
- Create: `raw/mm/web/202607/.gitkeep`
- Create: `raw/pp/article/202607/.gitkeep`
- Create: `raw/pp/pdf/202607/.gitkeep`
- Create: `raw/pp/web/202607/.gitkeep`
- Create: `raw/qm/article/202607/.gitkeep`
- Create: `raw/qm/pdf/202607/.gitkeep`
- Create: `raw/qm/web/202607/.gitkeep`

**Interfaces:**
- Consumes: Module list and raw directory rule from Task 1.
- Produces: Concrete intake folders for first sources under each module.

- [ ] **Step 1: Create the intake directories**

Create the module/type/month directories as empty folders with `.gitkeep` files so they are tracked by Git.

- [ ] **Step 2: Verify the raw layout**

Run:
```bash
find raw -maxdepth 4 -type d | sort
```
Expected: the `fico`, `abap`, `mm`, `pp`, `qm` trees each contain `article`, `pdf`, and `web` with `202607` subdirectories.

- [ ] **Step 3: Commit**

```bash
git add raw
 git commit -m "docs: add raw intake skeleton"
```

### Task 4: Final self-check and handoff

**Files:**
- Modify: `docs/superpowers/plans/2026-07-06-knowledge-base-initialization.md`
- Optional: `欢迎.md` only if you decide later to convert it into a landing page

**Interfaces:**
- Consumes: All prior tasks' outputs.
- Produces: A validated implementation plan and a stable handoff to execution.

- [ ] **Step 1: Review the plan for gaps**

Check that the plan covers every global constraint and that each planned file has a clear responsibility.

- [ ] **Step 2: Remove ambiguity**

Ensure the plan uses one naming convention consistently: lowercase module names, `YYYYMM` buckets, and Markdown frontmatter fields `module`, `kind`, `updated`, `source_count`, `tags`.

- [ ] **Step 3: Hand off for implementation**

After approval, execute with `superpowers:subagent-driven-development` or `superpowers:executing-plans`.
