---
module: sd
kind: overview
updated: 2026-07-15
source_count: 15
tags: []
---

# SD 模块总览

这个模块用于沉淀 SAP SD（Sales and Distribution，销售与分销）相关知识，当前重点覆盖销售订单处理、销售退货、销售发货、销售开票、ATP、客户资质、物料销售视图和 SD 相关配置。

## 结构

- `entities/`
- `concepts/`
- `comparisons/`
- `sources/`
- `synthesis/`

## 常用入口

- [[wiki/sd/sources/raw资料清单]]：SD 原始资料清单
- [[wiki/sd/sources/SAP S4HANA销售订单处理（从询价到合同）]]：销售订单处理来源页
- [[wiki/sd/sources/SD销售退货开票发货业务笔记]]：销售退货、开票和发货业务笔记
- [[wiki/sd/sources/物料扩充销售视图]]：物料销售视图扩充
- [[wiki/sd/sources/江西康莱特胶囊注射液手动 ATP 操作手册]]：手动 ATP 操作
- [[wiki/sd/sources/销售下单客户资质校验业务逻辑]]：客户资质校验逻辑
- [[wiki/sd/sources/销售退货物料移动类型配置]]：销售退货移动类型配置
- [[wiki/sd/sources/SAP SD非常见配置点]]：SD 非常见配置点
- [[wiki/sd/entities/VA01]]：创建销售凭证
- [[wiki/sd/entities/VA02]]：修改销售凭证
- [[wiki/sd/entities/VA03]]：显示销售凭证
- [[wiki/sd/concepts/销售订单]]：销售订单核心概念
- [[wiki/sd/concepts/销售退货]]：销售退货
- [[wiki/sd/concepts/销售发货]]：销售发货
- [[wiki/sd/concepts/SD客户资质校验]]：客户资质校验
- [[wiki/sd/concepts/SD物料销售视图]]：物料销售视图
- [[wiki/sd/concepts/销售ATP确认]]：ATP 确认

## 已整理来源

| 原始资料 | 对应来源页 |
| --- | --- |
| `raw/sd/article/202607/SAP S4HANA销售订单处理（从询价到合同）.md` | [[wiki/sd/sources/SAP S4HANA销售订单处理（从询价到合同）]] |
| `raw/sd/article/202607/SD.md` | [[wiki/sd/sources/SD销售退货开票发货业务笔记]] |
| `raw/sd/article/202607/业务流程.md` | [[wiki/sd/sources/SD业务流程与事务码碎片]] |
| `raw/sd/article/202607/山禾医药迎检新建物料注意事项.md` | [[wiki/sd/sources/山禾医药迎检新建物料注意事项]] |
| `raw/sd/article/202607/恒生委外销售订单操作手册.md` | [[wiki/sd/sources/恒生委外销售订单操作手册]] |
| `raw/sd/article/202607/恒生销售到九华sap订单操作手册.md` | [[wiki/sd/sources/恒生销售到九华sap订单操作手册]] |
| `raw/sd/article/202607/江西康莱特EC推送订单是否过量重复下单判断.md` | [[wiki/sd/sources/江西康莱特EC推送订单是否过量重复下单判断]] |
| `raw/sd/article/202607/江西康莱特胶囊注射液手动 ATP 操作手册.md` | [[wiki/sd/sources/江西康莱特胶囊注射液手动 ATP 操作手册]] |
| `raw/sd/article/202607/物料件数维护操作手册.md` | [[wiki/sd/sources/物料件数维护操作手册]] |
| `raw/sd/article/202607/物料扩充销售视图.md` | [[wiki/sd/sources/物料扩充销售视图]] |
| `raw/sd/article/202607/销售下单客户资质校验业务逻辑.md` | [[wiki/sd/sources/销售下单客户资质校验业务逻辑]] |
| `raw/sd/article/202607/销售退货物料移动类型配置.md` | [[wiki/sd/sources/销售退货物料移动类型配置]] |
| `raw/sd/article/202607/SAP SD非常见配置点.pdf` | [[wiki/sd/sources/SAP SD非常见配置点]] |

## 核心概念

- [[wiki/sd/concepts/销售订单]]
- [[wiki/sd/concepts/售前单据]]
- [[wiki/sd/concepts/框架协议]]
- [[wiki/sd/concepts/特殊销售订单类型]]
- [[wiki/sd/concepts/文档流]]
- [[wiki/sd/concepts/销售凭证复制控制]]
- [[wiki/sd/concepts/不完整性检查]]
- [[wiki/sd/concepts/销售退货]]
- [[wiki/sd/concepts/销售开票]]
- [[wiki/sd/concepts/销售发货]]
- [[wiki/sd/concepts/SD客户资质校验]]
- [[wiki/sd/concepts/SD物料销售视图]]
- [[wiki/sd/concepts/销售ATP确认]]
- [[wiki/sd/concepts/销售退货移动类型]]
- [[wiki/sd/concepts/SD非常见配置点]]

## 当前状态

`raw/sd/` 当前 15 个有效原始资料已完成本轮整理。后续新增 SD 原始资料后，继续按 `raw/sd/<type>/<YYYYMM>/` 归档，再整理到 `wiki/sd/sources/`，并根据内容补充实体页、概念页、对比页或综合页。
