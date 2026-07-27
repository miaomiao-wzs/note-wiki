---
title: "SAP 作业分割原理  OKEW"
source: "https://www.cnblogs.com/SlashOut/articles/3941093.html"
author:
  - "[[Slashout]]"
published: 2014-08-28
created: 2026-07-27
description: "定义分割（OKES）时怎么能实现上述分割办法？OKES:定义分割结构设定作业的发送成本要素组 和 作业组 等OKEW:将分割结构分配到成本中心.定义分割规则,分割方法选择12, 一定要选上Wt.(权数指标)标志业务场景举个例子,SAP项目组请了2类咨询顾问的,甲 初级顾问的人天作业类型TFZY1是按"
tags:
  - "clippings"
---
**定义分割（OKES）时怎么能实现上述分割办法？**

**OKES**:定义分割结构

设定作业的发送成本要素组 和 作业组 等

**OKEW**:将分割结构分配到成本中心.

定义分割规则

,分割方法选择12, 一定要选上Wt.(**权数指标**)标志

业务场景举个例子,SAP项目组请了2类咨询顾问的,

甲 初级顾问的人天作业类型TFZY1是按3000元人/天 标准价格计算,

乙 资深顾问的人天作业类型TFZY1是按6400元人/天 标准价格计算, 但是计费按小时计算,作业TFZY2是按小时计算的,作业单位小时,按800元/小时标准.

这样实际发生的咨询费在结算到作业类型TFZY1和TFZY2时,就有一个单位问题,假设甲 做了22人天 Days, 乙 做了32小时 Hrs, 咨询费总共120,000 CNY, 计入成本中心A,

(1).无Wt.的权重指数,实际成本如下分割到作业:

TFZY1: \[12万 / (22 + 32) \] \* 22 = 48,.889

TFZY2: \[12万 / (22 + 32) \] \* 36 = 71,111

(2).有Wt.,在作业计划价格的权数TFZY1/ TFZY2是8/1, 实际成本如下分割: (即实际上allocation都按小时 Hrs的权重来结算），此设置有效。

TFZY1: \[12万 / (22\*8 + 32) \] \* (22 \*8) = 101,538

TFZY2: \[12万 / (22\*8 + 32) \] \* (32) = 18,462

其实最后的 allocation 数据过账到表COKL

本文来自博客园，作者： [Slashout](https://www.cnblogs.com/SlashOut/) ，转载请注明原文链接： [https://www.cnblogs.com/SlashOut/articles/3941093.html](https://www.cnblogs.com/SlashOut/articles/3941093.html)