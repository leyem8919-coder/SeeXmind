# SeeXmind

[English](README.md) · [下载插件](https://github.com/leyem8919-coder/SeeXmind/releases/latest) · [反馈问题](https://github.com/leyem8919-coder/SeeXmind/issues)

在 Obsidian 中预览本地 `.xmind` 文件、把导图嵌入笔记，需要编辑时用本机 Xmind 打开原文件。

SeeXmind 是独立的非官方插件，与 Xmind、Obsidian 无隶属、赞助或官方背书关系。插件不包含 Xmind，也不解锁其付费功能。

## 功能

- 文件目录显示 `.xmind`：单击预览，双击交给 Xmind 打开。
- 使用 `![[导图.xmind]]` 在 Markdown 中嵌入可操作预览。
- 在预览上方选择同一文件的不同 sheet（画布）。
- 放大、缩小、适应窗口、刷新四个图标按钮在右边竖排悬浮，悬停显示文字提示。
- “用 Xmind 打开”按钮在右下角悬浮。
- 按钮闲置不透明度可设为 **0%–100%**，悬停或键盘聚焦时恢复完全显示。
- 界面支持英文、简体中文，尽量跟随 Obsidian 当前语言；其他语言回退到英文。
- 可自定义 Mac `.app` 和 Windows `.exe` 路径。

## 安装

需要桌面版 Obsidian 1.5.0 或以上，支持 macOS 和 Windows，不支持手机和平板。建议另外安装 [Xmind](https://xmind.app/) 以便编辑。预览受支持的文件不需要 Xmind 账号，也不需要让 Xmind 一直运行。

如果社区插件目录已能搜索到 **SeeXmind**，可以直接安装并启用；尚未显示时可以手动安装：

1. 从同一个[公开版本](https://github.com/leyem8919-coder/SeeXmind/releases/latest)下载 `main.js`、`manifest.json`、`styles.css`。
2. 把三个文件放进 `<你的库>/.obsidian/plugins/seexmind/`。
3. 重新加载 Obsidian，在第三方插件中启用 SeeXmind。

用户无需访问 private 源码库。更新时只替换这三个安装文件，保留 `data.json` 可以保留原有设置。请停用其他接管 `.xmind` 文件类型的插件。

## 使用

先将 `.xmind` 文件放进 Obsidian 库。单击文件打开预览；双击文件目录中的条目、点击“用 Xmind 打开”或使用右键菜单，即可打开原文件编辑。在 Xmind 保存后返回 Obsidian，插件会在库报告文件变更时刷新，也可点击刷新图标重新读取。

### 嵌入 Markdown 笔记

```md
![[导图.xmind]]
```

也可以写库内路径，例如 `![[Maps/学习计划.xmind]]`。请在阅读模式查看，或在实时预览模式把光标移出嵌入内容。每个预览的画布选择、缩放、平移互不影响。拖动右下角的尺寸手柄可以调整预览高度。

原生嵌入接口不可用时，可使用兼容代码块：

````md
```xmind
Maps/学习计划.xmind
```
````

实时预览使用经过可用性检查的 Obsidian 原生嵌入接口；阅读模式和代码块提供回退方式。未来 Obsidian 调整接口时，可能需要更新插件。

### 原始图片与多画布预览的区别

- **内置图片（原始布局）**：显示 Xmind 保存在文件内部的 PNG，保留该图片的外观。它可能只包含一个画布；未重新保存时可能是旧内容，放大清晰度也受图片分辨率限制。
- **按名称选择的画布**：读取 `content.json` 或受支持的 `content.xml`，在本机重建结构预览。可以切换不同画布，但布局、字体、间距和高级元素可能与 Xmind 不一致。资源图片和部分高级功能尚不重建。

插件不会把同一张内置图片冒充为不同画布。需要精确外观时，请选择内置图片，或在 Xmind 打开原文件。不支持的格式、加密、损坏或过于复杂的文件可能无法预览；文件上限为 128 MB，同时限制解压大小和结构复杂度。

### 操作与设置

- 右侧工具栏依次为：放大、缩小、适应窗口、刷新。
- 在导图上滚动缩放、拖动平移；画布获得键盘焦点后可用 `+` / `-` 缩放，`0` 适应窗口。
- **悬浮按钮闲置不透明度**：修改后立即应用于打开的预览。设为 0% 后按钮仍在原位置，鼠标移入或键盘聚焦即可显示。
- **Mac 应用路径**：通常留空；也可填写 `/Applications/Xmind.app` 等完整 `.app` 路径。
- **Windows 程序路径**：留空使用 `.xmind` 默认打开方式；也可填写 `Xmind.exe` 的完整路径，不添加引号或命令参数。
- 修改 Obsidian 语言后，重新打开预览或重载插件，使现有界面文字更新。

## 隐私与范围

预览在本地内存中完成。插件不主动联网、不加载远程资源、不上传导图、不采集分析数据或遥测。通过 Obsidian API 读取选中的库内文件，把应用路径和不透明度保存在插件本地设置中。只有用户主动要求打开时，才将选中文件的本地路径交给已安装的 Xmind。

Xmind、Obsidian、GitHub，以及 iCloud、网络盘等同步或存储服务各自的网络行为不受本插件控制。Obsidian 插件不是受到严格权限隔离的安全沙箱。详见 [PRIVACY.md](PRIVACY.md)。

## 验证与限制

0.2.0 已在 macOS 的 Obsidian 1.13.7 中检查独立文件预览、浮动按钮、透明度、多画布切换，以及实时预览和阅读模式中的多个独立嵌入。自动化测试覆盖压缩包校验、画布解析、语言、设置及 Mac/Windows 启动参数。**Windows 实际桌面验证仍待完成。**

SeeXmind 提供查看和打开功能，不是思维导图编辑器。编辑、保存、导出、账号和付费能力由 Xmind 提供。

## 仓库与许可

public 库提供说明和安装文件；完整开发源码、构建配置和测试仍保留在 private 库，用于维护和授权源码审核。公开的 `main.js` 是可阅读的 JavaScript，私有开发库并不隐藏已分发的运行逻辑，也不改变许可证。

项目采用 [Apache-2.0](LICENSE)。部分结构解析及渲染代码改编自 [yuanzhixiang/obsidian-xmind](https://github.com/yuanzhixiang/obsidian-xmind)，已在 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) 保留署名和修改说明，不包含 Xmind 专有引擎。

软件按现状提供，具体保证与责任限制以许可证及适用法律为准。范围说明不排除法律不允许排除的责任，也不是不侵权或“零法律风险”的保证。
