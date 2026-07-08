---
module: fico
kind: source
updated: 2026-07-08
source_count: 1
tags: []
---

# GRIR重分类详解

## 来源信息
- 来源类型：pdf
- 原始位置：`raw/fico/pdf/202607/SAP中GR_IR重分类详解.pdf`
- 解析位置：`.claudian/tmp/pdf_extract/SAP中GR_IR重分类详解/SAP中GR_IR重分类详解.md`
- 解析工具：`opendataloader-pdf`
- 语言：中文
- 适用模块：FICO / MM

## 一句话结论
GR/IR 是采购收货和发票校验之间的中间科目，月末需先通过 `F.13` 清账，未完结采购业务导致的正常差异可通过 `F.19` 重分类到在途物资或应付暂估等科目，并在次月冲回。

## 关键内容
- GR/IR 全称是 Goods Receipt / Invoice Receipt，用于采购收货和发票校验清算。
- 正常完结采购业务中，GR/IR 科目余额应为 0，并在月末通过 `F.13` 自动清账。
- GR/IR 差异常见原因包括：货到票未到、票到货未到、发票数量与收货数量不一致。
- 未完结采购业务形成的正常差异，不应强行转走业务余额，而应通过重分类反映报表列示。
- 已完结采购业务仍有非正常差异时，需要用 MR11 等方式处理。
- GR/IR 重分类通常利用 GR/IR 调整科目、在途物资科目、应付暂估科目等技术性科目。
- `F.19` 可将 GR/IR 借方或贷方余额调整到在途物资或暂估科目，并在下月初冲回。
- 如果管理流程严格禁止票先到货后到，并且 GR/IR 科目本身按表内科目处理，部分场景可能不需要重分类。

## 相关实体
- [[wiki/fico/entities/F.13]]
- [[wiki/fico/entities/F.19]]
- [[wiki/fico/entities/MR11]]
- [[wiki/fico/entities/MIRO]]
- [[wiki/fico/entities/MIGO]]

## 相关概念
- [[wiki/fico/concepts/GRIR重分类]]
- [[wiki/fico/concepts/GRIR 自动清账]]
- [[wiki/fico/concepts/货到票未到]]
- [[wiki/fico/concepts/票到货未到]]
- [[wiki/fico/concepts/应付暂估]]

## 和现有知识的关系
- 本资料深化了 [[wiki/fico/concepts/GRIR 自动清账]]，区分了自动清账和重分类的边界。
- 与 [[wiki/fico/sources/财务月结操作]] 的 `F.13` 总账未清科目清账步骤直接相关。

## 后续动作
- 后续可补充 `F.19` 配置和科目映射示例。
