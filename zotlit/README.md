# ZotLit 2.2 模板配置

本目录保存实际使用的 ZotLit 模板，建议先备份当前 Template Workbench 内容，再复制对应模板。

## 1. 论文笔记模板

文件：[templates/paper-note.md](templates/paper-note.md)

将文件内容复制到 ZotLit Template Workbench 的**笔记**模板中。保留原始 Liquid 占位符和 `zotquery` 代码块。

模板包含：

- `{{ zt.title }}`：论文标题；
- `{{ zt.date | date: "%Y" }}`：年份；
- `zt.tags` 循环：以 HTML 徽标展示标签；
- `zt.backlink` 与 `zt.attachments`：Zotero 文献及附件链接；
- `zt.abstract`：摘要；
- Research Question、Methodology、Experiments：供人工撰写的研究记录；
- PDF Annotations：使用 `zotquery` 动态显示当前条目的批注。

动态批注查询保留原有条件 `item == this.item`，先按 `attachment.dateAdded` 升序，再按 `sortIndex` 升序。

## 2. 标注模板

文件：[templates/annotation.md](templates/annotation.md)

将文件内容复制到 ZotLit Template Workbench 的**标注**模板中。

该模板使用 `{% bq %}` 包裹 Obsidian Callout，包含：

- `zt.pageLabel`：存在页码时在标题显示 `PDF Highlight · Page N`；
- `zt.imgLink | embed`：嵌入图片标注；
- `zt.text`：标注原文；
- `zt.comment`：有评论时显示 `💭 Note`；
- `zt.backlink`：可点击的 `Open PDF`；
- `zt.citation`：有引用时追加到 PDF 链接后面。

## 3. 与 Zotero 原生拖拽的区别

**从 ZotLit 拖拽标注**：由 ZotLit 的标注模板控制输出。

**从 Zotero 内置 PDF 阅读器直接拖拽高亮**：由 Zotero 原生 HTML 模板控制初始输出，再由 [Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout) 在 Obsidian 中自动整理。

两条路径可以同时使用，互不需要替换。

## 4. 注意事项

这些模板来自当前工作流提供的原文。请在 ZotLit 2.2 中分别测试新建论文笔记、文字高亮、带评论标注和图片标注；不同版本的渲染结果可能存在差异。
