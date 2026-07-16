---
module: sd
kind: source
updated: 2026-07-15
source_count: 1
tags: []
---

# SAP SD非常见配置点

## 来源信息
- 来源类型：pdf
- 原始位置：`raw/sd/article/202607/SAP SD非常见配置点.pdf`
- 解析位置：`.claudian/tmp/pdf_extract/sd_202607/SAP SD非常见配置点/SAP SD非常见配置点.md`
- 解析工具：`opendataloader-pdf`
- 适用模块：SD

## 一句话结论
SD 非常见配置多集中在凭证状态更新、拒绝原因、库存地点确定、交货类型、开票类型、文本控制、税收确定、销售状态、订单原因、不完整日志和合并交货条件等细节控制点。

## 关键配置点
- `OVLY`：按销售凭证类型定义交货计划，影响服务类订单是否被错误判定为需交货。
- `V_TVAG`：定义拒绝原因，控制拒绝行项目是否计入抬头净值、统计和开票清单。
- `OVLQ`：根据装运点、工厂、存储条件确定默认拣配地点 / 库存地点。
- `VOLF`：定义交货类型，控制是否必须有销售订单、是否允许新增交货行。
- `VOFA`：定义开票类型，控制开票后是否自动过账到会计。
- `VOTXN`：定义文本控制，控制文本是否复制到下游单据。
- `OVK6`：分配税收确定的交货工厂。
- `VOF3`：按销售组织、分销渠道、产品组、订单原因分配成本中心。
- `VAUP`：将销售凭证类型和销售组织分配给订单原因，减少业务人员选错。
- `OVA2`：交货单不完整控制，可在保存、开票、过账发货等节点检查必填字段。
- `VBX1`：销售订单合并交货的复制控制条件。

## 相关实体
- [[wiki/sd/entities/OVLY]]
- [[wiki/sd/entities/V_TVAG]]
- [[wiki/sd/entities/OVLQ]]
- [[wiki/sd/entities/VOFA]]
- [[wiki/sd/entities/VOTXN]]
- [[wiki/sd/entities/OVK6]]
- [[wiki/sd/entities/VOF3]]
- [[wiki/sd/entities/VAUP]]
- [[wiki/sd/entities/OVA2]]
- [[wiki/sd/entities/VBX1]]

## 相关概念
- [[wiki/sd/concepts/SD非常见配置点]]
- [[wiki/sd/concepts/不完整性检查]]
- [[wiki/sd/concepts/文档流]]
- [[wiki/sd/concepts/销售凭证复制控制]]
