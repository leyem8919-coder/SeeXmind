SeeXmind 0.1.3 fixes directory review findings while retaining custom Xmind application paths.

- Pure in-memory ZIP preview reading through the Obsidian Vault API; no runtime Node filesystem dependency.
- CSS selectors no longer use `!important`.
- English installation and usage documentation included.
- macOS custom `.app` and Windows custom `.exe` remain supported. User-triggered process execution is still disclosed; no shell command strings are evaluated.
- Only `main.js`, `manifest.json`, and `styles.css` are attached for installation. Full project/dependency license notices are embedded in `main.js` and available in the repository.
- GitHub attestations cover assembly of these public distribution files. Private-source compilation is verified separately by the Obsidian directory against the matching private tag.

Install these three files in `.obsidian/plugins/seexmind/`, then reload SeeXmind. Windows GUI testing remains pending. Embedded previews in ZIP64 or split ZIP archives are not supported.

Also fixes private-source review errors: preserve panes on unload, remove redundant setting headings, validate saved settings, use window timers, and expose custom paths in settings search.
