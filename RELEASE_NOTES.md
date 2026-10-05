# SeeXmind 0.2.2

Requires desktop Obsidian **1.8.7 or later**.

- Removes Node.js child-process APIs and custom application path settings.
- Double-click and Open in Xmind now use the system default application for the selected `.xmind` file. **Set Xmind as the default for `.xmind` in macOS/Windows first.** Old custom paths are ignored; idle opacity is preserved.
- Retains all 0.2.1 review fixes for language detection, compatibility, typing, deprecated APIs and unused code.
- Updates privacy disclosure and English/Chinese setup instructions. No browser localStorage/sessionStorage or process-execution APIs remain in the runtime.

Download the three assets into `.obsidian/plugins/seexmind/` and reload the plugin. Preserve `data.json` to retain opacity. Structure previews, embedded images, sheets and Markdown embeds are unchanged.

Automated path-validation, parsing, localization and settings tests and TypeScript checks passed. Version 0.2.0 was tested on macOS and reported working on Windows by the maintainer. The changed external opening behavior in this patch still needs a fresh desktop GUI test.

[English instructions](https://github.com/leyem8919-coder/SeeXmind#readme) · [简体中文](https://github.com/leyem8919-coder/SeeXmind/blob/main/README.zh-CN.md)
