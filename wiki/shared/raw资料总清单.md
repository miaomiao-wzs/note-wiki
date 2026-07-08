---
module: shared
kind: source
updated: 2026-07-08
source_count: 34
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

## 总体状态

| 模块 / 目录 | 有效原始资料 | 当前整理状态 | 对应清单 |
| --- | ---: | --- | --- |
| `raw/fico/` | 34 | 已完成本轮整理 | [[wiki/fico/sources/raw资料清单]] |
| `raw/abap/` | 0 | 暂无有效原始资料 | 暂无 |
| `raw/mm/` | 0 | 暂无有效原始资料 | 暂无 |
| `raw/pp/` | 0 | 暂无有效原始资料 | 暂无 |
| `raw/qm/` | 0 | 暂无有效原始资料 | 暂无 |
| `raw/assets/` | 0 | 附件目录，不作为来源页整理 | 暂无 |
| 合计 | 34 | 当前 raw 有效原始资料已完成本轮整理 | 见各模块清单 |

## FICO

`raw/fico/` 当前有效原始资料共 34 个，已全部整理到 `wiki/fico/`：

- Markdown：4 个
- Word：22 个
- PDF：7 个
- Excel：1 个

详见：[[wiki/fico/sources/raw资料清单]]

## ABAP

`raw/abap/` 当前只有以下占位目录：

- `raw/abap/article/202607/.gitkeep`
- `raw/abap/pdf/202607/.gitkeep`
- `raw/abap/web/202607/.gitkeep`

暂无有效原始资料，不创建来源页。

## MM

`raw/mm/` 当前只有以下占位目录：

- `raw/mm/article/202607/.gitkeep`
- `raw/mm/pdf/202607/.gitkeep`
- `raw/mm/web/202607/.gitkeep`

暂无有效原始资料，不创建来源页。

## PP

`raw/pp/` 当前只有以下占位目录：

- `raw/pp/article/202607/.gitkeep`
- `raw/pp/pdf/202607/.gitkeep`
- `raw/pp/web/202607/.gitkeep`

暂无有效原始资料，不创建来源页。

## QM

`raw/qm/` 当前只有以下占位目录：

- `raw/qm/article/202607/.gitkeep`
- `raw/qm/pdf/202607/.gitkeep`
- `raw/qm/web/202607/.gitkeep`

暂无有效原始资料，不创建来源页。

## 附件目录

`raw/assets/` 当前存放 raw Markdown 实际引用过的图片附件，共 6 张：

- `Pasted image 20260616140057.png`
- `Pasted image 20260616140126.png`
- `Pasted image 20260616140526.png`
- `Pasted image 20260616140537.png`
- `Pasted image 20260616140913.png`
- `Pasted image 20260617103323.png`

这些图片是原始资料附件，不单独整理成知识来源页。

## 当前结论

截至 2026-07-08，`raw/` 下当前有效原始资料已全部完成本轮整理。后续如果新增资料，继续按 `raw/<module>/<type>/<YYYYMM>/` 归档，再整理到对应 `wiki/<module>/sources/`。
