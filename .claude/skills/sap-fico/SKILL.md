---
name: sap-fico
description: "Knowledge base from \"由浅入深学习SAP财务\" by 高林旭. Use when applying FICO frameworks for configuration, organizational structure design, master data management, cost controlling, profitability analysis, or referencing SAP FI/CO concepts and best practices."
allowed-tools:
  - Read
  - Grep
argument-hint: [topic, module name, or chapter number]
---

# 由浅入深学习SAP财务
**Author**: 高林旭 | **Pages**: ~549 | **Chapters**: 11 | **Generated**: 2026-05-27

## How to Use This Skill

- **Without arguments** — load core frameworks for reference
- **With a topic** — ask about `统驭科目`, `成本中心`, `折旧范围`, or another indexed topic; I find and read the relevant chapter
- **With chapter** — ask for `ch05`; I load that specific chapter
- **Browse** — ask "what chapters do you have?" to see the full index

When you ask about a topic not covered in Core Frameworks below, I will read the relevant chapter file before answering.

---

## Core Frameworks & Mental Models

### FI组织结构三层模型
- **公司代码** = 一套账（独立法人），FI的基石
- **公司** = 合并单元（公司代码之上的合并概念）
- **业务范围** = 业务归类（可高于或低于公司代码）
- Use "1个法人=1个公司代码" as default design rule
- 同一公司下的公司代码必须共用同一科目表和会计年度变式

### CO组织结构层级
- **经营范围** > **控制范围** > **公司代码**
- 控制范围 = 管理会计的边界（1对多公司代码）
- 经营范围 = 获利分析的容器（1对多控制范围）
- 控制范围的科目表和会计年度变式必须与下属公司代码一致

### 主数据双层结构
- **科目表层**（通用属性）+ **公司代码层**（特定属性）
- 客户/供应商：**基本视图** + **公司代码视图** + **销售/采购视图**
- 统驭科目是子模块与总账的桥梁（D=客户/K=供应商/A=资产）

### 费用流转模型
- **FI→CO**: 费用通过初级成本要素从FI记账传到CO
- **成本中心→工单**: 通过作业类型将制造费用输送到生产订单
- **成本中心→CO-PA**: 通过分配/分摊将销售管理费用输送到获利分析
- **内部订单→成本中心**: 非统计型订单月末结算到最终对象

### 成本核算体系
- **S价**（标准价格）= 预算思维，月末需差异还原
- **V价**（移动平均价格）= 实际思维，自动更新无须还原
- 制造件标准成本 = BOM材料成本 + 工艺路线作业成本
- 月末通过物料分类账将S价差异分摊到存货和损益

### 合并抵销逻辑
- 集团内客户/供应商必须设置**贸易伙伴**字段
- 集团科目表与操作科目表建立**组科目号**对应关系
- 合并单元按**股权投资结构**排列成树形层次

---

## Chapter Index

| # | Title | Key Frameworks |
|---|-------|----------------|
| [ch01](chapters/ch01-sap-basics.md) | SAP基础知识 | 三层架构、前台-后台分离 |
| [ch02](chapters/ch02-general-ledger.md) | 总账模块 | 科目表双层结构、公司代码-公司层级 |
| [ch03](chapters/ch03-accounts-receivable.md) | 应收模块 | 客户三视图、账户组控制、贸易伙伴 |
| [ch04](chapters/ch04-accounts-payable.md) | 应付模块 | 供应商三视图、对冲功能 |
| [ch05](chapters/ch05-asset-accounting.md) | 资产模块 | 折旧范围-折旧表层级、S/V价折旧 |
| [ch06](chapters/ch06-cost-center-accounting.md) | 成本中心会计 | 控制范围设计、费用流转模型 |
| [ch07](chapters/ch07-product-cost-controlling.md) | 产品成本控制 | S价vs V价、标准成本三步走 |
| [ch08](chapters/ch08-profitability-analysis.md) | 获利分析 | Costing-based vs Account-based、特征+值字段 |
| [ch09](chapters/ch09-internal-orders.md) | 内部订单 | 统计vs非统计、双重记账规则 |
| [ch10](chapters/ch10-consolidation.md) | 合并模块 | 合并单元-合并组层次、数据收集方式 |
| [ch11](chapters/ch11-deep-thinking.md) | 深入思考 | 组织结构四维作用、约束链 |

## Topic Index

- **公司代码** → ch02, ch11
- **科目表** → ch02, ch06
- **统驭科目** → ch02, ch03, ch04, ch05
- **客户主数据** → ch03
- **供应商主数据** → ch04
- **贸易伙伴** → ch03, ch04, ch10
- **折旧范围** → ch05
- **控制范围** → ch06, ch11
- **成本中心** → ch06
- **作业类型** → ch06, ch07
- **标准成本/价格控制** → ch07
- **物料分类账** → ch07
- **获利分析/CO-PA** → ch08
- **经营范围** → ch08, ch11
- **内部订单** → ch09
- **合并** → ch10
- **组织结构设计** → ch02, ch06, ch08, ch11

## Supporting Files

- [glossary.md](glossary.md) — all key terms with definitions
- [patterns.md](patterns.md) — design patterns and decision frameworks
- [cheatsheet.md](cheatsheet.md) — quick reference tables and transaction codes

---

## Scope & Limits

This skill covers the book content only. For hands-on SAP system configuration or ABAP development,
combine with project-specific tools. For topics beyond this book (such as Treasury, Special Purpose Ledger,
or SAP S/4HANA specific changes), check related skills or ask the agent directly.
