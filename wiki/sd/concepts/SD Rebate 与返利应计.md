---
module: sd
kind: concept
updated: 2026-07-23
source_count: 1
tags: [rebate, 返利]
---

# SD Rebate 与返利应计

## 概念定义
SD Rebate 是根据客户、物料、销售组织或采购额等条件，按协议计算返利应计，并在约定期间执行部分或最终结算的机制。

## 核心链路
`返利协议 → 开票时应计 → 阶梯/追溯调整 → 返利结算 → 贷项凭证与 FI 冲销`

## 对账重点
- 协议有效期和结算日期范围。
- 发票、退货、贷项凭证是否都被纳入或反向处理。
- Scale 档位变化和 Retroactive Accrual。
- 已计提金额、最终返利和结算凭证状态。

## 参考来源
- [[wiki/sd/sources/SD Rebate]]
