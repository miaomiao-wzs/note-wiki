---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# ME2N

## 定义
`ME2N` 是按采购订单号批量查询采购订单的事务码。

## 作用
- 输入采购订单号（可输范围），批量查询多张采购订单清单。
- 结果列表中同时显示供应商、物料、数量、价格、收货和来票情况。
- 与 `ME23N` 的区别：`ME23N` 显示单张订单详情，`ME2N` 批量查询订单清单。

## 相关对象
- [[wiki/fico/entities/ME23N]]

## 相关概念
- [[wiki/fico/concepts/采购订单查询]]

## 参考来源
- [[wiki/fico/sources/事务代码清单]]
