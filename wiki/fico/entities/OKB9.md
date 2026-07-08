---
module: fico
kind: entity
updated: 2026-07-07
source_count: 1
tags: []
---

# OKB9

## 定义
`OKB9` 是 SAP 中用于为成本要素配置默认成本中心的事务码。

## 作用
- 当 FI 凭证涉及成本要素但未手工输入成本中心时，系统可根据 `OKB9` 自动带出默认成本中心。
- 减少“成本中心必填”类过账错误。
- 可用于某些费用科目、费用性采购、物料差异科目等场景。

## 相关对象
- [[wiki/fico/entities/OBBH]]
- [[wiki/fico/entities/CKMLCP]]

## 相关概念
- [[wiki/fico/concepts/成本要素默认成本中心]]
- [[wiki/fico/concepts/物料分类账差异处理]]

## 常见问题
- `OKB9` 的默认成本中心优先级较低，会被手工填写、订单/WBS 结算规则和替代规则覆盖。
- 如果科目需要由用户按实际业务指定不同成本中心，不建议配置固定默认成本中心。

## 参考来源
- [[wiki/fico/sources/OKB9 成本要素默认成本中心配置]]
