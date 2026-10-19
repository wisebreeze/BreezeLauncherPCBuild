# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4.svg)](https://dotnet.microsoft.com/)
[![Framework](https://img.shields.io/badge/Avalonia-12-00A2ED.svg)](https://avaloniaui.net/)

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

---

BreezeLauncher is the desktop edition — a modern, cross-platform launcher for Minecraft Bedrock Edition. It brings a native, polished experience to Windows and Linux from a single codebase.

> [!IMPORTANT]
> **Disclaimer**
>
> BreezeLauncher is **not affiliated with, endorsed by, or sponsored by** Mojang Studios, Microsoft, or any other third party. This is **not an official Minecraft product**. Minecraft is a trademark of Mojang Studios. All product names, logos, and brands are property of their respective owners.

## Requirements

- **Windows** 10 64-bit or later, or **Linux** x64 / ARM64 with glibc 2.28+
- Currently framework-dependent — requires .NET 10 Desktop Runtime installed (will switch to self-contained for stable release)

## Features

### Implemented (v0.1.0)

- **Home** — App overview
- **Download** — Minecraft Bedrock version list (Release / Preview), with search and filter
  - Data sources: BMCBL API (primary) + mcappx.com (fallback)
  - Click a version → dialog: instance name, install directory, Xbox Live CDN server selection
  - 10 CDN nodes tested in parallel, color-coded latency (green / olive / orange / red)
  - Auto-selects the fastest node, with retest support
- **Instances** — Installed game instance list
  - Import from local `.msixvc` file (decrypt + extract)
  - Auto-detect Release / Preview build type (trial decryption)
  - Instances persisted across sessions
- **Settings**
  - Personalization: theme mode (light / dark / system), transparency effect
  - General: language (Simplified Chinese / Traditional Chinese / English / System), game directory management
  - Game directories: add, edit, delete, drag-and-drop reorder, open in file browser
  - About: version info, check for updates

### Planned

- Microsoft account OAuth login + purchase verification
- Instance detail page (launch game, open directory, delete)
- Save management (backup / restore)
- Resource pack / behavior pack management
- World management

## Downloads

Pre-built installers are published on the [Releases](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases) page:

| Platform | Format | Download |
|----------|--------|----------|
| Windows x64 | `.exe` installer | [BreezeLauncher-setup.exe](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-setup.exe) |
| Linux x64 | `.deb` | [breezelauncher_latest_amd64.deb](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/breezelauncher_0.1.0_amd64.deb) |
| Linux x64 | `.rpm` | [BreezeLauncher-latest.x86_64.rpm](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-0.1.0-1.x86_64.rpm) |
| Linux ARM64 | `.deb` | [breezelauncher_latest_arm64.deb](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/breezelauncher_0.1.0_arm64.deb) |
| Linux ARM64 | `.rpm` | [BreezeLauncher-latest.aarch64.rpm](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-0.1.0-1.aarch64.rpm) |

The latest build is always attached to the [`artifact`](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/tag/artifact) rolling release.

## Open Source Acknowledgements

BreezeLauncher is built on the following open-source projects:

**Runtime / Language**
- [.NET 10](https://dotnet.microsoft.com/) — cross-platform runtime and SDK (LTS, expires 2028-11)
- [C# 14](https://learn.microsoft.com/dotnet/csharp/) — programming language

**UI / Framework**
- [Avalonia UI 12.1.4](https://avaloniaui.net/) — cross-platform XAML UI framework
- [Avalonia Fluent Theme](https://avaloniaui.net/) — Win11 Fluent design theme
- [FluentIcons.Avalonia 2.1.344](https://github.com/dotnetprojects/FluentIcons) — MIT icon library
- [Inter font](https://rsms.me/inter/) — UI font family

**Packaging**
- [Inno Setup 6](https://jrsoftware.org/isinfo.php) — Windows installer creator
- [fpm](https://github.com/jordansissel/fpm) — Linux .deb / .rpm package builder

## License

Copyright © 2026 wisebreeze. All rights reserved.

Unauthorized copying, modification, distribution, or reverse engineering of this software, in whole or in part, is strictly prohibited without prior written permission from the copyright holder.
