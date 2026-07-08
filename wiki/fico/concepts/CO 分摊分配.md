---
module: fico
kind: concept
updated: 2026-07-07
source_count: 1
tags: []
---

# CO 分摊分配

## 概念定义
CO 分摊分配用于在成本中心之间转移和分配费用。分摊使用次级成本要素，分配保留原始初级成本要素。

## 为什么重要
- 用于成本中心期末费用归集和分摊。
- 不同处理方式会影响是否保留原始费用科目明细。
- 分摊依据可以来自统计指标、成本要素、实际作业或固定比例。

## 工作机制 / 处理流程
1. 创建或维护分摊循环。
2. 在循环中设置段，每个段包含发送方和接收方。
3. 配置发送方规则、接收方规则和追踪因子。
4. 维护统计指标或实际作业等基础数据。
5. 通过 `KSU5` 测试运行并正式执行。

## 相关实体
- [[wiki/fico/entities/KSU1]]
- [[wiki/fico/entities/KSU5]]
- [[wiki/fico/entities/KK01]]
- [[wiki/fico/entities/KB31N]]

## 相关概念
- [[wiki/fico/concepts/统计指标]]
- [[wiki/fico/concepts/实际作业分摊]]

## 参考来源
- [[wiki/fico/sources/CO 分摊分配配置说明]]
