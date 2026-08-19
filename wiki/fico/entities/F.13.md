---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# F.13

## 定义
`F.13` 是 SAP FI 中自动清账事务码。

## 作用
- 月结时用于总账未清科目清账，主要是 GR/IR 应付暂估科目。
- 清理收货与发票已匹配但未清账的项目。
- **必须在 F.19 重分类之前执行**：跳过 F.13 直接跑 F.19，已匹配的 GR/IR 未清项目会被错误调整到报表科目。
- 可先测试运行，确认后取消测试运行正式执行。

## 相关概念
- [[wiki/fico/concepts/GRIR 自动清账]]
- [[wiki/fico/concepts/财务月结]]

## 参考来源
- [[wiki/fico/sources/财务月结操作]]

