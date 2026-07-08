---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# ZFIU010

## 定义
`ZFIU010` 是回款认领平台对应的自开发事务码。

## 作用
- 出纳可根据九恒星回款流水生成 SAP 收款明细。
- 往来会计可基于回款明细生成收款预制凭证并过账。
- 支持维护回款类别、回款类别对应会计科目，以及银行账号与银行科目的对应关系。

## 相关对象
- [[wiki/fico/entities/BP]]
- [[wiki/fico/entities/FBV3]]
- [[wiki/fico/entities/FB03]]

## 相关概念
- [[wiki/fico/concepts/客户收款]]
- [[wiki/fico/concepts/回款认领]]
- [[wiki/fico/concepts/预制凭证]]

## 参考来源
- [[wiki/fico/sources/客户收款]]
