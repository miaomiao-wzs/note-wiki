---
title: "SAP 如何修改统驭科目类型"
source: "https://zhuanlan.zhihu.com/p/721977130"
author:
  - "[[ERP讲堂]]"
published:
created: 2026-08-04
description: "在SAP中，科目设置错了统驭科目类型并且记账了要如何修改？ 例如：前期应收账款对应的统驭科目类型前期设置成了供应商，并且供应商用该科目过来账，现在需要调整，想要将供应商调整到客户，科目为当前使用科目。 …"
tags:
  - "clippings"
---
2 人赞同了该文章

在 [SAP](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=SAP&zhida_source=entity) 中，科目设置错了 [统驭科目类型](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=%E7%BB%9F%E9%A9%AD%E7%A7%91%E7%9B%AE%E7%B1%BB%E5%9E%8B&zhida_source=entity) 并且记账了要如何修改？

例如：前期 [应收账款](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=%E5%BA%94%E6%94%B6%E8%B4%A6%E6%AC%BE&zhida_source=entity) 对应的统驭科目类型前期设置成了 [供应商](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=%E4%BE%9B%E5%BA%94%E5%95%86&zhida_source=entity) ，并且供应商用该科目过来账，现在需要调整，想要将供应商调整到 [客户](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=%E5%AE%A2%E6%88%B7&zhida_source=entity) ，科目为当前使用科目。

部分公司会遇到这种情况，可能是前期系统上线为了方便随便先维护然后过账，后面调整的时候发现调整不了。

这种情况要调整是可以调整的，其中总的来说就是要把要调整的这个科目的统驭科目类型维护成正确的，然后把相关数据放进正确客户里面。

有两种方式：

第一种：

调整的科目科目不为同一个，这样的话可以重新新增一个业务需要的科目，科目统驭类型维护成正确的客户，然后把维护错误的那个科目里面的数据转到正确的科目上即可，完成后将错误的科目停用掉，如果这个科目还有余额的话是不能操作停用的，还是得保留

第二种：

该种方式要比第一种要麻烦些，首先要把错误科目里面的数据转移到一个 [表外科目](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=%E8%A1%A8%E5%A4%96%E7%A7%91%E7%9B%AE&zhida_source=entity) 里面，将错误科目里面的供应商数据都清空掉（也就是调整到表外科目里面），然后再把这个科目的统驭科目类型维护成正确的客户，再把表外科目里面的数据调到已修改的这个科目里面就可以了。（前台修改完之后还需要在后台维护下备选统驭科目）

第三种

资产期初导入用总账的方式，所以会先设置为非统驭科目，导入数据后有余额，又不能直接从前台改，那么就用 [OAMK](https://zhida.zhihu.com/search?content_id=248568767&content_type=Article&match_order=1&q=OAMK&zhida_source=entity) 去更改

发布于 2024-09-25 10:07・四川

赞同 2