---
module: abap
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# CX_DYNAMIC_CHECK

## 定义
`CX_DYNAMIC_CHECK` 是 ABAP 基于类异常体系中的动态检查异常基类。

## 作用
- 表示主要在运行时检查的异常。
- 适合数据库操作失败、权限不足等运行期错误场景。
- 通常建议显式捕获和处理。

## 相关对象
- [[wiki/abap/entities/CX_ROOT]]
- [[wiki/abap/entities/CX_STATIC_CHECK]]
- [[wiki/abap/entities/CX_NO_CHECK]]

## 相关概念
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/ABAP 异常处理]]

## 参考来源
- [[wiki/abap/sources/ABAP 异常处理基础与核心概念]]
