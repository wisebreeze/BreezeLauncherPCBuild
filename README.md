# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![Tauri](https://img.shields.io/badge/Tauri-2-24C8DB.svg)](https://tauri.app/)
[![Rust](https://img.shields.io/badge/Rust-1.77.2+-000000.svg?logo=rust)](https://www.rust-lang.org/)

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

---

BreezeLauncher is the desktop edition — a cross-platform launcher for Minecraft Bedrock and Java Edition. It brings a native, polished experience to Windows, Linux and macOS from a single codebase.

This repository hosts CI and release assets only; the source lives in a private repository and is cloned at build time.

> [!IMPORTANT]
> **Disclaimer**
>
> BreezeLauncher is **not affiliated with, endorsed by, or sponsored by** Mojang Studios, Microsoft, or any other third party. This is **not an official Minecraft product**. Minecraft is a trademark of Mojang Studios. All product names, logos, and brands are property of their respective owners.

## Requirements

- **Windows** 10 1803+ with WebView2 Runtime (preinstalled on Windows 10/11), x64
- **Linux** x64 with glibc 2.28+, `webkit2gtk-4.1` and `libgtk-3`
- **macOS** 10.15 or later, Intel or Apple Silicon

Portable builds — no installer required, no registry writes, nothing placed in `Program Files`.

## Features

- Home, Download, Instances, Tasks, Settings pages
- Minecraft Bedrock version list with search and filter
- Xbox Live CDN server selection with speed test
- msixvc import (decrypt + extract)
- Game directory management with drag-to-reorder
- Java Edition: version list, mod loaders (Fabric / Quilt / Forge / NeoForge), install from a single task
- Java Edition launch: classpath, natives, account, memory, JVM arguments, window size
- Accounts: Microsoft (device code), offline, third-party (authlib-injector)
- i18n: English / 简体中文 / 繁體中文

### Planned

- Launch tracking for Bedrock instances
- Save / resource pack / world management

## Downloads

Pre-built builds are published on the [Releases](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases) page. File names follow `BreezeLauncher_0.1.0_*`:

| Platform | Format |
|----------|--------|
| Windows x64 | `.exe` installer (NSIS), `.msi` |
| Linux x64 | `.deb`, `.rpm`, `.AppImage` |
| macOS universal | `.dmg` (Intel + Apple Silicon) |

The latest build is always attached to the [`artifact`](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/tag/artifact) rolling release.

### macOS: first launch

Builds are not signed or notarized with an Apple Developer certificate, so Gatekeeper blocks the first launch. Either right-click `BreezeLauncher.app` → **Open**, or remove the quarantine flag:

```bash
xattr -dr com.apple.quarantine /Applications/BreezeLauncher.app
```

## Open Source Acknowledgements

BreezeLauncher is built on the following open-source projects:

**Runtime / Language**
- [Rust](https://www.rust-lang.org/) — backend language
- [Tauri 2](https://tauri.app/) — desktop application framework

**Frontend**
- [React 19](https://react.dev/) — UI library
- [Fluent UI React v9](https://react.fluentui.dev/) — Microsoft's design system components
- [Fluent System Icons](https://github.com/microsoft/fluentui-system-icons) — MIT icon set
- [Vite](https://vite.dev/) — build tool
- [React Router](https://reactrouter.com/) — routing
- [i18next / react-i18next](https://www.i18next.com/) — internationalization
- [dnd-kit](https://dndkit.com/) — drag-and-drop
- [TanStack Virtual](https://tanstack.com/virtual) — list virtualization
- [Framer Motion](https://motion.dev/) — animation

**Packaging**
- [Tauri bundler](https://tauri.app/) — `.msi` / NSIS / `.deb` / `.rpm` / `.AppImage` / `.dmg`

## License

Copyright © 2026 wisebreeze. All rights reserved.

Unauthorized copying, modification, distribution, or reverse engineering of this software, in whole or in part, is strictly prohibited without prior written permission from the copyright holder.
