# Zotero → Obsidian：PDF 高亮自动转换

插件源码仓库：[Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout)

## 安装

在 Obsidian 仓库的以下目录放置插件：

```text
<Obsidian 仓库>/.obsidian/plugins/zotero-drop-callout/
```

目录内应包含 `main.js` 和 `manifest.json`。随后在 Obsidian「设置 → 第三方插件」中启用插件。

## 配置步骤

1. 在 Zotero 10 中备份并设置 [原生高亮模板](../zotero/templates/highlight.html)。
2. 在 Obsidian 中启用 Zotero Drop Callout。
3. 打开一篇可编辑的 Markdown 笔记。
4. 从 Zotero PDF 阅读器拖入一条高亮。
5. 检查 Callout 标题、正文、单个 Open PDF 链接和引用是否正确。

## 已验证效果

插件会识别原文中的 `([pdf](zotero://open-pdf/...))`，将链接移到底部并命名为 `Open PDF`，同时清理模板可能生成的重复 Open PDF 文本。页码由 URL 中的 `page` 参数提取，保留 `annotation` 标识符。

## 常见问题

- **没有自动转换**：确认插件已启用，拖拽发生在可编辑笔记内，且内容包含 `zotero://open-pdf/` 链接。
- **出现两个 Open PDF**：检查是否仍在使用旧版插件。
- **作者、年份格式不同**：由 Zotero 引用样式与语言环境控制。
- **点击后不能定位 PDF**：检查系统是否已将 `zotero://` 协议关联到 Zotero。
