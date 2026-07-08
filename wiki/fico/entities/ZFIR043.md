---
module: fico
kind: entity
updated: 2026-07-08
source_count: 1
tags: []
---

# ZFIR043

## 定义
`ZFIR043` 是维护金税发票与系统形式发票关系的自开发事务码。

## 作用
- 维护金税发票号与系统形式发票号之间的对应关系。
- 可在金税发票作废、红冲或重新开票后更新对应关系。
- 与 `ZFIU026` 是否已开通金税发票相关，操作模式可选择新增或修改。

## 相关对象
- [[wiki/fico/entities/ZFIU026]]
- [[wiki/fico/entities/VF01]]
- [[wiki/fico/entities/VF11]]

## 相关概念
- [[wiki/fico/concepts/金税发票关系维护]]
- [[wiki/fico/concepts/形式发票]]
- [[wiki/fico/concepts/金税发票]]

## 参考来源
- [[wiki/fico/sources/ZFIR043维护金税发票与形式发票关系]]
- [[wiki/fico/sources/金税发票冲销作废]]

