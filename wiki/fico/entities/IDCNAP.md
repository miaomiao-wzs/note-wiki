---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# IDCNAP

## 定义
`IDCNAP` 是中国本地化的应付账款账龄报表事务码。

## 作用
- 查询供应商账龄，按到期日划分账龄区间（默认 30/60/90/120 天）。
- 可按供应商、公司代码、关键日期、特别总账业务等条件筛选。
- 支持本币金额或交易货币金额展示。
- 账龄日期逻辑：基准日期（通常为记账日期）+ 付款条件 = 到期日，按到期日划分账龄桶。

## 相关对象
- [[wiki/fico/entities/FBL1N]]
- [[wiki/fico/entities/FK10N]]
- [[wiki/fico/entities/IDCNAR]]

## 相关概念
- [[wiki/fico/concepts/供应商账龄]]
- [[wiki/fico/concepts/应付账款]]
- [[wiki/fico/concepts/往来账龄分析]]

## 参考来源
- [[wiki/fico/sources/IDCNAP应付账款账龄报告]]
- [[wiki/fico/sources/发票校验]]

