---
module: fico
kind: entity
updated: 2026-07-07
source_count: 1
tags: []
---

# CKMLCP

## 定义
`CKMLCP` 是物料分类账月末结算相关事务码。

## 作用
- 在启用物料分类账后，用于月末结算并处理差异还原。
- 与不启用物料分类账时通过 `OKB9` 分配差异科目的处理方式不同。

## 相关对象
- [[wiki/fico/entities/OKB9]]

## 相关概念
- [[wiki/fico/concepts/物料分类账差异处理]]
- [[wiki/fico/concepts/成本要素默认成本中心]]

## 参考来源
- [[wiki/fico/sources/OKB9 成本要素默认成本中心配置]]
