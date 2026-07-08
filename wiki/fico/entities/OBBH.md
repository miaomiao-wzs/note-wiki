---
module: fico
kind: entity
updated: 2026-07-07
source_count: 1
tags: []
---

# OBBH

## 定义
`OBBH` 是用于维护替代规则的事务码。

## 作用
- 可通过替代规则自动填写成本中心等字段。
- 在 `OKB9` 默认成本中心逻辑中，替代规则优先级高于 `OKB9` 默认值。

## 相关对象
- [[wiki/fico/entities/OKB9]]

## 相关概念
- [[wiki/fico/concepts/成本要素默认成本中心]]

## 参考来源
- [[wiki/fico/sources/OKB9 成本要素默认成本中心配置]]
