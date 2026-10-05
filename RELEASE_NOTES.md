# SeeXmind 0.2.1

- Fix the minimum Obsidian version: **desktop Obsidian 1.8.7 or later is required**. The language API is used directly without a legacy storage fallback.
- Resolve automated review findings for an unsafe assignment, a deprecated slider helper, and an unused function.
- Keep Markdown embeds, sheet switching, floating controls, configurable opacity, and custom Xmind application paths.
- Download the three attached files and place them in `.obsidian/plugins/seexmind/`; preserve `data.json` when updating.

[English instructions](https://github.com/leyem8919-coder/SeeXmind#readme) · [简体中文说明](https://github.com/leyem8919-coder/SeeXmind/blob/main/README.zh-CN.md)

macOS GUI testing and automated checks completed for 0.2.0; Windows testing was confirmed by the maintainer on 2026-10-05. This patch has automated test and build validation. Full development source remains private; this release distributes readable JavaScript under Apache-2.0. See THIRD_PARTY_NOTICES.md for adapted renderer attribution.

Opening a file in a custom desktop application still requires a user-triggered process launch. The plugin does not initiate network requests or collect telemetry.
