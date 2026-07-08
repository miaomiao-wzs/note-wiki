---
module: fico
kind: concept
updated: 2026-07-08
source_count: 1
tags: []
---

# POD

## 概念定义
POD 是交货确认相关控制点，资料中提示未做 POD 可能导致销售发票无法发布到会计。

## 为什么重要
- POD 状态会影响销售开票后续会计发布。

## 工作机制 / 处理流程
1. 销售或客户服务完成 POD。
2. 财务再执行 `VF02` 或 `VFX3` 发布至会计。

## 相关实体
- 按具体业务参见相关来源页中的事务码。

## 相关概念
- [[wiki/fico/concepts/客户收款]]

## 参考来源
- [[wiki/fico/sources/销售开票和冲销流程]]

