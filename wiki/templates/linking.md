---
module: shared
kind: template
updated: 2026-07-06
source_count: 0
tags: [template]
---

# 链接规范

这个页面说明 `wiki/` 中页面之间怎么互相链接。

## 基本原则

- 优先使用明确的页面链接，不要只写模糊的主题名。
- 页面名尽量中文化，但路径仍保持模块码和目录结构。
- 重要概念尽量双向互链：实体页连概念页，概念页连来源页，综合页连相关页面。

## 链接写法

### 1. 同模块内页面
优先直接链接到对应页面：
- [[wiki/fico/overview]]
- [[wiki/fico/entities/凭证号]]
- [[wiki/fico/concepts/应收账款清账]]

### 2. 跨模块页面
如果内容会跨模块理解，直接写完整路径：
- [[wiki/abap/concepts/内表循环]]
- [[wiki/mm/concepts/采购订单]]

### 3. 模板页和总览页
模板页和总览页可以直接从 `wiki/index.md` 进入：
- [[wiki/templates/source]]
- [[wiki/templates/entity]]
- [[wiki/templates/concept]]
- [[wiki/templates/comparison]]
- [[wiki/templates/synthesis]]
- [[wiki/templates/module-overview]]

## 命名建议

- 页面标题优先中文。
- 必要时在标题里补模块名，避免跨模块同名。
- 如果一个主题在不同模块都出现，优先把概念写在各模块下，再通过链接串起来。

## 什么时候用完整路径

- 页面名可能重名时。
- 跨模块引用时。
- 模板页、总览页、索引页。
