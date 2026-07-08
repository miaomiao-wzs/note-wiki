---
module: fico
kind: concept
updated: 2026-07-07
source_count: 1
tags: []
---

# CO-PA 获利能力分析

## 概念定义
CO-PA 获利能力分析用于按产品、客户、渠道、销售区域等维度分析收入、成本和毛利。

## 为什么重要
- 主营业务成本是否进入 CO-PA 会影响毛利率分析。
- 如果主营业务成本科目未创建成本要素，CO-PA 可能无法取得成本数据。
- 制造业、贸易行业等需要多维度盈利分析时通常依赖 CO-PA。

## 工作机制 / 处理流程
1. 主营业务成本科目需设置为 P 类型并创建合适的成本要素。
2. SD 发货或开票相关凭证将成本数据同步到 CO。
3. CO-PA 按产品、客户、渠道、销售区域等维度分析毛利。

## 相关实体
- [[wiki/fico/entities/FS00]]
- [[wiki/fico/entities/VF01]]

## 相关概念
- [[wiki/fico/concepts/主营业务成本科目与成本要素]]
- [[wiki/fico/concepts/成本要素类别]]

## 参考来源
- [[wiki/fico/sources/主营业务成本科目是否勾选成本要素]]
