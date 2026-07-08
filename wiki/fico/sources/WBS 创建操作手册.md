---
module: fico
kind: source
updated: 2026-07-08
source_count: 1
tags: []
---

# WBS 创建操作手册

## 来源信息
- 来源类型：article
- 原始位置：`raw/fico/article/202607/WBS 创建操作手册.docx`
- 语言：中文
- 适用模块：FICO / PS

## 一句话结论
WBS 创建操作手册说明了通过 `CJ20N` 创建项目定义、WBS 元素、公司标识型 WBS 编码，并下达项目状态到 `REL` 的基本步骤。

## 关键内容
- 使用事务码 `CJ20N` 进入项目创建界面。
- 新增项目时维护项目定义、项目参数文件、公司代码、利润中心等字段。
- 创建第二层 WBS 时维护 WBS 元素字段和项目类型字段。
- WBS 元素编码中可追加 `.2010` 等公司标识，用于区分所属公司。
- 需要勾选科目分配元素，使 WBS 可作为成本对象使用。
- 创建完成后在项目状态中执行下达，并检查 WBS 状态为 `REL`。

## 相关实体
- [[wiki/fico/entities/CJ20N]]

## 相关概念
- [[wiki/fico/concepts/WBS 元素]]
- [[wiki/fico/concepts/项目成本对象]]
- [[wiki/fico/concepts/科目分配元素]]

## 和现有知识的关系
- 本资料补充了费用凭证、资产主数据和成本对象中的 WBS 使用前提。
- 与 [[wiki/fico/sources/凭证记账]] 中“费用科目需要输入成本对象，成本中心或 WBS 二选一”直接相关。

## 后续动作
- 后续可在 PS 模块扩展项目定义、WBS 结算规则和项目结算专题。
