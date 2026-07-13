---
title: 生产工单跨月陆续交货TECO重新打开-物料差异结算问题
source: https://mp.weixin.qq.com/s/d0YcOVFZc7eO2_QZE7UeEg
author:
  - "[[小泉2007]]"
published:
created: 2026-07-08
description:
tags:
  - clippings
---
小泉2007 SAP实务分享 *2026年7月8日 17:39*

**■** **业务概述**

生产工单的数量为10000个，2017.8交货5000个，并且在当月TECO，2017.8月结对该工单进行结算后余额为0，2017.9生产工单TECO被打开，将剩余的5000个交货且TECO，在2017.9月结中再次对该工单进行结算，工单余额为0。2017.8和2017.9每个月产生的差异都可以在物料账结算中被带走，如果工单发生跨月交货，每个月生产工单都TECO，则不影响差异物料差异结算

1.生产工单计划生产数量10000个

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/iccUeWbl6GunQsONcMFPMbQyQvUwhBuELe4MuaialFcWwSjc46dZjzz1E3QViaXpXtFlzJdsUm2UKp0AHRDownsBT5OocBkHWEMzyTe74ZJNSU/640?wx_fmt=png&watermark=1&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=0)

2.生产工单分别在2017.8及2017.9发生过两次交货，交货数量都为5000个

![图片](https://mmbiz.qpic.cn/mmbiz_png/iccUeWbl6GumHEQmouq52FvUlpvrvR18Jk27kO1ER6kLZe2IcmQgajx7wESvv1AcvWq2Xx3SUovPXrfLRLmmkbpuECw0XtQmetyPlAVc9icbQ/640?wx_fmt=png&watermark=1#imgIndex=1)

3.生产工单分别在2017.8和2017.9发生过两次完工入库转出和两次结算转出材料成本差异

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/iccUeWbl6GunTAkEMA8jj0ia8H6DwGhKu7Ig57o30RaicNS0ibqHoDt4ZCYqLgHQqh5U1IdoIM9qtzZV6gibJNRZmOMtEd4PI6zJvjoMO0vOAOcI/640?wx_fmt=png&watermark=1#imgIndex=2)

4.生产工单在TECO后参与当月结算，结算完次月被打开TECO，在交完剩下的5000个后，再次TECO参与当月结算

![图片](https://mmbiz.qpic.cn/sz_mmbiz_jpg/iccUeWbl6GukEk8f5hicgQMcuPCPtvFxC3T4hm35LQduh9s8xtrFiabm2lvlvpfro16V5tvDanC5ZEVhvJRGrsfkmlbbQrjjqw0gzwLY6ITgZ4/640?wx_fmt=jpeg&watermark=1#imgIndex=4)

5.查看2017.8该物料的物料账：结算出已交货5000的物料差异

![图片](https://mmbiz.qpic.cn/mmbiz_png/iccUeWbl6GumhsgIf74m5CgwKicTI4zLibgXb5HdALx1ib3ibKs1Bugl74bpDEyGwZl7GkUPQ6nG3IyQBPczFEHx39LZ3j2q2lgKUupAafDqEiaE8/640?wx_fmt=png&watermark=1#imgIndex=5)

6查看2017.9该物料的物料账：结算出剩余5000个的物料差异

![图片](https://mmbiz.qpic.cn/mmbiz_png/iccUeWbl6GunuButlhgQW7MO2FXPl7BicF3nCQptM2TToVmALNwPnuCkYV2W7eLvJJQMRvYLVjPpQT0PopYnlz6dZFxUIPUWew8IVzTFfHeDc/640?wx_fmt=png&watermark=1#imgIndex=7)

**微信扫一扫赞赏作者**