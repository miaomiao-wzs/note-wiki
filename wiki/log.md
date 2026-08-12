---
module: shared
kind: log
updated: 2026-08-12
source_count: 68
tags: []
---

## 2026-08-12 | 维护教材来源页 | accounting
- 主题：为大体积历史教材后续从 raw 移除做准备，并清理全局索引重复登记
- 来源：`raw/accounting/article/202607/2022初级会计实务官方教材电子版.pdf`
- 做了什么：删除 `wiki/index.md` 中该教材来源页的重复链接；保留唯一入口和完整来源页；在来源页增加 `raw_availability: present-planned-removal`，明确当前 PDF 仍存在、后续移除后保留历史路径、页数、SHA-256 和已整理知识内容；将解析目录标记为历史临时产物
- 结果：PDF 当前 SHA-256 仍为 `e44d258cb058505181b8ec1c020f6a6050df59aa24cbde6f1376b8a5a31568c9`；当前 accounting 7 个、全局 80 个物理 raw 文件统计暂不变化
- 后续：用户实际删除 PDF 后，将来源页生命周期改为 `removed`，重新扫描并同步 accounting 清单、模块总览、全局 raw 总清单、知识库总览和日志；预计 accounting 7→6、全局 80→79（以实际扫描为准）


- 主题：为大体积历史教材后续从 raw 移除做准备，并清理全局索引重复登记
- 来源：`raw/accounting/article/202607/2022初级会计实务官方教材电子版.pdf`
- 做了什么：删除 `wiki/index.md` 中该教材来源页的重复链接；保留唯一入口和完整来源页；在来源页增加 `raw_availability: present-planned-removal`，明确当前 PDF 仍存在、后续移除后保留历史路径、页数、SHA-256 和已整理知识内容；将解析目录标记为历史临时产物
- 结果：PDF 当前 SHA-256 仍为 `e44d258cb058505181b8ec1c020f6a6050df59aa24cbde6f1376b8a5a31568c9`；当前 accounting 7 个、全局 80 个物理 raw 文件统计暂不变化
- 后续：用户实际删除 PDF 后，将来源页生命周期改为 `removed`，重新扫描并同步 accounting 清单、模块总览、全局 raw 总清单、知识库总览和日志；预计 accounting 7→6、全局 80→79（以实际扫描为准）


- 主题：整理用户更新后的 raw 资料并纳入知识库
- 来源：`raw/Clippings/` 中 3 篇固定资产 Markdown、1 篇 SAP 项目集成测试 Markdown及其 18 张流程图
- 做了什么：将 3 篇固定资产资料归档到 `raw/fico/article/202608/`，建立资产折旧计算逻辑、固定资产折旧开始日期和资产会计常见日期 3 个来源页；将项目集成测试文档归档到 `raw/shared/article/202608/`，建立 shared 来源页和清单，18 张流程图归档到 `raw/assets/` 并修正原文本地图片路径
- 结果：当前有效 raw 物理文件为 80 个：FICO 54、ABAP 1、accounting 7、SD 17、shared 1；`raw/Clippings/` 已无有效资料；流程图作为附件不计入 raw 文件统计
- 原始资料边界：固定资产网络文章、测算器公式、AFAMP/T090NP/ABT1N 线索及项目自开发事务码和外部系统接口均标记为待官方/目标系统核验；未将测试脚本升级为正式操作规范
- 后续：核对固定资产日期和折旧逻辑的目标系统凭证；统一项目测试场景编号、补齐空白连通测试明细，并补充接口报文和责任系统证据

- 主题：核对全库 raw 统计、当前入口、wiki-link 和新增剪藏来源页之间的一致性
- 做了什么：按有效扩展名和排除规则重新扫描 `raw/`；确认物理文件 76、SHA-256 去重 76，FICO 51、ABAP 1、accounting 7、SD 17；将 ABAP 当前 raw 口径从误写的 2 修正为 1，并保留缺失的旧 ABAP 异常处理原始 Markdown 来源页为待恢复状态
- 链接修复：将 [[wiki/fico/sources/报表查询]] 中不存在的 `现金流量表原因代码` 概念链接改为明确的待建主题说明；为 CKMLCP、IDCNAP、统驭科目和 ALV 来源页补充可确认的实体/概念/来源页关联，并为 CKMLCP、IDCNAP、统驭科目实体/概念页补回新来源反向链接
- 冲突边界：CKMLCP、IDCNAP、统驭科目类型、ALV 导出权限、ABAP 架构和 accounting 合并报表中的网络文章观点仍保持待官方/目标系统核验；未修改 raw 原文、历史日志统计或模板占位符链接
- 结果：当前统计与模块入口统一；真实内容断链已处理，模板占位符和历史示例资源未误删。- 主题：将 7 篇网络 Markdown 剪藏纳入模块化知识库
- 来源：`raw/Clippings/` 中 CKMLCP、IDCNAP、统驭科目类型、ALV 导出权限、SAP 系统架构白皮书、财务部内部工作体系、合并报表 ERP 视角资料
- 做了什么：按 `created`/当前批次统一归档到 `raw/fico/article/202608/`（4 篇）、`raw/abap/article/202608/`（1 篇）和 `raw/accounting/article/202608/`（2 篇）；建立 7 个来源页；更新各模块 raw 清单、模块总览、全局索引、总览和本日志
- 结果：7 个原始文件迁移前后 SHA-256 保持一致；`raw/Clippings/` 无有效 `.md/.docx/.pdf/.xlsx`；当前有效 raw 物理文件为 FICO 51、ABAP 1、accounting 7、SD 17，全局 76 个（按当前扫描；SHA-256 去重仍为 76）。来源页均保留原始 URL，外部图片未批量下载
- 原始资料边界：网络文章的事务码、字段、配置、版本、性能阈值和操作观点均按 `status: unknown`/待系统或官方核验处理；accounting 两篇仅作教育/实务参考，不替代法规、准则或企业制度；图片型财务部资料只记录可见摘要，图表细节待核验
- 后续：在目标 SAP/ERP 版本和企业制度中核对 CKMLCP、IDCNAP、统驭科目、ALV 授权、架构性能指标及合并报表政策；若需本地化图片，另行核验版权并下载至 `raw/assets/`

- 主题：补充《企业会计准则——基本准则》官网复制全文
- 来源：`raw/accounting/article/202607/企业会计准则——基本准则.md`；既有网页摘录 `raw/accounting/web/202607/企业会计准则基本准则（财政部令第33号）.md`
- 做了什么：核验新增全文覆盖财政部令第33号第一条至第五十条；记录官网复制全文 SHA-256 `a600c5985e3001e3d0b987cca57135085f73eb63b96ad5f81a835bddc22856a` 和网页摘录 SHA-256 `d4d0eff3fc801bc538fc9b3839f19588a99689b6efffae39a891756659d7abda`；去除网页导航/HTML 噪声并统一排版后确认正文一致；在同一来源页合并两种 raw 证据形态
- 结果：更新 [[wiki/accounting/sources/企业会计准则基本准则（财政部令第33号）]]、accounting raw 清单、accounting 总览、[[wiki/index]]、[[wiki/overview]] 和 [[wiki/shared/raw资料总清单]]；accounting 物理文件更新为 5、规范/主题去重为 4，全局物理文件更新为 69、主题去重仍为 67
- 原始资料边界：两个 raw 文件均保留且未改写；SHA-256 不同仅反映网页抓取噪声和排版形态差异，不代表不同规范；未创建重复来源页
- 后续：如需确认后续修订或现行适用性，继续以财政部官方发布信息核验，不以本地复制文本替代现行版本判断

## 2026-07-30 | 新增来源页 | accounting
- 主题：新增会计基础 PDF 资料整理
- 来源：`raw/accounting/article/202607/500强企业成本核算实务.pdf`、`2022初级经济法基础官方教材电子版.pdf`、`2022初级会计实务官方教材电子版.pdf`
- 做了什么：使用 `opendataloader-pdf` 解析 3 份 PDF；记录 550 页成本核算实务、433 页经济法教材和 335 页会计实务教材的工具识别结果、SHA-256、原始路径和解析路径；按 `accounting-practice`/`economic-law` 建立 3 篇来源页
- 结果：新增 [[wiki/accounting/sources/500强企业成本核算实务]]、[[wiki/accounting/sources/2022初级经济法基础官方教材电子版]]、[[wiki/accounting/sources/2022初级会计实务官方教材电子版]]；更新 accounting 清单、模块首页、全局索引、总览和 raw 总清单
- 版本与风险：新增 PDF 均标记 `status: unknown`；教材和实务资料仅作教育/实务参考，不能替代现行法律、企业会计准则或 SAP/FICO 配置；解析文本存在 OCR、字体、列表或推广水印问题，版权与授权待核验
- 后续：核验三份 PDF 的版权页、ISBN、出版社和授权范围；涉及现行法律、税率、会计准则或企业制度时，回到官方来源逐项确认

## 2026-07-30 | 新增来源页 | FICO
- 主题：固定资产余额与期间查询
- 来源：用户对 `S_ALR_87011967` 与 `ZFIR001` 实际查询结果的确认
- 做了什么：整理资产余额清单与固定资产明细表的定位差异，记录 `S_ALR_87011967` 查询截止期间资产原值、折旧、累计折旧和净值的适用场景；补充 5 月末与 6 月末对比方法、总账核对要点，并记录 `ZFIR001` 日期筛选当前未改变结果的系统观察
- 结果：新增 [[wiki/fico/sources/固定资产余额与期间查询]]、[[wiki/fico/entities/S_ALR_87011967]]；更新 [[wiki/fico/entities/ZFIR001]]、[[wiki/fico/sources/资产业务操作]]、FICO 与全局索引
- 后续：如需修复 `ZFIR001`，应由开发人员核查日期字段、资产价值期间和历史数据取数逻辑

- 做了什么：整理资产余额清单与固定资产明细表的定位差异，记录 `S_ALR_87011967` 查询截止期间资产原值、折旧、累计折旧和净值的适用场景；补充 5 月末与 6 月末对比方法、总账核对要点，并记录 `ZFIR001` 日期筛选当前未改变结果的系统观察
- 结果：新增 [[wiki/fico/sources/固定资产余额与期间查询]]、[[wiki/fico/entities/S_ALR_87011967]]；更新 [[wiki/fico/entities/ZFIR001]]、[[wiki/fico/sources/资产业务操作]]、FICO 与全局索引
- 后续：如需修复 `ZFIR001`，应由开发人员核查日期字段、资产价值期间和历史数据取数逻辑

## 2026-07-30 | 新增模块 | accounting
- 主题：会计与经济法知识模块初始化
- 来源：用户确定的新模块方案；中国政府网官方《企业会计准则——基本准则》页面
- 做了什么：建立 `raw/accounting/` 与 `wiki/accounting/` 同构目录；以 `subject: economic-law|accounting-practice` 区分主题；建立会计模块首页、原始资料清单和 FICO/accounting 归属映射；采集并归档 1 份官方会计准则网页摘录，记录财政部令第33号、发布/生效日期、官方 URL 和 SHA-256
- 结果：新增 [[wiki/accounting/overview]]、[[wiki/accounting/sources/企业会计准则基本准则（财政部令第33号）]]、[[wiki/accounting/entities/企业会计准则——基本准则]]、[[wiki/accounting/concepts/企业会计准则基本原则]]、[[wiki/accounting/sources/raw资料清单]]、[[wiki/accounting/synthesis/FICO 与 accounting 归属映射]]；更新全局索引、总览和 raw 总清单
- 后续：继续按官方白名单核验《中华人民共和国会计法》《企业财务会计报告条例》《小企业会计准则》；官方版本无法确认时标记 `unknown`，不以商业转载替代


- 来源：用户查询整理；[[raw/fico/article/202607/FICO.md]]
- 做了什么：整理 `CON2` 的作用、实际作业价格重估计算逻辑、生产成本月结位置、与 `KSS2`/`KSII`/`KKS1`/`CO88` 的关系、检查方法和异常排查方向；明确 `CON2` 不等同于生产订单最终结算
- 结果：新增 [[wiki/fico/sources/CON2 生产订单按实际作业价格重估]]，并同步更新 FICO 与全局索引
- 后续：如需形成企业正式操作手册，应补充目标系统的实际作业价格结果、重估凭证样例和配置核验记录

## 2026-07-30 | 新增来源页 | FICO
- 主题：CO88 生产订单结算与会计分录
- 来源：用户确认的生产订单结算科目映射；[[raw/fico/article/202607/FICO.md]]
- 做了什么：整理 `CO88` 的作用、成本月结位置、产成品/在产品/生产差异结算逻辑、当前企业科目映射、典型分录示例、关联事务码和凭证核对方法；明确典型方向不替代实际系统凭证
- 结果：新增 [[wiki/fico/sources/CO88 生产订单结算与会计分录]]，并同步更新 FICO 与全局索引
- 后续：如需形成企业正式操作手册，应补充目标系统结算变式、自动科目配置、真实 CO/FI 凭证样例和测试证据



- 单条记录建议使用 [[wiki/templates/log-entry]] 的格式。
- 标题使用 `## 日期 | 动作 | 模块`。
- 日志继续采用追加式写法，不回头重排历史记录。

## 2026-07-06 | 初始化知识库 | shared
- 主题：知识库骨架初始化
- 来源：`LLM WIKI.md`
- 做了什么：初始化 raw/wiki 分层结构，补齐模板、链接规范和日志条目模板
- 结果：建立 `CLAUDE.md`、`wiki/index.md`、`wiki/overview.md`、`wiki/log.md` 和 `wiki/templates/`
- 后续：继续按模块分批整理 raw 原始资料

## 2026-07-07 | 整理 raw | FICO
- 主题：FICO Markdown 原始资料第一轮整理
- 来源：`raw/fico/article/202607/`
- 做了什么：整理 4 个 Markdown 原始资料，建立来源页、raw 资料清单、实体页和概念页
- 结果：新增 `wiki/fico/sources/raw资料清单.md`，并整理 `ABAW 资产减值准备`、`CO 分摊分配配置说明`、`OKB9 成本要素默认成本中心配置`、`主营业务成本科目是否勾选成本要素` 四个来源页
- 后续：继续分批处理 FICO 的 Word、PDF 和 Excel 原始资料

## 2026-07-08 | 迁移附件 | FICO
- 主题：raw Markdown 图片引用统一
- 来源：`/Users/waterboy/jmkx_work/note/财务/note/images`
- 做了什么：复制 raw Markdown 实际引用的 6 张图片到 `raw/assets/`，并将图片链接统一改为 `![[raw/assets/图片名.png]]`
- 结果：更新 `raw/fico/article/202607/ABAW 资产减值准备.md` 和 `raw/fico/article/202607/OKB9 成本要素默认成本中心配置.md` 的图片引用
- 后续：后续新增 raw Markdown 时，图片统一放入 `raw/assets/`

## 2026-07-08 | 制定计划 | FICO
- 主题：FICO 原始资料后续整理计划
- 来源：`raw/fico/`
- 做了什么：盘点剩余 30 个待整理文件，并按基础操作、应收应付、月结年结、成本资产、发票税票、PDF 专题和事务代码清单拆分批次
- 结果：新增 `wiki/fico/synthesis/FICO 原始资料后续整理计划.md`
- 后续：建议下一步执行第二批 FICO 基础操作手册整理

## 2026-07-08 | 整理 raw | FICO
- 主题：第二批 FICO 基础操作手册整理
- 来源：`raw/fico/article/202607/`
- 做了什么：提取并整理 4 个 Word 操作手册，建立来源页、补充实体页和概念页
- 结果：新增 `会计科目主数据维护`、`凭证记账`、`报表查询`、`汇率维护` 四个来源页，并补充 FS00、FI 凭证记账、财务报表查询、汇率维护等相关页面
- 后续：建议下一步执行第三批：应收应付与客商主数据

## 2026-07-08 | 修正结论 | FICO
- 主题：凭证批量导入事务码确认
- 来源：用户确认
- 做了什么：确认 `ZFIU001` 才是凭证批量导入记账功能，可导入预制凭证，也可批量导入过账凭证
- 结果：更新 `wiki/fico/sources/凭证记账.md`、`wiki/fico/entities/ZFIU001.md`、`wiki/fico/entities/ZFIC002.md`，并新增 `wiki/fico/concepts/凭证批量导入.md`
- 后续：如后续在系统中确认 `ZFIC002` 的真实用途，再补充对应实体页说明

## 2026-07-08 | 整理 raw | FICO
- 主题：FICO raw 原始资料完整整理
- 来源：`raw/fico/`
- 做了什么：继续整理剩余 18 个 Word、7 个 PDF 和 1 个 Excel 资料；使用 `opendataloader-pdf` 解析 PDF；建立来源页并补充大量事务码实体页和概念页
- 结果：FICO 当前 34 个有效 raw 原始资料已完成本轮整理，更新 `wiki/fico/sources/raw资料清单.md`、`wiki/fico/overview.md`、`wiki/index.md` 和 `wiki/fico/synthesis/FICO 原始资料后续整理计划.md`
- 后续：建议基于已整理资料继续提炼专题综合页，如 FICO 期末处理流程、采购发票到付款清账流程、销售开票到客户收款流程、成本月结与物料分类账处理

## 2026-07-08 | 整理 raw | shared
- 主题：全 raw 目录整理状态确认
- 来源：`raw/`
- 做了什么：盘点所有模块 raw 目录，确认 FICO 已完成，ABAP/MM/PP/QM 暂无有效资料，附件和系统文件不作为来源页整理
- 结果：新增 `wiki/shared/raw资料总清单.md`，并更新 `wiki/index.md`、`wiki/overview.md`、`wiki/abap/overview.md`、`wiki/mm/overview.md`、`wiki/pp/overview.md`、`wiki/qm/overview.md`
- 后续：后续新增 raw 文件后，按模块继续整理到对应 `wiki/<module>/sources/`

## 2026-07-08 | 整理特别总账 | FICO
- 主题：F-02 特别总账录入操作手册
- 来源：用户确认的特别总账规则
- 做了什么：整理 F-02 特别总账录入的操作规则，明确客户常见过账码为 09/19、供应商常见过账码为 29/39，SGL 为特别总账标识，并补充客户/供应商特别总账概念页
- 结果：新增 `wiki/fico/sources/F-02 特别总账录入.md`、`wiki/fico/concepts/特别总账.md`、`wiki/fico/concepts/客户特别总账.md`、`wiki/fico/concepts/供应商特别总账.md`、`wiki/fico/synthesis/F-02 特别总账录入操作手册.md`，并更新索引
- 后续：如需可继续补充客户/供应商特别总账的单据示例

## 2026-07-08 | 整理项目结转 | FICO
- 主题：月结项目结转操作手册
- 来源：`raw/fico/article/202607/SAP实施项目_FICO_操作手册_成本模块_V1.0.docx`
- 做了什么：从成本模块原始 Word 中提取项目结算规则、CJ88 单个项目结算、CJ8G 批量项目结算、CJI3 余额检查等相关截图，并整理成月结项目结转操作手册
- 结果：新增 `wiki/fico/synthesis/月结项目结转操作手册.md`，提取 18 张项目结转截图到 `raw/assets/`，并更新 `wiki/index.md` 与 `wiki/fico/sources/成本模块操作手册.md`
- 后续：如后续确认项目接收方、结算变式和公司实际月结步骤，可继续补充真实案例

## 2026-07-15 | 新增 SD 并整理新增 raw | shared
- 主题：新增 SD 模块与剪藏资料整理
- 来源：`raw/Clippings/`
- 做了什么：新增 `raw/sd/` 和 `wiki/sd/` 同构目录；将新增剪藏资料复制归档到 SD、FICO、ABAP 对应模块目录；迁移剪藏 Markdown 中的外部图片到 `raw/assets/`；整理 SD 销售订单处理、FICO 科目主数据批量扩充、ABAP 异常处理三篇来源页及相关实体页、概念页
- 结果：新增 [[wiki/sd/overview]]、[[wiki/sd/sources/SAP S4HANA销售订单处理（从询价到合同）]]、[[wiki/fico/sources/SAP 如何批量扩充科目主数据到其他子公司]]、[[wiki/abap/sources/ABAP 异常处理基础与核心概念]]，并更新全局索引、raw 总清单、模块首页和终端 Claude 使用说明
- 后续：后续新增 SD 资料时继续按 `raw/sd/<type>/<YYYYMM>/` 归档，并优先补充 VA01 创建销售订单、VA21 创建报价、VA41 创建合同等操作手册


## 2026-07-15 | 整理新增 raw | FICO / SD / MM
- 主题：新增 FICO、SD、MM 相关原始资料整理
- 来源：`raw/fico/article/202607/`、`raw/sd/article/202607/`
- 做了什么：整理新增 FICO Markdown、SD Markdown 和 3 个 PDF；使用 `opendataloader-pdf` 解析 PDF；为 F.19 GR/IR 重分类、在建工程转固反向处理、成本中心流入工单核对、生产工单收货与质检取样成本、资产负债表与利润表勾稽、生产工单跨月 TECO、SD 销售退货、销售订单、ATP、物料销售视图、客户资质校验、销售退货移动类型、SD 非常见配置点、费用类采购科目确定等主题建立来源页、实体页和概念页
- 结果：更新 [[wiki/fico/sources/raw资料清单]]、[[wiki/sd/sources/raw资料清单]]、[[wiki/mm/sources/raw资料清单]]、[[wiki/shared/raw资料总清单]]、[[wiki/index]]、[[wiki/overview]]、[[wiki/fico/overview]]、[[wiki/sd/overview]]、[[wiki/mm/overview]]；并将新增 Markdown 图片复制到 `raw/assets/` 后改为 Obsidian 嵌入
- 后续：如需处理当前工作树中缺失的旧 `ZFIR043` Word 原件，应先确认是否恢复；后续新增 PDF 仍必须用 `opendataloader-pdf` 解析

## 2026-07-16 | 重新整理 FICO 综合资料 | FICO
- 主题：`FICO.md` 综合资料重新整理与图片修复
- 来源：`raw/fico/article/202607/FICO.md`
- 做了什么：确认原 `FICO.docx` 已替换为 Markdown；从此前图片目录复制 114 张缺失图片到 `raw/assets/`，并将原文 Markdown 图片、HTML 图片和旧 wiki 图片引用统一改为 Obsidian 嵌入；重写 [[wiki/fico/sources/FICO 综合资料]]，补充报表勾稽、事务码、凭证冲销、供应商客户往来、采购发票与 GR/IR、成本月结、物料分类账、固定资产、WBS、销售开票等主题索引
- 结果：更新 [[wiki/fico/sources/raw资料清单]]、[[wiki/fico/overview]] 和 [[wiki/index]]，将来源路径从 `FICO.docx` 调整为 `FICO.md`
- 后续：原文中存在高风险操作、debug、默认密码和带 token 的外部链接内容，后续如需沉淀为正式操作手册，应先脱敏并经过测试系统验证

## 2026-07-27 | 整理作业分割资料 | FICO
- 主题：SAP 作业分割原理、OKES/OKEW 分割结构、权数指标与作业类型成本分割
- 来源：`raw/Clippings/SAP 作业分割原理  OKEW.md`，归档到 `raw/fico/article/202607/SAP 作业分割原理 OKEW.md`
- 做了什么：建立 [[wiki/fico/sources/SAP 作业分割原理 OKEW]] 和 [[wiki/fico/concepts/作业分割]]；增量更新成本中心、作业类型、作业价格、实际作业分摊、CO 分摊分配、产品成本结算、KSS2 和 KSII 关联；同步 FICO/全局索引与 raw 清单
- 结果：沉淀 22 人天、32 小时、8:1 权重的等效数量计算；记录原文 `32/36` 疑似笔误，并将方法 12、`Wt.`、`COKL` 及 KSS2/KSII 关系标记为待系统或官方资料核验；原始剪藏保留
- 后续：如需形成企业操作步骤，应结合目标 SAP 版本、分割结构和月结方案验证具体配置与执行顺序

## 2026-07-27 | 补充 SCC4 生产维护边界 | FICO
- 主题：生产环境 OKB9/OKEW 临时维护方法
- 来源：用户提供的现场处理方法
- 做了什么：新增 [[wiki/fico/synthesis/生产环境 OKB9 OKEW 临时维护方法]]、[[wiki/fico/entities/SCC4]] 和 [[wiki/fico/entities/OKEW]]；并更新 OKB9 实体、OKB9 来源、成本要素默认成本中心、作业分割、作业分割来源页及 FICO 导航
- 结果：记录在授权、审批、备份和回退准备完成后，SCC4 可临时从“不允许更改”切换为“不带自动记录的更改”，完成必要 OKB9/OKEW 修改和验证后必须立即恢复为“不允许更改”；明确该方法可能影响正常传输追踪，不是 SAP 标准的无条件推荐流程
- 后续：按目标 SAP 版本和企业生产变更制度核验 SCC4 选项行为，并保留真实变更单、前后配置值和审计记录

- 主题：迁移已整理剪藏原始文件
- 来源：`raw/Clippings/`
- 做了什么：将 4 篇 FICO 剪藏移动到 `raw/fico/article/202607/`，将 2 篇 SD 剪藏移动到 `raw/sd/article/202607/`；删除 `raw/Clippings/.DS_Store`
- 结果：6 篇 Markdown 剪藏均与既有归档副本逐字一致，`raw/Clippings/` 已无有效文件；同步 FICO、SD 和全局 raw 清单中的暂存目录说明
- 后续：新增剪藏应先按模块归档并建立来源页，再清理暂存目录

- 主题：`FICO.md` 综合资料新增接口报表与特殊业务专题
- 来源：`raw/fico/article/202607/FICO.md`
- 做了什么：更新 [[wiki/fico/sources/FICO 综合资料]]；新增 [[wiki/fico/sources/FICO 接口日志与报表逻辑]]、[[wiki/fico/sources/FICO 特殊业务与期初边界]]；补充物料价格控制、物料分类账差异处理、财务月结、发票校验和 WBS 元素概念页，并同步 FICO 导航与全局索引
- 结果：沉淀 EAS/EC/OA/SRM 接口日志和自开发报表取值线索；补充农产品税务、免费赠送、运费、统计型 WBS、承兑现金流、CKMLCP/KSII 排查及期初库存/资产边界；敏感信息已脱敏，高风险动作均标记为现场经验/待核验/非无条件推荐

## 2026-07-28 | 整理 AB08 资产凭证冲销文章 | FICO
- 主题：FI-AA 资产会计凭证冲销边界与 `AB08` 核验清单
- 来源：`raw/fico/article/202607/SAP FICO基础笔记：AA模块凭证冲销操作详解-AB08.md`
- 做了什么：将原始剪藏从 `raw/Clippings/` 移动到 `raw/fico/article/202607/`；新增 [[wiki/fico/sources/SAP AA模块凭证冲销 AB08]]；更新 [[wiki/fico/entities/AB08]]、[[wiki/fico/concepts/凭证冲销]]、[[wiki/fico/sources/raw资料清单]]、[[wiki/shared/raw资料总清单]]、[[wiki/overview]]、[[wiki/fico/overview]] 和 [[wiki/index]]
- 结果：保留 `AB08` 与 `FB08` 的业务来源边界，明确采购/销售/物料集成凭证应回到原业务模块处理；将冲销原因、跨期跨年度、负值记账、批量处理、折旧先后顺序和 `ABMW` 标记为系统/配置待核验；排除删除资产记录、直接改底表和固定原因码结论
- 后续：如需形成企业级冲销手册，应补充目标系统版本、凭证样例、配置截图、审批矩阵、测试证据和回退方案

- 主题：SAP 固定资产折旧异常的诊断、调整事务边界与 AO78 配置依赖
- 来源：`raw/fico/article/202607/SAP资产折旧调错了怎么办？用ABMA冲销与ABAA补提（附AO78配置）.md`
- 做了什么：将原始剪藏从 `raw/Clippings/` 移动到 `raw/fico/article/202607/`；同步更新 [[wiki/fico/sources/SAP资产折旧错误调整]]、[[wiki/fico/sources/raw资料清单]]、[[wiki/shared/raw资料总清单]]、[[wiki/overview]] 和 [[wiki/fico/overview]] 的来源路径与统计
- 结果：`raw/Clippings/` 不再保留该文件；FICO 物理有效资料更新为 46 个，按主题去重为 45 个，全局模块化有效资料更新为 62 个
- 后续：新增 Clippings 整理任务按所属模块、类型和年月完成归档后，再建立或更新 wiki 来源页
- 后续：以目标系统当前代码、配置、日志和税务政策核验自开发对象、报表取值、特殊业务税务结果及期初导入方案；本轮未新增 raw 文件，FICO 统计仍为 45 个物理资料、44 个主题去重资料
