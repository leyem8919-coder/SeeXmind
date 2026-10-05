# SeeXmind

## English

SeeXmind previews the PNG image embedded in a local `.xmind` file without re-rendering its layout. Single-click a file in Obsidian to preview it; double-click to open the original in the desktop Xmind application. Zoom, pan, fit to window, and refresh after saved-file changes are supported.

### Screenshots

These user-provided screenshots show 0.1.3. In 0.1.4, preview controls float vertically on the right, the Xmind button sits at the bottom-right, and settings include adjustable idle opacity.

Preview the image saved inside your Xmind file, with zoom, pan, fit, and refresh controls.

![SeeXmind preview inside Obsidian](docs/images/preview.png)

Set an optional custom Xmind application path on macOS or Windows.

![Custom Xmind application path settings](docs/images/settings.png)

### Installation

Installable files are distributed from the **public SeeXmind repository**. You do not need access to the private source repository, which is used for development and source/build verification.

1. Download `main.js`, `manifest.json`, and `styles.css` from [GitHub Releases](https://github.com/leyem8919-coder/SeeXmind/releases/tag/0.1.4).
2. Create `.obsidian/plugins/seexmind/` inside your vault and place those three files directly inside it.
3. Reload the community plugin list in Obsidian settings and enable **SeeXmind**.
4. We recommend installing [Xmind from its official website](https://xmind.com/) separately for editing. Previewing embedded images does not require Xmind. On Windows, associate `.xmind` files with Xmind or specify the executable path in SeeXmind settings.

### Usage

Place an `.xmind` file inside your vault. Single-click it in the file explorer to preview, and double-click to edit it in Xmind. Use the mouse wheel or toolbar to zoom, drag to pan, and choose Fit to view the whole preview. Save changes in Xmind before refreshing. A missing, encrypted, outdated, or low-resolution embedded preview cannot be reconstructed by this plugin. Multi-sheet files may provide only one preview image.

### Floating controls

The right-side icon buttons zoom in/out, fit the preview, and refresh it. Hover to see their labels. The **Open in Xmind** button floats at the bottom-right. In settings, adjust idle opacity from **0–100%** (default **35%**). Controls become fully visible when hovered or keyboard-focused; even 0% keeps their hover targets and Tab navigation available. Changes apply immediately to open previews.

### Privacy, permissions, and project status

SeeXmind itself makes no network requests and has no uploads, analytics, telemetry, or accounts. It reads selected vault files through Obsidian, stores application paths and display preferences locally, and launches an installed application only on a user action. Previewing uses Obsidian’s Vault API and an in-memory ZIP reader; the bundled preview code does not import Node filesystem APIs. Desktop app opening uses Node process APIs and does not execute shell command strings. Xmind, Obsidian, network drives, and synchronization services operate under their own policies. See [PRIVACY.md](PRIVACY.md) for details.

This independent project is not affiliated with, sponsored by, or endorsed by Xmind or Obsidian. It does not bundle their applications or bypass licenses, paid features, or encryption. Distributed files retain the existing [Apache-2.0 license](LICENSE) and [dependency notices](THIRD_PARTY_NOTICES.md); privately maintained source does not make the distributed JavaScript unreadable or proprietary. The plugin is desktop-only: macOS core behavior is tested; Windows GUI verification is pending. Community-directory availability depends on the current listing status; the public GitHub release supports manual installation.

---

**在 Obsidian 中预览，在 Xmind 中编辑。**

SeeXmind 是面向 macOS 和 Windows 桌面版 Obsidian 的独立第三方插件。单击 `.xmind` 查看内置预览，双击使用本机 Xmind 打开原文件。

> 建议同时从 [Xmind 官方网站](https://xmind.com/) 安装 Xmind。SeeXmind 不包含、不代装 Xmind，也不提供 Xmind 账号或付费功能授权。仅查看含内置图片的文件不需要安装 Xmind；双击打开和编辑需要另行安装。

## 功能

| 操作 | 效果 |
| --- | --- |
| 单击文件目录中的 `.xmind` | 在右侧内容区显示文件内置图片 |
| 双击 `.xmind` | 用本机 Xmind 打开原文件 |
| 滚轮或缩放按钮 | 放大、缩小预览 |
| 鼠标拖动 / 适应窗口 | 平移或显示完整图片 |
| Xmind 保存后 | 检测本地文件变化并刷新，也可手动刷新 |

每份文件读取自己的 `Thumbnails/thumbnail.png`，不重新计算节点布局、字体和连接线。Mac 和 Windows 使用相同的读取方式，不依赖 macOS Quick Look。

## 悬浮按钮

右侧竖排四个图标：放大、缩小、适应窗口、刷新；悬停显示文字提示。「用 Xmind 打开」在右下角。设置中的「悬浮按钮闲置不透明度」支持 **0–100%**，默认 **35%**，修改立即生效；鼠标移到控件区域或键盘聚焦时完全显示。0% 时控件隐藏，但原位置仍可悬停唤出，也可使用 Tab 键定位。

上方两张截图为 0.1.3，0.1.4 已采用上述浮动布局并增加透明度设置。

## 安装

当前版本 **0.1.4**。社区目录可用性以市场页面状态为准；也可从公开 GitHub Release 手动安装。支持 Obsidian 桌面版 1.5.0 或更新版本；macOS 已完成核心功能实测，Windows 实际桌面验证仍待完成。

**安装只需访问公开的 SeeXmind 仓库**。私有仓库用于开发与源码、构建校验，用户不需要从它下载，也不需要访问权限。

1. 从 [Releases](https://github.com/leyem8919-coder/SeeXmind/releases) 下载 `main.js`、`manifest.json`、`styles.css`（不是 Source code 压缩包）。
2. 在库内建立 `.obsidian/plugins/seexmind/` 文件夹，将这三个文件放进去。
3. 在 Obsidian「设置 → 第三方插件」刷新列表并启用 **SeeXmind**。
4. 将 `.xmind` 文件放进笔记库，在文件目录单击预览或双击打开。

每个笔记库独立安装。若另一插件已接管 `.xmind`，先停用其对应功能，再启用 SeeXmind。

**Mac：** 默认打开本机 Xmind，也可在设置中指定 `.app` 的完整路径。

**Windows：** 默认使用 `.xmind` 的系统文件关联，请先将 Xmind 设为默认打开应用；也可在 SeeXmind 设置中填写 `Xmind.exe` 的完整路径，不加引号或命令参数。

卸载时停用插件并删除 `.obsidian/plugins/seexmind` 即可，导图原文件不受影响。

## 隐私与本地处理

SeeXmind 本身：

- 不主动发起网络请求，不连接预览服务器或加载远程图片、字体、脚本。
- 不上传笔记、导图、文件路径或使用记录。
- 不收集用户身份、设备标识或行为数据；没有统计分析、遥测、广告或崩溃上报。
- 不要求注册 SeeXmind 账号，不需要 API 密钥，不安装或自动更新自身及依赖。
- 只为预览读取用户选中的导图，不写入或改动 `.xmind` 内容；应用路径和显示偏好保存在本地插件配置中。

上述描述限于 **SeeXmind 插件自身**。下载或更新插件需要 Obsidian、浏览器或 GitHub 联网；被打开的 Xmind、系统网络盘、iCloud、Obsidian Sync 等可能按各自的规则联网或同步文件。这些行为不受 SeeXmind 控制，不能据此理解为整台设备或所有相关应用都不会联网。

完整说明见 [PRIVACY.md](PRIVACY.md)。

## 权限提醒与发行校验

自定义 Xmind 程序路径需要调用系统进程接口，因此审核工具可能显示 Shell Execution 提醒。插件只在用户主动打开文件时调用，使用参数数组，不使用 shell 命令字符串；此能力并非沙箱权限限制。

GitHub 发行来源证明记录公开仓库如何组装并发布这三个安装文件，不宣称公开工作流编译了私有 TypeScript 源码。私有源码与发行文件的一致性由社区目录的 Source verified 构建校验单独确认。许可证和依赖声明仍保留在 main.js 内以及本仓库中。

## 功能范围与使用限制

- 这是已保存图片的预览工具，不是 Xmind 编辑器、文件转换器或在线服务。
- 清晰度取决于文件保存的 PNG；放大可能模糊，不能恢复原图中没有的细节。
- 多画布文件的内置图片可能只覆盖一个画布，本版本不提供画布切换。
- 缺少预览、文件加密、损坏使用暂不支持的 ZIP64 / 分卷压缩格式，或超出安全尺寸限制时会提示，不尝试绕过保护或猜测导图布局。
- 未保存的编辑、尚未完成的文件同步，或 Xmind 未更新内置图片，可能导致预览显示旧内容。
- 当前不支持 iOS、Android 或 Linux。超大文件限制：归档 128 MiB、预览 24 MiB、4000 万像素、单边 32768 像素。
- Xmind 的安装、使用、账号、付费功能及服务条款由 Xmind 独立提供和管理；SeeXmind 不保证所有 Xmind 版本和文件格式都兼容。

## 独立项目与权利声明

SeeXmind 与 Xmind、Obsidian 及其权利人**不存在官方隶属、合作、赞助、认证或背书关系**。名称仅用于如实描述文件兼容性和使用方式，相关商标归各自权利人所有。

本项目不捆绑 Xmind 或 Obsidian 的应用程序、品牌图标、付费组件、模板或用户导图，不替代第三方产品许可，不绕过账号、付费限制或文件加密。用户应仅访问和处理有权使用的文件；导图及图片内容的权利属于相应权利人。

项目工程源码单独维护在私有仓库；公开仓库提供文档和可安装的构建文件。发行文件 `main.js` 是可读 JavaScript，私有源码工程不等于发行代码不可查看或复制。本发行版沿用 [Apache-2.0](LICENSE)，不另行宣称专有或禁止该许可允许的使用；打包依赖保留各自许可，见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

软件按现状提供，具体保证与责任限制以许可证及适用法律为准。以上范围说明不排除法律不允许排除的责任，也不是不侵权或“零法律风险”的保证。
