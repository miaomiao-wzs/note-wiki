---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# ZFIR008

## 定义
`ZFIR008` 是自开发的凭证序时账事务码。

## 作用
- 查询凭证序时账，支持按公司代码、会计年度、凭证编号、过账日期等条件筛选。
- 选择屏幕中有**”是否查询预制凭证”**勾选项：
  - **勾选**：查询结果全部为预制凭证
  - **不勾选**：查询结果全部为已过账凭证
- 支持按”预制此凭证的用户名”筛选预制凭证的创建人。

![[../../raw/assets/Pasted image 20260819112003.png]]

## 适用场景
- 需要同时查看预制凭证和已过账凭证时，通过勾选切换。
- 需要按预制人筛选预制凭证时，使用”预制此凭证的用户名”字段。

## 相关对象
- [[wiki/fico/entities/FB03]]
- [[wiki/fico/entities/FBV3]]

## 相关概念
- [[wiki/fico/concepts/FI 凭证记账]]
- [[wiki/fico/concepts/预制凭证]]

## 参考来源
- [[wiki/fico/sources/事务代码清单]]
