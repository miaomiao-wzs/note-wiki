---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# MR8M

## 定义
`MR8M` 是后勤发票校验中的发票冲销事务码。

## 作用
- 冲销已过账的采购发票校验凭证。
- 需要输入发票凭证编号、会计年度、冲销原因和过账日期。
- 冲销原因 `03` 表示当前期间红冲，`04` 表示关闭期间红冲。

## 相关对象
- [[wiki/fico/entities/MIRO]]
- [[wiki/fico/entities/MIR6]]

## 相关概念
- [[wiki/fico/concepts/发票校验冲销]]

## 参考来源
- [[wiki/fico/sources/发票校验]]

