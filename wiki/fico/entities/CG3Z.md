---
module: fico
kind: entity
updated: 2026-07-15
source_count: 1
tags: []
---

# CG3Z

## 定义
`CG3Z` 是 SAP 中用于将本地文件上传到应用服务器的事务码。

## 作用
- 将本地文件上传到 SAP 应用服务器指定路径。
- 在科目主数据批量扩充场景中，可把 `FS15` 生成并下载的科目主数据文件上传到目标服务器。
- 上传后可由 `FS16` 在目标端接收并导入。

## 相关对象
- [[wiki/fico/entities/FS15]]
- [[wiki/fico/entities/FS16]]
- [[wiki/fico/entities/CG3Y]]

## 相关概念
- [[wiki/fico/concepts/会计科目主数据]]

## 参考来源
- [[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]]
