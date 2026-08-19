---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# IDCNAR

## 定义
`IDCNAR` 是中国本地化的客户应收账龄报表事务码。

## 作用
- 查询客户账龄，按到期日划分账龄区间。
- 账龄日期逻辑：基准日期（通常为记账日期）+ 付款条件 = 到期日，按到期日划分账龄桶。
- 与 `IDCNAP` 为对应关系，分别覆盖应收和应付两侧。

## 相关对象
- [[wiki/fico/entities/IDCNAP]]
- [[wiki/fico/entities/FBL5N]]
- [[wiki/fico/entities/FD10N]]

## 相关概念
- [[wiki/fico/concepts/往来账龄分析]]

## 参考来源
- [[wiki/fico/sources/事务代码清单]]
