---
module: shared
kind: log
updated: 2026-07-08
source_count: 34
tags: []
---

# 整理记录

## 记录方式

- 单条记录建议使用 [[wiki/templates/log-entry]] 的格式。
- 标题使用 `## 日期 | 动作 | 模块`。
- 日志继续采用追加式写法，不回头重排历史记录。

## 2026-07-06 | 初始化知识库 | shared
- 主题：知识库骨架初始化
- 来源：`LLM WIKI.md`
- 做了什么：初始化 raw/wiki 分层结构，补齐模板、链接规范和日志条目模板
- 结果：建立 `CLAUDE.md`、`wiki/index.md`、`wiki/overview.md`、`wiki/log.md` 和 `wiki/templates/`
- 后续：继续按模块分批整理 raw 原始资料

## 2026-07-07 | 整理 raw | FICO
- 主题：FICO Markdown 原始资料第一轮整理
- 来源：`raw/fico/article/202607/`
- 做了什么：整理 4 个 Markdown 原始资料，建立来源页、raw 资料清单、实体页和概念页
- 结果：新增 `wiki/fico/sources/raw资料清单.md`，并整理 `ABAW 资产减值准备`、`CO 分摊分配配置说明`、`OKB9 成本要素默认成本中心配置`、`主营业务成本科目是否勾选成本要素` 四个来源页
- 后续：继续分批处理 FICO 的 Word、PDF 和 Excel 原始资料

## 2026-07-08 | 迁移附件 | FICO
- 主题：raw Markdown 图片引用统一
- 来源：`/Users/waterboy/jmkx_work/note/财务/note/images`
- 做了什么：复制 raw Markdown 实际引用的 6 张图片到 `raw/assets/`，并将图片链接统一改为 `![[raw/assets/图片名.png]]
- 结果：更新 `raw/fico/article/202607/ABAW 资产减值准备.md` 和 `raw/fico/article/202607/OKB9 成本要素默认成本中心配置.md` 的图片引用
- 后续：后续新增 raw Markdown 时，图片统一放入 `raw/assets/`

## 2026-07-08 | 制定计划 | FICO
- 主题：FICO 原始资料后续整理计划
- 来源：`raw/fico/`
- 做了什么：盘点剩余 30 个待整理文件，并按基础操作、应收应付、月结年结、成本资产、发票税票、PDF 专题和事务代码清单拆分批次
- 结果：新增 `wiki/fico/synthesis/FICO 原始资料后续整理计划.md`
- 后续：建议下一步执行第二批 FICO 基础操作手册整理

## 2026-07-08 | 整理 raw | FICO
- 主题：第二批 FICO 基础操作手册整理
- 来源：`raw/fico/article/202607/`
- 做了什么：提取并整理 4 个 Word 操作手册，建立来源页、补充实体页和概念页
- 结果：新增 `会计科目主数据维护`、`凭证记账`、`报表查询`、`汇率维护` 四个来源页，并补充 FS00、FI 凭证记账、财务报表查询、汇率维护等相关页面
- 后续：建议下一步执行第三批：应收应付与客商主数据

## 2026-07-08 | 修正结论 | FICO
- 主题：凭证批量导入事务码确认
- 来源：用户确认
- 做了什么：确认 `ZFIU001` 才是凭证批量导入记账功能，可导入预制凭证，也可批量导入过账凭证
- 结果：更新 `wiki/fico/sources/凭证记账.md`、`wiki/fico/entities/ZFIU001.md`、`wiki/fico/entities/ZFIC002.md`，并新增 `wiki/fico/concepts/凭证批量导入.md`
- 后续：如后续在系统中确认 `ZFIC002` 的真实用途，再补充对应实体页说明

## 2026-07-08 | 整理 raw | FICO
- 主题：FICO raw 原始资料完整整理
- 来源：`raw/fico/`
- 做了什么：继续整理剩余 18 个 Word、7 个 PDF 和 1 个 Excel 资料；使用 `opendataloader-pdf` 解析 PDF；建立来源页并补充大量事务码实体页和概念页
- 结果：FICO 当前 34 个有效 raw 原始资料已完成本轮整理，更新 `wiki/fico/sources/raw资料清单.md`、`wiki/fico/overview.md`、`wiki/index.md` 和 `wiki/fico/synthesis/FICO 原始资料后续整理计划.md`
- 后续：建议基于已整理资料继续提炼专题综合页，如 FICO 期末处理流程、采购发票到付款清账流程、销售开票到客户收款流程、成本月结与物料分类账处理

## 2026-07-08 | 整理 raw | shared
- 主题：全 raw 目录整理状态确认
- 来源：`raw/`
- 做了什么：盘点所有模块 raw 目录，确认 FICO 已完成，ABAP/MM/PP/QM 暂无有效资料，附件和系统文件不作为来源页整理
- 结果：新增 `wiki/shared/raw资料总清单.md`，并更新 `wiki/index.md`、`wiki/overview.md`、`wiki/abap/overview.md`、`wiki/mm/overview.md`、`wiki/pp/overview.md`、`wiki/qm/overview.md`
- 后续：后续新增 raw 文件后，按模块继续整理到对应 `wiki/<module>/sources/`
