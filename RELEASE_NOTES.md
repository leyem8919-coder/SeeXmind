# SeeXmind 0.2.3

Requires desktop Obsidian **1.8.7 or later**.

- Restores optional macOS `.app` and Windows `.exe` paths. Paths saved before 0.2.2 are reused if still present; if you saved settings in 0.2.2, you may need to enter them again. Opacity is preserved.
- Retains the 0.2.1 fixes for language detection, API compatibility, typing, and deprecated/unused code.
- Adds clear capability disclosure in English/Chinese documentation and path settings.

**Expected Shell Execution warning:** Node.js process-launching APIs are used only when you actively open a file in Xmind. Paths are validated; arguments are passed separately, without a shell interpreter. The plugin does not request administrator elevation. The chosen application runs with your existing permissions and receives the file path; select only a trusted local Xmind installation. This is not a sandbox or a claim that the capability warning has disappeared.

Download the three assets into `.obsidian/plugins/seexmind/`, retain `data.json`, and reload the plugin. Full source remains private.

[English instructions](https://github.com/leyem8919-coder/SeeXmind#external-application-capability-warning) · [简体中文](https://github.com/leyem8919-coder/SeeXmind/blob/main/README.zh-CN.md)
