---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# FBV0

## 定义
`FBV0` 是用于过账预制凭证的事务码。

## 作用
- 将预制凭证正式过账。
- 预制凭证过账成功后凭证号不变。

> [!warning] 业务规则：不允许使用删除功能
> 虽然系统菜单中存在删除预制凭证的入口，但企业业务规则不允许用户直接删除。推荐做法是将金额改为 0 后过账，或过账后用 `FB08` 冲销。

## 相关对象
- [[wiki/fico/entities/F-65]]
- [[wiki/fico/entities/FBV2]]
- [[wiki/fico/entities/FB08]]

## 相关概念
- [[wiki/fico/concepts/预制凭证]]
- [[wiki/fico/concepts/FI 凭证记账]]
- [[wiki/fico/concepts/凭证冲销]]

## 参考来源
- [[wiki/fico/sources/凭证记账]]
