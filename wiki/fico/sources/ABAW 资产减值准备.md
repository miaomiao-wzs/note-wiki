---
module: fico
kind: source
updated: 2026-07-07
source_count: 1
tags: []
---

# ABAW 资产减值准备

## 来源信息
- 来源类型：article
- 原始位置：`raw/fico/article/202607/ABAW 资产减值准备.md`
- 语言：中文
- 适用模块：FICO

## 一句话结论
固定资产减值准备建议通过 `ABAW` 的资产重估方式处理，避免只做手工总账凭证导致资产子账与总账不一致。

## 关键内容
- 资产减值有三种处理思路：`ABAW` 资产重估减值、`ABAA` 计划外折旧、`F-02` / `FB50` 手工总账凭证。
- 文档推荐使用 `ABAW`，因为它能更新资产卡片并保持子账与总账一致。
- 使用 `ABAW` 前需要完成 `OABW`、`OAYR`、`AO84`、`AO90` 等配置。
- `ABAW` 过账后先更新资产子模块，总账凭证通常在月底运行 `AFAB` 后生成。
- 错误凭证可通过 `AB08` 冲销。
- 常见报错包括 `AA629` 和 `AA816`，通常与事务类型、折旧范围负值、总账科目分配有关。

## 相关实体
- [[wiki/fico/entities/ABAW]]
- [[wiki/fico/entities/AB08]]
- [[wiki/fico/entities/AO90]]
- [[wiki/fico/entities/AFAB]]

## 相关概念
- [[wiki/fico/concepts/资产减值准备]]
- [[wiki/fico/concepts/固定资产重估]]

## 和现有知识的关系
- 这是第一轮 FICO Markdown 原始资料整理，尚未发现与已有 wiki 结论冲突。
- 文档中存在 `images/` 图片引用，当前未迁移到 `raw/assets/`，后续可单独处理图片归档。

## 后续动作
- 后续可补充固定资产减值的完整操作清单页。
- 后续可补充 `AO84`、`OABW`、`OAYR` 等实体页。
