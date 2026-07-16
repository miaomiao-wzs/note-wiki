---
module: sd
kind: source
updated: 2026-07-15
source_count: 1
tags: []
---

# SD销售退货开票发货业务笔记

## 来源信息
- 来源类型：markdown
- 原始位置：`raw/sd/article/202607/SD.md`
- 适用模块：SD / FICO / QM / WMS

## 一句话结论
该资料记录了销售退货、销售开票、销售发货以及部分医药行业客户资质和 WMS 对接场景，重点是区分 EC、SAP、WMS、OA、质量资质维护之间的责任边界。

## 关键内容
### 销售退货
- EC 可根据正向发货订单创建销售退货订单；SAP 中也可通过 `ZSDU006` 参考创建。
- 退货订单推送 SAP 后，批次信息可能未对接，需要按公司和 WMS 场景补充退货批次。
- 医药公司通常通过 `ZJM_SD002` 推送退货申请到 WMS，再由 WMS 回传退货交货单和质量入库复核单。
- 非医药公司可在 SAP 手工用 `VL01N` 创建退货交货单，并在 `VL02N` 过账收货。

### 销售开票
- 用户在 OA 发起开票申请，财务收到流程后在 SAP 开票。
- EC 获取已开票数量时，以 `ZFIR043` 维护的金税票数量为准。
- 商务根据可开票数量发起 OA 开票申请。

### 销售发货
- 统销客户需在 EC 做商业备案，并由质量管理部门在 SAP 中维护客户资质。
- 药监局等无资质客户发货时，需要在 MDM、BP / `ZMMU010`、`ZQMU011`、`ZQMU009` 等环节处理客户、销售视图和资质范围。

## 相关实体
- [[wiki/sd/entities/ZSDU006]]
- [[wiki/sd/entities/ZJM_SD002]]
- [[wiki/sd/entities/VL01N]]
- [[wiki/sd/entities/VL02N]]
- [[wiki/fico/entities/ZFIR043]]

## 相关概念
- [[wiki/sd/concepts/销售退货]]
- [[wiki/sd/concepts/销售开票]]
- [[wiki/sd/concepts/销售发货]]
- [[wiki/sd/concepts/SD客户资质校验]]
