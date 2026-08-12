---
module: accounting
kind: source
subject: shared
owner: shared
updated: 2026-07-30
source_count: 1
tags: [accounting, ownership, fico]
---

# FICO 与 accounting 归属映射

## 目的

本页用于避免会计规范与 SAP/FICO 系统实现重复建页。`accounting` 和 `fico` 都会使用“科目、折旧、收入、财务报表”等词，但页面归属依据资料的权威身份和内容用途，而不是关键词。

## 归属规则

### accounting 权威规范

归入 `wiki/accounting/`：

- 全国人大、国务院及其他政府部门发布的法律法规；
- 财政部发布的企业会计准则、应用指南、解释和权威制度文件；
- 会计确认、计量、列报和法定财务报告要求的规范性资料；
- 经济法制度及会计法律责任。

### FICO SAP 实现

保留在 `wiki/fico/`：

- SAP 事务码、配置和系统版本行为；
- 企业自开发报表和接口；
- 企业实际科目映射、凭证样例和操作手册；
- SAP 月结、资产、生产成本、应收应付等系统流程。

### 交叉引用

当 FICO 页面解释系统怎么落地、accounting 页面解释为什么这样核算时，两个页面互相链接，但不复制整段内容。

## 已有 FICO 页面归属

| 主题 | 规范依据归属 | SAP/企业实现归属 |
|---|---|---|
| 会计科目和记账 | accounting 可沉淀会计要素、借贷记账法 | [[wiki/fico/sources/会计科目主数据维护]]、[[wiki/fico/concepts/会计科目主数据]]、[[wiki/fico/concepts/FI 凭证记账]] |
| 财务报表 | accounting 可沉淀报告目标和法定要求 | [[wiki/fico/sources/报表查询]]、[[wiki/fico/concepts/财务报表勾稽检查]] |
| 固定资产 | accounting 可沉淀确认、计量和折旧原则 | [[wiki/fico/sources/资产业务操作]]、[[wiki/fico/entities/AFAB]]、[[wiki/fico/entities/AW01N]]、[[wiki/fico/entities/S_ALR_87011967]] |
| 月结年结 | accounting 可沉淀期间归属和报告原则 | [[wiki/fico/concepts/财务月结]]、[[wiki/fico/sources/财务年结]] |
| 发票和税票 | accounting 可沉淀适用的会计和法定规则 | [[wiki/fico/sources/发票校验]]、[[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系]] |
| 产品成本 | accounting 可沉淀存货、成本和报告原则 | [[wiki/fico/concepts/产品成本结算]]、[[wiki/fico/sources/CO88 生产订单结算与会计分录]]、[[wiki/fico/sources/CON2 生产订单按实际作业价格重估]] |

## 待确认边界

- 具体税法、行业会计制度和地方监管口径尚未纳入本模块，后续必须以官方现行版本为准。
- 既有 FICO 页面中的业务经验、系统配置和企业科目名称，不应直接当作普遍适用的会计准则结论。
- 如果一份资料同时包含规范和 SAP 操作，应建立一篇规范来源页，并在 FICO 页面保留系统实现链接；不重复复制原文。

## 当前参考

- [[wiki/accounting/sources/企业会计准则基本准则（财政部令第33号）]]
- [[wiki/accounting/concepts/企业会计准则基本原则]]
- [[wiki/fico/overview]]
