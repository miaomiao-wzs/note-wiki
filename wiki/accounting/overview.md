---
module: accounting
kind: overview
updated: 2026-08-12
source_count: 6
tags: [accounting]
---

# 会计模块总览

本模块用于沉淀与 SAP/FICO 系统知识相互衔接的会计和经济法知识，重点区分规范依据与系统实现。

## 两类主题

- `economic-law`：会计法、企业财务会计报告法定要求及相关经济法律制度。
- `accounting-practice`：企业会计准则、确认计量、会计处理和财务报告实务。

## 与 FICO 的边界

- `accounting`：保存法律、法规、企业会计准则和权威会计政策资料。
- `fico`：保存 SAP 事务码、系统配置、企业操作手册、自开发报表和企业科目映射。
- 两个模块通过 wiki-link 互相引用，不复制或整体迁移既有 FICO 页面。

例如，会计准则解释“固定资产为什么计提折旧”，而 [[wiki/fico/entities/AFAB]]、[[wiki/fico/entities/AW01N]] 和 [[wiki/fico/entities/S_ALR_87011967]] 解释 SAP 中如何执行、查看和汇总。

## 结构

- `entities/`：法律、准则及其他可复用对象
- `concepts/`：会计原则、确认计量和法律制度
- `comparisons/`：准则、制度或处理方式对比
- `sources/`：权威法规、准则和原始资料整理页
- `synthesis/`：知识框架、跨模块归属和综合结论

> 说明：上述目录在当前已有页面时使用；空目录可能不会被 Git 单独记录，新增对应主题页面后再自然形成目录内容。

## 常用入口

- [[wiki/accounting/sources/raw资料清单]]：会计原始资料清单
- [[wiki/accounting/synthesis/FICO 与 accounting 归属映射]]：会计与 SAP/FICO 页面归属
- [[wiki/accounting/sources/企业会计准则基本准则（财政部令第33号）]]：首批官方会计准则资料（网页摘录与官网复制全文）
- [[wiki/accounting/sources/500强企业成本核算实务]]：成本核算与标准成本/作业成本法实务参考
- [[wiki/accounting/sources/2022初级经济法基础官方教材电子版]]：2022 年经济法教育教材（历史参考）
- [[wiki/accounting/sources/2022初级会计实务官方教材电子版]]：2022 年会计实务教育教材（历史参考；原始 PDF 已移除，来源页保留）
- [[wiki/accounting/sources/财务部内部工作体系]]：财务岗位与内部工作流程图片型实务参考（待核验）
- [[wiki/accounting/sources/合并报表实务流程（ERP视角）]]：合并报表六步流程框架（待准则、制度和系统核验）
- [[wiki/accounting/concepts/企业会计准则基本原则]]：基本准则核心原则
- [[wiki/accounting/entities/企业会计准则——基本准则]]：准则对象页
- [[wiki/accounting/entities/]]：实体页
- [[wiki/accounting/concepts/]]：概念页
- [[wiki/accounting/comparisons/]]：对比页
- [[wiki/accounting/sources/]]：来源页
- [[wiki/accounting/synthesis/]]：综合页

## 当前状态

当前已采集 6 个会计 raw 文件，按规范/主题去重为 5 份：财政部令第33号官方会计准则保留 1 份网页摘录和 1 份官网复制全文，另有 1 份成本核算实务参考、1 份仍保留的 2022 年经济法教育教材和 2 份 2026-08 网络教育/实务参考文章。2022 年初级会计实务教材原始 PDF 已移除，但其来源页和历史 provenance 保留。资料中 `accounting-practice` 5 个 raw 文件（按主题去重 4 份）、`economic-law` 1 个 raw 文件（按主题去重 1 份）；新增文章和既有 PDF 均标记为 `status: unknown`，在版本、授权、准则适用性和企业制度核验前，不写入确定性法律、制度或 SAP 操作结论。
