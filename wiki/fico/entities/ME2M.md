---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# ME2M

## 定义
`ME2M` 是按物料查询采购订单的事务码。

## 作用
- 输入物料编号（必填），查询该物料的所有采购订单。
- 结果列表中同时显示物料和供应商信息，可查看收货情况和来票情况。
- 供应商可留空，查看该物料全部订单。

## 相关对象
- [[wiki/fico/entities/ME2L]]

## 相关概念
- [[wiki/fico/concepts/采购订单查询]]

## 参考来源
- [[wiki/fico/sources/事务代码清单]]
