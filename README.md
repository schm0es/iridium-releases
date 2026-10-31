# Opacity

A fast native media viewer, player and editor. This repository holds its releases.

## Install

```bash
curl -fsSL https://github.com/schm0es/opacity-releases/releases/latest/download/install.sh | bash
```

Windows (PowerShell):

```powershell
irm https://github.com/schm0es/opacity-releases/releases/latest/download/install.ps1 | iex
```

or run `opacity-windows-x86_64-setup.exe` from the latest release (unsigned:
SmartScreen asks first, More info → Run anyway).

Installs the app and ffmpeg, which it needs to open media: on Linux
`~/.local/bin/opacity` with a menu entry and icons (ffmpeg from your package
manager), on macOS `/Applications/Opacity.app` (ffmpeg from Homebrew). Linux
x86_64 and arm64; macOS Intel and Apple Silicon; Windows x64 (per user,
`%LOCALAPPDATA%\Opacity`, no admin, ffmpeg bundled; uninstall from Settings >
Apps).

- Skip ffmpeg: `... | bash -s -- --no-ffmpeg`
- Make it the default app for its file types: `... | bash -s -- --default`
  (Windows: `$env:OPACITY_DEFAULT = "1"` before `irm`, or `setup.exe /DEFAULT`)
- A specific version: `... | OPACITY_VERSION=v0.2.0 bash`
  (Windows: `$env:OPACITY_VERSION = "v0.2.0"`)
- Uninstall: `... | bash -s -- --uninstall`

Opacity checks for updates on start and every few hours, downloads them in the
background (each is signature-checked) and offers **Restart to update** in the
title bar. The menu has **Check for Updates**.

## Default app

Installing never takes over your file types; Opacity is added to "Open with".
To make it the default, use **Make Opacity the Default App** in its menu, or
pass `--default` to the installer (Windows: `/DEFAULT` opens Settings > Default
apps for Opacity, where you pick the file types). On macOS you can also use
Finder: Get Info > Open with > Opacity > Change All.
