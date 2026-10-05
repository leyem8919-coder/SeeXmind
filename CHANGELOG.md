# Changelog / 更新记录

## 0.3.0 — 2026-10-05

- Add iPhone, iPad and Android support for local `.xmind` previews, Markdown embeds and sheet selection.
- Add one-finger panning and two-finger pinch zoom, at least 44 px touch buttons, and a canvas tap that reveals controls for 3.5 seconds even at 0% idle opacity.
- Add mobile Open / share through Obsidian's available system file handoff. Choose Xmind in the system flow; imported copies may require saving back or replacing the vault file after editing.
- Keep custom macOS `.app` and Windows `.exe` paths. Desktop-only Node.js/Electron capabilities load only when used; desktop double-click behavior is unchanged.
- Update English and Simplified Chinese guides and privacy disclosures. Source, build configuration and tests remain private; existing screenshots show macOS.

## 0.2.3 — 2026-10-05

- Restore custom macOS `.app` and Windows `.exe` paths and user-triggered process launching. Keep the 0.2.1 language, minimum-version, typing and deprecated API fixes.
- Explain the expected Shell Execution capability warning in English/Chinese documentation and beside path settings. The plugin does not request administrator elevation; custom programs must be trusted.
- Restore the settings screenshot. Existing paths load when present; paths removed by saving settings in 0.2.2 must be entered again. Preserve opacity.

## 0.2.2 — 2026-10-05

- Remove Node.js child-process APIs and custom executable/application path settings. User-triggered external opening now passes only a validated `.xmind` path to the system default application on macOS and Windows.
- Set Xmind as the system default for `.xmind` files before using external opening. Old custom paths are ignored; idle opacity is preserved.
- Retain the 0.2.1 review fixes: minimum Obsidian 1.8.7, official language API, no browser storage, typed ZIP entries, and no deprecated/unused helpers.
- Update English/Chinese instructions and privacy disclosure; stop showing the outdated custom-path settings screenshot in the READMEs.

## 0.2.1 — 2026-10-05

- Correct the minimum Obsidian version to 1.8.7, matching the language API used by the plugin.
- Use the official language API and remove unused legacy locale detection.
- Resolve review findings for an unsafe assignment, a deprecated slider helper, and an unused resource helper.
- Add a voluntary support QR code and thanks to the public GitHub documentation only.
- Correct release documentation: Windows testing was confirmed by the maintainer on 2026-10-05.

## 0.2.0 — 2026-10-05

- Add independent Markdown embeds in Live Preview and Reading view, plus an `xmind` code-block fallback.
- Add sheet selection and local structure rendering, while preserving embedded PNG mode for original appearance. Structure layouts are approximate; resource images and some advanced features are not reconstructed.
- Follow Obsidian English/Simplified Chinese language for preview controls, settings, messages, and commands.
- Reuse floating controls, idle opacity, and custom application paths in embedded previews.
- Add bounded document parsing and attribution for adapted Apache-2.0 renderer components.
- Split English README and Simplified Chinese documentation. No new promotional screenshots were uploaded.

## 0.1.4 — 2026-10-05

- Move zoom, fit, and refresh to a vertical floating icon toolbar with hover labels.
- Float Open in Xmind at the bottom-right of the preview.
- Add live idle opacity (0–100%, default 35%) with full visibility on hover and keyboard focus.
- Keep invisible controls reachable, and keep control clicks separate from canvas drag/zoom.
- Add user-provided documentation screenshots (0.1.3 layout) and clarify public downloads versus private source review.

## 0.1.3 — 2026-10-05

- Remove the redundant plugin-name heading from the legacy settings renderer. Custom application paths are unchanged.

## 0.1.2 — 2026-10-05

- Preserve workspace pane positions when unloading the plugin.
- Use standard settings headings and window timers.
- Validate loaded settings instead of assigning untyped data.
- Make custom application paths searchable using Obsidian 1.13's declarative settings API, with an older-version rendering fallback.

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
