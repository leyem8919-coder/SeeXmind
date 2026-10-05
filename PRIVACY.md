# SeeXmind privacy / 隐私说明

Applies to version 0.2.3. Updated 2026-10-05.

## Local processing

SeeXmind reads the selected vault `.xmind` file through Obsidian's Vault API. It extracts the embedded PNG and, when available, parses bounded `content.json` or `content.xml` data to draw sheet structures locally in memory. It does not modify the source file, scan the entire disk, or upload previews. Structured rendering does not load remote links, fonts, or image resources. No Node.js filesystem module is used by the runtime plugin.

The plugin listens for vault file changes to refresh active previews. Application paths and idle opacity are stored in `.obsidian/plugins/seexmind/data.json`. Each preview's temporary zoom, pan and sheet selection stay in memory.

## Network and data collection

SeeXmind does not initiate network requests, operate a backend, load remote scripts, upload documents, collect personal information, track usage, show ads, or send telemetry/crash reports. It requires no SeeXmind account, credentials, or API key. This statement describes the implementation, not a security sandbox or permission restriction imposed by Obsidian.

## External application capability warning

The directory may show **“Shell Execution / child_process”**. SeeXmind uses Node.js process-launching APIs to open Xmind on macOS (including a custom `.app`) or a user-selected `.exe` on Windows. Windows with no custom path uses the system file association.

- Launching happens only after you double-click a file or choose an Open in Xmind button, command, or menu item. Loading the plugin and displaying previews do not launch the application.
- Local `.xmind` paths and custom application paths are validated. The executable and arguments are passed separately, without concatenated shell command strings or a shell interpreter.
- SeeXmind does not request administrator elevation. This warning describes a powerful API available to the plugin; it is not a request for administrator or Full Disk Access permission.
- This is **not a sandbox or a guarantee of safety**. The selected program runs with the current user's permissions and receives the file path. A malicious executable can cause harm: choose only a trusted local Xmind installation. File-extension checks do not verify the publisher or contents of that program.

We retain and disclose this capability to support custom application paths; we do not hide it or claim the warning has been eliminated. The plugin does not initiate network requests or collect telemetry; external applications have their own behavior. See [PRIVACY.md](PRIVACY.md).

## Opening another application

Only a user action (double-click, button, command, or file menu) opens the selected file externally. The plugin passes its local path to Xmind or the operating system file association. A custom application path uses process-launching APIs with argument arrays, not shell command strings. The chosen application receives access to that file and may edit it. The plugin does not access Xmind accounts or passwords.

Xmind, Obsidian, GitHub, network storage and synchronization services have independent network behavior and privacy policies. Downloading/updating this plugin, opening a network-mounted file, or using Xmind's cloud features may involve network access outside SeeXmind. Synchronizing the plugin configuration folder may also synchronize saved application paths.

## Removal and feedback

Disable the plugin and remove its `seexmind` plugin folder to delete its local settings. There is no developer-operated remote user database. Before posting public issues, remove sensitive information from files, screenshots, and logs.

## 中文说明

插件仅在本机内存中读取选中的库内文件，解析内置 PNG 或导图结构，不修改导图，不扫描整个磁盘，不主动联网，不加载远程资源，不上传文件，不采集个人信息、行为统计、遥测或崩溃报告。

应用路径及闲置不透明度保存在当前库的 `data.json`。缩放、平移和画布选择为临时内存状态。用户主动打开原文件时，插件将本地路径交给 Xmind 或系统默认应用；指定程序路径时使用参数数组启动程序，不执行拼接的 shell 命令字符串。

Xmind、Obsidian、GitHub、网络盘或同步服务自身的网络行为另行管理；同步插件配置目录可能连同应用路径一起同步。插件“不主动联网”不等于外部应用或网络盘不联网，也不代表 Obsidian 对插件提供了安全沙箱。停用并删除插件目录可清除本地设置；反馈时请先移除敏感内容。

## 打开外部程序的能力警告

插件目录可能显示 **“Shell 执行 / child_process”**。SeeXmind 使用 Node.js 程序启动接口，在 Mac 上打开 Xmind（包括指定的 `.app`），或在 Windows 上启动你指定的 `.exe`；Windows 未填写路径时使用系统默认打开方式。

- 只有你双击文件，或使用“用 Xmind 打开”按钮、命令、菜单时才会启动程序；启用插件、显示预览不会自动启动程序。
- 插件会校验 `.xmind` 本地文件路径和自定义应用路径，使用独立参数传递，不拼接 shell 命令字符串，也不通过 shell 解释器执行。
- 插件不请求管理员提权。这是对强大 API 的能力提示，不是要求你授予管理员权限或“完全磁盘访问权限”。
- 这**不代表有安全沙箱，也不是绝对安全保证**。所选程序以当前用户权限运行，并得到文件路径。恶意程序仍可能造成危害，因此请只选择可信的本机 Xmind；路径和后缀校验不能验证程序的发布者与内容。

我们为保留自定义程序路径而如实披露这项能力，不隐藏它，也不声称该警告已经消除。插件不主动联网、不采集遥测；外部程序自身的行为另行管理。详见 [隐私说明](PRIVACY.md)。
