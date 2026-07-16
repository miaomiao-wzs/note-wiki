---
module: fico
kind: source
updated: 2026-07-15
source_count: 1
tags: []
---

# SAP F.19 GRIR重分类

## 来源信息
- 来源类型：markdown
- 原始位置：`raw/fico/article/202607/SAP F.19 GRIR重分类.md`
- 适用模块：FICO / MM

## 一句话结论
`F.19` 不是用来清掉 GR/IR 余额，而是在月末关键日期把 GR/IR 借贷方未清差异按经济实质重分类，避免资产和负债在资产负债表上被错误抵销。

## 关键内容
- GR/IR 贷方余额通常代表“已收货未收票”，本质偏负债，应考虑列报为应付暂估等负债类项目。
- GR/IR 借方余额通常代表“已收票未收货”，本质偏资产，应考虑列报为在途物资等资产类项目。
- `F.13` 负责自动清账，`F.19` 负责重分类，两者目的不同。
- 重分类通常在月末执行，并在次月初自动冲回，避免影响原始采购业务链条。
- 如果业务已经完结但 GR/IR 仍有异常余额，应先分析是否需要用 `MR11` 等方式处理，而不是简单依赖重分类。

## 相关实体
- [[wiki/fico/entities/F.19]]
- [[wiki/fico/entities/F.13]]
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
- 本资料补充了 [[wiki/fico/sources/GRIR重分类详解]] 中对 `F.19` 的定位说明。
- 回答“GR/IR 重分类是什么意思”时，应优先说明清账和重分类的边界。
