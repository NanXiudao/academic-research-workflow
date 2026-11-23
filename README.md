# 学术研究工作流配置

本仓库统一保存 **Zotero 10 + Obsidian + ZotLit 2.2 + Zotero Style** 的文献管理、论文笔记和 PDF 批注配置，方便复现、备份和迁移。

目前已保存实际使用的 **ZotLit 论文笔记模板与标注模板原文**，以及 Zotero 原生 PDF 高亮模板、Zotero Style 界面调整方法。

## 项目目录

| 路径 | 内容 |
|---|---|
| [zotlit/templates/paper-note.md](zotlit/templates/paper-note.md) | ZotLit 论文笔记模板，含元数据、摘要、研究问题、方法、实验与动态批注 |
| [zotlit/templates/annotation.md](zotlit/templates/annotation.md) | ZotLit 标注拖拽模板，含页码、图片、评论与 PDF 定位链接 |
| [zotlit/README.md](zotlit/README.md) | ZotLit 模板安装与字段说明 |
| [zotero/templates/highlight.html](zotero/templates/highlight.html) | Zotero PDF 阅读器原生高亮模板 |
| [zotero/userChrome.css](zotero/userChrome.css) | 隐藏 Zotero Style Graph View 按钮 |
| [zotero/zotero-style.md](zotero/zotero-style.md) | Zotero Style 配置与注意事项 |
| [obsidian/README.md](obsidian/README.md) | Obsidian Callout 显示效果 |
| [integrations/zotero-drop-callout.md](integrations/zotero-drop-callout.md) | Zotero 原生高亮拖入 Obsidian 的自动转换方案 |
| [docs/backup-and-migration.md](docs/backup-and-migration.md) | 备份和环境迁移清单 |

## 使用流程

1. 在 Zotero 中通过 DOI 获取论文元数据，阅读 PDF 并标注。
2. 在 Obsidian 中使用 ZotLit 导入论文笔记。笔记模板会输出论文标题、年份、标签、附件链接、摘要，以及用于动态展示 PDF 批注的 `zotquery` 代码块。
3. 通过 ZotLit 拖入标注时，使用 [标注模板](zotlit/templates/annotation.md) 生成包含页码和引用的 Callout。
4. 直接从 Zotero PDF 阅读器拖入高亮时，使用独立插件 [Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout) 自动调整 Callout 和 PDF 定位链接。

## 示例

```markdown
> [!quote] PDF Highlight · Page 3
>
> In RBO, we test the optimization performance...
>
> [📄 Open PDF](zotero://open-pdf/library/items/HGACVREL?page=3&annotation=L5RV6EX5) · (Tom 等, 2025, p. 3)
```

以上 PDF 标识符为示例。

## 配置状态

- **已验证**：ZotLit 论文笔记与标注模板来自实际使用的原文；Zotero 原生高亮与 Obsidian 自动转换已在本地流程中验证。
- **待补充**：Zotero Style 自定义标签列的完整表达式，以及 Catppuccin 主题的精确设置。
- **可选**：隐藏 Zotero Style 的 Graph View 按钮。

## 备份建议

修改 ZotLit Template Workbench、Zotero 高级设置或 Obsidian 插件前，先备份当前可用配置。不要将个人文献数据库、未公开笔记、同步凭据或 API Token 提交到公开仓库。

## 关联仓库

[Zotero Drop Callout](https://github.com/NanXiudao/zotero-drop-callout)：独立维护 Obsidian 插件源码、测试和版本。本仓库集中维护工作流配置，不重复保存插件源码。

## 许可证

本仓库原创文档与配置示例采用 MIT License。第三方插件遵循各自许可证。
