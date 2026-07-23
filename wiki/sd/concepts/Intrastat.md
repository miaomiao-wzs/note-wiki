---
module: sd
kind: concept
updated: 2026-07-23
source_count: 1
tags: [intrastat, 欧盟贸易统计]
---

# Intrastat

## 概念定义
Intrastat 是欧盟成员国之间货物流动的贸易统计申报机制，不是第三国出口报关。申报门槛、期限、字段和报送系统按国家及期间确定。

## SAP 处理视角
资料提到 `VE01`、`VE02`、`VERA`、`VEIA` 等维护、选择和生成申报数据的入口。数据可能来自发票或交货，具体取决于企业配置的货物流/发票流口径。

## 关键检查
- 物料是否维护 HS/Commodity Code、原产国和重量。
- 客户 VAT 号码、公司代码和贸易伙伴国家是否正确。
- 统计期间、交易金额、净重和补充单位是否符合当地申报要求。
- 国家门槛和申报文件格式不可直接套用其他国家案例。

## 参考来源
- [[wiki/sd/sources/SD 出口与 Intrastat]]
