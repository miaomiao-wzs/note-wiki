---
module: fico
kind: concept
updated: 2026-07-08
source_count: 1
tags: []
---

# FI 凭证记账

## 概念定义
FI 凭证记账是 SAP 财务会计中录入、预制、过账、修改、显示、冲销和打印会计凭证的一组基础操作。

## 为什么重要
- 是总账、应收、应付日常工作的基础。
- 会影响总账余额、客户余额、现金流量表项和后续报表查询。
- 凭证字段如凭证日期、过账日期、凭证类型、公司代码、货币、过账码、科目、金额、成本对象等都影响凭证质量。

## 工作机制 / 处理流程
1. 可先通过 `F-65` 或 `F-64` 创建预制凭证。
2. 通过 `FBV2` 修改预制凭证。
3. 通过 `FBV0` 过账预制凭证。
4. 已过账凭证可通过 `FB02` 修改部分字段，通过 `FB03` 显示，通过 `FB08` 冲销。
5. 可通过 `FAGLB03`、`FAGLL03`、`FD10N`、`FBL5N` 查询余额和行项目。

## 相关实体
- [[wiki/fico/entities/F-65]]
- [[wiki/fico/entities/FBV2]]
- [[wiki/fico/entities/FBV0]]
- [[wiki/fico/entities/FB02]]
- [[wiki/fico/entities/FB03]]
- [[wiki/fico/entities/FB08]]

## 相关概念
- [[wiki/fico/concepts/预制凭证]]
- [[wiki/fico/concepts/凭证冲销]]
- [[wiki/fico/concepts/原因代码]]

## 参考来源
- [[wiki/fico/sources/凭证记账]]
