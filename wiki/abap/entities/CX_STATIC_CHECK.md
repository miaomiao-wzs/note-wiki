---
module: abap
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# CX_STATIC_CHECK

## 定义
`CX_STATIC_CHECK` 是 ABAP 基于类异常体系中的静态检查异常基类。

## 作用
- 表示编译器要求显式声明或捕获的异常。
- 适合用于调用者必须处理的可预期业务或技术错误。
- 常用于自定义异常类的父类。

## 相关对象
- [[wiki/abap/entities/CX_ROOT]]
- [[wiki/abap/entities/CX_DYNAMIC_CHECK]]
- [[wiki/abap/entities/CX_NO_CHECK]]

## 相关概念
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/ABAP 异常处理]]

## 参考来源
- [[wiki/abap/sources/ABAP 异常处理基础与核心概念]]
