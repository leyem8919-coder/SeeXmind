# SeeXmind privacy / 隐私说明

Applies to version 0.2.2. Updated 2026-10-05.

## Local processing

SeeXmind reads the selected vault `.xmind` file through Obsidian's Vault API. It extracts the embedded PNG and, when available, parses bounded `content.json` or `content.xml` data to draw sheet structures locally in memory. It does not modify the source file, scan the entire disk, or upload previews. Structured rendering does not load remote links, fonts, or image resources. No Node.js filesystem module is used by the runtime plugin.

The plugin listens for vault file changes to refresh active previews. Idle opacity is saved with Obsidian's plugin data API in `.obsidian/plugins/seexmind/data.json`. Preview zoom, pan and sheet selection stay in memory. Legacy custom application paths are ignored and omitted the next time settings are saved. The plugin does not read or write browser localStorage or sessionStorage.

## Network and data collection

SeeXmind does not initiate network requests, operate a backend, load remote scripts, upload documents, collect personal information, track usage, show ads, or send telemetry/crash reports. It requires no SeeXmind account, credentials, or API key. This statement describes the implementation, not a security sandbox or permission restriction imposed by Obsidian.

## Opening another application

Only a user action (double-click, button, command, or file menu) opens the selected file externally. SeeXmind validates its local `.xmind` path and hands it to Electron's `shell.openPath` desktop-integration API, which uses the operating system's default application. Set Xmind as that default application. The plugin does not accept a program path or command, use Node.js child-process APIs, execute shell command strings, or request administrator elevation. Electron's module name `shell` does not mean SeeXmind supplies a shell command. The chosen application receives the file and may edit it.

Xmind, Obsidian, GitHub, network storage and synchronization services have independent network behavior and privacy policies. Downloading/updating the plugin, opening a network-mounted file, or using Xmind cloud features may involve network access outside SeeXmind. Synchronizing the plugin configuration folder may synchronize its settings, including legacy fields left by older versions. Obsidian desktop plugins are not security-sandboxed.

## Removal and feedback

Disable the plugin and remove its `seexmind` folder to delete local settings. There is no developer-operated remote user database. Remove sensitive information from files, screenshots, and logs before posting public issues.

## 中文说明

插件仅在本机内存中读取选中的库内文件，解析内置 PNG 或导图结构，不修改导图，不扫描整个磁盘，不主动联网，不加载远程资源，不上传文件，不采集个人信息、行为统计、遥测或崩溃报告。

闲置不透明度通过 Obsidian 插件数据 API 保存在当前库的 `data.json`；缩放、平移和画布选择只保留在内存中。不读写浏览器 localStorage 或 sessionStorage。旧版自定义程序路径不再使用，下次保存设置时会从配置中移除。

只有用户主动打开原文件时，插件才把经过校验的 `.xmind` 本地路径交给系统默认应用。请在系统中把 Xmind 设为默认应用。0.2.2 不再接受程序路径或命令，不使用 Node.js 子进程 API，不执行 shell 命令字符串，不请求管理员提权。Electron 的 `shell.openPath` 是默认应用打开文件接口；模块名中的 shell 不等于执行命令。

Xmind、Obsidian、GitHub、网络盘或同步服务自身的网络行为另行管理。插件“不主动联网”不等于外部应用或网络盘不联网，也不代表 Obsidian 为插件提供了安全沙箱。停用并删除插件目录可清除本地设置；反馈时请先移除敏感内容。
