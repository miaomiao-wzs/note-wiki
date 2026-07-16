![image 1](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile1.png>)

![image 2](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile2.png>)

![image 3](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile3.png>)

![image 4](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile4.png>)

博客 学习 社区 GitCode InsCode 会议 经验分享 搜索 AI 搜索 消息

# SAP-MM费⽤类采购通过物料组确定科⽬

![image 5](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile5.png>)

![image 6](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile6.png>)

原创 · 4.6k 阅读 · 2 · 32 ·

于 2023-05-27 09:33:51 发布 CC 4.0 BY-SA版权

⽂章标签： #经验分享

![image 7](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile7.png>)

SAP-MM 专栏收录该内容 135 篇⽂章 订阅专栏

## ⼀、WRX的配置，分两类GR/IR科⽬：

- 1、做库存管理物料的GR/IR科⽬，需要配置评估类，此评估类就是物料 主数据 ⾥配置的评估类；

- 2、⾮库存管理费⽤化物料的GR/IR科⽬，如固定资产、办公⽤品、低值易耗品等等，不需要配置评估类，GR/IR科⽬可以配置成


跟做库存管理物料的⼀致，也可不⼀致；

![image 8](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile8.png>)

⼆、带物料号的费⽤类采购业务，创建PO时，必须要输⼊帐户分配类别，然后系统会通过帐户分配类别⾥配置的科⽬修改，和物料 主数据⾥配置的评估类，⼀起到OBYC-GBB⾥确定科⽬，然后显示到PO上，后续收货和发票校验，都要⽤到此科⽬，注 意 ，此 处 确 定 科 ⽬ 逻辑 ，跟 移 动 类 型 ⽆ 关 ，以帐户分配类别K为例，如下图：

![image 9](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile9.png>)

![image 10](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile10.png>)

![image 11](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile11.png>)

![image 12](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile12.png>)

#### AI 助 ⼿

![image 13](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile13.png>)

![image 14](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile14.png>)

![image 15](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile15.png>)

![image 16](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile16.png>)

三、不带物料号的费⽤类采购业务，创建PO时，必须要输⼊帐户分配类别和物料组，然后系统会通过帐户分配类别⾥配置的科⽬修 改，和物料组指定的默认评估类，⼀起到OBYC-GBB⾥确定科⽬，然后显示到PO上，后续收货和发票校验，都要⽤到此科⽬，注 意 ，此 处 确 定 科 ⽬ 逻辑 ，跟 移 动 类 型 ⽆ 关 ：

- 1、OMSK，创建⾮库存管理物料的评估类，如Z001-办公⽤品；
- 2、OMSF，创建物料组，如Z001-办公⽤品物料组；
- 3、OMQW，为物料组定义⼀个默认的评估类：

![image 17](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile17.png>)

- 4、FS00创建相应的科⽬，如59010107-办公⽤品；
- 5、OBYC-GBB，增加记录：


![image 18](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile18.png>)

![image 19](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile19.png>)

#### AI 助 ⼿

![image 20](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile20.png>)

![image 21](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile21.png>)

![image 22](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile22.png>)

- 6、以帐户分配类别K为例：

![image 23](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile23.png>)

- 7、创建⾮库存管理物料 PO ，输⼊物料组，系统⾃动带出科⽬：

![image 24](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile24.png>)

- 8、MIGO收货产⽣的财务凭证：


![image 25](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile25.png>)

![image 26](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile26.png>)

![image 27](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile27.png>)

#### AI 助 ⼿

![image 28](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile28.png>)

![image 29](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile29.png>)

显示推荐内容

![image 30](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile30.png>)

![image 31](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile31.png>)

![image 32](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile32.png>)

![image 33](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile33.png>)

![image 34](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile34.png>)

![image 35](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile35.png>)

![image 36](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile36.png>)

![image 37](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile37.png>)

SAP⻰哥 2 32 0 分享 打赏 专栏⽬录

SAP 费⽤类采购_sap 费⽤化采购 10-27

1、ME51N创建费⽤率采购申请 采购类型选择:ZA03费⽤类采购申请,科⽬分配类别选择“K” “物料数据”,选择,采购对应的物料组。假如,我们是⼴告费,…

SAP FICO 概念与流程 11-4

lsap中所有 科⽬类型:总帐 s 供应商 k 客户d 资产a 物料m 其中物料科⽬⽐较特殊,不可直接记帐,仅可以通过物流⽅式由系统产⽣凭证。另外四类都可…

sap物料组科⽬设置与单据分录关系 01-05

SAP物料组科⽬设置与单据产⽣的分录关系，通过实例说明。

SAP 分配科⽬ 2501_91359491的博客 273

![image 38](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile38.png>)

系统默认有两个可选值：KOFI（实际决定）、KOFK（带有CO的科⽬确定），⼀般选KOFI。在销售中应⽤的科⽬确定过程主要有KOFI，它包含两个…

SAP 费⽤化采购订单简介_sap费⽤类采购订单 11-8

SAP费⽤化采购订单简介 费⽤性采购的核⼼特点 费⽤性采购的流程 费⽤性采购的优势 适⽤场景 业务场景 前台操作 1、创建成本中⼼---KS01 2、创…

2 SAP前台操作⼿册-MM模块-库存管理-费⽤化采购订单收货-MIGO(Mvt.101... 11-5

SAP实施项⽬中,到了第3个阶段-系统实现,在这个阶段,因为蓝图汇报已经结束,配置也差不多完成了,⾃开发还在进⾏中,SAP标准功能下,可以进⾏基础…

SAP MIGO 收货/退货操作和科⽬配置，货物移动类型101/122 Moodbeansk的博客 6188

![image 39](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile39.png>)

确保已经创建了采购订单，并且采购订单号码已知。这是进⾏收货操作的基础。输⼊事务码MIGO，然后按Enter键。【菜单路径】“后勤 - 物料管理 - …

sap-通过定义物料组的评估类-设置⽆物料号的费⽤采购（转) ckk1712的博客 1192

![image 40](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile40.png>)

现在还是以外购电来说⼀下ERP中费⽤采购单的使⽤步骤： (1).Tcode:OMSF定义物料组D1,如下图。 (2).到配置路径IMG Path:物料管理->采购->帐…

SAPFICO成本⽉结操作指南_sap⽉结操作流程资源 11-17

- **路径**: 后台 => SAP⽤户化实施指南 => ⼀般设置 => 货币 => 检查货币... 格式:pdf 资源⼤⼩:1.1MB ⻚数:64 SAP培训资料-FICO⼊⻔.pdf 浏览:88…

SAP成本管理概述及⼀般费⽤介绍 资源 11-2

其中,“⼀般费⽤成本CO”是指在SAP系统中处理⼀般费⽤的过程和⽅法。 - **⼀般费⽤**: 指的是企业内部产⽣的间接费⽤,这些费⽤通常⽆法直接归因…

SAP ⽆料号成本中⼼采购-物料组对应总帐科⽬ 乐期⽆许的博客 3012

![image 41](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile41.png>)

使⽤采购单采购费⽤和外协服务更便于控制,⽐如可以在SAP系统中设置采购申请和相关审批流程。 ⻓话短说，直⼊整体，现在还是以费⽤采购单的…

SAP-MM知识精解-⾃动科⽬记账（05）- 物料组的科⽬确定 Kerwin-G的博客 5583

![image 42](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile42.png>)

导读： 通过之前我们对科⽬⾃动记账的分享，我们知道科⽬的⾃动确定，取决于“⼯⼚+物料+业务事物（货物移动/发票校验）。 在有些采购业务中，…

创建费⽤化采购订单(PR->PO)_bapiesllc 11-9

创建费⽤化采购订单(PR->PO) 本⽂详细介绍了如何使⽤BAPI_PO_CREATE1BAPI在SAP系统中根据采购申请创建费⽤化采购订单。过程涉及⾃动…

SAP MM 采购 服务类采购 04-12

SAP的物料管理（MM）模块提供了⼀种有效的⽅式来处理这些⾮库存类的采购需求，即服务型采购订单。不同于传统的库存物料采购，服务采购订…

SAP-MM常⽤表.docx 08-25

在SAP-MM模块中，这些表格是⽤于管理物料管理和采购的核⼼数据。以下是对这些表的详细解释： 1. EBAN（采购申请）：这个表存储了采购申请…

SAP物料⾃动记账科⽬设置总结 yanzibing99的博客 1052

![image 43](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile43.png>)

所谓的后续结算(Subsquent settlement),可这样理解在PO中定义了折扣condition(Volumn-based rebate数量折扣),在收货后获取折扣,这时可给conditi…

![image 44](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile44.png>)

SAP物料与总账科⽬集成业务 qq_41342741的博客 2097

![image 45](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile45.png>)

SAP物料和总账科⽬之间的关系 1、有物料主数据的正常物料－>评估类－>科⽬ 2、⽆物料主数据的消耗性物料－>物料组－>评估类－>科⽬ 问题…

SAP_SD模块 物料科⽬分配/成本简介 我⼩时候很⿊的博客 2234

![image 46](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile46.png>)

路径：SPRO—销售与分销—基本功能—科⽬分配/成本—收⼊账户确定—收⼊科⽬确定相关性—定义并分配科⽬代码—定义科⽬代码。路径：SPR…

SAP 消耗型采购科⽬确定（⼀） willieyuan的博客 3706

![image 47](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile47.png>)

![image 48](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile48.png>)

消耗型采购科⽬确定： 正常采购⼊库的时候：账⽬记录到“存货科⽬：BSX” 消耗性采购时：账⽬记录到“费⽤性科⽬” 费⽤性科⽬确定逻辑： 1、若…

#### AI 助 ⼿

SAP MM 物料主数据的重要概念：物料类型、物料组、评估类(物料层次） 热⻔推荐 andymagickai的博客 1万+

![image 49](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile49.png>)

物料主数据的重要概念：物料类型、物料组、评估类 （评估级别） 物料主数据是各业务部⻔，特别是物流相关部⻔的重要信息媒介，物料主数据所…

SAP MM科⽬是怎么确定的 weixin_51233095的博客 1596

![image 50](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile50.png>)

1、科⽬是由【移动类型、物料、⼯⼚】设置最后锁定的TE码和评估类决定的；--OMWB2、TE码来源：（包括科⽬修改，我的理解中科⽬修改是TE…

![image 51](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile51.png>)

matinal：SAP 物料⾃动记账科⽬设置总结 matinal 當冬夜漸暖 。公众号：matinal 1607

![image 52](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile52.png>)

请看DEL,当purchase account管理被激活时

![image 53](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile53.png>)

SAP MM模块与FI模块集成之科⽬配置 m0_73971710的博客 1827

![image 54](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile54.png>)

IMG：物料管理->评估和科⽬设置->科⽬确定->⽆向导的科⽬确定->配置⾃动记帐。IMG：物料管理->评估和科⽬设置->科⽬确定->⽆向导的科⽬确…

SAP期初数据导⼊时，GR/IR的导⼊⽅案 最新发布 09-27

<think>嗯，⽤户这次专⻔询问SAP期初数据导⼊时GR/IR的导⼊⽅案，看来是财务或IT实施顾问⻆⾊。从ta精准使⽤"GR/IR"这个科⽬代码来看，应…

![image 55](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile55.png>)

![image 56](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile56.png>)

#### AI 助 ⼿

![image 57](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile57.png>)

![image 58](<SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客_images/imageFile58.png>)

