---
module: fico
kind: source
updated: 2026-07-08
source_count: 1
tags: []
---

# CKM3取值逻辑

## 来源信息
- 来源类型：pdf
- 原始位置：`raw/fico/pdf/202607/SAPCO-CKM3取值逻辑.pdf`
- 解析位置：`.claudian/tmp/pdf_extract/SAPCO-CKM3取值逻辑/SAPCO-CKM3取值逻辑.md`
- 解析工具：`opendataloader-pdf`
- 语言：中文
- 适用模块：FICO / CO

## 一句话结论
CKM3/CKM3N 的物料价格分析数据可从物料分类账相关底表追溯，核心思路是先通过 `CKMLHD` 找到成本估算号，再结合 `MLDOC`、`MLDOCS` 等表按业务类型和组件字段分析期初、收据、消耗和实际单位成本。

## 关键内容
- 资料主题是 CKM3N 取值分析和物料分类账业务流转。
- 总体思路是从后台底层数据找出 CKM3N 中各项数据值来源。
- 可通过 `CKMLHD` 根据物料和工厂查到成本估算号。
- 再根据成本估算号和月份在 `MLDOC` 中获取物料当月数据。
- 在 `MLDOCS` 中按业务类型筛选：例如期初、收据、消耗等不同业务类型。
- 通过凭证参考、组件字段和金额字段可分析物料当月收发实际单位成本。
- 资料提示直接使用 `CKMLPRKEPH` 的单位实际成本和单位标准成本可能只有两位小数，数量很大时会导致差异。

## 相关实体
- [[wiki/fico/entities/CKM3]]
- [[wiki/fico/entities/CKM3N]]
- [[wiki/fico/entities/CKMLHD]]
- [[wiki/fico/entities/MLDOC]]
- [[wiki/fico/entities/MLDOCS]]
- [[wiki/fico/entities/CKMLPRKEPH]]

## 相关概念
- [[wiki/fico/concepts/CKM3取值逻辑]]
- [[wiki/fico/concepts/物料分类账差异处理]]
- [[wiki/fico/concepts/物料实际成本]]

## 和现有知识的关系
- 本资料补充了 [[wiki/fico/concepts/物料分类账差异处理]] 的底层取值视角。
- 与 [[wiki/fico/sources/成本模块操作手册]] 中 `CKMLCP` 成本核算运行相关。

## 后续动作
- 后续如需要做 ABAP 报表或数据核对，可继续整理 CKM3N 底表字段映射表。
