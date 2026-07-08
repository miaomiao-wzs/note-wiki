# 日志条目模板补充 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 为 `wiki/log.md` 补充一个统一的日志条目模板，让维护日志可以同时记录 raw 整理和 wiki 维护动作，并保持中文、可检索、格式统一。

**Architecture:** 新增一个专门的日志模板页，作为日志条目的标准写法说明；同时在索引页和规范文件里补上入口与用途说明。日志本身继续保持 append-only，只增加模板说明，不改变已有记录结构。

**Tech Stack:** Markdown, Obsidian, YAML frontmatter, Git.

## Global Constraints

- `raw/` 存放原始资料，只做归档与读取，不在这里整理总结。
- `wiki/` 存放 LLM 维护的知识页面。
- `wiki/index.md`、`wiki/log.md`、`wiki/overview.md` 是全局入口文件。
- `wiki/shared/` 用于跨模块通用内容。
- 页面建议使用最小 frontmatter：`module`、`kind`、`updated`、`source_count`、`tags`。
- 所有页面正文使用中文；路径、模块码、frontmatter 字段名保留技术英文。
- `wiki/templates/source.md`、`wiki/templates/module-overview.md`、`wiki/templates/entity.md`、`wiki/templates/concept.md`、`wiki/templates/comparison.md`、`wiki/templates/synthesis.md`、`wiki/templates/linking.md` 都已存在并可继续引用。

---

### Task 1: Create the log-entry template

**Files:**
- Create: `wiki/templates/log-entry.md`

**Interfaces:**
- Consumes: 现有的 `wiki/log.md` 写法、知识库维护流程、中文化文档约定。
- Produces: 一个可复用的日志条目模板，后续在 `wiki/log.md` 中记录维护动作时可直接套用。

- [ ] **Step 1: Write the template file**

Create `wiki/templates/log-entry.md` with the following exact content:

```markdown
---
module: shared
kind: template
updated: 2026-07-07
source_count: 0
tags: [template]
---

# 日志条目模板

这个模板用于 `wiki/log.md` 里的单条维护记录。

## 适用场景

- 整理原始资料
- 新增 wiki 来源页
- 新增实体页、概念页、对比页、综合页
- 调整规范、模板或链接规则

## 模板内容

```markdown
## 2026-07-07 | 整理 raw | FICO
- 主题：采购发票处理流程
- 来源：`raw/fico/article/202607/采购发票处理流程.pdf`
- 做了什么：整理成来源页并补充相关实体链接
- 结果：新增 `wiki/fico/sources/采购发票处理流程.md`
- 后续：需要补充 `wiki/fico/concepts/采购发票处理流程`
```

## 书写规则

- 日期使用 `YYYY-MM-DD`。
- 标题结构统一为：`## 日期 | 动作 | 模块`。
- 动作用简短中文短语，例如：`整理 raw`、`新增来源页`、`更新概念页`、`补充模板`。
- 每条记录尽量包含：主题、来源或目标路径、做了什么、结果、后续。
- 一条日志只记一件事，避免把多件不同类型的动作混在一起。
- 如果同一天有多条动作，按时间顺序继续往下追加即可。
```

- [ ] **Step 2: Verify the file content**

Run:
```bash
grep -n "日志条目模板\|## 2026-07-07 | 整理 raw | FICO\|wiki/log.md\|动作\|后续" wiki/templates/log-entry.md
```
Expected: matching lines for the title, sample entry, and rules.

### Task 2: Expose the template in the vault entry points

**Files:**
- Modify: `wiki/index.md`
- Modify: `wiki/log.md`
- Modify: `CLAUDE.md`

**Interfaces:**
- Consumes: `wiki/templates/log-entry.md` from Task 1.
- Produces: Index and rules that tell future sessions where to find and how to use the log-entry template.

- [ ] **Step 1: Update the index page**

Update `wiki/index.md` to include this new bullet alongside the existing template links:

```markdown
- `[[wiki/templates/log-entry]]`：日志条目模板
```

- [ ] **Step 2: Update the log page guidance**

Add a short section to `wiki/log.md` that explains the log format and points to the template. Use this exact text under the existing log entries:

```markdown
## 记录方式

- 单条记录建议使用 `[[wiki/templates/log-entry]]` 的格式。
- 标题使用 `## 日期 | 动作 | 模块`。
- 日志继续采用追加式写法，不回头重排历史记录。
```

- [ ] **Step 3: Update the project rules**

Add a short note to `CLAUDE.md` in the running-constraints section stating that `wiki/log.md` uses the log-entry template and is append-only.

- [ ] **Step 4: Verify all references**

Run:
```bash
grep -n "wiki/templates/log-entry.md\|wiki/templates/log-entry\|记录方式\|append-only\|追加式" CLAUDE.md wiki/index.md wiki/log.md
```
Expected: all three files reference the new log-entry template and its append-only rule.

- [ ] **Step 5: Commit**

```bash
git add wiki/templates/log-entry.md wiki/index.md wiki/log.md CLAUDE.md
 git commit -m "docs: add log entry template"
```

### Task 3: Final self-check and handoff

**Files:**
- Modify: `docs/superpowers/plans/2026-07-07-log-entry-template.md`

**Interfaces:**
- Consumes: Tasks 1-2 outputs.
- Produces: A completed plan ready for implementation.

- [ ] **Step 1: Check for placeholders**

Confirm the plan has no vague steps like `TBD`, `TODO`, or `fill in details`.

- [ ] **Step 2: Check scope**

Confirm the plan only touches the log template, index, log page guidance, and project rules.

- [ ] **Step 3: Hand off for implementation**

After user approval, execute with `superpowers:subagent-driven-development` or `superpowers:executing-plans`.
