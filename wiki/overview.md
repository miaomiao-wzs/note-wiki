---
module: shared
kind: overview
updated: 2026-07-08
source_count: 34
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

- 当前 `raw/` 下有效原始资料共 34 个，已完成本轮整理。
- 有效资料目前集中在 `raw/fico/`，详见 [[wiki/fico/sources/raw资料清单]]。
- 全局整理状态见 [[wiki/shared/raw资料总清单]]。
- `raw/abap/`、`raw/mm/`、`raw/pp/`、`raw/qm/` 当前只有占位文件，暂无有效原始资料。
- `raw/assets/` 是 raw Markdown 图片附件目录，不单独整理成来源页。

## 终端 Claude 使用方式

如果用户是在终端 Claude 中查询知识库，不需要理解 `raw/`、`wiki/`、`sources/`、`entities/`、`concepts/` 的内部结构，可以直接用自然语言提问，例如：

- 如何创建财务客商？
- 如何创建 WBS？
- `F-53` 是什么？
- 月结怎么做？
- 采购发票怎么校验？
- GR/IR 重分类是什么意思？

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
