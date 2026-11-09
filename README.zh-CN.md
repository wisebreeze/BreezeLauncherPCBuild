# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![Tauri](https://img.shields.io/badge/Tauri-2-24C8DB.svg)](https://tauri.app/)
[![Rust](https://img.shields.io/badge/Rust-1.77.2+-000000.svg?logo=rust)](https://www.rust-lang.org/)

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

---

BreezeLauncher 桌面版 — 跨平台的 Minecraft 基岩版与 Java 版启动器。单一代码库，为 Windows、Linux 和 macOS 提供原生、精致的体验。

本仓库只承载 CI 与发布产物，源码位于私有仓库，构建时检出。

> [!IMPORTANT]
> **免责声明**
>
> BreezeLauncher **不隶属于、不受认可、也不受赞助于** Mojang Studios、Microsoft 或任何第三方。这**不是官方 Minecraft 产品**。Minecraft 是 Mojang Studios 的商标。所有产品名称、徽标和品牌均归其各自所有者所有。

## 系统要求

- **Windows** 10 1803+（含 WebView2 运行时，Win10/11 已预装），x64
- **Linux** x64，glibc 2.28+，需要 `webkit2gtk-4.1` 与 `libgtk-3`
- **macOS** 10.15 及以上，Intel 与 Apple Silicon 均可

便携版 — 无需安装器，不写注册表，不占用 `Program Files`。

## 功能

- 首页、下载、实例、任务、设置页面
- Minecraft 基岩版版本列表，支持搜索和过滤
- Xbox Live CDN 服务器选择 + 测速
- msixvc 导入（解密 + 解压）
- 游戏目录管理，支持拖拽排序
- Java 版：版本列表、模组加载器（Fabric / Quilt / Forge / NeoForge）、单任务完成安装
- Java 版启动：classpath、natives、账号、内存、JVM 参数、窗口大小
- 账号：微软（设备代码）、离线、第三方（authlib-injector）
- 多语言：简体中文 / 繁体中文 / English

### 计划中

- 基岩版实例的启动跟踪
- 存档 / 资源包 / 世界管理

## 下载

预构建产物发布在 [Releases](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases) 页面，文件名形如 `BreezeLauncher_0.1.0_*`：

| 平台 | 格式 |
|------|------|
| Windows x64 | `.exe` 安装器（NSIS）、`.msi` |
| Linux x64 | `.deb`、`.rpm`、`.AppImage` |
| macOS 通用 | `.dmg`（Intel + Apple Silicon） |

最新构建始终附在 [`artifact`](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/tag/artifact) 滚动发布上。

### macOS 首次打开

产物未用 Apple 开发者证书签名和公证，Gatekeeper 会拦截首次启动。右键 `BreezeLauncher.app` → **打开**，或在终端去掉隔离标记：

```bash
xattr -dr com.apple.quarantine /Applications/BreezeLauncher.app
```

## 开源致谢

BreezeLauncher 基于以下开源项目构建：

**运行时 / 语言**
- [Rust](https://www.rust-lang.org/) — 后端语言
- [Tauri 2](https://tauri.app/) — 桌面应用框架

**前端**
- [React 19](https://react.dev/) — UI 库
- [Fluent UI React v9](https://react.fluentui.dev/) — 微软 Fluent 设计系统组件
- [Fluent System Icons](https://github.com/microsoft/fluentui-system-icons) — MIT 图标集
- [Vite](https://vite.dev/) — 构建工具
- [React Router](https://reactrouter.com/) — 路由
- [i18next / react-i18next](https://www.i18next.com/) — 国际化
- [dnd-kit](https://dndkit.com/) — 拖拽排序
- [TanStack Virtual](https://tanstack.com/virtual) — 列表虚拟化
- [Framer Motion](https://motion.dev/) — 动画

**打包**
- [Tauri bundler](https://tauri.app/) — `.msi` / NSIS / `.deb` / `.rpm` / `.AppImage` / `.dmg`

## 许可

版权所有 © 2026 wisebreeze。保留所有权利。

未经版权所有者事先书面许可，严禁以任何形式复制、修改、分发或逆向工程本软件的全部或部分内容。
