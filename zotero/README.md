# Zotero 10 配置

## 已验证功能

- 通过 DOI 获取文献元数据；
- 使用 Zotero 内置 PDF 阅读器进行高亮；
- 将 PDF 高亮直接拖入 Obsidian；
- 使用原生高亮 HTML 模板生成兼容 Obsidian 的内容。

## 原生高亮模板

模板文件：[templates/highlight.html](templates/highlight.html)

在 Zotero 高级配置中找到：

```text
extensions.zotero.annotations.noteTemplates.highlight
```

先备份原值，再替换为模板文件内容。

`{{highlight quotes='false'}}` 用于输出不带外层引号的高亮文本；`{{citation}}` 输出 Zotero 当前引用格式。拖拽时可能额外产生 `([pdf](zotero://open-pdf/...))` 定位链接，由 Obsidian 端的 Zotero Drop Callout 插件负责调整位置。

## Zotero Style

参见 [zotero-style.md](zotero-style.md)。隐藏 Graph View 按钮的 CSS 已保存；自定义标签列的完整配置仍待补充。
