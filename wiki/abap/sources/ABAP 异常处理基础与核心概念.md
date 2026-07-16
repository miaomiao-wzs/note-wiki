---
module: abap
kind: source
updated: 2026-07-15
source_count: 1
tags: []
---

# ABAP 异常处理基础与核心概念

## 来源信息
- 来源类型：article
- 原始位置：`raw/abap/article/202607/ABAP 异常处理基础与核心概念.md`
- 原始来源：微信公众号文章 `SAP-ABAP：ABAP异常处理基础与核心概念 —— 从机制到实践的系统化认知`
- 语言：中文
- 适用模块：ABAP

## 一句话结论
ABAP 异常处理的核心目标是让程序在错误发生时可控、可诊断、可恢复；现代 ABAP 应优先使用基于类的异常体系，并结合 `TRY...CATCH...CLEANUP`、异常链和消息类进行结构化处理。

## 关键内容
- ABAP 异常处理用于避免程序短转储、保障资源释放、控制业务错误路径并提升调试效率。
- ABAP 异常主要分为基于类的异常和传统异常两类。
- 基于类的异常以 `CX_ROOT` 为根类，常见子类包括 `CX_STATIC_CHECK`、`CX_DYNAMIC_CHECK`、`CX_NO_CHECK`。
- 传统异常常见于函数模块 `EXCEPTIONS` 和 `SY-SUBRC` 返回码处理。
- 异常生命周期包括抛出、传播、捕获和处理。
- `TRY...CATCH...CLEANUP` 是结构化异常处理的核心控制流。
- 自定义异常类可携带业务字段，并可通过 `previous` 属性保留原始异常上下文。
- 消息类 `SE91` 可与异常处理结合，用于多语言消息和统一提示。

## 相关实体
- [[wiki/abap/entities/CX_ROOT]]
- [[wiki/abap/entities/CX_STATIC_CHECK]]
- [[wiki/abap/entities/CX_DYNAMIC_CHECK]]
- [[wiki/abap/entities/CX_NO_CHECK]]
- [[wiki/abap/entities/SE24]]
- [[wiki/abap/entities/SE91]]

## 相关概念
- [[wiki/abap/concepts/ABAP 异常处理]]
- [[wiki/abap/concepts/基于类的异常]]
- [[wiki/abap/concepts/传统异常处理]]
- [[wiki/abap/concepts/TRY CATCH CLEANUP]]
- [[wiki/abap/concepts/异常链]]

## 和现有知识的关系
- 本资料为 ABAP 模块补充第一篇有效来源页，建立异常处理主题入口。
- 后续可继续拆分为“企业级异常处理框架”“异常日志设计”“消息类与异常类结合”等专题。

## 后续动作
- 如后续新增专题二资料，可继续整理企业级异常处理框架设计。
- 如需用于开发实践，可补充自定义异常类模板和 ABAP 单元测试示例。
