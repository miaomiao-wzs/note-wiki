![image 1](<SAP-MR21和MR22的应用_sap mr22_images/imageFile1.png>)

![image 2](<SAP-MR21和MR22的应用_sap mr22_images/imageFile2.png>)

![image 3](<SAP-MR21和MR22的应用_sap mr22_images/imageFile3.png>)

![image 4](<SAP-MR21和MR22的应用_sap mr22_images/imageFile4.png>)

![image 5](<SAP-MR21和MR22的应用_sap mr22_images/imageFile5.png>)

###### 博客 下载 社区 GitCode GPU算⼒ 更多 数据库 搜索 AI 搜索 会员中⼼

![image 6](<SAP-MR21和MR22的应用_sap mr22_images/imageFile6.png>)

![image 7](<SAP-MR21和MR22的应用_sap mr22_images/imageFile7.png>)

![image 8](<SAP-MR21和MR22的应用_sap mr22_images/imageFile8.png>)

![image 9](<SAP-MR21和MR22的应用_sap mr22_images/imageFile9.png>)

![image 10](<SAP-MR21和MR22的应用_sap mr22_images/imageFile10.png>)

![image 11](<SAP-MR21和MR22的应用_sap mr22_images/imageFile11.png>)

# SAP-MR21和MR22的应⽤

![image 12](<SAP-MR21和MR22的应用_sap mr22_images/imageFile12.png>)

![image 13](<SAP-MR21和MR22的应用_sap mr22_images/imageFile13.png>)

原创 · 518 阅读 · 4 · 0

于 2025-12-17 10:10:24 发布

⽂章标签： #数据库 #⼤数据

![image 14](<SAP-MR21和MR22的应用_sap mr22_images/imageFile14.png>)

SAP CO模块成本核… 专栏收录该内容 2 篇⽂章

在企业 的物料管理与财务核算过程中，准确掌握库存的价值⾄关重要。SAP 系统提供了多种⼯具来帮助企业维护和调整物料价格，其中 MR 是两个常⽤且容易混淆的事务代码 。MR21主要⽤于直接调整物料的标准价格，⽽MR22则⽤于在特殊情况下对库存进⾏价值调整。理解它们的区别 以及操作⽅法，不仅能提升财务数据的准确性，也能为企业的成本控制和决策提供可靠依据。

本篇⽂章说明步骤如下：

- 1. 场景清单排列(使⽤MR21和MR22修改不同价格控制的物料)
- 2. 物料主数据准备（⽅便分析，每种场景单独建⽴物料）
- 3. 前台操作
- 4. 运⾏CKMLCP&差异还原逻辑总结
- 5. 总结


进⼊正⽂....

- 1、场景清单排列
- 2、物料主数据准备


|场景|物料|价格控制|价格|事务代码|
|---|---|---|---|---|
|场景1|15027|S+3|100|MR21|
|场景2|15028|V+2|100|MR21|
|场景3|15029|S+3|100|MR22|
|场景4|15030|V+2|100|MR22|


- 15027主数据 如下:


![image 21](<SAP-MR21和MR22的应用_sap mr22_images/imageFile21.png>)

#### 15028主数据如下：

![image 28](<SAP-MR21和MR22的应用_sap mr22_images/imageFile28.png>)

#### 15029主数据如下：

![image 35](<SAP-MR21和MR22的应用_sap mr22_images/imageFile35.png>)

#### 15030主数据如下:

![image 42](<SAP-MR21和MR22的应用_sap mr22_images/imageFile42.png>)

### 3、前台操作

初始化 物料库存

分别⼊库存10个，⾦额分别为1000，下图为初始化会计分录，初始化后S价物料⽆差异产⽣。下图为初始化会计凭证

![image 43](<SAP-MR21和MR22的应用_sap mr22_images/imageFile43.png>)

查看库存报表,库存分别为10个，库存价值分别为1000

![image 50](<SAP-MR21和MR22的应用_sap mr22_images/imageFile50.png>)

以上数据准备好后，接下来按场景系统操作

### 场景1

- 使⽤MR21更改15027价格，价格由100，改为120


![image 51](<SAP-MR21和MR22的应用_sap mr22_images/imageFile51.png>)

![image 52](<SAP-MR21和MR22的应用_sap mr22_images/imageFile52.png>)

查看价格更改凭证CKMPCD

![image 53](<SAP-MR21和MR22的应用_sap mr22_images/imageFile53.png>)

下图为价格更改凭证，新价格120，新旧价差=120-100=20，数量为10，所以产⽣20*10=200的差异.科⽬来源为OBYC-BSX、OBYC-UMB

![image 60](<SAP-MR21和MR22的应用_sap mr22_images/imageFile60.png>)

查看库存报表，库存已变化

![image 61](<SAP-MR21和MR22的应用_sap mr22_images/imageFile61.png>)

### 场景2

- 使⽤MR21更改15028价格，价格由100，改为120


![image 62](<SAP-MR21和MR22的应用_sap mr22_images/imageFile62.png>)

新价格120，新旧价差=120-100=20，数量为10，所以产⽣20*10=200的差异.科⽬来源为OBYC-BSX、OBYC-UMB

![image 63](<SAP-MR21和MR22的应用_sap mr22_images/imageFile63.png>)

![image 64](<SAP-MR21和MR22的应用_sap mr22_images/imageFile64.png>)

![image 65](<SAP-MR21和MR22的应用_sap mr22_images/imageFile65.png>)

![image 66](<SAP-MR21和MR22的应用_sap mr22_images/imageFile66.png>)

![image 67](<SAP-MR21和MR22的应用_sap mr22_images/imageFile67.png>)

![image 68](<SAP-MR21和MR22的应用_sap mr22_images/imageFile68.png>)

![image 69](<SAP-MR21和MR22的应用_sap mr22_images/imageFile69.png>)

查看库存报表，库存已变化 SAP孤狼 关注 4 0 0 分享

![image 70](<SAP-MR21和MR22的应用_sap mr22_images/imageFile70.png>)

### 场景3

- 使⽤MR22更改15029库存价值，增加200

![image 71](<SAP-MR21和MR22的应用_sap mr22_images/imageFile71.png>)

![image 72](<SAP-MR21和MR22的应用_sap mr22_images/imageFile72.png>)

库存增加200，借⽅科⽬来源OBYC-PRD -UMB、贷⽅科⽬来源OBYC-UMB

![image 73](<SAP-MR21和MR22的应用_sap mr22_images/imageFile73.png>)

查看库存报表,库存还未发⽣变化

![image 74](<SAP-MR21和MR22的应用_sap mr22_images/imageFile74.png>)

场景4

- 使⽤MR22更改15030库存价值，增加200


![image 81](<SAP-MR21和MR22的应用_sap mr22_images/imageFile81.png>)

![image 82](<SAP-MR21和MR22的应用_sap mr22_images/imageFile82.png>)

库存增加200，借⽅科⽬来源OBYC-BSX、贷⽅科⽬来源OBYC-UMB

![image 83](<SAP-MR21和MR22的应用_sap mr22_images/imageFile83.png>)

查看库存报表,库存已发⽣变化

![image 84](<SAP-MR21和MR22的应用_sap mr22_images/imageFile84.png>)

## 1. 运⾏CKMLCP

下图为CKMLCP差异还原凭证

![image 91](<SAP-MR21和MR22的应用_sap mr22_images/imageFile91.png>)

四个物料CKM3界⾯依次截图 如下：

### 场景1：

![image 92](<SAP-MR21和MR22的应用_sap mr22_images/imageFile92.png>)

- 总结：使⽤MR21更改S物料价格，并不能真正使库存价值发⽣变化，价格更改产⽣的差异（OBYC-UMB），在CKMLCP滚算后，会将差异还原到库存 价值并没有发⽣变化。


### 场景2：

![image 99](<SAP-MR21和MR22的应用_sap mr22_images/imageFile99.png>)

总结:总结：使⽤MR21更改V物料价格，会使库存价值发⽣变化，价格更改产⽣的差异（OBYC-UMB）留在差异科⽬，不还原。

### 场景3：

![image 100](<SAP-MR21和MR22的应用_sap mr22_images/imageFile100.png>)

总结: 使⽤MR22更改S物料价格，会使库存价值发⽣变化，价格更改产⽣的差异，通过OBYC-PRY进⼊库存，达到改变库存价值的⽬的

### 场景4:

![image 107](<SAP-MR21和MR22的应用_sap mr22_images/imageFile107.png>)

- 总结：使⽤MR22更改V物料价格，会使库存价值发⽣变化，价格更改产⽣的差异（OBYC-UMB）留在差异科⽬，不还原。


1. 总结

|场景|物料|价 格 控 制|结论|
|---|---|---|---|
|场景1|15027|S+3|使⽤MR21调增S价物料时， ⽣成会计分录： S：库存科⽬ OBYC-BSX H：材料重估差异 OBYC-UMB ML还原： S：材料重估差异 OBYC-UMB H：库存科⽬ OBYC-BSX 差异抵消，库存价值并没有发⽣变 化|
|场景2|15028|V+2|实时更改物料价格和库存价值|
|场景3|15029|S+3|使⽤MR22调增S价物料库存时， ⽣成会计分录: S:差异科⽬OBYC-PRD-UMB H:差异科⽬OBYC-UMB ML还原时： S：库存科⽬ OBYC-BSX H：差异科⽬ OBYC-PRY 此时OBYC-UMB可以维护成损益科 ⽬，不参与物料帐还原|
|场景4|15030|V+2|实时更改物料价格和库存价值|


SAP 物料价格修改 willieyuan的博

1、MR21：是更改的单个物料的价格，即MR21可以更改移动平均价（V）或标准价（S）的物料价格。 2、MR22：更改库存总价值，即MR22只能更改移动平均价（V）的

SAP MR21和MR22 对CKMLCP结果影响_sap mr22

SAP MR21和MR22 对CKMLCP结果影响 ⽂章介绍了通过MR22交易代码如何改变⾃制半成品的周期价格,从⽽影响当⽉成本。使⽤MR22会⽣成差异科⽬凭证,调整后,差异

...MM 事务代码MR22通过修改库存⾦额的⽅式调整物料单价_sap mr22...

SAPMM模块中事务代码MR22也可以⽤于修改物料的移动平均价。不同于MR21事务代码直接修改价格,MR22事务代码是通过增加或者减少库存价值的⽅式来更新物料的移

SAP 事务码 MR21 的作⽤介绍 2007 年 ~ 2025 年，深耕 SAP 技术 18

SAP S/4HANA 中的事务码 MR21 ⽤于更改物料的评估价格。在企业资源规划（ERP）系统中，物料的评估价格直接影响库存的财务价值。通过 MR21，⽤户可以调整物料

![image 108](<SAP-MR21和MR22的应用_sap mr22_images/imageFile108.png>)

![image 109](<SAP-MR21和MR22的应用_sap mr22_images/imageFile109.png>)

![image 110](<SAP-MR21和MR22的应用_sap mr22_images/imageFile110.png>)

![image 111](<SAP-MR21和MR22的应用_sap mr22_images/imageFile111.png>)

![image 112](<SAP-MR21和MR22的应用_sap mr22_images/imageFile112.png>)

![image 113](<SAP-MR21和MR22的应用_sap mr22_images/imageFile113.png>)

SAP孤狼 关注 4 0 0 分享

讲解MR21和MR22修改价格的逻辑 五⾕散

前⾔ SAP中MR21和MR22都可以⽤来修改物料的价格，但是因为修改价格的系统逻辑不⼀致，所以其作⽤和结果也不⼀致。本⽂主要通过讲解其过程来理解其中的异同。

MR22处理冲销顺序错误导致的采购价格差异_sap mr22的凭证如何冲销-CSDN...

MR22处理冲销顺序错误导致的采购价格差异 ⽤户反馈采购价格整错了,把⾦额18,732.74做成了2,116,800.00,导致销售成本虚增了200多万。 ⾃⾏处理情况: 新创建了⼀个正

SAP S4 MR22修改价格未同步维护公司货币与集团货币的影响_sap集团货币价...

⽂章浏览阅读751次。在MR22时,只填写了公司币别的⾦额,集团货币⻚⾦额未维护;导致跑完CKMLCP物料账后消耗及结存的差异⾦额在公司币别与集团货币的不⼀致。前提

- SAP MR21 和 MR22 区别 天边浮云的博 MR21 : 商品原单价为0.78，现在改为0.87 库存值为34 其会计科⽬为。MR**是不能改标准价格的，即使改了也到PRD去了，只能改移动平均价。MR21和MR22⽤来调整库

SAP MM实战笔记 - ⾖知识03 - MR21调价策略与影响，MM02/MMAM变更限制与数据清理 wasm7browser的

本⽂深⼊解析了SAP MM模块中MR21价格调整、MM02/MMAM修改物料基本单位与评估类的核⼼操作与⻛险。重点阐述了MR21作为财务过账事务的底层逻辑、调价对库

MR21、MR22和CK24的区别

MR21、MR22和CK24的区别 本⽂详细介绍了SAP系统中物料价格修改的⽅法,包括MR21、MR22及CK24的功能区别与使⽤场景。重点对⽐了MR21与MR22在修改物料价

讲解MR21和MR22修改价格的逻辑

SAP中MR21和MR22都可以⽤来修改物料的价格,但是因为修改价格的系统逻辑不⼀致,所以其作⽤和结果也不⼀致。本⽂主要通过讲解其过程来理解其中的异同。 ⼀、 MR

SAP 更改物料价格 MR21 MaiKouBei的博

MR21实现的功能：更改物料计价类型对应的价格；如是S，Mr21更改的就是S的价格；需要修改另外⼀个价格时，直接⽤MM02修改即可；

SAP 批量MR21修改物料价格（TCODE:CKMPRPN和CKME）＜转载＞ qq_55488207的博

当更新标准价时，涉及到的物料往往都很多，如果通过MR21更改价格，需要输⼊物料编号、新价格，⼯作量会很⼤。通常情况下，企业会以物料的实际价更新标准价，此

SAP Note 2032764 MR21 Price Change in Previous Period not updated in MM03 - SAP ERP & SAP S/4 HANA

当在MR21中发布前⼀期间的价格变更时，系统未正确更新当前期间的价格。原因在于SPRO定制设置中的标志“将价格变更从前⼀期间结转到当前期间”(V_169P_PR-PRAV

SAP License：MR22借贷物料⼀步设置可以把差异带⾛ SAP权限管控|SAP⽤户权限管理|SAP权限合规检查

最近真的很忙，N天没有更新了，其实忙只是借⼝，归根结底是没养成好习惯。 MR22类似于MIRO事后借记可以调整物料的⾦额，如果是半成品或者是成品就不能⽤MIRO

基于SpringBoot的流浪动物救助收养系统 计算机学姐的博

【2026最新】基于Java+SpringBoo+Vue+MySQL的流浪动物救助收养系统

实现JVM进程缓存 m0_61787196的博

实现JVM进程缓存

【MyBatis-Plus】Spring Boot + MyBatis-Plus 进⾏各种数据库操作（附完整 CRUD 项⽬代码示例） ⼩江的记录

在SpringBoot项⽬中使⽤MyBatis-Plus进⾏数据库操作，核⼼是利⽤其通⽤Mapper、条件构造器和各类插件，⽆需编写⼤量SQL即可完成80%以上的单表操作。

趣味项⽬与综合实战 2301_81548293的

python# 创建基类# 定义⼀对多关系# 定义多对⼀关系# 定义多对多关系（通过关联表）# 关联表（⽤于多对多关系）SQLAlchemy ORM提供了强⼤⽽灵活的数据库操作⽅

requests接⼝⾃动化测试 最新发布 2301_79941274的

schema = {"required": ["code", "msg", "data"], # 必填字段"code": {"type": "integer"}, # code 必须是整数"msg": {"type": "string"}, # msg 必须是字符串"data": {

从抽象设计到落地实践：openJiuwen可插拔会话存储机制深度解析 热⻔推荐 2301_81073317的博

openJiuwen v0.1.7的可插拔会话存储机制是⼀个设计精良、⽣产就绪的特性：维度评分说明功能完整性⭐ ⭐ ⭐ ⭐ ⭐ 覆盖内存/本地/分布式三种场景架构设计⭐ ⭐ ⭐ ⭐

Mysql数据库操作 Silascc的

基础规范：创建库 / 表时必加，指定utf8mb4字符集，优先使⽤InnoDB引擎；核⼼操作：CRUD 中，必须加WHERE条件，查询避免⽤SELECT *；性能优化：对常⽤查询字

DM8 切库实战 Amarone

摘要 本⽂探讨了DM8数据库迁移⾄MySQL、KingbaseES和神通数据库的核⼼挑战，指出迁移的本质不是简单的类型替换，⽽是语义迁移。⽂章对⽐了三类⽬标库的迁移难

数据库SM4和pg_rewind冲突导致HGHAC备库时间线不同步 Hig

数据库SM4和pg_rewind冲突导致HGHAC切换时备库时间线不同步。永久解决⽅案： 数据库更新P007_SEE458补丁。执⾏pg_rewind命令，集群切换后导致 备库⽆法同步

TDengine IDMP 组态⾯板 —— 画布 TDengine(⽼段）专注时序数据库

其中，TDengine TSDB 是⼀款⾼性能、分布式的时序数据库（Time Series Database），同时它还带有内建的缓存、流式计算、数据订阅等系统功能；TDengine IDMP 是⼀

- SAP MR22 底表 ### SAP MR22 底层表结构及字段说明 SAP 系统中的事务码MR22主要⽤于物料分类账的管理。为了理解MR22的具体实现⽅式及其底层数据存储机制，有必要探讨与其相


![image 114](<SAP-MR21和MR22的应用_sap mr22_images/imageFile114.png>)

![image 115](<SAP-MR21和MR22的应用_sap mr22_images/imageFile115.png>)

![image 116](<SAP-MR21和MR22的应用_sap mr22_images/imageFile116.png>)

关于我们 招贤纳⼠ 商务合作 寻求报道 400-660-0108 kefu@csdn.net 在线客服 ⼯作时间 8:30-22:00

公安备案号11010502030143 京ICP备19004658号 京⽹⽂〔2020〕1039-165号 经营性⽹站备案信息 北京互联⽹违法和不良信息举报中⼼ 家⻓监护 ⽹络110报警服务 中国互联⽹举报中⼼ Chrome商店下载 账号管理规范 版权与免责声明 版权申诉 出版物许可证 营业执照 ©1999-2026北京创新乐知⽹络技术有限公司

