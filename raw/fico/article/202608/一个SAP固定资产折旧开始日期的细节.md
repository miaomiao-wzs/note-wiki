---
title: "一个SAP固定资产折旧开始日期的细节"
source: "https://blog.csdn.net/stone0823/article/details/145861085"
author:
  - "[[stone0823]]"
published: 2025-02-25
created: 2026-08-10
description: "文章浏览阅读1.6k次，点赞5次，收藏10次。最近一个项目用到固定资产跨公司代码的转移（ABT1N)，在做测试的时候，碰到一个问题。固定资产从公司 A 转到公司 B 之后，固定资产每月的折旧金额变化了。经检查，原来是在 B 公司折旧开始日期没有沿用原来的折旧开始日期。经查找，发现了 SAP 对资产折旧日期控制的一个细节，记录下来备忘。_sap t090np"
tags:
  - "clippings"
---
最近一个项目用到固定资产跨公司代码的转移（ABT1N)，在做测试的时候，碰到一个问题。固定资产从公司 A 转到公司 B 之后，固定资产每月的折旧金额变化了。经检查，原来是在 B 公司折旧开始日期没有沿用原来的折旧开始日期。

经查找，发现了 SAP 对资产折旧日期控制的一个细节，记录下来备忘。

SAP 支持两种折旧开始日期的控制逻辑：

- 折旧开始日期（资产主数据）
- 资产购置日期（资产主数据）

我们都熟悉 AFAMP 的界面 （设置期间控制):

![](https://i-blog.csdnimg.cn/direct/24fd09c6fa4648bca2c16d7f3b674448.png)  
这个配置对应的后台表是 T090NP，比界面上多一个关键字段：

![](https://i-blog.csdnimg.cn/direct/1f0c1ec9310f446da1876acf1f28f8c3.png)  
如果勾上，对于资产购置，将基于折旧开始日期开始计提折旧，如果没有勾上，将基于原始购置日期开始计提折旧。

之前的版本，是可以通过 AFAMP 事务码来进行维护这个选项的，后来 SAP 取消了界面的这个字段，所以如果需要设置，只能通过修改后台表。

### 参考

53166 - Depr acc to asset value date indicator cannot be maintained  
92925 - Indicator: “Calculate dep. after value date” cannot be maintained