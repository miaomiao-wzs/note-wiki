---
module: fico
kind: source
updated: 2026-08-12
source_count: 54
tags: []
---

# FICO raw 资料清单

本页记录 `raw/fico/` 下当前已经归档的原始资料。原始文件保持不动，本页只用于跟踪整理状态。

## 汇总

> 当前物理文件中 3 份 202608 固定资产资料已新增来源页；另有 1 份内容近重复的 FS15/FS16 Markdown 资料，已登记但暂不重复整理。因此当前物理有效资料数为 54，按主题去重口径待后续复核。

| 类别 | 数量 | 当前状态 |
| --- | ---: | --- |
| Markdown | 27 | 已完成整理 |
| Word 文档 | 19 | 已完成整理 |
| PDF | 7 | 已使用 `opendataloader-pdf` 解析并完成整理 |
| Excel | 1 | 已完成事务代码清单整理 |
| 合计 | 54 | FICO 当前 raw 资料已完成本轮整理 |

## 已整理资料

### 第一轮 Markdown

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/ABAW 资产减值准备.md` | [[wiki/fico/sources/ABAW 资产减值准备]] |
| `raw/fico/article/202607/CO 分摊分配配置说明.md` | [[wiki/fico/sources/CO 分摊分配配置说明]] |
| `raw/fico/article/202607/OKB9 成本要素默认成本中心配置.md` | [[wiki/fico/sources/OKB9 成本要素默认成本中心配置]] |
| `raw/fico/article/202607/主营业务成本科目是否勾选成本要素.md` | [[wiki/fico/sources/主营业务成本科目是否勾选成本要素]] |
| `raw/fico/article/202607/SAP 如何批量扩充科目主数据到其他子公司.md` | [[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]] | 已补充 15 张操作截图 |
| `raw/fico/article/202607/SAP 如何批量扩充（复制）科目主数据到其他子公司复制科目主数据详解 FS15&FS16.md` | [[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]] | 内容近重复，暂保留原始资料，未重复嵌入截图 |

### 2026-07-15 新增 Markdown

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/SAP F.19 GRIR重分类.md` | [[wiki/fico/sources/SAP F.19 GRIR重分类]] |
| `raw/fico/article/202607/SAP在建工程转固后的反向处理.md` | [[wiki/fico/sources/SAP在建工程转固后的反向处理]] |
| `raw/fico/article/202607/SAP月结成本中心流入工单金额核对.md` | [[wiki/fico/sources/SAP月结成本中心流入工单金额核对]] |
| `raw/fico/article/202607/SAP生产工单收货数量与质检取样成本.md` | [[wiki/fico/sources/SAP生产工单收货数量与质检取样成本]] |
| `raw/fico/article/202607/SAP资产负债表与利润表勾稽检查.md` | [[wiki/fico/sources/SAP资产负债表与利润表勾稽检查]] |
| `raw/fico/article/202607/ZFIR043维护金税发票与形式发票关系.md` | [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系-图片补充]] |
| `raw/fico/article/202607/生产工单跨月陆续交货TECO重新打开-物料差异结算问题.md` | [[wiki/fico/sources/生产工单跨月陆续交货TECO重新打开-物料差异结算问题]] | 已补充 6 张操作截图 |

### 2026-08 新增固定资产资料

| 原始资料 | 对应来源页 | 说明 |
| --- | --- | --- |
| `raw/fico/article/202608/asset-depreciation-calculation-logic.md` | [[wiki/fico/sources/资产折旧计算逻辑说明]] | 测算器剩余寿命直线法；不代表所有 SAP 折旧码规则 |
| `raw/fico/article/202608/一个SAP固定资产折旧开始日期的细节.md` | [[wiki/fico/sources/固定资产折旧开始日期]] | `AFAMP`、`T090NP` 和 `ABT1N` 线索；待官方与目标系统核验 |
| `raw/fico/article/202608/资产会计中常见日期(资本化日期、资产价值日等)解析-CSDN博客.md` | [[wiki/fico/sources/资产会计常见日期]] | 资产日期术语参考；来源为网络文章，状态 unknown |


| 原始资料 | 对应来源页 | 说明 |
| --- | --- | --- |
| `raw/fico/article/202608/CKMLCP：把差异分摊到每一颗物料.md` | [[wiki/fico/sources/CKMLCP差异分摊到物料]] | CKMLCP 四步框架；版本、配置和期间行为待核验 |
| `raw/fico/article/202608/SAP FICO深度总结：IDCNAP应付账款账龄报告（中国）详细分析.md` | [[wiki/fico/sources/IDCNAP应付账款账龄报告]] | 中国本地化应付账款账龄报表线索；字段和激活条件待核验 |
| `raw/fico/article/202608/SAP 如何修改统驭科目类型.md` | [[wiki/fico/sources/SAP统驭科目类型修改]] | 高风险主数据更正观点；不作为无条件生产方案 |
| `raw/fico/article/202608/限制用户在 SAP 中导出ALV报表数据.md` | [[wiki/fico/sources/SAP ALV报表导出权限控制]] | `S_GUI`/KBA 线索；授权效果待系统与官方核验 |


| 原始资料 | 对应来源页 | 说明 |
| --- | --- | --- |
| `raw/fico/article/202607/SAP 作业分割原理 OKEW.md` | [[wiki/fico/sources/SAP 作业分割原理 OKEW]] | 原文示例和 OKES/OKEW 配置说法保留待系统核验 |

### 2026-07-28 新增 Markdown

| 原始资料 | 对应来源页 | 说明 |
| --- | --- | --- |
| `raw/fico/article/202607/SAP资产折旧调错了怎么办？用ABMA冲销与ABAA补提（附AO78配置）.md` | [[wiki/fico/sources/SAP资产折旧错误调整]] | 原文含未经核验的事务配置和高风险伪代码，来源页已分层标注 |
| `raw/fico/article/202607/SAP FICO基础笔记：AA模块凭证冲销操作详解-AB08.md` | [[wiki/fico/sources/SAP AA模块凭证冲销 AB08]] | 原文对 AB08、FB08、跨期冲销和集成凭证存在待核验的绝对化描述 || `raw/fico/article/202607/SAP实施项目_FICO_操作手册_凭证记账.docx` | [[wiki/fico/sources/凭证记账]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_报表查询.docx` | [[wiki/fico/sources/报表查询]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_汇率维护.docx` | [[wiki/fico/sources/汇率维护]] |

### 第三批：应收应付与客商主数据

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_供应商付款.docx` | [[wiki/fico/sources/供应商付款]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_客户收款.docx` | [[wiki/fico/sources/客户收款]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_客商创建.docx` | [[wiki/fico/sources/客商创建]] |
| `raw/fico/article/202607/财务客商创建操作手册.docx` | [[wiki/fico/sources/财务客商创建]] |

### 第四批：月结、年结与期末处理

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_财务月结操作.docx` | [[wiki/fico/sources/财务月结操作]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_财务年结.docx` | [[wiki/fico/sources/财务年结]] |
| `raw/fico/article/202607/年结余额结转操作手册 (用户).docx` | [[wiki/fico/sources/年结余额结转]] |
| `raw/fico/article/202607/SAP 月结全景图从精密运转到业务洞察.md` | [[wiki/fico/sources/SAP 月结全景图]] |
| `raw/fico/article/202607/SAP年结与财务报表：账结法vs表结法全解析.md` | [[wiki/fico/sources/SAP 年结与财务报表]] |

### 第五批：成本、资产与项目相关

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_成本模块_V1.0.docx` | [[wiki/fico/sources/成本模块操作手册]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_资产业务操作_V1.0.docx` | [[wiki/fico/sources/资产业务操作]] |
| `raw/fico/article/202607/WBS 创建操作手册.docx` | [[wiki/fico/sources/WBS 创建操作手册]] |
| `raw/fico/article/202607/SAP 集团内资产买卖原值、折旧一起入账.docx` | [[wiki/fico/sources/集团内资产买卖原值折旧入账]] |

### 第六批：发票、税票与销售开票

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_发票校验.docx` | [[wiki/fico/sources/发票校验]] |
| `raw/fico/article/202607/SAP实施项目_FICO_操作手册_销售开票和冲销流程.docx` | [[wiki/fico/sources/销售开票和冲销流程]] |
| `raw/fico/article/202607/金税发票冲销作废操作手册.docx` | [[wiki/fico/sources/金税发票冲销作废]] |

### 第七批：补充资料

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/FICO.md` | [[wiki/fico/sources/FICO 综合资料]] |
| `raw/fico/article/202607/SAP FICO基础笔记：AA模块的事务类型.md` | [[wiki/fico/sources/FI-AA 事务类型]] |
| `raw/fico/article/202607/通过凭证查找业务单据方法.docx` | [[wiki/fico/sources/通过凭证查找业务单据方法]] |

### 第八批：PDF 专题资料

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/pdf/202607/SAPCO-CKM3取值逻辑.pdf` | [[wiki/fico/sources/CKM3取值逻辑]] |
| `raw/fico/pdf/202607/SAP 采购运费处理方式方案大全(一).pdf` | [[wiki/fico/sources/采购运费处理方式]] |
| `raw/fico/pdf/202607/SAP-MR21和MR22的应用_sap mr22.pdf` | [[wiki/fico/sources/MR21和MR22的应用]] |
| `raw/fico/pdf/202607/SAP中GR_IR重分类详解.pdf` | [[wiki/fico/sources/GRIR重分类详解]] |
| `raw/fico/pdf/202607/【SAP FICO】CO成本控制（成本中心、成本要素、活动类型、分配分摊）_sap 成本中心-CSDN博客.pdf` | [[wiki/fico/sources/CO成本控制概览]] |
| `raw/fico/pdf/202607/物料评估XXXX在估价范围XXX内不一致处理_物料估价在估价范围内不一致-CSDN博客.pdf` | [[wiki/fico/sources/物料评估不一致处理]] |
| `raw/fico/pdf/202607/J3RFLVMOBVEDH俄罗斯库存报表无库存数据问题处理方式.pdf` | [[wiki/fico/sources/俄罗斯库存报表无库存数据处理]] |

### 第九批：Excel 事务代码清单

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/fico/article/202607/事务代码清单.xlsx` | [[wiki/fico/sources/事务代码清单]] |

## 跨模块相关资料

| 原始资料 | 对应来源页 | 说明 |
| --- | --- | --- |
| `raw/sd/article/202607/SAP FICO物料价格控制_sap s+3 v+2.pdf` | [[wiki/fico/sources/SAP FICO物料价格控制]] | 原始文件暂在 SD 目录，内容归属 FICO/MM |

## 待处理资料

本轮 FICO raw 资料已整理完成；新增月结、年结、FI-AA 和作业分割资料已建立来源页，原始文件均已归档到 `raw/fico/article/202607/`。

说明：`raw/fico/article/202607/~$事务代码清单.xlsx` 是 Office 临时锁文件，不作为有效原始资料整理，也未删除。

注意：既有 wiki 中仍保留 [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系]] 和 [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系-补充]] 两个旧 Word 来源页；当前工作树中对应两个 Word 原件未在 `raw/fico/article/202607/` 检出，是否恢复需单独确认，不在本轮整理中擅自处理。
