---
module: fico
kind: source
updated: 2026-07-15
source_count: 1
tags: []
---

# SAP FICO物料价格控制

## 来源信息
- 来源类型：pdf
- 原始位置：`raw/sd/article/202607/SAP FICO物料价格控制_sap s+3 v+2.pdf`
- 解析位置：`.claudian/tmp/pdf_extract/sd_202607/SAP FICO物料价格控制_sap s+3 v+2/SAP FICO物料价格控制_sap s+3 v+2.md`
- 解析工具：`opendataloader-pdf`
- 适用模块：FICO / MM

## 一句话结论
物料价格控制中的 `S+3` 和 `V+2` 会影响物料移动计价、差异归集以及是否参与实际成本核算；生产或采购物料不应随意在标准价和移动平均价之间切换。

## 关键内容
- SAP 物料价格控制常见为 `S` 标准价格和 `V` 移动平均价。
- 价格确定常见组合包括 `S+3` 和 `V+2`。
- 通过 `CKMM` 可以修改物料价格控制和价格确定，但有库存或历史业务时风险较高。
- 从 `S+3` 改为 `V+2` 时，系统会提示差异不再分配，因为物料不再参与实际成本核算。
- `MR21` 可用于维护物料价格，但价格维护与物料分类账、库存估价、差异处理要一起评估。

## 实务判断
- 新物料且无库存、无历史业务时，价格控制调整风险较低。
- 已有库存或已发生采购、收货、发票、生产入库的物料，不建议随意切换价格控制。
- 标准价物料的采购价差异通常进入差异科目，后续通过物料分类账或订单结算处理。

## 相关实体
- [[wiki/fico/entities/CKMM]]
- [[wiki/fico/entities/MR21]]
- [[wiki/fico/entities/MR22]]
- [[wiki/fico/entities/CKMLCP]]

## 相关概念
- [[wiki/fico/concepts/物料价格控制]]
- [[wiki/fico/concepts/物料分类账差异处理]]
