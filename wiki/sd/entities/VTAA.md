---
module: sd
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# VTAA

## 定义
`VTAA` 是 SAP SD 中维护销售凭证到销售凭证复制控制的配置事务码。

## 作用
- 控制询价到报价、报价到订单、合同到释放订单等销售凭证间复制逻辑。
- 影响前序凭证数据如何带入后续凭证。
- 可结合完成规则、复制需求和数据传输例程控制业务链路。

## 相关对象
- [[wiki/sd/entities/VA11]]
- [[wiki/sd/entities/VA21]]
- [[wiki/sd/entities/VA01]]
- [[wiki/sd/entities/VA41]]

## 相关概念
- [[wiki/sd/concepts/销售凭证复制控制]]
- [[wiki/sd/concepts/文档流]]
- [[wiki/sd/concepts/售前单据]]

## 参考来源
- [[wiki/sd/sources/SAP S4HANA销售订单处理（从询价到合同）]]
