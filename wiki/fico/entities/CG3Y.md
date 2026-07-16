---
module: fico
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# CG3Y

## 定义
`CG3Y` 是 SAP 中用于从应用服务器下载文件到本地的事务码。

## 作用
- 将应用服务器上的文件下载到本地电脑。
- 在科目主数据批量扩充场景中，可下载 `FS15` 生成的源文件。
- 常与 `CG3Z` 配合，用于服务器文件迁移。

## 相关对象
- [[wiki/fico/entities/FS15]]
- [[wiki/fico/entities/FS16]]
- [[wiki/fico/entities/CG3Z]]

## 相关概念
- [[wiki/fico/concepts/会计科目主数据]]

## 参考来源
- [[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]]
