---
module: shared
kind: source
updated: 2026-07-27
source_count: 60
tags: []
---

# raw 资料总清单

本页记录整个 `raw/` 目录的有效原始资料整理状态，用于判断当前是否还有未整理资料。

## 统计口径

计入有效原始资料：
- Markdown：`.md`
- Word：`.docx`
- PDF：`.pdf`
- Excel：`.xlsx`

不计入有效原始资料：
- `.gitkeep`：目录占位文件
- `.DS_Store`：macOS 系统文件
- `~$` 开头文件：Office 临时锁文件
- `raw/assets/` 下图片：raw Markdown 附件资源，不单独整理成来源页
- `raw/Clippings/`：剪藏暂存目录；本轮已将其中 Markdown 资料全部迁移到对应模块目录，不重复计入合计

## 总体状态

| 模块 / 目录 | 有效原始资料 | 当前整理状态 | 对应清单 |
| --- | ---: | --- | --- |
| `raw/fico/` | 45（按主题去重口径为 44） | 已完成本轮整理；其中 1 份 FS15/FS16 Markdown 资料近重复，暂保留未重复整理 | [[wiki/fico/sources/raw资料清单]] |
| `raw/abap/` | 0 | 当前物理目录无有效原始文件；已有 ABAP 来源页和截图，原始文件缺失待确认 | [[wiki/abap/sources/raw资料清单]] |
| `raw/sd/` | 17 | 已完成本轮整理 | [[wiki/sd/sources/raw资料清单]] |
| `raw/mm/` | 0 | 暂无独立 raw 原始资料；有 1 份跨模块 PDF 来源页 | [[wiki/mm/sources/raw资料清单]] |
| `raw/pp/` | 0 | 暂无有效原始资料 | 暂无 |
| `raw/qm/` | 0 | 暂无有效原始资料 | 暂无 |
| `raw/assets/` | 0 | 附件目录，不作为来源页整理 | 暂无 |
| `raw/Clippings/` | 0 | 暂存目录已清理，Markdown 资料全部迁移到对应模块目录 | 暂无 |
| 合计 | 61（按主题去重）；64 个物理模块文件 | 当前模块化 raw 有效原始资料已完成本轮整理；ABAP 原始文件缺失和 FICO 重复资料均已标注 | 见各模块清单 |

说明：`raw/Clippings/` 当前无有效资料文件；按知识库口径不计入合计。

## FICO

`raw/fico/` 当前物理有效原始资料共 45 个，按主题去重口径为 44 个，已整理到 `wiki/fico/`：

- Markdown：17 个物理文件，其中 1 份 FS15/FS16 资料近重复；按主题去重为 16 个
- Word：19 个
- PDF：7 个
- Excel：1 个

详见：[[wiki/fico/sources/raw资料清单]]

## ABAP

`raw/abap/` 当前物理目录无有效原始资料；已有 ABAP 来源页和截图，但对应原始 Markdown 文件缺失，是否恢复需单独确认。

## SD

`raw/sd/` 当前有效原始资料共 17 个，已整理到 `wiki/sd/` 或按内容归属整理到对应模块：

- Markdown：14 个
- PDF：3 个

其中 `SAP FICO物料价格控制_sap s+3 v+2.pdf` 内容偏 FICO/MM，来源页为 [[wiki/fico/sources/SAP FICO物料价格控制]]；`SAP-MM费用类采购通过物料组确定科目_sap费用化采购-CSDN博客.pdf` 内容偏 MM/FICO，来源页为 [[wiki/mm/sources/SAP-MM费用类采购通过物料组确定科目]]。

详见：[[wiki/sd/sources/raw资料清单]]

## MM

`raw/mm/` 当前只有占位目录，暂无独立有效原始资料。

但本轮从 `raw/sd/article/202607/` 中识别出 1 个内容归属 MM/FICO 的 PDF，并已建立 MM 来源页：[[wiki/mm/sources/SAP-MM费用类采购通过物料组确定科目]]。

## PP

`raw/pp/` 当前只有占位目录，暂无有效原始资料。

## QM

`raw/qm/` 当前只有占位目录，暂无有效原始资料。

## 附件目录

`raw/assets/` 当前存放 raw Markdown 实际引用过的图片附件，包含早期 raw Markdown 图片、项目结转截图、剪藏资料图片，以及本轮新增 SD/FICO Markdown 图片。

这些图片是原始资料附件，不单独整理成知识来源页。

## 当前结论

截至 2026-07-27，`raw/` 下按主题去重的模块化有效原始资料已完成本轮整理；原 `raw/Clippings/` 中的 6 篇剪藏已分别迁移到 FICO/SD 模块目录，附件已本地化到 `raw/assets/`。
