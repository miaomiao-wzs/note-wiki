---
title: "SAP 如何批量扩充（复制）科目主数据到其他子公司|复制科目主数据详解 FS15&FS16"
source: "https://zhuanlan.zhihu.com/p/619755052"
author:
  - "[[ERP讲堂]]"
published:
created: 2026-07-10
description: "现假设我们成立一家新的子公司，需要把母公司的科目批量复制到子公司，如何快速的操作呢？ SAP提供两个T-CODE：FS15和FS16： FS15是将某公司的某部分科目复制到其他公司。 FS16是通过上传文件将科目复制到相关公司…"
tags:
  - "clippings"
---
6 人赞同了该文章

现假设我们成立一家新的子公司，需要把母公司的科目批量复制到子公司，如何快速的操作呢？

[SAP](https://zhida.zhihu.com/search?content_id=225854786&content_type=Article&match_order=1&q=SAP&zhida_source=entity) 提供两个T-CODE： [FS15](https://zhida.zhihu.com/search?content_id=225854786&content_type=Article&match_order=1&q=FS15&zhida_source=entity) 和FS16：

FS15是将某公司的某部分科目复制到其他公司。

FS16是通过上传文件将科目复制到相关公司

1. **前提条件：**  
	发送和目标公司代码的科目组、容差组、字段状态组、留存收益科目要相同！
2. **事务代码FS15的界面说明**
![](https://pic2.zhimg.com/v2-5f1fb1568e6f9ffc765fb5f09b7a0651_1440w.jpg)

1. **直接复制科目主数据，事务代码FS15**
![](https://pic1.zhimg.com/v2-259bad0178d80bff64cc086ac1df4df4_1440w.jpg)

![](https://pic4.zhimg.com/v2-56db1cf60098679ca284525afc36b84d_1440w.jpg)

![](https://pic3.zhimg.com/v2-003274505d753f04ad30ea2412d7383e_1440w.jpg)

1. **将源公司代码科目主数据打包成文件**
1. **事务代码FS15**  
	会生成一个源文件，存放在服务器上，要把这个服务器地址记住，下一步要把这个源文件下载下来，源文件服务器地址如下：
![](https://picx.zhimg.com/v2-8e967f4182591b722fba74a24e4f5111_1440w.png)

![](https://pic4.zhimg.com/v2-fd0ef4b7ea1cc9c8db0d780396e42345_1440w.jpg)

![](https://pic3.zhimg.com/v2-e1ad4fcd271cc1b94ac9759a185c9602_1440w.jpg)

1. **事务代码 [CG3Y](https://zhida.zhihu.com/search?content_id=225854786&content_type=Article&match_order=1&q=CG3Y&zhida_source=entity)**  
	将上一步生成的源文件下载到本地磁盘，源文件地址：  
	D:\\usr\\sap\\LRP\\SYS\\global\\FBISZZZZ
![](https://picx.zhimg.com/v2-b0fa399fb3b590cf37013e1c428eb031_1440w.jpg)

![](https://picx.zhimg.com/v2-4734a1430714d6fd0c77f6abf80cdccd_1440w.jpg)

![](https://pic4.zhimg.com/v2-a5bef4ab36655cfd52f5b037608e7a53_1440w.png)

1. **事务代码 [CG3Z](https://zhida.zhihu.com/search?content_id=225854786&content_type=Article&match_order=1&q=CG3Z&zhida_source=entity)**  
	再将下载到桌面的源文件上传到需要导入的服务器，操作过程与上一步正好相反：
![](https://picx.zhimg.com/v2-d7bc6377f2c79d44621dd49035a80d47_1440w.jpg)

![](https://picx.zhimg.com/v2-4734a1430714d6fd0c77f6abf80cdccd_1440w.jpg)

1. **事务代码FS16**

在目标服务器，接收上一步已经上传到目标服务器的科目主数据：

![](https://pic1.zhimg.com/v2-1ac4048dbf7036d41f1ed36e6c3efc2e_1440w.jpg)

![](https://pic4.zhimg.com/v2-629a33f62a43a37f8b3676982d63fba9_1440w.jpg)

![](https://pic3.zhimg.com/v2-6986ebf47a39fe3ad78aa9141ccbff0c_1440w.jpg)

发布于 2023-04-06 09:51・四川

赞同 6