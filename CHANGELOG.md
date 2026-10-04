# Changelog / 更新记录

## 0.1.1 — 2026-10-05

- Replace the ZIP reader with bounded in-memory parsing; remove runtime filesystem dependencies. Reject corrupt checksums, inconsistent entries, unsupported ZIP64/split archives, and dishonest decompressed sizes.
- Remove CSS `!important` using view-scoped selectors.
- Retain custom macOS `.app` and Windows `.exe` paths, with stricter Mac path validation. User-triggered process launching remains explicitly disclosed.
- Add English installation and usage instructions to both distribution and source documentation.
- Distribute only Obsidian's three installation assets. Preserve license notices inside `main.js` and in the repository.
- Add a public distribution workflow and artifact provenance; private source rebuild verification remains separate.
- Windows GUI verification remains pending.


## 0.1.0 — 2026-10-05

首次公开安装文件，供提交社区目录前使用。

- 在 Obsidian 文件目录显示 `.xmind`，单击读取内置 PNG 预览。
- 双击或使用打开按钮，在本机 Xmind 中打开原文件。
- 提供缩放、拖动、适应窗口、文件变化后刷新。
- 支持 Mac 和 Windows 打开方式配置；Windows 实际桌面验证待完成。
- 本地处理，无插件主动联网、遥测或数据上传。

macOS 核心功能已实测；本版本尚未获得 Obsidian 社区目录审核或上架。
