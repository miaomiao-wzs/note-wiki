# 知识库增量整理与图片补齐实施计划

> **For agentic workers:** 按任务逐项执行；每完成一项都要验证结果，避免覆盖用户现有工作树修改。

**Goal:** 在保持 raw 原始资料不变的前提下，补齐已整理来源页的缺失截图，并同步清单、入口索引和维护日志。

**Architecture:** 以 `raw/assets/` 作为统一附件目录，以已有 `wiki/<module>/sources/` 来源页作为整理边界。先按文件名匹配外部图片并复制缺失附件，再在对应步骤附近加入 Obsidian 图片嵌入，最后修正仅受本轮影响的清单和日志；不重写大型综合资料，不处理缺失原始文件恢复和重复资料合并等未确认事项。

**Tech Stack:** Obsidian Markdown、YAML frontmatter、Obsidian wiki-link/embed、macOS shell、Git diff 检查。

---

### Task 1: 建立图片候选映射

**Files:**
- Read: `wiki/fico/sources/`、`wiki/sd/sources/`、`wiki/abap/sources/`
- Read: `/Users/waterboy/jmkx_work/note/财务/note/images`
- Modify: `raw/assets/`（仅复制实际对应且缺失的附件）

- [ ] 列出优先来源页中的现有图片引用和外部目录中的同名文件。
- [ ] 只复制同名且当前 `raw/assets/` 不存在的图片；不复制无法确认归属的泛化图片。
- [ ] 对带账号、密码、token 或调试信息的截图先跳过，避免进入 wiki。

### Task 2: 补齐 FICO 与 ABAP 来源页

**Files:**
- Modify: `wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司.md`
- Modify: `wiki/fico/sources/生产工单跨月陆续交货TECO重新打开-物料差异结算问题.md`
- Modify: `wiki/fico/sources/ZFIR043维护金税发票与形式发票关系-图片补充.md`
- Modify: `wiki/fico/sources/ABAW 资产减值准备.md`
- Modify: `wiki/fico/sources/OKB9 成本要素默认成本中心配置.md`
- Modify: `wiki/abap/sources/ABAP 异常处理基础与核心概念.md`

- [ ] 在每个页面的对应操作步骤中加入已有截图的 `![[raw/assets/文件名]]` 嵌入。
- [ ] 对找不到附件或原始文件缺失的页面写明现状，不虚构来源或恢复文件。
- [ ] 保留现有 frontmatter 和文字结论，只做必要的图片、来源说明和安全提示补充。

### Task 3: 补齐 SD 操作来源页

**Files:**
- Modify: `wiki/sd/sources/SAP S4HANA销售订单处理（从询价到合同）.md`
- Modify: `wiki/sd/sources/恒生委外销售订单操作手册.md`
- Modify: `wiki/sd/sources/恒生销售到九华sap订单操作手册.md`
- Modify: `wiki/sd/sources/江西康莱特EC推送订单是否过量重复下单判断.md`
- Modify: `wiki/sd/sources/江西康莱特胶囊注射液手动 ATP 操作手册.md`
- Modify: `wiki/sd/sources/物料件数维护操作手册.md`
- Modify: `wiki/sd/sources/物料扩充销售视图.md`
- Modify: `wiki/sd/sources/销售退货物料移动类型配置.md`
- Modify: `wiki/sd/sources/山禾医药迎检新建物料注意事项.md`

- [ ] 按步骤插入可确认归属的截图，统一使用 Obsidian embed。
- [ ] 对含账号或密码的迎检资料只保留脱敏后的说明，不嵌入暴露凭据的截图。
- [ ] 不把 125 张 `SD-xx` 综合截图全部复制到单一来源页，只处理明确对应的操作手册截图。

### Task 4: 同步清单、索引和日志

**Files:**
- Modify: `wiki/fico/sources/raw资料清单.md`
- Modify: `wiki/abap/sources/raw资料清单.md`
- Modify: `wiki/sd/sources/raw资料清单.md`
- Modify: `wiki/shared/raw资料总清单.md`
- Modify: `wiki/index.md`
- Modify: `wiki/fico/overview.md`
- Modify: `wiki/sd/overview.md`
- Modify: `wiki/log.md`

- [ ] 只更新本轮实际完成的图片补齐状态和日期。
- [ ] 不擅自解决 ABAP 原始文件缺失、FICO 重复资料和历史 Clippings 统计争议；必要时记录为待确认事项。
- [ ] 追加一条本轮整理日志，说明图片来源目录、迁移数量、跳过原因和验证结果。

### Task 5: 验证引用和格式

**Files:**
- Read: 所有本轮修改的 wiki 页面和 `raw/assets/`

- [ ] 扫描所有 `![[raw/assets/...]]` 引用，确认目标文件存在。
- [ ] 检查新增图片文件类型和文件名编码正常。
- [ ] 运行 `git diff --check -- <本轮修改文件>`，忽略预先存在的无关插件文件问题。
- [ ] 检查工作树，确认未修改 raw 原始 Markdown、未删除文件、未把凭据写入 wiki。
