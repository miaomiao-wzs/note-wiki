---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# ME2L

## 定义
`ME2L` 是按供应商查询采购订单的事务码。

## 作用
- 输入供应商编号（必填），查询该供应商的所有采购订单。
- 结果列表中同时显示供应商和物料信息，可查看收货情况和来票情况。
- 物料编号可留空，查看该供应商全部订单。

## 相关对象
- [[wiki/fico/entities/ME2M]]

## 相关概念
- [[wiki/fico/concepts/采购订单查询]]

## 参考来源
- [[wiki/fico/sources/事务代码清单]]
