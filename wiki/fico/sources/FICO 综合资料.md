---
module: fico
kind: source
updated: 2026-07-08
source_count: 1
tags: []
---

# FICO 综合资料

## 来源信息
- 来源类型：article
- 原始位置：`raw/fico/article/202607/FICO.docx`
- 语言：中文
- 适用模块：FICO

## 一句话结论
`FICO.docx` 是一份 FICO 综合型资料，混合记录了报表勾稽关系、常用事务码、资产、成本、物料分类账、GR/IR、WBS、接口、凭证冲销、账龄、月结复盘等大量知识碎片，适合作为后续校正实体页和专题综合页的资料池。

## 关键内容
- 报表勾稽：资产负债表、利润表、现金流量表之间存在期初/期末、净利润、未分配利润、货币资金等勾稽关系。
- 常用事务码：资料列出大量 FICO、MM、SD、CO、PS 相关事务码，如 `MIRO`、`MIR6`、`MR8M`、`FB03`、`FB08`、`VF11`、`AFAB`、`FAGL_FCV`、`FAGLF101`、`FAGLGVTR`、`CKMLCP`、`CJ20N` 等。
- 资产管理：包含资产折旧、资产报废、资产转移、历史资产、计划外折旧、资产报表、资产与 EAS 接口等内容。
- 成本管理：包含成本中心、成本对象、作业类型、作业价格、标准成本、成本月结、生产订单差异、物料分类账差异处理等内容。
- 应收应付：包含客户/供应商余额、账龄、清账、回款认领、预付款、供应商付款、采购发票校验等内容。
- GR/IR：包含 MR11、F.13、F.19、GR/IR 重分类、暂估应付和采购收货/来票差异处理。
- 销售开票：包含形式发票、金税发票、POD、VF01/VF02/VFX3/VF11、开票差异调整等内容。
- 项目/WBS：包含 WBS 创建、结算规则、CJ8G/CJ88、项目成本明细和 WBS 批量处理等内容。
- 凭证冲销：按总账凭证、清账凭证、销售发票、采购发票、资产凭证、物料账、项目结算、CO 分摊等场景区分冲销事务码。
- 系统接口：包含 SAP 与 EAS、OA、销管、EC 等外围系统之间的部分接口函数、通信信道和业务逻辑。

## 相关实体
- [[wiki/fico/entities/MIRO]]
- [[wiki/fico/entities/MR8M]]
- [[wiki/fico/entities/FAGL_FCV]]
- [[wiki/fico/entities/FAGLF101]]
- [[wiki/fico/entities/CKMLCP]]
- [[wiki/fico/entities/CJ20N]]
- [[wiki/fico/entities/ZFIR043]]
- [[wiki/fico/entities/ZFIU010]]

## 相关概念
- [[wiki/fico/concepts/财务月结]]
- [[wiki/fico/concepts/财务年结]]
- [[wiki/fico/concepts/成本中心]]
- [[wiki/fico/concepts/物料分类账差异处理]]
- [[wiki/fico/concepts/GRIR 自动清账]]
- [[wiki/fico/concepts/销售开票]]
- [[wiki/fico/concepts/凭证冲销]]

## 和现有知识的关系
- 本资料不是单一操作手册，而是综合笔记，适合用于校正和扩展既有实体页、概念页。
- 已在前面批次中被拆分吸收到多个主题：发票校验、销售开票、月结年结、成本资产、WBS、金税发票等。
- 对其中未确认或过于零散的内容，暂不直接覆盖已有结论；后续按专题逐步核实。

## 后续动作
- 后续可从本资料继续拆出“FICO 常用事务码速查”“凭证冲销场景对照”“成本月结问题排查”“GR/IR 专题”等综合页。
