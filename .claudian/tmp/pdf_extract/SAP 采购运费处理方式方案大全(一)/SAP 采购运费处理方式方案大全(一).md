# SAP 采购运费处理⽅式⽅案⼤全(⼀)

ERP数智化咨询 2026年3⽉3⽇ 07:58 湖北

#### ⼀、业务场景

⽆论是采购业务还是销售业务，都会产⽣运费。但依据不同的财务核算要求，运费处理⽅式会存在 ⼀定差异，基本分为运费成本化和运费费⽤化。这⾥仅是以运费为代表，可⽤来处理各类交货成 本。

#### ⼆、处理⽅式

- 情况1：创建采购订单时，运费是由供应商承担，很多时候是包含在材料报价中，这种情况不需要专 ⻔针对运费进⾏处理，材料价格中已包含运费。这种情况，运费⾃然就属于成本化处理⽅式。
- 情况2：创建采购订单时已确定运费，运费是由供应商承担，但运费并没有包含在材料价格，需要 单独计算。在这个⼤前提下，运费处理⼜分为⼏种情况：


- （1）材料供应商和运费供应商属于同⼀个供应商，并且在创建采购订单时已确定运费供应商。


![image 1](<SAP 采购运费处理方式方案大全(一)_images/imageFile1.png>)

采购订单⾏项⽬中添加“运费”条件类型，针对每⾏维护运费。如果觉得维护麻烦，可以将运费条件 类型设置为抬头条件，在抬头数据中维护总的运费后，每个⾏项⽬会按照⼀定条件将运费分摊到各 个⾏项⽬。注意，我这⾥使⽤了“⼀定条件”，这个⼀定条件是可以通过增强来⾃定义分摊逻辑。如 果使⽤增强控制，就需要把该条件类型选择“组条件”，然后通过写例程进⾏⾃定义逻辑。默认的是 按照⾦额进⾏分摊，⾃定义的就可以按照重量、体积等进⾏维度进⾏分摊。只要可以想到的维度， 并且有清晰的关系，都可以执⾏。

- （2）材料供应商和运费供应商属于不同⼀个供应商，并且在创建采购订单时已确定运费供应商。

![image 2](<SAP 采购运费处理方式方案大全(一)_images/imageFile2.png>)

![image 3](<SAP 采购运费处理方式方案大全(一)_images/imageFile3.png>)

处理逻辑同（1），但需要在运费的条件类型细节中修改供应商，将供应商修改为运费供应商。此处 修改后，主要对发票校验环节有影响，需要分别对材料和运费进⾏发票校验。

- （3）创建采购订单时尚不确定运费供应商。 创建采购订单时，可参照（1）进⾏维护，默认为材料供应商。可通过在运费条件类型中勾选 “Vevdor in GR”，这样在进⾏MIGO 收货时，可以修改运费供应商。在收货环节是肯定是要知道 承运商了。


![image 4](<SAP 采购运费处理方式方案大全(一)_images/imageFile4.png>)

在配置中将“控制数据2→收货的供应商”值改为2，配置路径“物料管理→采购→条件→定义价格确认流 程→定义条件类型 在MIGO收货操作时如图 ，明细部分会出现运费标签⻚，栅格中包含运费的信息，在此可以修改运 输商的编号。

![image 5](<SAP 采购运费处理方式方案大全(一)_images/imageFile5.png>)

以上（1）（2）（3）中的运费可按数量、百分⽐和固定⾦额三种⽅式计算。这三种⽅式运费成本化处理。 收货后⽣成的会计分录是： 借：原材料（材料⾦额+运费⾦额）--BSX 贷：应付暂估 --WRX

运费科⽬ --FR1

- （4）SAP中也通过“后续借计”的⽅式处理运费发票，因此要先录⼊材料发票后，才能做后续借计。如果 运费发票先到，⼀般等材料发票录⼊后再处理运费发票。录⼊运费发票时，如果运费供应商和材料供应商 不同，记得要在“细节”⻚中更改发票⽅，否则系统默认应付给材料供应商。


![image 6](<SAP 采购运费处理方式方案大全(一)_images/imageFile6.png>)

- 情况3：创建采购订单时⽆法确定运费⾦额。这类运费称为计划外交货成本，需要在发票校验时进⾏处 理。因为在创建采购订单时不知道具体运费，可以不维护运费，只需要维护材料价格。收货时，材料成本 中就不会包含运费。在发票校验时，可以通过录⼊计划外运费的⽅式进⾏处理。


此处录⼊的计划外运费可以分摊到发票的各个⾏项⽬中，这样这部分运费可以记账到物料成本中； 也可以记账到特定的会计科⽬。⼀般情况下，还是会要求分摊到各个⾏项⽬，然后记账到物料成本 中。具体配置如下：物料管理 -> 后勤发票校验 -> 收⼊发票 -> 配置如何过账未计划交货成本

⽆论你选择了哪种分摊⽅式，都需要在⾃动过账配置中指定未计划交货成本（UPF）所对应的总账科⽬ OBYC-UPF

### 若获取更多完整资料，可扫码加⼊如下知识星球获取更多⾏业解决⽅案以及电⼦书籍

#### 加⼊星球会员享如下五项专属福利。

- ① 可 下 载 知 识 星 球 所 有 ⽅ 案 （ 含 持 续 更 新 内 容 ）；

- ② 领 取 实 施 项 ⽬ 过 程 材 料 ；

- ③ 领 取 各 模 块 实 施 培 训 视 频 材 料 ；

- ④ 领 取 模 块 ⾏ 业 图 书 ， 管 理 及 咨 询 图 书 等 ；

- ⑤ 领 取 项 ⽬ 管 理 材 料


## 更多阅读

SAP Integrated Business Planning的实施与⽅案

新 能 源 汽 ⻋ 智 能 化 ⼯ ⼚ P L M 项 ⽬ 解 决 ⽅ 案 供 应 链 协 同 管 理 蓝 图 规 划 项 ⽬ 整 体 解 决 ⽅ 案 S A P 半 导 体 及 光 伏 ⾏ 业 最 佳 业 务 实 践 ⽅ 案 ⼯ 程 ⻋ 辆 集 团 数 字 化 转 型 S A P 解 决 ⽅ 案 S A P 化 ⼯ ⾏ 业 数 字 化 转 型 ⽅ 案 煤 炭 ⾏ 业 S A P 数 字 化 转 型 规 划 ⽅ 案

新 能 源 汽 ⻋ 智 能 制 造 企 业 数 字 化 转 型 S A P 解 决 ⽅ 案 S A P 医 疗 ⾏ 业 解 决 ⽅ 案 S A P ⾼ 级 仓 库 管 理 解 决 ⽅ 案 S A P B P C 全 ⾯ 预 算 及 合 并 解 决 ⽅ 案

- A B A P 开 发 技 术 详 解 实 例 篇 S A P 零 售 ⾏ 业 解 决 ⽅ 案 S A P 汽 ⻋ 零 部 件 供 应 商 ⾏ 业 解 决 ⽅ 案 P r o d u c t D e v e l o p m e n t w i t h S A P P L M


- P r o d u c t C o s t C o n t r o l l i n g w i t h S A P
- Q u a l i t y M a n a g e m e n t w i t h S A P M a t e r i a l s M a n a g e m e n t w i t h S A P E R P S A P S a l e s a n d D i s t r i b u t i o n i n S A P E R P


- S A P F i n a n c i a l s C o n f i g u r a t i o n a n d D e s i g n S A P 销 售 与 分 销 模 块 定 价 完 全 实 施 ⼿ 册 新 能 源 汽 ⻋ 智 能 化 ⼯ ⼚ P L M 项 ⽬ 解 决 ⽅ 案 S A P 项 ⽬ 管 理 模 块 ( P S ) 功 能 详 解 | 1 6 6 ⻚ S A P M R P 视 图 及 运 ⾏ 参 数 详 解 | 1 5 7 ⻚ S A P 汽 ⻋ 租 赁 管 理 解 决 ⽅ 案 以 及 全 球 贸 易 解 决 ⽅ 案 和 分 销 终 端 客 户 管 理 解 决 ⽅ 案 | 1 0 6 ⻚ S A P B P C 全 ⾯ 预 算 管 理 解 决 ⽅ 案 | 4 6 ⻚ S 4 信 ⽤ 控 制 详 解 | 4 6 ⻚ S A P 整 ⻋ ⼚ ⼀ 体 化 解 决 ⽅ 案 | 7 0 ⻚ S A P 系 统 M R P 整 体 逻 辑 及 运 ⾏ 参 数 详 解 | 3 6 5 ⻚
- S A P G l o b a l P r o j e c t F I C O M o d u l e O v e r v i e w | P 1 2 0 S A P 零 售 ⾏ 业 解 决 ⽅ 案 总 结 | 8 4 ⻚ G u i d e b o o k t o M a t e r i a l s R e q u i r e m e n t s P l a n n i n g | 1 7 2 ⻚ S A P P R E S S - C o n f i g u r i n g F i n a n c i a l A c c o u n t i n g i n S A P | 7 6 5 ⻚ S / 4 H A N A 销 售 定 价 详 解 | 1 1 7 ⻚ S A P 集 成 业 务 计 划 ( I B P ) O v e r v i e w


- D e e p s e e k 如 何 与 S A P 功 能 集 成 三 ⼀ 重 ⼯ E R P 项 ⽬ - 销 售 和 分 销 培 训 - 1 0 2 ⻚ S A P 需 求 传 递 与 策 略 定 义 关 联 逻 辑 S / 4 H A N A 中 的 交 货 处 理 | 7 6 ⻚ S A P M R P 视 图 参 数 精 讲 | 5 1 ⻚
- E n h a n c i n g S u p p l i e r R e l a t i o n s h i p M a n a g e m e n t U s i n g S A P S R M | 6 9 1 ⻚ 浅 析 S A P 中 各 种 成 本 的 解 释 和 计 算 ⽅ 法 S A P 序 列 号 管 理 ⽅ 案 解 析 S A P 质 量 管 理 的 应 ⽤ 与 开 发 | 4 7 3 ⻚ S A P W M 仓 库 管 理 精 讲 | 6 8 ⻚ S A P ⾥ ⾯ 的 A T P 的 定 义 S A P 销 售 与 分 销 实 施 ⼿ 册 | 4 4 5 ⻚ S T O ⾃ 动 触 发 交 货 单 、⾃ 动 发 票 、⾃ 动 交 货 、⾃ 动 采 购 发 票 | 3 0 ⻚ S A P F i o r i A d d a c u s t o m w o r k f l o w i n 6 s t e p s I n t e g r a t i o n o f M a t e r i a l M a n a g e m e n t w i t h F i n a n c i a l C o n t r o l l i n g P r o f i t a b i l i t y A n a l y s i s w i t h S A P S A P P P B i l l s o f M a t e r i a l G u i d e | 2 4 3 ⻚


S A P 需 求 管 理 ( 计 划 策 略 ) 详 解 | 1 9 ⻚

- S A P P P P r o d u c t i o n O r d e r s | 1 8 2 ⻚ S A P I n t e g r a t e d B u s i n e s s P l a n n i n g 1 8 0 8 的 新 内 容 S A P 变 式 B O M 详 解 | 1 0 ⻚ P P M a t e r i a l R e q u i r e m e n t s P l a n n i n g 物 料 分 类 账 教 程 详 解 | 3 2 ⻚ P P R o u t i n g s ⼯ 艺 路 线 详 解 S A P M M 仓 库 管 理 指 南 | 3 5 4 ⻚ S A P ⽂ 档 管 理 系 统 ( D M S ) | 1 0 6 ⻚ S A P + 商 务 智 能 完 全 解 决 ⽅ 案 | 4 3 0 ⻚ S A P B W 培 训 教 程 | 6 1 ⻚ S A P M D M 主 数 据 管 理 | 1 1 9 ⻚

F i n a n c i a l R e p o r t i n g w i t h S A P | 6 7 2 ⻚ S A P S 4 H A N A 的 财 务 概 览 | 9 2 ⻚ 财 务 ⾯ 向 S A P S 4 H A N A 的 转 换 | 1 5 9 ⻚ B u s i n e s s P r o c e s s M a n a g e m e n t t h e S A P R o a d m a p | 6 2 ⻚ 全 ⾯ 预 算 管 理 ⽅ 案 | 5 6 ⻚

- S A P Q M 质 量 管 理 模 块 前 台 操 作 详 解 | 1 3 3 ⻚ S A P - S D 信 ⽤ 管 理 实 施 总 结 | 5 5 ⻚


- C o n t r o l l i n g P r o f i t a b i l i t y + A n a l y s i s w i t h S A P | 5 5 5 ⻚ S A P 全 ⾯ 预 算 管 理 解 决 ⽅ 案 _ B P C | 4 2 ⻚ S A P S 4 H A N A 中 的 财 务 报 表 | 1 8 2 ⻚ C u r r e n c y C h a n g e o v e r i n E R P | 9 3 ⻚ M M 供 应 商 评 估 详 解 | 6 8 ⻚ S A P 中 ⽂ 使 ⽤ ⼿ 册 - - F I 总 账 | 1 8 1 ⻚ S A P 中 ⽂ 使 ⽤ ⼿ 册 F I 应 收 账 款 | 2 5 1 ⻚ S A P 中 ⽂ 使 ⽤ ⼿ 册 F I 应 付 账 款 | 2 8 9 ⻚ S A P 产 品 成 本 计 划 | 4 8 7 ⻚ 按 库 存 ⽣ 产 和 与 销 售 订 单 相 关 ⽣ 产 （ 服 务 ） 的 成 本 对 象 控 制 | 4 0 3 ⻚ C O - 物 料 分 类 账 | 3 5 ⻚ S t o c k T r a n s f e r w i t h V a l u a t e d S t o c k i n T r a n s i t S A P M M 模 块 主 数 据 与 采 购 流 程 | 5 6 9 ⻚ S A P M M 库 存 管 理 和 库 存 盘 点 | 5 2 5 ⻚ S A P 发 票 校 验 | 3 3 1 ⻚ S A P 基 于 消 耗 的 计 划 和 预 测 | 2 3 5 ⻚ M M 中 的 跨 功 能 定 制 | 4 6 5 ⻚ 在 S A P S / 4 H A N A 中 进 ⾏ 获 利 能 ⼒ 分 析 | 2 0 7 ⻚ ⾯ 向 S A P R E P C O 专 业 ⼈ ⼠ 的 S A P S 4 H A N A 管 理 会 计 | 1 8 2 ⻚ ⾯ 向 S A P E R P F I 专 业 ⼈ ⼠ 的 S A P S / 4 H A N A 财 务 会 计


在 S A P S / 4 H A N A 中 进 ⾏ 获 利 能 ⼒ 分 析 | 2 0 7 ⻚ S A P S / 4 H A N A 中 的 利 润 中 ⼼ 会 计 | 9 3 ⻚ S A P S / 4 H A N A 中 的 成 本 中 ⼼ 与 内 部 订 单 | 1 8 5 ⻚ S 4 H A N A 中 的 财 务 关 账 | 1 7 1 ⻚ S A P S / 4 H A N A 中 的 S A P C e n t r a l F i n a n c e | 2 3 2 ⻚ S A P S / 4 H A N A 中 的 财 务 报 表 | 1 8 2 ⻚ 财 务 会 计 订 制 的 基 础 知 识 、总 账 、就 收 款 和 应 付 款 | 2 1 5 ⻚ S 4 H A N A 附 加 财 务 会 计 配 置 | 2 2 5 ⻚ S A P S / 4 H A N A 中 管 理 会 计 的 业 务 流 程 | 2 6 5 ⻚ S 4 H A N A 管 理 会 计 的 业 务 流 程 | 4 1 8 ⻚ S A P B I - U s e r M a n a g e m e n t & A u t h o r i z a t i o n s | 2 6 9 ⻚ S A P B I P e r f o r m a n c e & A d m i n i s t r a t i o n | 5 3 1 ⻚

【版权声明】本专栏部分材料搜集于互联⽹公开资料，仅⽤于学习交流，版权归作者或出版商所有，本公众号不对所涉及 的版权等问题承担任何法律问题，如有侵权请联系公众号删除

