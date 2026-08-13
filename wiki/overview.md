---
module: shared
kind: overview
updated: 2026-08-13
source_count: 78
tags: []
---

# 知识库总览

这个仓库采用“原始资料层 + 知识沉淀层”的方式维护：
- `raw/` 存放不可直接整理的原始资料。
- `wiki/` 存放整理后的知识页面，包括实体、概念、对比和综合结论。
- `CLAUDE.md` 定义以后如何维护这套结构。

## 两层的分工

- `raw/`：保存原始文件，尽量不改动文件内容，只负责归档。
- `wiki/`：保存整理后的知识页面，适合统一格式、交叉链接和持续维护。

## 当前 raw 整理状态

- 当前 `raw/` 下有效原始资料按文件口径共 78 个；按 SHA-256 去重当前仍为 78 个。`raw/Clippings/` 中 4 篇 Markdown 已迁移到 FICO 和 shared 的 202608 目录；18 张集成测试流程图归档到 `raw/assets/`，不重复计入原始资料。
- FICO 当前 54 个模块内有效原始资料（含 3 篇 202608 固定资产资料）已整理，详见 [[wiki/fico/sources/raw资料清单]]。
- shared 当前 1 个跨模块项目集成测试 Markdown 已整理，详见 [[wiki/shared/sources/raw资料清单]]。
- accounting 当前 5 个有效 raw 文件，按规范/主题去重为 4 份；两份 2022 年教材原始 PDF 已移除，但来源页和历史整理内容保留；新增网络教育/实务参考文章均标记 `status: unknown`，详见 [[wiki/accounting/sources/raw资料清单]]。
- ABAP 当前 1 个有效原始资料已整理，详见 [[wiki/abap/sources/raw资料清单]]。
- SD 当前 17 个有效原始资料已整理，详见 [[wiki/sd/sources/raw资料清单]]。
- MM 当前无独立 raw 原始资料，但已从 SD 目录中识别并整理 1 个 MM/FICO 跨模块来源页：[[wiki/mm/sources/SAP-MM费用类采购通过物料组确定科目]]。
- `raw/assets/` 是 raw Markdown 图片附件目录，不单独整理成来源页。
- `raw/pp/`、`raw/qm/` 当前只有占位文件，暂无有效原始资料。
- `raw/shared/` 当前有 1 个跨模块项目集成测试 Markdown，已建立 [[wiki/shared/sources/SAP项目集成测试业务流程与事务码]]；其 18 张流程图归档在 `raw/assets/`，不单独计入来源页。

## 终端 Claude 使用方式

如果用户是在终端 Claude 中查询知识库，不需要理解 `raw/`、`wiki/`、`sources/`、`entities/`、`concepts/` 的内部结构，可以直接用自然语言提问，例如：

- 如何创建财务客商？
- 如何创建 WBS？
- `F-53` 是什么？
- 月结怎么做？
- 采购发票怎么校验？
- GR/IR 重分类是什么意思？
- 销售订单怎么创建？
- 销售退货移动类型怎么确定？
- 物料销售视图怎么扩充？

Claude 应主动根据问题检索 `wiki/` 中已有页面，并用中文给出步骤化回答。终端查询说明见 [[wiki/shared/terminal-claude-startup]]。

## 典型工作流

1. 把原始资料直接放进 `raw/<module>/<type>/<YYYYMM>/`
2. 需要沉淀时，再把这份资料整理成 `wiki/<module>/sources/` 的来源页
3. 再由来源页继续更新实体页、概念页、对比页和综合页
4. 每次整理后更新对应 raw 清单、模块首页、全局索引和日志

## 链接习惯

- 同模块页面优先直接链接。
- 跨模块内容优先写完整路径，避免重名。
- 模板和索引页面统一从 `wiki/index.md` 进入。
- 具体写法见 [[wiki/templates/linking]]。

## 最新补充

- 已整理 `F-02 特别总账录入` 相关来源页、概念页和综合操作手册。
- 已新增 SD 模块，并整理 `SAP S4HANA销售订单处理（从询价到合同）`。
- 已新增 ABAP 异常处理主题，并整理 `ABAP 异常处理基础与核心概念`。
- 已整理本轮新增 FICO / SD / MM 相关原始资料，补充 GR/IR 重分类、在建工程转固反向处理、成本中心流入工单核对、生产工单跨月 TECO、SD 销售退货、销售订单、ATP、物料销售视图、客户资质校验、SD 非常见配置点和费用类采购科目确定等主题。
