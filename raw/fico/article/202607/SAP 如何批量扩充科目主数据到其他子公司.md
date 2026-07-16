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
![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片01.jpg]]

1. **直接复制科目主数据，事务代码FS15**
![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片02.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片03.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片04.jpg]]

1. **将源公司代码科目主数据打包成文件**
1. **事务代码FS15**  
	会生成一个源文件，存放在服务器上，要把这个服务器地址记住，下一步要把这个源文件下载下来，源文件服务器地址如下：
![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片05.png]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片06.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片07.jpg]]

1. **事务代码 [CG3Y](https://zhida.zhihu.com/search?content_id=225854786&content_type=Article&match_order=1&q=CG3Y&zhida_source=entity)**  
	将上一步生成的源文件下载到本地磁盘，源文件地址：  
	D:\\usr\\sap\\LRP\\SYS\\global\\FBISZZZZ
![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片08.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片09.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片10.png]]

1. **事务代码 [CG3Z](https://zhida.zhihu.com/search?content_id=225854786&content_type=Article&match_order=1&q=CG3Z&zhida_source=entity)**  
	再将下载到桌面的源文件上传到需要导入的服务器，操作过程与上一步正好相反：
![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片11.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片09.jpg]]

1. **事务代码FS16**

在目标服务器，接收上一步已经上传到目标服务器的科目主数据：

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片13.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片14.jpg]]

![[raw/assets/SAP-如何批量扩充科目主数据到其他子公司-图片15.jpg]]

发布于 2023-04-06 09:51・四川

赞同 6