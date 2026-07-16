---
module: shared
kind: log
updated: 2026-07-15
source_count: 59
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
- 做了什么：复制 raw Markdown 实际引用的 6 张图片到 `raw/assets/`，并将图片链接统一改为 `![[raw/assets/图片名.png]]`
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

## 2026-07-08 | 整理特别总账 | FICO
- 主题：F-02 特别总账录入操作手册
- 来源：用户确认的特别总账规则
- 做了什么：整理 F-02 特别总账录入的操作规则，明确客户常见过账码为 09/19、供应商常见过账码为 29/39，SGL 为特别总账标识，并补充客户/供应商特别总账概念页
- 结果：新增 `wiki/fico/sources/F-02 特别总账录入.md`、`wiki/fico/concepts/特别总账.md`、`wiki/fico/concepts/客户特别总账.md`、`wiki/fico/concepts/供应商特别总账.md`、`wiki/fico/synthesis/F-02 特别总账录入操作手册.md`，并更新索引
- 后续：如需可继续补充客户/供应商特别总账的单据示例

## 2026-07-08 | 整理项目结转 | FICO
- 主题：月结项目结转操作手册
- 来源：`raw/fico/article/202607/SAP实施项目_FICO_操作手册_成本模块_V1.0.docx`
- 做了什么：从成本模块原始 Word 中提取项目结算规则、CJ88 单个项目结算、CJ8G 批量项目结算、CJI3 余额检查等相关截图，并整理成月结项目结转操作手册
- 结果：新增 `wiki/fico/synthesis/月结项目结转操作手册.md`，提取 18 张项目结转截图到 `raw/assets/`，并更新 `wiki/index.md` 与 `wiki/fico/sources/成本模块操作手册.md`
- 后续：如后续确认项目接收方、结算变式和公司实际月结步骤，可继续补充真实案例

## 2026-07-15 | 新增 SD 并整理新增 raw | shared
- 主题：新增 SD 模块与剪藏资料整理
- 来源：`raw/Clippings/`
- 做了什么：新增 `raw/sd/` 和 `wiki/sd/` 同构目录；将新增剪藏资料复制归档到 SD、FICO、ABAP 对应模块目录；迁移剪藏 Markdown 中的外部图片到 `raw/assets/`；整理 SD 销售订单处理、FICO 科目主数据批量扩充、ABAP 异常处理三篇来源页及相关实体页、概念页
- 结果：新增 [[wiki/sd/overview]]、[[wiki/sd/sources/SAP S4HANA销售订单处理（从询价到合同）]]、[[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]]、[[wiki/abap/sources/ABAP 异常处理基础与核心概念]]，并更新全局索引、raw 总清单、模块首页和终端 Claude 使用说明
- 后续：后续新增 SD 资料时继续按 `raw/sd/<type>/<YYYYMM>/` 归档，并优先补充 VA01 创建销售订单、VA21 创建报价、VA41 创建合同等操作手册


## 2026-07-15 | 整理新增 raw | FICO / SD / MM
- 主题：新增 FICO、SD、MM 相关原始资料整理
- 来源：`raw/fico/article/202607/`、`raw/sd/article/202607/`
- 做了什么：整理新增 FICO Markdown、SD Markdown 和 3 个 PDF；使用 `opendataloader-pdf` 解析 PDF；为 F.19 GR/IR 重分类、在建工程转固反向处理、成本中心流入工单核对、生产工单收货与质检取样成本、资产负债表与利润表勾稽、生产工单跨月 TECO、SD 销售退货、销售订单、ATP、物料销售视图、客户资质校验、销售退货移动类型、SD 非常见配置点、费用类采购科目确定等主题建立来源页、实体页和概念页
- 结果：更新 [[wiki/fico/sources/raw资料清单]]、[[wiki/sd/sources/raw资料清单]]、[[wiki/mm/sources/raw资料清单]]、[[wiki/shared/raw资料总清单]]、[[wiki/index]]、[[wiki/overview]]、[[wiki/fico/overview]]、[[wiki/sd/overview]]、[[wiki/mm/overview]]；并将新增 Markdown 图片复制到 `raw/assets/` 后改为 Obsidian 嵌入
- 后续：如需处理当前工作树中缺失的旧 `ZFIR043` Word 原件，应先确认是否恢复；后续新增 PDF 仍必须用 `opendataloader-pdf` 解析
