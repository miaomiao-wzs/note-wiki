---
title: 限制用户在 SAP 中导出ALV报表数据
source: https://mp.weixin.qq.com/s/76UPpjqiGp5KZGNgr1lOJw
author:
  - "[[观兴]]"
published:
created: 2026-07-30
description: 限制用户在 SAP 中导出ALV报表数据
tags:
  - clippings
---
观兴 观兴 *2026年6月29日 20:06*

![图片](https://mmbiz.qpic.cn/mmbiz_gif/FdjrTBUHbMhwh8B23bRk5YQEUElD8tv9e1B9UEXr8GQhS9Bmm0jjicE6xWo8hTfcfoMbiaeBbnrOKiao7A4TLGiciaChA07dvcHEucKP56mdbmsw/640?from=appmsg&wxfrom=5&wx_lazy=1&tp=webp#imgIndex=2)

**文章详情**

**本文适用人群**

1、乙方FICO顾问

2、甲方FICO顾问

**本文适用场景**

1、 SAP GUI限制导出数据

**阅读事项说明**

1、文字数量 ： **258** 字

2、图片数量： **2** 图

3、阅读时间： **2** 分钟

****问题：  
****

有一个客户，因为一些原因，想要限制用户在SAP中导数据的权限，这个需求虽然也是第一次听说，但是客户的需求总得满足是不是......

**0** **1**

处理办法

直接上答案，参考SAP KBA 3276383 - Restriction for downloading ALV data，没事多看看SAP文档，没准啥时候用得到。

![图片](https://mmbiz.qpic.cn/mmbiz_png/PeuWrS1jUVDoQU7iclrqdvEZCdfD9jLicjsRGjagtbqGGvzj2tHzzE4MbyKmpzUkv9gU59bV0PzOaOWP3rMkNGG7dgP6HAzIIpUIEg5qzRXCM/640?wx_fmt=png&from=appmsg&watermark=1&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=4)

直接把权限对象 S\_GUI 中的权限字段 导出 给取消掉就可以了。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/PeuWrS1jUVAMwgVwHibmDWnnWEuyjDNfkJ6E5IufxJQrV6BSiccMTuGzUMwIOFTSKt2EjvnbDmfUkE9L97rr7NBB10uZZSoEOpewl5pqfdwo0/640?wx_fmt=png&from=appmsg&watermark=1&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=5)

**END**

还是SAP Press资料令人耳目一新

![图片](https://mmbiz.qpic.cn/mmbiz_png/PeuWrS1jUVA8jkicUp59Guk38lyS84V1x9dWqAX65jPOj64kwBPHIzsHukibrib1UicjBen2Kf5iatWFmpNwIsf5icN2ZEOcsoxhCVu0ZCxWG29gY/640?wx_fmt=png&from=appmsg&watermark=1#imgIndex=6)

**微信扫一扫赞赏作者**

SAP冷门问题 · 目录

作者提示: 个人观点，仅供参考