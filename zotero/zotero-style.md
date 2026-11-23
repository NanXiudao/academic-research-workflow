# Zotero Style 配置

## 自定义标签列

此前已在 Zotero Style 中配置自定义标签列，但完整表达式尚未保存。后续可从当前 Zotero 配置中导出，再补充到仓库，避免凭记忆重建。

## 隐藏 Graph View 按钮（已验证）

Zotero Style 的对应工具栏元素选择器为 `#zoterostyle`。

1. 打开 Zotero 用户配置目录。
2. 创建或编辑 `chrome/userChrome.css`。
3. 复制 [userChrome.css](userChrome.css) 中的样式。
4. 将高级首选项 `toolkit.legacyUserProfileCustomizations.stylesheets` 设为 `true`。
5. 重启 Zotero。

这只隐藏对应界面元素，不卸载 Zotero Style。

## Catppuccin 主题

此前探索过 Catppuccin 风格，但没有保存完整主题参数，因此暂不提供未经验证的预设。
