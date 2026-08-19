---
module: fico
kind: entity
updated: 2026-08-13
source_count: 1
tags: []
---

# FBV3

## 定义
`FBV3` 是 SAP FI 中用于显示预制凭证的事务码。

## 作用
- 按凭证编号查看单张预制凭证。
- 通过菜单进入**凭证清单**，可批量查询预制凭证（只查预制凭证，不包含已过账凭证）。

> [!note] FBV3 vs FB03 凭证清单
> - `FBV3` 凭证清单：只查询**预制凭证**
> - `FB03` 凭证清单：查询**已过账凭证**
> - 两者互补，不能互相替代

## 查询预制凭证

1. 单张查询：进入 `FBV3`，输入凭证编号、公司代码、会计年度。
2. 批量查询：进入 `FBV3`，菜单选择**凭证 → 凭证清单**，设置公司代码、年度等条件后执行。

> [!warning] 注意
> FBV3 凭证清单**没有**动态选择功能，不能像 FB03 那样添加用户名等额外筛选字段。

## 相关对象
- [[wiki/fico/entities/FBV2]]
- [[wiki/fico/entities/FBV0]]
- [[wiki/fico/entities/FB03]]
- [[wiki/fico/entities/ZFIR008]]

## 相关概念
- [[wiki/fico/concepts/预制凭证]]
- [[wiki/fico/concepts/客户收款]]

## 参考来源
- [[wiki/fico/sources/客户收款]]
