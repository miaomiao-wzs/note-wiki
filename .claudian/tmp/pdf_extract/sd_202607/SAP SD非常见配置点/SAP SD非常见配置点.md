SAP SD⾮常⻅配置点 ⾸发于SAP SD

![image 1](<SAP SD非常见配置点_images/imageFile1.png>)

# SAP SD⾮常⻅配置点

![image 2](<SAP SD非常见配置点_images/imageFile2.png>)

Joker Yin

关注他

天下熙熙，皆为利来；天下攘攘，皆为利往。

###### 收录于 · SAP SD

17 ⼈赞同了该⽂章

发布于 2023-09-141:40・浙江 ，编辑于 2023-1-21:09・浙江

SAP中除了标准流程的配置，还有部分系统⾃校验、凭证更新以及优化⽤户体验的⾮ 常⻅配置点，本⽂为笔者⽬前项⽬中遇到的配置点记录

- 1、凭证流状态更新


项⽬中有碰到服务类销售订单（⽆需交货，⽆实物发出），依照销售订单进⾏开票，但是开票 后发现销售订单凭证流中的状态⼀直未更新，发票清账仍未更新，如下图：

![image 3](<SAP SD非常见配置点_images/imageFile3.png>)

销售订单凭证流

点击查看销售订单，发现其总体状态仍是处理中

赞同 17 3 条评论 分享 喜欢 收藏 申请转载

![image 4](<SAP SD非常见配置点_images/imageFile4.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

VA03/VA02查看销售订单详情

因该订单类型为服务类订单，⽆需发货。因此确定为系统配置问题，经测试，发现是由于销 售订单装运计划中交货计划配置未去掉

![image 5](<SAP SD非常见配置点_images/imageFile5.png>)

T-CODE: OVLY

IMG:SPRO-后勤执⾏-装运-基本发运功能-计划-交货计划和运输计划-按销售凭证类型定义计 划；将⽆需交货的交货计划改为空，去掉勾

重新下单，发现销售订单交货状态为空，且销售订单总体状态跟随开票更新，凭证流中也⾃ 动更新状态

![image 6](<SAP SD非常见配置点_images/imageFile6.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

VA02

![image 7](<SAP SD非常见配置点_images/imageFile7.png>)

凭证流

该配置还将控制销售订单计划⾏的交货计划中是否⾃动计算装载⽇期、发货⽇期；配置后会 ⾃动计算出【装载⽇期】、【发货⽇期】。在这⾥定义“拣配”，“装载”所 需要的时间。

![image 8](<SAP SD非常见配置点_images/imageFile8.png>)

#### 2、定义拒绝原因

IMG:SPRO-销售与分销-销售-销售凭证-销售凭证项⽬-定义拒绝原因

【统计】这个字段的 3 个可选项，“空⽩”是指该⾏项⽬的值可以复制到抬头合计中，即：即 使你给⾏项⽬分配了拒绝原因，但是在抬头中还是将这部分值进⾏合计。 X 和 Y 都是不将值 在抬头进⾏合计，X 与 Y 的区别是 X 在将来是不能⽤于统计的，⽽ Y 则可以⽤于统计。 这⾥

需要注意的是，⽆论使⽤空⽩还是 X、Y，做了拒绝的部分是不参与信贷计算的。此处的值为 销售值，即⾏项⽬⾦额。

SAP SD⾮常⻅配置点 ⾸发于SAP SD

![image 9](<SAP SD非常见配置点_images/imageFile9.png>)

T-CODE: V_TVAG

BLC-⽆开票：此处打勾后，财务VF04开票清单中将不显示打了拒绝原因的销售订单⾏项⽬；

值测试结果：

创建销售订单净值为69.03CNY

![image 10](<SAP SD非常见配置点_images/imageFile10.png>)

VA02

当10⾏打拒绝原因后，抬头净值为53.10CNY

![image 11](<SAP SD非常见配置点_images/imageFile11.png>)

VA02

- 3、分配拣配地点（库存地点）


Spro-后勤执⾏-装运-拣配-确定拣配地点-分配拣配地点

SAP SD⾮常⻅配置点 ⾸发于SAP SD

![image 12](<SAP SD非常见配置点_images/imageFile12.png>)

T-CODE: SPRO/SIMG

如下图，装运点+⼯⼚+存储条件确定默认的发货地点

![image 13](<SAP SD非常见配置点_images/imageFile13.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

T-CEOD: OVLQ

当VL01N创建交货单时，系统会⾃动获取库存地点；

#### 4、交货类型定义

IMG:SPRO-后请执⾏-装运-交货-定义交货类型

![image 14](<SAP SD非常见配置点_images/imageFile14.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

T-CODE: VOLF

需要订单：设置是否必须有销售订单

项⽬需求：如果选 202，表示在交货单中，可以⾃⼰添加新⾏。如果选 201，不能添加新 ⾏，只能从销售订单参照。

![image 15](<SAP SD非常见配置点_images/imageFile15.png>)

项⽬需求详情

#### 5、开票类型

IMG: SPRO-销售与分销-开票-开票凭证-定义销售开票类型

![image 16](<SAP SD非常见配置点_images/imageFile16.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

T-CODE: VOFA

此配置即SAP⼀步法开票与两步法开票的控制点，若不勾选“过账冻结”，系统会⾃动根据发票 产⽣会计凭证，若勾选，则需要在VF01开完发票后，使⽤VF02点击⼩绿旗，产⽣会计凭证；

- 6、开票到销售订单的复制控制

定义⾏项⽬类别时，【出具发票相关】选择“与订单相关开票”，在选中复制控制进⼊项⽬对话 框中，⾏项⽬类别将显示在这⾥：

![image 17](<SAP SD非常见配置点_images/imageFile17.png>)

- 7、定义⽂本控制


![image 18](<SAP SD非常见配置点_images/imageFile18.png>)

VOTXN详情

SAP SD⾮常⻅配置点 ⾸发于SAP SD

⽂本控制中的【参考/复制】字段，标识该⽂本是否需要复制到下游单据，⽐如从销售订单⾃ 动带⼊交货单

S4中将⽂本控制放在同⼀个IMG下进⾏定义与分配，如下图：

![image 19](<SAP SD非常见配置点_images/imageFile19.png>)

T-CODE: VOTXN

#### 8、定义税收确定规则

定税时交货⼯⼚必须分配给国家、地区或城市代码，所以我们可以使⽤下述菜单路径来执⾏ 分配操作。

Spro-销售和分销-基本功能-税收-分配税收确定的交货⼯⼚

![image 20](<SAP SD非常见配置点_images/imageFile20.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

T-CODE: OVK6

#### 9、定义物料销售状态

Spro-后勤-常规（S/4中翻译为物流-常规）-物料主数据-设置关键字段-与销售和分销-定义销 售状态 定义物料的销售状态，定义某个物料可以进⾏哪些操作。

![image 21](<SAP SD非常见配置点_images/imageFile21.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

SIMG

执⾏

![image 22](<SAP SD非常见配置点_images/imageFile22.png>)

双击

![image 23](<SAP SD非常见配置点_images/imageFile23.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

物料主数据中维护

![image 24](<SAP SD非常见配置点_images/imageFile24.png>)

M01/ M02

#### 10、订单原因

由于免费订单需公司内部划分成本中⼼，因此，我们项⽬中将它与订单原因集成

在销售订单中填写订单原因，通过分配成本中⼼(TCODE:VOF3)发票中系统确认成本中⼼

Spro-销售与分销-基本功能-科⽬分配/成本-分配成本中⼼

配置如下图：销售组织-分销渠道-产品组-订单原因-成本中⼼

![image 25](<SAP SD非常见配置点_images/imageFile25.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

TCODE:VOF3

配置完成后在订单中选择订单原因

![image 26](<SAP SD非常见配置点_images/imageFile26.png>)

va03

发票中将会⾃动确认对应的成本中⼼

![image 27](<SAP SD非常见配置点_images/imageFile27.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

T-CODE: VF03

并在会计凭证中确认该免费订单对应的成本中⼼

![image 28](<SAP SD非常见配置点_images/imageFile28.png>)

会计凭证

但是实际项⽬中由于订单原因业务⼈员不易理解，容易选错，因此可根据销售组织与部⻔对 应情况进⾏筛选，当选择某⼀销售组织时，订单原因只能选择特定的值，具体配置如下：

TECODE:VAUP

SPRO-销售与分销-销售-销售凭证-销售凭证抬头-将销售凭证类型和销售组织分配给订单原 因

![image 29](<SAP SD非常见配置点_images/imageFile29.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

![image 30](<SAP SD非常见配置点_images/imageFile30.png>)

VAUP

分配后结果如下：

![image 31](<SAP SD非常见配置点_images/imageFile31.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

VA03

在创建订单可以看到订单原因的阈值只有分配的⼏个，防⽌⽤户填错。分配前：

![image 32](<SAP SD非常见配置点_images/imageFile32.png>)

VA02

#### 1、交货单不完整配置

业务需求，在交货单过账发货时，必须填写物流公司名称，⽅便财务结算，但实际操作中因 ⼈⼯原因导致该字段忘记填写等情况，通过配置交货单不完整⽇志进⾏控制

IMG:SPRO-后勤执⾏-装运-基本发运功能-不完全控制交货-定义不完全处理

![image 33](<SAP SD非常见配置点_images/imageFile33.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

T-CODE: OVA2

选中G-交货抬头，双击过程

![image 34](<SAP SD非常见配置点_images/imageFile34.png>)

可以看到系统预定义的过程，选中过程，双击字段

![image 35](<SAP SD非常见配置点_images/imageFile35.png>)

点击新增，填⼊表名及字段名，其中状态解释如下：

交货：指在VL01N创建交货单时，保存按钮进⾏不完整⽇志检查，若该字段未填写则报错⽆ 法保存；

开票凭证：指交货单在开票时检查该字段是否填写，未填写则⽆法开票；

价格：未测试；

SAP SD⾮常⻅配置点 ⾸发于SAP SD

货物移动：指该字段在仓库过账发货时检查是否填写，若未填写则⽆法过账发货；

拣配/堆放：指在拣配时检查该字段是否填写，若未填写则⽆法保存；

包装：未测试；

其中货物移动测试如下：

![image 36](<SAP SD非常见配置点_images/imageFile36.png>)

VL02N

定义完不完全处理过程后，分配，和字段状态组的定义同路径定义即可

![image 37](<SAP SD非常见配置点_images/imageFile37.png>)

SIMG

## 12、销售订单合并交货条件控制

在vl01a的销售订单⾥⾯输⼊订单A B C，按后台执⾏后还是⽣成3张DN，⽽不是⼀张DN，系 统会⾃动拆分，具体的拆分条件配置如下：

![image 38](<SAP SD非常见配置点_images/imageFile38.png>)

SAP SD⾮常⻅配置点 ⾸发于SAP SD

事物码：VBX1

![image 39](<SAP SD非常见配置点_images/imageFile39.png>)

选中复制控制，双击

![image 40](<SAP SD非常见配置点_images/imageFile40.png>)

系统预设了⼀些例程，其中051例程是售达⽅、销售组织、分销渠道、产品组等

SAP SD⾮常⻅配置点 ⾸发于SAP SD

![image 41](<SAP SD非常见配置点_images/imageFile41.png>)

关于作者

![image 42](<SAP SD非常见配置点_images/imageFile42.png>)

Joker Yin

天下熙熙，皆为利来；天下…

⽂章

关注者

回答

20

58

### 1,03

关注他 发私信

2023.1.2更新

后续持续更新，敬请期待！

所属专栏 · 2025-06-09 19:59 更新

![image 43](<SAP SD非常见配置点_images/imageFile43.png>)

##### SAP SD

取消订阅

![image 44](<SAP SD非常见配置点_images/imageFile44.png>)

Joker Yin

47 篇内容 · 530 赞同

最热内容 ·SAP系统标准销售业务流程及配置

发布于 2023-09-141:40・浙江 ，编辑于 2023-1-21:09・浙江

SAP ⼊⻔ SAP 中国 思爱普 (SAP)

![image 45](<SAP SD非常见配置点_images/imageFile45.png>)

理性发⾔，友善互动

###### 3 条评论 默认 最新

![image 46](<SAP SD非常见配置点_images/imageFile46.png>)

air

厉害

01-13 · 云南 回复 喜欢

![image 47](<SAP SD非常见配置点_images/imageFile47.png>)

Joker Yin作者

![image 48](<SAP SD非常见配置点_images/imageFile48.png>)

01-13 · 浙江 回复 喜欢

![image 49](<SAP SD非常见配置点_images/imageFile49.png>)

肖先⽣

虽是细枝末节，但是⾮常重要。

2024-12-16 · 北京 回复 喜欢

推荐阅读

![image 50](<SAP SD非常见配置点_images/imageFile50.png>)

![image 51](<SAP SD非常见配置点_images/imageFile51.png>)

##### SAP批量导⼊操作

##### SAP各模块介绍

SAP SD⾮常⻅配置点 ⾸发于SAP SD

因为SAP经常需要处理⼤量的数 据，所以SAP系统允许从其它外部 系统导⼊数据，包括静态数据和动 态数据。选择什么样的SAP数据导 ⼊⽅法，同样需要根据数据的不同 进⾏考虑。对于SAP顾问来说，这…

SAP在管理功能上，它共有12个系 统模块,下⾯为你⼀⼀介绍,希望对你 了解SAP有所帮助。 （1）SAP M 模块（物料管理模块），主要有采 购、库房与库存管理、MRP、供应 商评价等管理功能。 （2）SAP…

##### SAP SD课程 1.5 创建销售订单

##### SAP F10⾃动付款配置

SAPers

阿东⼂

⼩动物会泡茶

转⻆遇到猪

