# Zotero Style 配置与隐藏 Graph View 按钮教程

本教程适用于 Zotero 10 的桌面版，目的是隐藏 Zotero Style 在工具栏显示的 Graph View 按钮，保留 Zotero Style 插件本身的其他功能。

## 一、找到 Zotero 的配置文件夹

**需要修改的是 Zotero 的 Profile（用户配置）目录，不是存放 `zotero.sqlite` 和 PDF 附件的 Data（数据）目录。**

### Windows 10 / 11

1. 按 `Win + R` 打开「运行」。
2. 粘贴以下路径并按回车：

   ```text
   %APPDATA%\Zotero\Zotero\Profiles
   ```

3. 打开里面实际正在使用的配置目录，名称通常类似 `xxxxxxxx.default` 或 `xxxxxxxx.default-release`。
4. 如果有多个配置目录，先确认当前 Zotero 使用的配置文件；不要随意修改其他配置文件。

完整路径示例：

```text
C:\Users\你的用户名\AppData\Roaming\Zotero\Zotero\Profiles\xxxxxxxx.default\
```

`AppData` 默认可能隐藏，使用 `%APPDATA%` 可以直接打开。

### macOS

1. 在 Finder 中按 `Command + Shift + G`。
2. 输入：

   ```text
   ~/Library/Application Support/Zotero/Profiles/
   ```

3. 打开当前使用的随机名称配置目录。

### Linux

一般位于：

```text
~/.zotero/zotero/
```

找到当前使用的配置目录。若使用 Flatpak、Snap 或自定义配置，实际路径可能不同。

Zotero 官方配置目录说明：https://www.zotero.org/support/kb/profile_directory

## 二、建立 chrome 文件夹和 userChrome.css

在**当前配置目录内部**创建一个名为 `chrome` 的文件夹。若已经存在，直接打开，不要删除其中原有文件。

最终目录结构应当是：

```text
Profiles/
└── xxxxxxxx.default/
    └── chrome/
        └── userChrome.css
```

### Windows：用记事本创建 CSS 文件

1. 打开刚建立的 `chrome` 文件夹。
2. 在文件资源管理器中选择「查看 → 显示 → 文件扩展名」（Windows 11）；Windows 10 可在「查看」中勾选「文件扩展名」。
3. 右键空白处，选择「新建 → 文本文档」，将文件名改为 **`userChrome.css`**。
4. 如果 Windows 提示更改扩展名，选择「是」。
5. 右键该文件，选择「打开方式 → 记事本」。
6. 粘贴下面的 CSS，按 `Ctrl + S` 保存。

**重要：** 文件必须叫 `userChrome.css`，不能是 `userChrome.css.txt`。如果已经有 `userChrome.css`，请在文件末尾追加 CSS，不要覆盖已有主题代码。

### macOS / Linux

在 `chrome` 目录下使用文本编辑器创建纯文本文件 `userChrome.css`。macOS 的「文本编辑」应先切换为纯文本模式（「格式 → 制作纯文本」），避免保存成 RTF。

## 三、写入隐藏按钮的 CSS

将下面内容粘贴到 `userChrome.css`：

```css
/* 隐藏 Zotero Style 的 Graph View 工具栏按钮 */
#zoterostyle {
  display: none !important;
}
```

也可以直接复制仓库中的 [userChrome.css](userChrome.css)。

这条规则只隐藏匹配 `#zoterostyle` 的界面元素，不卸载插件，也不删除 Zotero 数据。选择器来自当前已验证的界面；未来插件更新后如元素 ID 改变，需要重新检查选择器。

## 四、启用 Zotero 自定义 CSS

1. 打开 Zotero。
2. Windows / Linux：选择「编辑 → 设置」；macOS：选择「Zotero → 设置」。
3. 打开「高级（Advanced）」。
4. 点击「配置编辑器（Config Editor）」，按提示确认。
5. 搜索：

   ```text
   toolkit.legacyUserProfileCustomizations.stylesheets
   ```

6. 将该选项设置为布尔值 **`true`**（通常双击切换）。
7. **完全退出 Zotero，再重新启动**。

这个开关用于允许从配置目录加载 `userChrome.css`。相关讨论：https://forums.zotero.org/discussion/105221/zotero-7-beta-custom-themes-may-require-advanced-preference-config-editor-flag

## 五、验证

重启 Zotero 后，检查工具栏：Zotero Style 的 Graph View 按钮应当消失，Zotero Style 其他功能应当仍可使用。

如果没有生效，依次检查：

1. `chrome` 是否位于 **`Profiles/随机名称配置目录/` 内部**，而不是直接位于 `Profiles/` 或 `~/Zotero/`。
2. 文件名是否准确为 `userChrome.css`，尤其排除 `.txt` 扩展名。
3. 配置编辑器中的选项是否确实为 `true`。
4. 是否完整退出并重启 Zotero。
5. 是否修改了当前正在使用的 Profile；若有多个 Profile，请确认对应关系。
6. 如果安装了其他主题 CSS，检查是否有冲突。

## 六、恢复按钮

打开同一个 `userChrome.css`，删除或注释以下规则：

```css
#zoterostyle {
  display: none !important;
}
```

保存并重启 Zotero，即可撤销本项隐藏设置。如果文件还包含其他自定义样式，**不要删除整个文件**。

## 其他 Zotero Style 配置

此前使用过自定义标签列，但完整配置表达式尚未保存。Catppuccin 主题的具体参数也尚未保存，待取得实际配置后再补充。

## 参考资料

- [Zotero 官方：Profile directory location](https://www.zotero.org/support/kb/profile_directory)
- [Zotero 官方：Data directory（用于区分 Profile 和 Data）](https://www.zotero.org/support/zotero_data)
- [Zotero 论坛：启用 userChrome.css](https://forums.zotero.org/discussion/105221/zotero-7-beta-custom-themes-may-require-advanced-preference-config-editor-flag)
