---
module: abap
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# CX_ROOT

## 定义
`CX_ROOT` 是 ABAP 基于类异常体系中所有异常类的根类。

## 作用
- 为 ABAP 异常对象提供统一父类。
- 支持通过引用变量接收不同具体异常类。
- 提供异常文本、异常上下文和异常链等基础能力。

## 相关对象
- [[wiki/abap/entities/CX_STATIC_CHECK]]
- [[wiki/abap/entities/CX_DYNAMIC_CHECK]]
- [[wiki/abap/entities/CX_NO_CHECK]]

## 相关概念
- [[wiki/abap/concepts/ABAP 异常处理]]
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/异常链]]

## 参考来源
- [[wiki/abap/sources/ABAP 异常处理基础与核心概念]]
