---
module: abap
kind: concept
updated: 2026-07-15
source_count: 1
tags: []
---

# ABAP 异常处理

## 概念定义
ABAP 异常处理是在程序运行过程中对错误、异常状态和业务不可继续条件进行捕获、传播、处理和记录的机制。

## 为什么重要
- 避免程序因未处理错误直接短转储。
- 让业务错误有明确处理路径，而不是散落在各处。
- 保证文件、数据库连接、锁等资源在异常后得到释放。
- 提升问题定位效率。

## 工作机制 / 处理流程
1. 高风险代码抛出异常或返回错误状态。
2. 异常沿调用栈传播。
3. 上层代码通过 `CATCH` 或 `SY-SUBRC` 判断捕获错误。
4. 程序根据错误类型提示用户、写日志、释放资源或终止处理。

## 相关实体
- [[wiki/abap/entities/CX_ROOT]]
- [[wiki/abap/entities/SE24]]
- [[wiki/abap/entities/SE91]]

## 相关概念
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/传统异常处理]]
- [[wiki/abap/concepts/TRY CATCH CLEANUP]]
- [[wiki/abap/concepts/异常链]]

## 参考来源
- [[wiki/abap/sources/ABAP 异常处理基础与核心概念]]
