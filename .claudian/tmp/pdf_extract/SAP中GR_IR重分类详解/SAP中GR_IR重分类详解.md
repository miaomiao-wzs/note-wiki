![image 1](<SAP中GR_IR重分类详解_images/imageFile1.png>)

## SAP中GR/IR重分类详解

# SAP中GR/IR重分类详解

![image 2](<SAP中GR_IR重分类详解_images/imageFile2.png>)

###### ERP讲堂

已关注

交流可➕ :TOPSAP8

19 ⼈赞同了该⽂章

发布于 2025-07-01 21:32・四川

GR/IR重分类

#### GR/IR重分类概述

- • GR/IR科⽬全称是Gods Receipt/Invoice Receipt，是⽤于采购收货和发票校验清算的中间 科⽬，其在采购业务中的⽤途如下图所示：

![image 3](<SAP中GR_IR重分类详解_images/imageFile3.png>)

- • GR/IR是启⽤了未清项管理的总账科⽬，对于正常完结的采购业务，其GR/IR科⽬的余额应 该为0，然后⽉末运⾏⾃动清账程序F.13进⾏清账处理。
- • 但由于收货数量和发票数量可能不⼀致，导致这种不⼀致的原因⼀般有两种：第⼀，收货 了还没开票，或开票了还没收货，因为采购业务还未完结，所以这种差异属于正常差异； 第⼆，发票数量⼤于或⼩于收货数量，因为采购业务已经完结，所以这种差异就是⾮正常 差异，从⽽导致GR/IR科⽬余额不为0。
- • GR/IR科⽬是中间过渡科⽬，如果把它设置为表外科⽬，则必须要在期末出具财务报表前使 其余额为0，但对于采购业务还未完结的正常差异，⼜不能改变现有业务，强⾏将GR/IR科 ⽬余额转⾛，使其科⽬余额强⾏为0，如果这样操作，那么后续发票到了怎么办，货到了怎 么办，因此这就需要⽤到SAP的标准功能，期末对GR/IR科⽬做重分类处理，利⽤GR/IR调 整科⽬，将GR/IR科⽬余额调整到在途物资科⽬或应付暂估科⽬，⽉底做⼀笔调整凭证，次 ⽉⽉初再冲回来，两个⽉⼀起看，什么也没发⽣，但是单从⼀个⽉来看，⼜真实地反映了


企业的资产负债情况，这仅仅是⼀个调账的操作，不会影响实际业务。对于采购业务已经 完结的⾮正常差异，要运⾏MR1做调整处理。 上海快意

## SAP中GR/IR重分类详解

- • 另外，也可以把GR/IR设置为表内科⽬，这样GR/IR科⽬期末余额可以不必为0，但⽆论是把 它设置为1开头的资产类科⽬，还是把它设置为2开头的负债类科⽬，也都不能满⾜资产负 债表的要求，因此还是需要期末对GR/IR科⽬做重分类处理：

![image 4](<SAP中GR_IR重分类详解_images/imageFile4.png>)

- • 当然也有⼀种情况，是不需要做GR/IR重分类处理的：第⼀，把GR/IR科⽬设置为2开头的负 债类科⽬，相当于应付暂估科⽬；第⼆，从管理流程上做出规定，整个企业的所有采购业 务，不允许有票先到货后到（BNG）这种情况发⽣，即使偶尔有这种情况发⽣，也要先把 发票压着，等收货后再做发票校验；第三，要把GR/IR科⽬设置为表内科⽬。
- • GR/IR科⽬在⽉结时做重分类处理的流程如下：


![image 5](<SAP中GR_IR重分类详解_images/imageFile5.png>)

#### GR/IR重分类处理相关后台配置

GR/IR重分类处理需要⽤到三个技术性科⽬，分别是“GR/IR调整科⽬”、“在途物资科⽬”、“应 付暂估科⽬”，注意，所谓的技术性科⽬，是指纯粹是技术上的应⽤，⽽不是⽤户实际记账要 ⽤到的科⽬，这三个科⽬，⼀定要设置为⼀般总账科⽬，并且科⽬主数据不要勾选“只能⾃动 记账”和“未清项管理”，其中“GR/IR调整科⽬”，也被称为GR/IR科⽬的影⼦科⽬，这两个科⽬ 要放到⼀起取总余额，后台路径：财 务 会 计 （ 新 ） ->总帐 会 计 核 算 （ 新 ） ->定 期 处 理 ->重 新

分 类 ->定 义 GR/IR 结 清 的 调 整 科 ⽬ ， Tcode： OBYP

![image 6](<SAP中GR_IR重分类详解_images/imageFile6.png>)

![image 7](<SAP中GR_IR重分类详解_images/imageFile7.png>)

## SAP中GR/IR重分类详解

#### GR/IR科⽬应⽤场景

- • ⾸先，ME21N创建⼀个包含4个物料、4个⾏项⽬、数量都是10KG的PO：

![image 8](<SAP中GR_IR重分类详解_images/imageFile8.png>)

- • 其次，MIGO参照PO收货：

![image 9](<SAP中GR_IR重分类详解_images/imageFile9.png>)

- • 最后，MIRO参照PO做发票校验：

![image 10](<SAP中GR_IR重分类详解_images/imageFile10.png>)

GR/IR重分类处理前提（⼀）：清算

- • ⾸先，MR1对GR/IR科⽬做清算处理：


![image 11](<SAP中GR_IR重分类详解_images/imageFile11.png>)

## SAP中GR/IR重分类详解

![image 12](<SAP中GR_IR重分类详解_images/imageFile12.png>)

![image 13](<SAP中GR_IR重分类详解_images/imageFile13.png>)

- • 其次，MR1SHOW查看GR/IR清算凭证：

![image 14](<SAP中GR_IR重分类详解_images/imageFile14.png>)

- • 最后，点击“冲销”，可对GR/IR清算做冲销处理，点击“后继凭证”，可查看会计凭证：


![image 15](<SAP中GR_IR重分类详解_images/imageFile15.png>)

## SAP中GR/IR重分类详解

###### GR/IR重分类处理前提（⼆）：⾃动清账

- • F.13对GR/IR科⽬做⾃动清账处理，处理完毕后，剩下的未清项才需要做GR/IR重分类处理：

![image 16](<SAP中GR_IR重分类详解_images/imageFile16.png>)

![image 17](<SAP中GR_IR重分类详解_images/imageFile17.png>)

GR/IR重分类处理

- • F.19对GR/IR科⽬做重分类处理：⽇期⼀定要注意


![image 18](<SAP中GR_IR重分类详解_images/imageFile18.png>)

## SAP中GR/IR重分类详解

![image 19](<SAP中GR_IR重分类详解_images/imageFile19.png>)

![image 20](<SAP中GR_IR重分类详解_images/imageFile20.png>)

![image 21](<SAP中GR_IR重分类详解_images/imageFile21.png>)

## SAP中GR/IR重分类详解

- • SM35执⾏GR/IR重分类处理的批处理会话：


![image 22](<SAP中GR_IR重分类详解_images/imageFile22.png>)

![image 23](<SAP中GR_IR重分类详解_images/imageFile23.png>)

![image 24](<SAP中GR_IR重分类详解_images/imageFile24.png>)

## SAP中GR/IR重分类详解

- • SM35执⾏后，查看GR/IR重分类处理的财务凭证：


![image 25](<SAP中GR_IR重分类详解_images/imageFile25.png>)

![image 26](<SAP中GR_IR重分类详解_images/imageFile26.png>)

![image 27](<SAP中GR_IR重分类详解_images/imageFile27.png>)

## SAP中GR/IR重分类详解

发布于 2025-07-01 21:32・四川

sap课程 SAP FICO

赞同 19 1 条评论 分享 喜欢 收藏 申请转载

![image 28](<SAP中GR_IR重分类详解_images/imageFile28.png>)

理性发⾔，友善互动

###### 1 条评论 默认 最新

![image 29](<SAP中GR_IR重分类详解_images/imageFile29.png>)

###### CXY

写的挺清晰了 好⽂章 收藏了

07-03 · 重庆 回复 喜欢

推荐阅读

![image 30](<SAP中GR_IR重分类详解_images/imageFile30.png>)

###### SAP STO转储单

###### SAP那些事-技巧篇-45-费⽤类 采购按物料组默认总账科⽬

###### SAP-基础篇-83-CKM3详细说 明

示例1 ⼯⼚到⼯⼚ ⼀步法2 ⼯⼚到 ⼯⼚ 两步法3 ⽆销售的STO4 带SD 的STO5 带发票的STO采购订单类 型 -UBUBNB移动类型过帐使⽤301 发货：303 收货：305发货：351 收货：101发货：641 收货：101…

需求： 在F类采购中，需指定总账 科⽬和成本对象，希望能够按照物 料组设置默认总账科⽬，避免每次 ⼿⼯输⼊。 解决⽅案： 后台配置路 径：物料管理-采购-物料主数据-⽆ 物料主数据⾏项⽬输⼊帮… 秋去冬来春未远

成品价格⽉初发布标准成本，⽉中 按标准成本⼊账，成品⼊库（采 购、⽣产收货、转⼚等）时的实际 ⾦额与标准成本之前差异计⼊价差 科⽬，成品消耗（销售、⽣产投 料、成本中⼼领⽤等）以标准成… 常温20度

SAP License：GR/IR和暂估⼊ 库设计思路的简单对⽐

SAP权限管控

toqxj

关于作者

![image 31](<SAP中GR_IR重分类详解_images/imageFile31.png>)

### ERP讲堂

交流可➕ :TOPSAP8

⽂章

关注者

回答

529

52

##### 3,464

已关注 发私信

