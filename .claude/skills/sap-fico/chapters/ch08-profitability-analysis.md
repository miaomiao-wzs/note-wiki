# Chapter 8: 获利分析模块

## Core Idea
获利分析（CO-PA）从多维度（客户、产品、销售组织等）分析企业盈利能力，分为基于成本核算（Costing-based）和基于会计（Account-based）两种类型。

## Frameworks Introduced
- **Costing-based vs Account-based CO-PA**: 两种获利分析类型在数据来源、存储表、分析粒度上有本质区别。
  - When to use: 选择获利分析的实现方式
  - How: Costing-based从销售订单定价过程取数据（PR00收入/VPRS成本），存CE表；Account-based从会计记账取数据，存CO业务表

- **特征+值字段数据结构**: CO-PA的数据结构由特征字段（分析维度）和值字段（分析指标）组成。
  - When to use: 设计获利分析报表的分析维度和指标
  - How: 通过KEA5定义特征字段，通过KEA6定义值字段，通过KEA0分配给经营范围

## Key Concepts
- **经营范围（Operating Concern）**: CO-PA的组织结构，对多个组织的盈利情况进行分析的范围
- **特征字段（Characteristics）**: 分析维度，如公司代码、销售组织、客户、产品组
- **值字段（Value Fields）**: 分析指标，如收入、成本、毛利
- **获利能力段（Profitability Segment）**: 特征字段值的组合
- **控制范围-经营范围关系**: 经营范围与控制范围是一对多关系

## Mental Models
- Use "Costing-based在开票时取数" to understand timing — 发货时不产生CO-PA凭证（因为此时只有成本没有收入，容易误导），开票时同时取收入和成本
- Think of 经营范围 as "分析容器" — 它定义了用什么维度（特征）和什么指标（值字段）来分析盈利
- Use "Account-based=会计视角" when choosing type — 它的数据来自会计记账，与FI保持一致，适合需要科目级明细的场景

## Anti-patterns
- **发货时就传送到CO-PA**: Costing-based模式下发货时不应传CO-PA凭证，否则只有成本没有收入，报表残缺误导
- **经营范围环境非绿灯**: 跨client部分和特定client部分都必须是绿灯状态，否则经营范围不可用
- **忽略两种CO-PA的表差异**: Costing-based存CE1XXXX~CE4XXXX，Account-based存COEJ/COEP等CO表，取数逻辑不同

## Reference Tables

### 两种CO-PA类型对比
| 维度 | Costing-based | Account-based |
|------|---------------|---------------|
| 数据来源 | 销售订单定价过程 | 会计记账 |
| 取数时点 | 开票时 | 会计记账时 |
| 存储表 | CE1XXXX~CE4XXXX | COEJ/COEP/COSS/COSP |
| 成本展开 | 可展开为料工费 | 按成本要素（科目） |
| 与FI一致性 | 不完全一致 | 完全一致 |

## Key Takeaways
1. 经营范围是CO-PA的组织结构，通过KEA0配置
2. Costing-based在开票时取收入和成本，避免发货时残缺数据误导
3. Account-based从会计记账取数据，与FI保持一致
4. 特征字段定义分析维度，值字段定义分析指标
5. 经营范围与控制范围是一对多关系，控制范围与公司代码也是一对多关系

## Connects To
- **Ch6**: 成本中心的费用通过分配/分摊输送到CO-PA用于净利分析
- **Ch7**: 产品标准成本和实际成本传送到CO-PA作为销售成本
- **Ch11**: 经营范围的组织结构约束条件是跨模块综合知识
