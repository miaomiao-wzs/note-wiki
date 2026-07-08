---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# ZFIU001

## 定义
`ZFIU001` 是凭证批量导入记账功能对应的自开发事务码。

## 作用
- 可批量导入预制凭证。
- 可批量导入过账凭证。
- 支持下载导入模板、选择导入文件、执行导入，并通过 Posting 生成会计凭证。

## 注意
原始手册的事务代码列表中出现 `ZFIC002`，但详细操作段落写的是 `ZFIU001`。根据后续业务确认，凭证批量导入记账功能以 `ZFIU001` 为准。

## 相关对象
- [[wiki/fico/entities/ZFIC002]]

## 相关概念
- [[wiki/fico/concepts/FI 凭证记账]]
- [[wiki/fico/concepts/预制凭证]]

## 参考来源
- [[wiki/fico/sources/凭证记账]]
