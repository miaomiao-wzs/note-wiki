---
module: fico
kind: source
updated: 2026-07-08
source_count: 1
tags: []
---

# CO成本控制概览

## 来源信息
- 来源类型：pdf
- 原始位置：`raw/fico/pdf/202607/【SAP FICO】CO成本控制（成本中心、成本要素、活动类型、分配分摊）_sap 成本中心-CSDN博客.pdf`
- 解析位置：`.claudian/tmp/pdf_extract/【SAP FICO】CO成本控制（成本中心、成本要素、活动类型、分配分摊）_sap 成本中心-CSDN博客/【SAP FICO】CO成本控制（成本中心、成本要素、活动类型、分配分摊）_sap 成本中心-CSDN博客.md`
- 解析工具：`opendataloader-pdf`
- 语言：中文
- 适用模块：FICO / CO

## 一句话结论
该 PDF 是 CO 成本控制概览资料，覆盖管理会计功能、成本流转、成本主数据、成本中心、成本要素、统计指标、作业类型、KP26 作业价格和 KSV/KSU 分配分摊流程。

## 关键内容
- 内容结构包括成本控制概览、成本主数据、成本中心会计和分配分摊流程。
- 管理会计主数据包括成本控制范围、成本要素、成本中心、统计指标、作业类型等。
- 成本中心主数据维护涉及 `KS01`、`KS02`、成本中心标准层次结构和成本中心组。
- 成本中心费用预算可通过 `KP06` 等方式维护。
- 统计指标用于分配分摊中的数量基础，可通过 `KB31N` 记账。
- 作业类型计划价格通过 `KP26` 维护。
- 分配通常通过 `KSV1` 建立循环、`KSV5` 执行。
- 分摊通常通过 `KSU1` 建立循环、`KSU5` 执行。
- 资料强调分配和分摊都是成本中心会计中期末费用流转和归集的重要工具。

## 相关实体
- [[wiki/fico/entities/KS01]]
- [[wiki/fico/entities/KS02]]
- [[wiki/fico/entities/KP06]]
- [[wiki/fico/entities/KP26]]
- [[wiki/fico/entities/KB31N]]
- [[wiki/fico/entities/KSV1]]
- [[wiki/fico/entities/KSV5]]
- [[wiki/fico/entities/KSU1]]
- [[wiki/fico/entities/KSU5]]

## 相关概念
- [[wiki/fico/concepts/CO成本控制]]
- [[wiki/fico/concepts/成本中心]]
- [[wiki/fico/concepts/成本要素组]]
- [[wiki/fico/concepts/统计指标]]
- [[wiki/fico/concepts/作业类型]]
- [[wiki/fico/concepts/CO 分摊分配]]

## 和现有知识的关系
- 本资料从概览角度补充 [[wiki/fico/sources/成本模块操作手册]] 的操作步骤。
- 与 [[wiki/fico/sources/CO 分摊分配配置说明]] 互为理论和操作补充。

## 后续动作
- 后续可拆分 CO 主数据、CO 分配分摊、作业价格三个专题综合页。
