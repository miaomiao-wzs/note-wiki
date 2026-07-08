# 知识库规范

## 作用

这个仓库是一个面向 SAP / ABAP / FICO 等主题的 Obsidian 知识库。维护时遵循“原始资料层”和“知识沉淀层”分离的原则。

## 目录约定

### raw/
- `raw/` 存放原始资料，只做归档与读取，不在这里整理总结。
- 统一结构：`raw/<module>/<type>/<YYYYMM>/`
- `module` 使用小写模块名，例如：`fico`、`abap`，后续可扩展 `mm`、`pp`、`qm`。
- `type` 使用来源类型，例如：`article`、`pdf`、`web`、`note`。
- `YYYYMM` 使用年月桶，例如：`202607`。
- 文件命名建议采用“主题清晰、长度适中、便于搜索”的中文名称，例如：`采购发票处理流程.pdf`、`ABAP 内表循环优化.md`。
- 如果同一月份同一主题有多份资料，建议在文件名前补充区分信息，例如：`01-采购发票处理流程.pdf`、`02-采购发票示例.md`。
- raw 里的文件优先保留原始形态，不为了统一格式去重写内容。
- `raw/assets/` 专门存放 raw 中 Markdown 原始资料引用的图片、截图等附件。
- 图片在 Markdown 中优先使用 Obsidian wiki 嵌入格式，例如：`![[raw/assets/示例图片.png]]`。

### wiki/
- `wiki/` 存放 LLM 维护的知识页面。
- 每个模块采用同构结构：`wiki/<module>/{entities,concepts,comparisons,sources,synthesis}/`
- 当前初始化模块包括：`fico`、`abap`。
- 预留同构扩展模块：`mm`、`pp`、`qm`。
- 全局入口文件固定为：`wiki/index.md`、`wiki/log.md`、`wiki/overview.md`。
- `wiki/shared/` 用于跨模块通用内容。
- `wiki/templates/source.md`：单篇来源页模板，同时包含来源页命名规则。
- `wiki/templates/module-overview.md`：模块首页模板。
- `wiki/templates/entity.md`：实体页模板。
- `wiki/templates/concept.md`：概念页模板。
- `wiki/templates/comparison.md`：对比页模板。
- `wiki/templates/synthesis.md`：综合页模板。
- `wiki/templates/linking.md`：页面链接规范。
- `wiki/templates/log-entry.md`：日志条目模板。

## 维护原则

- 原始资料尽量不改动，只新增或归档。
- wiki 页面负责总结、串联、纠错、对比和综合。
- 新增知识时，优先更新相关的 `sources`、`entities`、`concepts`，必要时再更新 `comparisons` 和 `synthesis`。
- 发现新资料与旧结论冲突时，不直接覆盖旧内容；先记录差异，再给出综合判断。
- 页面建议使用最小 frontmatter：`module`、`kind`、`updated`、`source_count`、`tags`。

## 运行约定

- `wiki/index.md`：目录入口，帮助快速定位页面。
- `wiki/log.md`：记录每次整理、新增和修订。
- `wiki/overview.md`：说明知识库的使用方式与整体结构。
- `wiki/templates/source.md`：单篇来源页模板，同时包含来源页命名规则。
- `wiki/templates/module-overview.md`：模块首页模板。
- `wiki/templates/entity.md`：实体页模板。
- `wiki/templates/concept.md`：概念页模板。
- `wiki/templates/comparison.md`：对比页模板。
- `wiki/templates/synthesis.md`：综合页模板。
- `wiki/templates/linking.md`：页面链接规范。
- `wiki/templates/log-entry.md`：日志条目模板。
- 单篇来源页用于把一份原始资料整理成可持续维护的 wiki 页面。
- 模块首页用于说明某个模块的范围、结构和常用入口。
- 实体页用于描述一个具体对象是什么、做什么、和谁相关。
- 概念页用于描述一个原理、规则或流程怎么运作。
- 对比页用于比较多个对象或方案。
- 综合页用于把多篇资料合成一个可用结论。
- 链接优先清晰明确；跨模块、重名或模板页面优先使用完整路径。
- `wiki/log.md` 采用追加式写法，单条记录建议使用 `wiki/templates/log-entry.md` 的格式。

## 终端 Claude 使用约定

目标：在终端中通过 `cd "/Users/waterboy/myself_study/note/note_wiki" && claude` 打开本项目时，也尽量获得接近 Obsidian / Claudian 窗口的知识库使用体验。

### 启动后的默认上下文

当 Claude 在本仓库根目录启动时，应把当前目录视为 Obsidian vault 根目录，并遵守以下默认上下文：

- 当前项目是 Obsidian 知识库，不是普通代码仓库。
- 回答 SAP / FICO / ABAP / MM / PP / QM 相关问题时，优先使用 `wiki/` 中已有知识页面。
- 不要只凭模型记忆回答业务操作问题；应先检索或阅读相关 wiki 页面。
- 回答时优先使用 Obsidian wiki-link 引用相关页面，例如 `[[wiki/fico/sources/客商创建]]`。
- 如果 wiki 中没有对应内容，应明确说明“当前 wiki 尚未沉淀该主题”，再给出通用判断或建议。

### 必读入口

每次终端会话开始后，如用户提出 SAP、FICO、ABAP、MM、PP、QM 或知识库相关问题，应优先读取这些入口来建立上下文：

- `CLAUDE.md`：项目维护规则
- `wiki/index.md`：全局索引
- `wiki/overview.md`：知识库总览
- `wiki/shared/raw资料总清单.md`：raw 资料整体整理状态

如果问题属于某个具体模块，还应继续读取对应模块首页：

- FICO：`wiki/fico/overview.md`
- ABAP：`wiki/abap/overview.md`
- MM：`wiki/mm/overview.md`
- PP：`wiki/pp/overview.md`
- QM：`wiki/qm/overview.md`

### 回答业务问题的检索顺序

当用户问“如何操作”“某个事务码是什么”“某个 SAP 概念如何理解”时，按以下顺序检索：

1. 先查 `wiki/index.md` 和对应模块 `overview.md`。
2. 再查对应模块的 `sources/` 来源页。
3. 再查对应模块的 `entities/` 实体页。
4. 再查对应模块的 `concepts/` 概念页。
5. 必要时查 `comparisons/` 和 `synthesis/`。
6. 如果仍找不到，再基于通用 SAP / ABAP / FICO 知识回答，并说明 wiki 暂无沉淀。

### FICO 问题优先入口

当前 FICO 资料最完整。回答 FICO 问题时，优先查：

- `wiki/fico/overview.md`
- `wiki/fico/sources/raw资料清单.md`
- `wiki/fico/sources/`
- `wiki/fico/entities/`
- `wiki/fico/concepts/`

常见问题示例：

- 问“如何创建财务客商”：优先查 `[[wiki/fico/sources/客商创建]]`、`[[wiki/fico/sources/财务客商创建]]`、`[[wiki/fico/concepts/客商主数据]]`。
- 问“如何创建 WBS”：优先查 `[[wiki/fico/sources/WBS 创建操作手册]]`、`[[wiki/fico/concepts/WBS 元素]]`、`[[wiki/fico/concepts/项目成本对象]]`。
- 问事务码用途：优先查 `wiki/fico/entities/<事务码>.md`，再查 `[[wiki/fico/sources/事务代码清单]]`。

### 普通用户查询模式

当终端 Claude 已经在本项目中启动，且使用者可能不了解目录结构或 wiki 页面路径时，Claude 应主动承担“知识库检索入口”的角色。

用户可能会直接问：

- `如何创建财务客商？`
- `WBS 怎么建？`
- `F-53 是什么？`
- `月结怎么做？`
- `采购发票怎么校验？`
- `GR/IR 重分类是什么意思？`
- `帮我查一下某个 SAP 操作`

处理规则：

1. 不要求用户先提供文件路径。
2. 先判断问题所属模块，当前优先判断是否属于 FICO。
3. 主动从 `wiki/index.md`、模块首页、`sources/`、`entities/`、`concepts/` 中检索相关页面。
4. 如果问题是“怎么操作”，优先查 `sources/` 操作手册来源页。
5. 如果问题是“事务码是什么”，优先查 `entities/` 下对应事务码页面，再查 `wiki/fico/sources/事务代码清单.md`。
6. 如果问题是“概念是什么意思”，优先查 `concepts/` 下对应概念页。
7. 回答时用普通用户能理解的步骤化中文说明，不要只给路径或内部术语。
8. 回答末尾可以列出“参考页面”，使用 Obsidian wiki-link。

### 面向非维护者的回答风格

当使用者是在查询知识库，而不是要求维护知识库时：

- 直接回答问题，不要先讲知识库结构。
- 结论先行，再给操作步骤。
- SAP 操作用“事务码 + 业务含义 + 操作步骤 + 注意点”的结构回答。
- 遇到资料中未确认或有冲突的信息，应明确说明“知识库中该点尚未确认”或“资料存在不一致”。
- 不主动创建、修改 wiki 页面，除非用户明确要求“整理/新增/更新知识库”。
- 不要求用户理解 `raw/`、`wiki/`、`sources/`、`entities/`、`concepts/` 的内部结构。

### 推荐初始化说明页

如果终端会话需要更完整地模拟 Claudian / Obsidian 使用体验，可优先读取：

- `wiki/shared/terminal-claude-startup.md`

该页面记录了面向普通用户的查询方式、Claude 的检索策略和回答格式。

### 重要限制

终端 Claude 不应在启动时一次性读取整个 `wiki/` 目录。这样会浪费上下文，并可能导致关键信息被稀释。正确方式是：

- 启动时先读入口页。
- 根据用户问题按模块和关键词逐步读取相关页面。
- 回答时引用实际读到的 wiki 页面。

## 保持一致

- 所有目录名使用小写。
- 新增模块时，必须沿用同一套目录结构。
- 新增 raw 内容时，优先按模块、类型、年月放入对应目录。
- 不删除 `欢迎.md`，它暂时保留为默认欢迎页。
