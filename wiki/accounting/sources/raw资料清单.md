---
module: accounting
kind: source
updated: 2026-08-12
source_count: 6
tags: [accounting, source-inventory]
---

# accounting 原始资料清单

本页记录 `raw/accounting/` 的原始资料和权威版本状态。原始资料只归档，不在 raw 层改写；版本、来源和校验信息在本页及对应 wiki 来源页维护。

## 统计口径

- `raw/accounting/` 当前物理有效原始资料：6 个。
- 当前按 SHA-256 去重后的资料：6 份；按规范/主题去重后为 5 份。
- 当前状态：财政部令第33号官方会计准则保留网页摘录和官网复制全文两种 raw 形态；另有 1 份成本核算实务参考、1 份仍保留的 2022 年经济法教育教材和 2 份 2026-08 教育/实务参考文章，新增文章均为 `status: unknown`。2022 年初级会计实务教材原始 PDF 已移除，来源页保留为历史知识沉淀。
- subject 分布：`accounting-practice` 6 份 raw 文件、`economic-law` 1 份；按规范/主题去重后分别为 5 份、1 份。
- 访问日期：2026-08-07。

## 已采集资料

| Raw 路径 | subject | 权威机构 | 文号 | 版本 | 发布日期 | 生效日期 | 状态 | SHA-256 | 来源页 |
|---|---|---|---|---|---|---|---|---|---|
| `raw/accounting/web/202607/企业会计准则基本准则（财政部令第33号）.md` | `accounting-practice` | 中华人民共和国财政部 | 财政部令第33号 | 2006年修订版 | 2006-02-15 | 2007-01-01 | effective（现行适用性仍需持续核验；与下一行同一规范） | `d4d0eff3fc801bc538fc9b3839f19588a99689b6efffae39a891756659d7abda` | [[wiki/accounting/sources/企业会计准则基本准则（财政部令第33号）]] |
| `raw/accounting/article/202607/企业会计准则——基本准则.md` | `accounting-practice` | 中华人民共和国财政部 | 财政部令第33号 | 2006年修订版官网复制全文 | 2006-02-15 | 2007-01-01 | effective（与上一行同一规范；保留为完整本地全文） | `a600c5985e3001e3d0b987cca57135085f73eb63b96ad5f81a835bddc22856a` | [[wiki/accounting/sources/企业会计准则基本准则（财政部令第33号）]] |
| `raw/accounting/article/202607/500强企业成本核算实务.pdf` | `accounting-practice` | 机械工业出版社 / 华章分社（版权页） | null | 2020 年纸版；电子版待核验 | 2020 | null | unknown（实务/教育参考，非现行规范） | `f69cb5166ec75b5ea179a9d618c5b58561f2b7dbef1938d5e7314d3328ebd33c` | [[wiki/accounting/sources/500强企业成本核算实务]] |
| `raw/accounting/article/202607/2022初级经济法基础官方教材电子版.pdf` | `economic-law` | 待版权页核验 | null | 2022 年教材，具体版次待核验 | 2022 | null | unknown（历史教育参考，非现行法律） | `dbf39ecc1b8dd9b86949c868f592f77962e94e92ee92297d08f4978517a312c1` | [[wiki/accounting/sources/2022初级经济法基础官方教材电子版]] |
| `raw/accounting/article/202607/2022初级会计实务官方教材电子版.pdf` | `accounting-practice` | 待版权页核验 | null | 2022 年教材，具体版次待核验 | 2022 | null | removed（原始 PDF 已移除；历史教育参考，非现行准则） | `e44d258cb058505181b8ec1c020f6a6050df59aa24cbde6f1376b8a5a31568c9` | [[wiki/accounting/sources/2022初级会计实务官方教材电子版]] |
| `raw/accounting/article/202608/财务总监花了一周，搭建的财务部内部工作体系太清晰了，第一次见这么全面的财务部工作流程！.md` | `accounting-practice` | 待核验 | null | 2026-08 网络实务参考 | null | null | unknown（图片型教育/实务参考，不是企业制度或现行法规） | `7f190c3506afccd6cf356136ea29beff10d79fad0122e8d6c8d01fdd6c80b4a6` | [[wiki/accounting/sources/财务部内部工作体系]] |
| `raw/accounting/article/202608/财务白痴学财务：第五十三课：合并报表的实务流程（ERP视角）.md` | `accounting-practice` | 待核验 | null | 2026-08 网络实务参考 | null | null | unknown（教育/实务参考，具体准则和系统行为待核验） | `e4cb6f67dcfd192030a4ded46389615b6ef0078093534722e8820227ad3c3b87` | [[wiki/accounting/sources/合并报表实务流程（ERP视角）]] |

## 待采集白名单

以下资料属于下一批候选，但在官方页面、文号、版本和生效状态完成核验前，不作为本清单的已采集资料：

- 《中华人民共和国会计法》现行/2024 年修正文本：全国人大国家法律法规数据库。
- 《企业财务会计报告条例》现行文本：国务院或中国政府网。
- 《小企业会计准则》：财政部官方来源。

## 维护要求

- 同一规范的官方网页和官网复制全文不重复计数，除非二者是不同版本或具有不可替代内容；本清单可分别列出物理 raw 文件，但规范/主题统计只计 1 份。
- 旧版本不删除；在来源页记录 `superseded` 或 `effective_to`。
- 不能确认现行状态时使用 `unknown`，不把商业转载当作权威依据。
- 新增资料后同步更新 [[wiki/accounting/overview]]、[[wiki/overview]]、[[wiki/shared/raw资料总清单]]、[[wiki/index]] 和 [[wiki/log]]。
