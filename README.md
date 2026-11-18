# Kalam — free, local-first writing assistant

Website: https://tanzir71.github.io/kalam-app-releases/

This repository holds the **built website and unsigned release files only** (no source code).
Kalam is a Chrome/Edge extension with a Windows companion, **Kalam for Windows**, that keeps the
models on your PC and runs them locally. They talk over native messaging — no network, no open ports.

## Download

| File | What it is |
| --- | --- |
| [Kalam-Setup-0.3.0-x64.exe](https://github.com/tanzir71/kalam-app-releases/releases/download/v0.3.0/Kalam-Setup-0.3.0-x64.exe) | Kalam for Windows + extension (recommended) — 45.2 MB |
| [kalam-extension-0.3.0-chromium.zip](https://github.com/tanzir71/kalam-app-releases/releases/download/v0.3.0/kalam-extension-0.3.0-chromium.zip) | Extension only, Chrome & Edge — 22.8 MB |
| [kalam-extension-0.3.0-firefox-unsigned.xpi](https://github.com/tanzir71/kalam-app-releases/releases/download/v0.3.0/kalam-extension-0.3.0-firefox-unsigned.xpi) | Firefox, experimental, unsigned — 22.8 MB |

Models are in the [`models-v1`](https://github.com/tanzir71/kalam-app-releases/releases/tag/models-v1) release and are downloaded by the apps when you ask, with SHA-256 checks.

## Unsigned builds — verify first

Kalam is free, so there are no paid signing certificates and no store in between.

```powershell
Get-FileHash .\Kalam-Setup-0.3.0-x64.exe -Algorithm SHA256
```

Compare the hash with `SHA256SUMS.txt` on the release page. Windows SmartScreen will show
“Windows protected your PC” — choose **More info → Run anyway** only if the checksum matches.

## Install

1. Run the installer (per-user, no administrator rights). It installs to `%LOCALAPPDATA%\Kalam`.
2. In Kalam for Windows, open **Browser**: open `chrome://extensions` or `edge://extensions`, turn on
   **Developer mode**, choose **Load unpacked** and pick `%LOCALAPPDATA%\Kalam\extension`.
3. Open **Models** and download Kalam Detector 0.3 and the writer.

Extension only: unzip `kalam-extension-0.3.0-chromium.zip` and load the folder the same way. Firefox (experimental):
Developer Edition / Nightly / ESR with `xpinstall.signatures.required=false`.

## Honesty

- The AI-writing signal is per passage, can be wrong (especially on short, technical or edited text and for
  non-native writers) and is **not** a probability of authorship. Passages under 50 words are not scored.
- Never use it to judge someone else’s work or to enforce AI-use policies.
- Kalam Detector 0.3 is **free for noncommercial use** (see LICENSES/MODELS.txt).

## Licences

See [LICENSES/](LICENSES/). Built 2026-11-18 from source commit e207b0a66f6a.
