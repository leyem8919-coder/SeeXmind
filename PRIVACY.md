# SeeXmind privacy / 隐私说明

Applies to version 0.2.0. Updated 2026-10-05.

## Local processing

SeeXmind reads the selected vault `.xmind` file through Obsidian's Vault API. It extracts the embedded PNG and, when available, parses bounded `content.json` or `content.xml` data to draw sheet structures locally in memory. It does not modify the source file, scan the entire disk, or upload previews. Structured rendering does not load remote links, fonts, or image resources. No Node.js filesystem module is used by the runtime plugin.

The plugin listens for vault file changes to refresh active previews. Application paths and idle opacity are stored in `.obsidian/plugins/seexmind/data.json`. Each preview's temporary zoom, pan and sheet selection stay in memory.

## Network and data collection

SeeXmind does not initiate network requests, operate a backend, load remote scripts, upload documents, collect personal information, track usage, show ads, or send telemetry/crash reports. It requires no SeeXmind account, credentials, or API key. This statement describes the implementation, not a security sandbox or permission restriction imposed by Obsidian.

## Opening another application

Only a user action (double-click, button, command, or file menu) opens the selected file externally. The plugin passes its local path to Xmind or the operating system file association. A custom application path uses process-launching APIs with argument arrays, not shell command strings. The chosen application receives access to that file and may edit it. The plugin does not access Xmind accounts or passwords.

Xmind, Obsidian, GitHub, network storage and synchronization services have independent network behavior and privacy policies. Downloading/updating this plugin, opening a network-mounted file, or using Xmind's cloud features may involve network access outside SeeXmind. Synchronizing the plugin configuration folder may also synchronize saved application paths.

## Removal and feedback

Disable the plugin and remove its `seexmind` plugin folder to delete its local settings. There is no developer-operated remote user database. Before posting public issues, remove sensitive information from files, screenshots, and logs.

## 中文说明

插件仅在本机内存中读取选中的库内文件，解析内置 PNG 或导图结构，不修改导图，不扫描整个磁盘，不主动联网，不加载远程资源，不上传文件，不采集个人信息、行为统计、遥测或崩溃报告。

应用路径及闲置不透明度保存在当前库的 `data.json`。缩放、平移和画布选择为临时内存状态。用户主动打开原文件时，插件将本地路径交给 Xmind 或系统默认应用；指定程序路径时使用参数数组启动程序，不执行拼接的 shell 命令字符串。

Xmind、Obsidian、GitHub、网络盘或同步服务自身的网络行为另行管理；同步插件配置目录可能连同应用路径一起同步。插件“不主动联网”不等于外部应用或网络盘不联网，也不代表 Obsidian 对插件提供了安全沙箱。停用并删除插件目录可清除本地设置；反馈时请先移除敏感内容。
