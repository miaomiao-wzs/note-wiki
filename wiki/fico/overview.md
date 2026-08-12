---
module: fico
kind: overview
updated: 2026-08-12
source_count: 54
tags: []
---

# FICO 模块总览

这个模块用于沉淀 FICO 相关知识。

## 结构

- `entities/`
- `concepts/`
- `comparisons/`
- `sources/`
- `synthesis/`

## 常用入口

- [[wiki/fico/sources/raw资料清单]]：FICO 原始资料清单
- [[wiki/fico/synthesis/FICO 原始资料后续整理计划]]：后续整理计划
- [[wiki/fico/entities/]]：实体页
- [[wiki/fico/entities/SCC4]]：客户端更改和传输控制
- [[wiki/fico/entities/OKEW]]：作业分割配置对象
- [[wiki/fico/concepts/]]：概念页
- [[wiki/fico/comparisons/]]：对比页
- [[wiki/fico/sources/]]：来源页
- [[wiki/fico/synthesis/]]：综合页

## 已整理来源

### 第一轮 Markdown

- [[wiki/fico/sources/ABAW 资产减值准备]]
- [[wiki/fico/sources/CO 分摊分配配置说明]]
- [[wiki/fico/sources/OKB9 成本要素默认成本中心配置]]
- [[wiki/fico/sources/主营业务成本科目是否勾选成本要素]]
- [[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]]

### 2026-07-15 新增 Markdown

- [[wiki/fico/sources/SAP F.19 GRIR重分类]]
- [[wiki/fico/sources/SAP在建工程转固后的反向处理]]
- [[wiki/fico/sources/SAP月结成本中心流入工单金额核对]]
- [[wiki/fico/sources/SAP生产工单收货数量与质检取样成本]]
- [[wiki/fico/sources/SAP资产负债表与利润表勾稽检查]]
- [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系-图片补充]]
- [[wiki/fico/sources/生产工单跨月陆续交货TECO重新打开-物料差异结算问题]]

### 第二批 FICO 基础操作手册

- [[wiki/fico/sources/会计科目主数据维护]]
- [[wiki/fico/sources/凭证记账]]
- [[wiki/fico/sources/报表查询]]
- [[wiki/fico/sources/汇率维护]]

### 第三批：应收应付与客商主数据

- [[wiki/fico/sources/供应商付款]]
- [[wiki/fico/sources/客户收款]]
- [[wiki/fico/sources/客商创建]]
- [[wiki/fico/sources/财务客商创建]]

### 第四批：月结、年结与期末处理

- [[wiki/fico/sources/财务月结操作]]
- [[wiki/fico/sources/财务年结]]
- [[wiki/fico/sources/年结余额结转]]
- [[wiki/fico/sources/SAP 月结全景图]]
- [[wiki/fico/sources/SAP 年结与财务报表]]

### 第五批：成本、资产与项目相关

- [[wiki/fico/sources/成本模块操作手册]]
- [[wiki/fico/sources/SAP 作业分割原理 OKEW]]
- [[wiki/fico/synthesis/生产环境 OKB9 OKEW 临时维护方法]]：生产临时维护边界
- [[wiki/fico/sources/资产业务操作]]
- [[wiki/fico/sources/固定资产余额与期间查询]]：S_ALR_87011967 与 ZFIR001 的期间查询差异
- [[wiki/fico/sources/CO88 生产订单结算与会计分录]]：CO88 生产订单结算、科目映射与典型分录
- [[wiki/fico/sources/CON2 生产订单按实际作业价格重估]]：CON2 实际作业价格重估与月结关系
- [[wiki/fico/sources/SAP资产折旧错误调整]]：资产折旧异常诊断、调整边界与高风险内容治理
- [[wiki/fico/sources/SAP AA模块凭证冲销 AB08]]：资产会计凭证冲销边界与 AB08 核验清单
- [[wiki/fico/sources/WBS 创建操作手册]]
- [[wiki/fico/sources/集团内资产买卖原值折旧入账]]

### 第六批：发票、税票与销售开票

- [[wiki/fico/sources/发票校验]]
- [[wiki/fico/sources/销售开票和冲销流程]]
- [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系]]
- [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系-补充]]
- [[wiki/fico/sources/金税发票冲销作废]]

### 第七批：补充资料

- [[wiki/fico/sources/FICO 综合资料]]：已按 `FICO.md` 重新整理，并修复原文图片引用
- [[wiki/fico/sources/FI-AA 事务类型]]
- [[wiki/fico/sources/通过凭证查找业务单据方法]]

### 第八批：PDF 专题资料

- [[wiki/fico/sources/CKM3取值逻辑]]
- [[wiki/fico/sources/采购运费处理方式]]
- [[wiki/fico/sources/MR21和MR22的应用]]
- [[wiki/fico/sources/GRIR重分类详解]]
- [[wiki/fico/sources/CO成本控制概览]]
- [[wiki/fico/sources/物料评估不一致处理]]
- [[wiki/fico/sources/俄罗斯库存报表无库存数据处理]]

### 第九批：Excel 事务代码清单

- [[wiki/fico/sources/事务代码清单]]

### 2026-07-28 FICO 综合资料增量专题

- [[wiki/fico/sources/FICO 接口日志与报表逻辑]]：EAS/EC/OA/SRM 接口、日志和自开发报表取值线索；自开发对象待目标系统核验
- [[wiki/fico/sources/FICO 特殊业务与期初边界]]：农产品税务、免费赠送、运费、统计型 WBS、承兑、期初导入及高风险边界
### 2026-08 新增固定资产资料

- [[wiki/fico/sources/资产折旧计算逻辑说明]]：通用测算器的剩余寿命直线法与累计折旧追平逻辑
- [[wiki/fico/sources/固定资产折旧开始日期]]：资产折旧开始日期、`AFAMP`/`T090NP` 与 `ABT1N` 线索（待核验）
- [[wiki/fico/sources/资产会计常见日期]]：资本化日期、资产价值日、折旧开始日期和不活动日期（待核验）


- [[wiki/fico/sources/CKMLCP差异分摊到物料]]：物料分类账差异处理框架；期间、配置和分摊结果待核验
- [[wiki/fico/sources/IDCNAP应付账款账龄报告]]：中国本地化应付账款账龄报表线索；字段和激活条件待核验
- [[wiki/fico/sources/SAP统驭科目类型修改]]：统驭科目类型错误处理的高风险来源建议
- [[wiki/fico/sources/SAP ALV报表导出权限控制]]：ALV 导出权限治理线索；`S_GUI`-`EXPORT` 效果待核验


- [[wiki/fico/sources/SAP FICO物料价格控制]]：原始 PDF 暂在 `raw/sd/article/202607/`，内容归属 FICO/MM。

## 核心概念

- [[wiki/fico/concepts/FI 凭证记账]]
- [[wiki/fico/concepts/会计科目主数据]]
- [[wiki/fico/concepts/客商主数据]]
- [[wiki/fico/concepts/供应商付款]]
- [[wiki/fico/concepts/客户收款]]
- [[wiki/fico/concepts/财务月结]]
- [[wiki/fico/concepts/财务年结]]
- [[wiki/fico/concepts/成本中心]]
- [[wiki/fico/concepts/作业分割]]
- [[wiki/fico/concepts/CO 分摊分配]]
- [[wiki/fico/concepts/固定资产主数据]]
- [[wiki/fico/concepts/发票校验]]
- [[wiki/fico/concepts/销售开票]]
- [[wiki/fico/concepts/GRIR重分类]]
- [[wiki/fico/concepts/物料分类账差异处理]]
- [[wiki/fico/concepts/CKM3取值逻辑]]
- [[wiki/fico/concepts/在建工程转固反向处理]]
- [[wiki/fico/concepts/成本中心流入工单金额核对]]
- [[wiki/fico/concepts/生产工单收货与质检取样成本]]
- [[wiki/fico/concepts/财务报表勾稽检查]]
- [[wiki/fico/concepts/生产工单跨月TECO与物料差异结算]]
- [[wiki/fico/concepts/物料价格控制]]
- [[wiki/fico/sources/FI-AA 事务类型]]

## 当前状态

`raw/fico/` 当前 54 个有效原始资料已完成本轮整理，包含 3 篇 202608 固定资产资料；物理文件中原有 FS15/FS16 近重复资料仍保留。
