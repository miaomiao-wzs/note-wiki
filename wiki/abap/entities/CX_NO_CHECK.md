---
module: abap
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# CX_NO_CHECK

## 定义
`CX_NO_CHECK` 是 ABAP 基于类异常体系中的非检查异常基类。

## 作用
- 表示调用方不被强制声明或捕获的异常。
- 常用于较难恢复或不适合逐层声明的系统性错误。
- 使用时应谨慎，避免掩盖需要业务处理的错误。

## 相关对象
- [[wiki/abap/entities/CX_ROOT]]
- [[wiki/abap/entities/CX_STATIC_CHECK]]
- [[wiki/abap/entities/CX_DYNAMIC_CHECK]]

## 相关概念
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/ABAP 异常处理]]

## 参考来源
- [[wiki/abap/sources/ABAP 异常处理基础与核心概念]]
