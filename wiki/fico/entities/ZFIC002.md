---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# ZFIC002

## 定义
`ZFIC002` 是凭证记账手册事务代码列表中出现的凭证导入事务码。

## 作用
- 原始手册事务代码列表将其描述为“凭证导入”。
- 但后续业务确认：实际用于凭证批量导入记账的功能是 `ZFIU001`。

## 注意
`ZFIC002` 暂不作为已确认的凭证批量导入入口使用。后续如果在系统中确认其真实用途，再补充说明。

## 相关对象
- [[wiki/fico/entities/ZFIU001]]

## 相关概念
- [[wiki/fico/concepts/FI 凭证记账]]

## 参考来源
- [[wiki/fico/sources/凭证记账]]
