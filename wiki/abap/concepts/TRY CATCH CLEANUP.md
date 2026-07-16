---
module: abap
kind: concept
updated: 2026-07-15
source_count: 1
tags: []
---

# TRY CATCH CLEANUP

## 概念定义
`TRY...CATCH...CLEANUP` 是 ABAP 基于类异常处理中用于监控、捕获和清理异常的结构化控制流。

## 为什么重要
- `TRY` 明确标记高风险代码边界。
- `CATCH` 按异常类型处理不同错误。
- `CLEANUP` 确保异常传播时仍执行必要清理。

## 工作机制 / 处理流程
1. 在 `TRY` 块中放置可能抛出异常的代码。
2. 在 `CATCH` 块中从具体异常到通用异常逐层捕获。
3. 在 `CLEANUP` 块中释放资源、关闭文件或清理锁。
4. 异常未被处理时继续向上层传播。

## 相关实体
- [[wiki/abap/entities/CX_ROOT]]

## 相关概念
- [[wiki/abap/concepts/ABAP 异常处理]]
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/异常链]]

## 参考来源
- [[wiki/abap/sources/ABAP 异常处理基础与核心概念]]
