---
module: fico
kind: source
updated: 2026-07-08
source_count: 1
tags: []
---

# ZFIR043维护金税发票与形式发票关系

## 来源信息
- 来源类型：article
- 原始位置：`raw/fico/article/202607/ZFIR043维护金税发票与形式发票关系.docx`
- 语言：中文
- 适用模块：FICO / SD

## 一句话结论
该资料说明了通过 `ZFIR043` 维护金税发票与系统形式发票对应关系的基本操作。

## 关键内容
- 使用事务码 `ZFIR043` 进入维护界面。
- 输入公司代码。
- 点击“维护金税发票（系统发票）”按钮进入明细界面。
- 填写公司代码和系统形式发票号。
- 如果未使用 `ZFIU026` 开通金税发票，操作模式勾选“新增”；否则勾选“修改”。
- 执行后填写对应信息，将光标点击到旁边灰色单元格后保存。

## 相关实体
- [[wiki/fico/entities/ZFIR043]]
- [[wiki/fico/entities/ZFIU026]]

## 相关概念
- [[wiki/fico/concepts/金税发票关系维护]]
- [[wiki/fico/concepts/形式发票]]
- [[wiki/fico/concepts/金税发票]]

## 和现有知识的关系
- 本资料补充了销售开票后系统形式发票与金税发票之间的维护动作。
- 与 [[wiki/fico/sources/销售开票和冲销流程]]、[[wiki/fico/sources/金税发票冲销作废]] 直接相关。

## 后续动作
- `ZFIR043维护金税发票与形式发票关系 2.docx` 内容与本资料相同，作为补充来源记录，不重复沉淀不同结论。
