---
module: shared
kind: template
updated: 2026-07-06
source_count: 0
tags: [template]
---

# 模块首页模板

这个模板用于 `wiki/<module>/overview.md`。

## 适用场景

- FICO 模块首页
- ABAP 模块首页
- MM / PP / QM 等后续模块首页

## 模板内容

```markdown
---
module: fico
kind: overview
updated: 2026-07-06
source_count: 0
tags: []
---

# FICO 模块总览

这个模块用于沉淀 FICO 相关知识。

## 结构

- `entities/`
- `concepts/`
- `comparisons/`
- `sources/`
- `synthesis/`

## 常用入口

- [[wiki/fico/entities/]]：实体页
- [[wiki/fico/concepts/]]：概念页
- [[wiki/fico/comparisons/]]：对比页
- [[wiki/fico/sources/]]：来源页
- [[wiki/fico/synthesis/]]：综合页
```

## 使用原则

- 模块首页只负责说明这个模块的范围和入口。
- 具体知识放到 `entities`、`concepts`、`comparisons`、`sources`、`synthesis` 中。
- 以后新增模块时，直接复制这份结构，替换模块码和标题即可。
