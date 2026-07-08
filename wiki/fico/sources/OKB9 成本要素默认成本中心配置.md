---
module: fico
kind: source
updated: 2026-07-07
source_count: 1
tags: []
---

# OKB9 成本要素默认成本中心配置

## 来源信息
- 来源类型：article
- 原始位置：`raw/fico/article/202607/OKB9 成本要素默认成本中心配置.md`
- 语言：中文
- 适用模块：FICO

## 一句话结论
`OKB9` 用于为成本要素设置默认成本中心，在用户未手工输入成本中心且没有更高优先级规则时，系统自动带出默认成本中心。

## 关键内容
- `OKB9` 的核心用途是为成本要素设置默认成本中心，避免 FI 凭证过账时报“成本中心必填”。
- 常见场景包括费用类科目过账、费用性采购、物料差异科目和 GR/IR 科目。
- `OKB9` 默认值优先级最低，会被手工填写、订单/WBS 结算规则、替代规则（`OBBH`）覆盖。
- 不启用物料分类账时，差异科目可通过 `OKB9` 按公司分配到成本中心。
- 启用物料分类账后，差异处理更多依赖 `CKMLCP`，通常不再依赖 `OKB9`。

## 相关实体
- [[wiki/fico/entities/OKB9]]
- [[wiki/fico/entities/OBBH]]
- [[wiki/fico/entities/CKMLCP]]

## 相关概念
- [[wiki/fico/concepts/成本要素默认成本中心]]
- [[wiki/fico/concepts/物料分类账差异处理]]

## 和现有知识的关系
- 这是第一轮 FICO Markdown 原始资料整理，尚未发现与已有 wiki 结论冲突。
- 文档中存在 `images/` 图片引用，当前未迁移到 `raw/assets/`，后续可单独处理图片归档。

## 后续动作
- 后续可补充 `OBBH`、`CKMLCP` 实体页。
- 后续可对比“不启用物料分类账”和“启用物料分类账”下差异处理逻辑。
