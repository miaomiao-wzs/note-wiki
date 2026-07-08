---
module: fico
kind: entity
updated: 2026-07-07
source_count: 1
tags: []
---

# ABAW

## 定义
`ABAW` 是 SAP 固定资产模块中用于资产重估类过账的事务码，可用于固定资产减值处理。

## 作用
- 通过资产重估方式调整固定资产账面净值。
- 在资产子模块中记录资产价值变化。
- 相比手工总账凭证，更有利于保持资产子账与总账一致。

## 相关对象
- [[wiki/fico/entities/AB08]]
- [[wiki/fico/entities/AFAB]]
- [[wiki/fico/entities/AO90]]

## 相关概念
- [[wiki/fico/concepts/资产减值准备]]
- [[wiki/fico/concepts/固定资产重估]]

## 常见问题
- `ABAW` 过账后总账凭证通常不是立即生成，而是在运行 `AFAB` 后生成。
- 如果报 `AA629` 或 `AA816`，需要检查事务类型、折旧范围和 `AO90` 科目配置。

## 参考来源
- [[wiki/fico/sources/ABAW 资产减值准备]]
