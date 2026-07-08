---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# FAGLF101

## 定义
`FAGLF101` 是 AR/AP 重分类事务码。

## 作用
- 月结时对客户/供应商余额进行排序和重分类。
- 可按账户类型 `D` 客户、`K` 供应商筛选。
- 正式运行后可能产生批输入会话，需要通过 `SM35` 处理。

## 相关对象
- [[wiki/fico/entities/SM35]]
- [[wiki/fico/entities/FB03]]

## 相关概念
- [[wiki/fico/concepts/AR AP 重分类]]
- [[wiki/fico/concepts/财务月结]]

## 参考来源
- [[wiki/fico/sources/财务月结操作]]

