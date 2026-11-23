# Obsidian 配置

## PDF 高亮 Callout

Zotero PDF 高亮可以在 Obsidian 中自动呈现为：

```markdown
> [!quote] PDF Highlight · Page 3
>
> In RBO, we test the optimization performance...
>
> [📄 Open PDF](zotero://open-pdf/library/items/HGACVREL?page=3&annotation=L5RV6EX5) · (Tom 等, 2025, p. 3)
```

其中页码来自 Zotero PDF 深度链接的 `page` 参数，`annotation` 参数用于定位原始批注。

## 两种拖拽方式

- **ZotLit 标注拖拽**：使用本仓库的 [ZotLit 标注模板](../zotlit/templates/annotation.md)。
- **Zotero PDF 阅读器原生拖拽**：使用 [Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout) 自动调整格式。

## 注意

安装或更新插件前，先备份 Obsidian 仓库及 `.obsidian` 配置目录。点击 `zotero://` 链接需要系统能够正确调用 Zotero。
