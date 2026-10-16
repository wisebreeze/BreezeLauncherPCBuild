# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![.NET](https://img.shields.io/badge/.NET-8.0-512BD4.svg)](https://dotnet.microsoft.com/)
[![Framework](https://img.shields.io/badge/Avalonia-11-00A2ED.svg)](https://avaloniaui.net/)

---

BreezeLauncher is the desktop edition of BreezeLauncher — a modern, cross-platform launcher for Minecraft. It brings the BreezeLauncher experience to Windows and Linux with a native, self-contained binary that requires no additional runtime installation.

> [!IMPORTANT]
> **Disclaimer**
>
> BreezeLauncher is **not affiliated with, endorsed by, or sponsored by** Mojang Studios, Microsoft, or any other third party. This is **not an official Minecraft product**. Minecraft is a trademark of Mojang Studios. All product names, logos, and brands are property of their respective owners.

## Requirements

- **Windows** 10 64-bit or later, or **Linux** x64 / ARM64 with glibc 2.28+
- No .NET runtime installation needed — the app is fully self-contained

## Features

- **Cross-platform** — native experience on Windows and Linux from a single codebase
- **Self-contained** — no .NET runtime or SDK installation required; everything is bundled in the installer
- **Win11-style UI** — Fluent design with Mica-inspired materials, custom title bar, and smooth animations
- **Coming soon** — full feature set is under active development

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
- [.NET 8](https://dotnet.microsoft.com/) — cross-platform runtime and SDK
- [C#](https://learn.microsoft.com/dotnet/csharp/) — programming language

**UI / Framework**
- [Avalonia UI 11](https://avaloniaui.net/) — cross-platform XAML UI framework
- [Avalonia Fluent Theme](https://avaloniaui.net/) — Win11 Fluent design theme
- [Inter font](https://rsms.me/inter/) — UI font family

**Packaging**
- [Inno Setup 6](https://jrsoftware.org/isinfo.php) — Windows installer creator
- [fpm](https://github.com/jordansissel/fpm) — Linux .deb / .rpm package builder

## License

Copyright © 2026 wisebreeze. All rights reserved.

Unauthorized copying, modification, distribution, or reverse engineering of this software, in whole or in part, is strictly prohibited without prior written permission from the copyright holder.
