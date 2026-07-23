---
title: "SAP SD 出口业务全链路：你的货凭什么过海关？Intrastat申报×出口文档×禁运筛查全拆解（系列第40篇）"
source: "https://mp.weixin.qq.com/s/FtC9eTS7jvoxfou2RFsgkA"
author:
  - "[[Gary Bai]]"
published:
created: 2026-07-23
description: "SAP SD 出口业务全链路：你的货凭什么过海关？Intrastat申报×出口文档×禁运筛查全拆解（系列第4"
tags:
  - "clippings"
---
Gary Bai 小窝絮叨 *2026年7月20日 22:01*

## SAP SD 出口业务全链路：你的货凭什么过海关？Intrastat申报×出口文档×禁运筛查全拆解（系列第40篇）

> PEX 匈牙利工厂的物流经理快疯了。"一票货发到塞尔维亚（非欧盟），海关卡了一个星期——商业发票格式不对、原产地证明没做、HS Code 错了。客户那边产线快停了。"
> 
> 出口业务是 SD 里最容易踩坑的领域，因为 **不只是 SAP 配置问题** ——还涉及海关、税务、贸易合规。一个字段填错，货就卡在边境。

汽车零部件行业跨境出货极其频繁。欧盟内部出口（Intrastat）、欧盟到第三国（Export Customs）、来料加工出口、保税出口……今天把 SAP SD 出口业务的全链路拆明白。

---

## 一、出口业务的三层框架

### 1.1 先搞清楚：你的出口属于哪种？

```
第一层：欧盟内部交易（Intra-EU）
  ├── 德国 → 匈牙利（EU内部）
  ├── 匈牙利 → 罗马尼亚（EU内部）
  ├── 零税率（0% VAT）+ 欧盟销售清单(EC Sales List)
  └── Intrastat申报（每月统计）

第二层：欧盟到第三国（Export to 3rd Country）
  ├── 匈牙利 → 塞尔维亚
  ├── 匈牙利 → 中国
  ├── 真正的"出口"→ Customs出口报关
  └── √ 出口文档：商业发票 + 装箱单 + 原产地证明 + 报关单

第三层：来料加工/保税出口（Processing Trade / Bonded）
  ├── 临时出口加工后复进口
  ├── 暂免关税 → 来料加工手册管理
  └── SAP GTS(Global Trade Services) 或手工追踪
```

---

## 二、SAP 出口配置四件套

### 2.1 外国贸易数据（Foreign Trade Data）

```
核心Tcode：
  ├── VI01: 维护出口主数据（按物料的出口额外数据）
  ├── VI02: 修改
  └── VI03: 显示

物料出口主数据包含：
  ├── Commodity Code / HS Code（海关商品编码）
  ├── Export Control Classification Number (ECCN)
  ├── Origin Country of Material（原材料产地）
  ├── CAS Number（化学品，如果有）
  └── 净重 / 毛重（出口统计用）
```

### 2.2 HS Code（海关编码）是核心中的核心

```
HS Code = 海关商品编码 = 全球统一的货物分类编码

车窗传感器 = 9032.89.00
  90章: 光学、照相、测量、医疗器材
  32节: 自动调节或控制仪器
  89目: 其他
  00子目: 其他

HS Code 的作用：
  ├── 海关用：确定关税税率
  ├── Intrastat用：欧盟内部贸易统计
  ├── 原产地：用来判断是否签自贸协定优惠关税
  └── 出口管控：敏感货品（军民两用）特殊审批

每个产成品物料 → 必须维护 HS Code（MM03 → 外国贸易：出口数据）
```

### 2.3 出口许可证和禁运筛查（Embargo Check）

```
SAP GTS（Global Trade Services）: 标准功能

三种检查：
  ├── Sanction Party List Screening (SPL)
  │   → 客户/收货方是否在制裁名单上？
  │   → 俄罗斯、伊朗、朝鲜…
  │   → SAP Note 发布制裁名单更新
  ├── Embargo Check
  │   → 目的国是否被禁运？
  ├── Legal Control
  │   → 物料是否需要出口许可证？
  │   → 军民两用物资（Dual-Use Items）
  └── License Determination
      → 自动匹配适用的出口许可证类型

SPRO配置路径：
  SPRO → Logistics - General → Global Trade Services
  → Compliance Management → Sanctioned Party List Screening
```

---

## 三、出口文档体系：五张单子缺一不可

### 3.1 商业发票（Commercial Invoice）

```
= VF01 开的销售发票的出口版

额外字段（区别于国内发票）：
  ├── Incoterms（EXW / FCA / DAP 等）
  ├── Incoterms Location（具体地点：FCA Budapest）
  ├── 运输方式（海运/空运/陆运/铁路）
  ├── Country of Origin（原产国）
  ├── HS Code 每行显示
  ├── Net Weight + Gross Weight（净重/毛重）
  ├── Terms of Payment（付款条件: LC/TT/DP）
  ├── Bank Details（收款银行SWIFT）
  └── Declaration Statement（原产地声明/自由贸易声明）

SAP生成：通过输出类型（Output Type）定制出口版发票表单
  常用Form: SAPscript / Smart Form → 输出类型 ZCIN（Customs Invoice）
```

### 3.2 装箱单（Packing List）

```
= 每个箱子里装了什么

SAP来源：
  ├── VL01N 交货单 → VL02N 包装 → 创建 HU
  ├── HU 自动关联到交货单
  └── 装箱单输出 = HU 内容 × 交货单行项目明细

装箱单内容：
  ├── 箱号/托盘号（SSCC）
  ├── 每箱的物料+数量
  ├── 每箱的毛重/净重/体积
  ├── 总箱数
  └── 集装箱号（如果有）
```

### 3.3 原产地证明（Certificate of Origin / EUR.1）

```
出口到非欧盟国家 → 客户要求原产地证明
  ├── EUR.1: 欧盟-有自贸协定的国家（土耳其、韩国、日本…）
  ├── A.TR: 欧盟-土耳其关税联盟
  └── Certificate of Origin: 通用原产地证（商检局/商会出具）

SAP 的处理：
  ├── 物料主数据维护 Country of Origin
  ├── 销售订单中记录 Origin Country = 物料生产国
  ├── 长文本（VOTXN）存储原产地描述
  └── 出口发票表单中输出原产地声明

SAP GTS:
  ├── 自动判断是否适用优惠关税（Preference）
  ├── 自动计算优惠关税 vs 标准关税差异
  └── 生成 EUR.1 申请表（Need to print from Chamber）
```

### 3.4 出口报关单（Export Declaration）

```
欧盟出口报关：UN/EDIFACT 格式（CUSDEC）

SAP 接口：
  ├── SAP → 海关系统（ATLAS/ATRIGA 等各国海关门户）
  ├── IDoc: EXPINV01（出口发票IDoc）
  ├── IDoc: DESADV01（发货通知IDoc）
  └── RFC/文件传输到海关系统

用到的 SAP 标准 IDoc 接口：
  ├── EXPINV01: 出口发票
  ├── EXPINV02: 出口发票 V2
  ├── DESADV01/DESADV02: 发货通知
  └── INVOIC01/INVOIC02: 商业发票（EDI给客户的）
```

### 3.5 出口退税（Export VAT Refund）

```
出口到第三国 → 欧盟增值税退税

SAP 处理：
  ├── 发票税码: A3（出口免税，进项可退）
  ├── FTXP 配置：出口税码 = A3
  ├── 税务过账：出口收入不计提 VAT
  ├── 进项税退税：需申报（不与销项对冲）
  └── FI 侧自动分离进出口VAT科目
```

---

## 四、Intrastat：欧盟内部的"出口统计"

### 4.1 Intrastat 是什么？

```
Intrastat ≠ Customs Declaration（不是报关）

Intrastat = 欧盟内部贸易统计申报

谁要报？
  ├── 欧盟 A国家 → 欧盟 B国家 的发货
  └── 超过各国 Intrastat 门槛后必须申报

匈牙利 Intrastat 门槛（2026）：
  ├── Dispatch（发货）: HUF 150M+ / 年 → 必须报
  └── Arrival（收货）: HUF 100M+ / 年 → 必须报

申报内容：
  ├── 对方 VAT Number
  ├── Commodity Code（HS 8位）
  ├── 交易金额（EUR/HUF）
  ├── Net Mass（净重）
  └── Supplementary Unit（补充单位，如 个数 等）
```

### 4.2 SAP 的 Intrastat 配置

```
配置路径：
  SPRO → Logistics - General → Foreign Trade
  → Periodic Declarations → Intrastat

四个核心Tcode：
  ├── VE01: 维护 Intrastat 主数据（手工）
  ├── VE02: 修改
  ├── VERA: 自动选择Intrastat数据（按月份）
  └── VEIA: 生成Intrastat申报文件（生成XML/DAT）

数据来源：
  ├── 从 Billing Document 取（按发票日期）
  ├── 或从 Delivery 取（按发货日期）
  └── 取决于配置：Flow of Goods vs Flow of Invoice

数据流：
  VF01 开票 → 自动记录到Intrastat表
  → VERA 月度导出
  → VEIA 生成申报文件（XML）
  → 上传到匈牙利统计局 KSH / 税务局 NAV
```

---

## 五、Incoterms —— 报价单上的三个字母决定谁付运费

### 5.1 常用 Incoterms

```
EXW (Ex Works): 工厂交货
  → 买方自提、承担一切费用和风险
  → "货放门口，自己来拿"

FCA (Free Carrier): 货交承运人
  → 卖方负责出口清关，交到买方指定承运人
  → "我帮你清关，送到你指定的物流公司"

DAP (Delivered at Place): 目的地交货
  → 卖方付运费但不负责卸货和进口清关
  → "货送到你门口，卸货和清关你自己来"

DDP (Delivered Duty Paid): 完税后交货
  → 卖方负责一切，包括目的国进口关税
  → "货送到你手里，所有事我都包了"

汽车零部件常用：
  ├── OEM JIT供货: DAP（供应商送货到客户线边仓）
  ├── 售后市场: EXW 或 FCA
  └── 项目件: DDP（一站式交付）
```

### 5.2 SAP 中的 Incoterms

```
配置：
  SPRO → SD → Basic Functions → Incoterms

核心字段：
  ├── VBKD-INCO1: Incoterms Code（FCA、DAP等）
  ├── VBKD-INCO2: Incoterms Location（指定地点）
  └── 在销售订单头、客户主数据、销售合同均可维护

对定价的影响（VOFM）：
  → 可以写 Formula 让运费条件按 Incoterms 自动切换
  → DAP = 卖方承担运费 → 定价过程中运费条件激活
  → EXW = 买方承担运费 → 运费条件不激活
```

---

## 六、实战：匈牙利PEX出口塞尔维亚全链路

### 6.1 场景还原

```
订单：匈牙利PEX → 塞尔维亚客户（非欧盟）
货物：800个车窗传感器
金额：EUR 52,000
条件：FCA Budapest
付款：T/T 30天

SAP 处理链路：

Step 1: VA01 创建销售订单
  ├── 订单类型: ZOR3（出口订单）
  ├── Incoterms: FCA Budapest
  ├── 税码: A3（出口免税）
  ├── 付款条件: NT30（30天）
  └── 目的地: RS（塞尔维亚）

Step 2: VL01N 创建交货单
  ├── Shipping Point: 出口出货点
  ├── Route: TRUCK-EXPORT
  └── 自动触发外贸数据检查

Step 3: VL02N 包装 + 发货过账
  ├── 创建 HU → 装箱单自动生成
  ├── PGI 过账 → COGS 自动记账
  ├── 触发 IDoc: DESADV01（发给客户/货代）
  └── 触发 IDoc: EXPINV01（发给海关系统）

Step 4: VF01 开票
  ├── 自动生成出口商业发票（含HS Code、原产地、净重等）
  ├── 输出类型 ZCIN 打印海关发票
  └── FI 凭证：借 应收账款 | 贷 出口收入 A3（免税）

Step 5: 海关申报
  ├── 货代系统收到 SAP 的 EXPINV01 → 报关
  ├── 客户清关 → 提货
  └── 出口退税：进项税可退（独立申报）
```

### 6.2 出口订单订单类型的特殊配置

```
ZOR3（出口订单类型）vs ZOR1（国内订单）的区别：

配置差异：
  ├── 定价过程: ZRVAA01（出口定价，含运费条件）
  ├── 输出类型: 含 ZCIN（海关发票）
  ├── 文本确定: 含出口声明语句
  ├── 税码默认: A3（出口免税）
  ├── 信用检查: 启用（出口通常需要LC或预付款保证）
  └── 不完整性检查: 强制检查 Incoterms + HS Code + 原产国

订单类型的复制配置：
  VOV8 → 选中 ZOR1 → Copy as → 填 ZOR3 → 调整上述差异
```

---

## 七、出口最常见的 5 个故障

### 7.1 Intrastat 数据缺失

```
症状：月底跑 VERA → Intrastat 数据对不上

排查：
  1. VI03 → 确认物料有 HS Code (Commodity Code)
  2. VF02 → 确认发票行有 Foreign Trade 数据
  3. VE01 → 检查 Intrastat 主数据设置
  4. SPRO → 检查 Flow of Goods 或 Flow of Invoice 配置
  5. 确认 VAT Number 在客户主数据和公司代码主数据中维护
```

### 7.2 出口发票格式不对海关卡货

```
症状：海关说你的发票缺少 HS Code 或原产地信息

排查：
  1. Smartform 检查：出口发票表单是否包含这些字段
  2. VF02 → 发票头 → Foreign Trade 页签 → 检查数据是否完整
  3. VI03 → 确认物料出口数据已维护
  4. SE71 调整 Smartform：添加 HS Code / Country of Origin / 净重
```

### 7.3 禁运筛查报错

```
症状：VA01 创建出口订单时报 "Embargo check failed"

排查：
  1. SPL → 检查客户名称是否在制裁名单中
  2. GTS → Compliance Check → 检查详细日志
  3. 可能原因：
    → 客户所在国被禁运（如伊朗、朝鲜、叙利亚）
    → 物料是军民两用物资（需出口许可证）
    → 客户名称与制裁名单模糊匹配
```

### 7.4 欧盟内部交易的税码错误

```
症状：匈牙利→德国开了 27% VAT 发票

原因：
  → 客户主数据德国的 VAT Number 空
  → 系统不认为这是欧盟内部交易 → 按国内处理

修复：
  XD03 → 客户主数据 → Tax Data → VAT Registration Number: DE123456789
  → 重新开票 → 系统自动切 EU 税码 → 0%
```

### 7.5 出口退税报了也没用

```
症状：出口当月申报了进项税退税，但税务局说数据不对

原因：
  → 出口发票和采购发票在同一个 VAT Return 申报
  → 系统没有在 FI 侧分离出口相关进项和国内进项

正确配置：
  → OB40: 出口进项税科目独立（VST-EXPORT）
  → 采购发票税码：区分出口物料和国内物料
  → VAT Return Report 报表模板修改：出口进项独立一行
```

---

## 八、一句话总结

> **SAP 出口 = HS Code 是基石 + Incoterms 定义责任边界 + Intrastat 管欧盟内部统计 + 出口文档五件套缺一不可。出口业务三分靠 SAP 配置，七分靠海关和贸易合规知识。把 HS Code 和客户 VAT Number 维护对了，80% 的出口问题就消失了。**

**下篇预告** ：第41篇 —— SAP SD 数量合同：系统怎么管"年度500万个零件、按月分批叫"？

---

📌 **SAP SD 系列往期回顾** ：

- 第1篇：销售组织架构与主数据
- 第5篇：定价过程 Condition Technique
- 第15篇：ATP 可用性检查
- 第34篇：SD × PP MTO 全链路
- 第35篇：批次管理三把刀
- 第36篇：HU 包装管理
- 第37篇：物料替代 × Discontinuation
- 第38篇：返利管理 Rebate 全链路
- 第39篇：SD × FI 一张发票的财务之旅

👆 关注公众号查看完整系列。

SAP入门配置 · 目录

作者提示: 个人观点，仅供参考