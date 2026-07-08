---
module: fico
kind: source
updated: 2026-07-07
source_count: 1
tags: []
---

# CO 分摊分配配置说明

## 来源信息
- 来源类型：article
- 原始位置：`raw/fico/article/202607/CO 分摊分配配置说明.md`
- 语言：中文
- 适用模块：FICO

## 一句话结论
CO 分摊和分配都用于成本中心费用分摊，但分摊使用次级成本要素、分配保留原始初级成本要素，二者适用场景不同。

## 关键内容
- 分摊（Assessment）使用次级成本要素，适合不需要追溯原始费用科目的场景。
- 分配（Distribution）保留初级成本要素，适合需要保留原始费用明细的场景。
- 分摊循环由 Cycle 和 Segment 组成，每个段包含发送方和接收方规则。
- 接收方追踪因子可使用统计指标、成本要素、实际作业或固定百分比。
- 统计指标可用 `KK01` 创建，用 `KB31N` 录入数据。
- 实际作业分摊依赖接收方成本中心的作业类型消耗记录和作业类型价格。
- `KSU5` 用于执行分摊循环，也可用于冲销。

## 相关实体
- [[wiki/fico/entities/KSU5]]
- [[wiki/fico/entities/KSU1]]
- [[wiki/fico/entities/KK01]]
- [[wiki/fico/entities/KB31N]]

## 相关概念
- [[wiki/fico/concepts/CO 分摊分配]]
- [[wiki/fico/concepts/统计指标]]
- [[wiki/fico/concepts/实际作业分摊]]

## 和现有知识的关系
- 这是第一轮 FICO Markdown 原始资料整理，尚未发现与已有 wiki 结论冲突。
- 该资料适合后续扩展为成本中心期末分摊专题。

## 后续动作
- 后续可补充 `KSU1`、`KSU5`、`KK01`、`KB31N` 等实体页。
- 后续可建立“分摊 vs 分配”的对比页。
