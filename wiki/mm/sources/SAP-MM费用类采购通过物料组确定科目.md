---
module: mm
kind: source
updated: 2026-07-15
source_count: 1
tags: []
---

# SAP-MM费用类采购通过物料组确定科目

## 来源信息
- 来源类型：pdf
- 原始位置：`raw/sd/article/202607/SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客.pdf`
- 解析位置：`.claudian/tmp/pdf_extract/sd_202607/SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客/SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客.md`
- 解析工具：`opendataloader-pdf`
- 适用模块：MM / FICO

## 一句话结论
费用类采购的科目确定要区分是否带物料号：带物料号时通常由账户分配类别和物料评估类决定；不带物料号时可通过物料组默认评估类，再到 `OBYC` 的 `GBB` 确定科目。

## 关键内容
- `WRX` 的 GR/IR 科目可区分库存管理物料和非库存管理费用化物料。
- 带物料号的费用类采购，需要输入账户分配类别，系统结合账户分配类别中的科目修改和物料主数据评估类到 `OBYC-GBB` 确定科目。
- 不带物料号的费用类采购，需要输入账户分配类别和物料组。
- 通过 `OMSK` 创建非库存管理物料评估类。
- 通过 `OMSF` 创建物料组。
- 通过 `OMQW` 为物料组定义默认评估类。
- 通过 `FS00` 创建费用科目，再在 `OBYC-GBB` 维护科目确定。

## 相关实体
- [[wiki/mm/entities/OMSK]]
- [[wiki/mm/entities/OMSF]]
- [[wiki/mm/entities/OMQW]]
- [[wiki/fico/entities/FS00]]
- [[wiki/fico/entities/MIGO]]
- [[wiki/fico/entities/MIRO]]

## 相关概念
- [[wiki/mm/concepts/费用类采购科目确定]]
- [[wiki/fico/concepts/GRIR重分类]]
