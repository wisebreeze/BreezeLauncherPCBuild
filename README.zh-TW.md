# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![Tauri](https://img.shields.io/badge/Tauri-2-24C8DB.svg)](https://tauri.app/)
[![Rust](https://img.shields.io/badge/Rust-1.77.2+-000000.svg?logo=rust)](https://www.rust-lang.org/)

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

---

BreezeLauncher 桌面版 — 跨平台的 Minecraft 基岩版與 Java 版啟動器。單一程式碼庫，為 Windows、Linux 與 macOS 提供原生、精緻的體驗。

本倉庫僅承載 CI 與發行產物，原始碼位於私有倉庫，建置時檢出。

> [!IMPORTANT]
> **免責聲明**
>
> BreezeLauncher **不隸屬於、不受認可、也不受贊助於** Mojang Studios、Microsoft 或任何第三方。這**不是官方 Minecraft 產品**。Minecraft 是 Mojang Studios 的商標。所有產品名稱、標誌與品牌均歸其各自所有者所有。

## 系統需求

- **Windows** 10 1803+（含 WebView2 執行階段，Win10/11 已預裝），x64
- **Linux** x64，glibc 2.28+，需要 `webkit2gtk-4.1` 與 `libgtk-3`
- **macOS** 10.15 以上，Intel 與 Apple Silicon 皆可

可攜版 — 無需安裝器，不寫登錄檔，不佔用 `Program Files`。

## 功能

- 首頁、下載、實例、任務、設定頁面
- Minecraft 基岩版版本列表，支援搜尋與過濾
- Xbox Live CDN 伺服器選擇 + 測速
- msixvc 匯入（解密 + 解壓縮）
- 遊戲目錄管理，支援拖曳排序
- Java 版：版本列表、模組載入器（Fabric / Quilt / Forge / NeoForge）、單一任務完成安裝
- Java 版啟動：classpath、natives、帳號、記憶體、JVM 參數、視窗大小
- 帳號：微軟（裝置代碼）、離線、第三方（authlib-injector）
- 多語言：繁體中文 / 简体中文 / English

### 計畫中

- 基岩版實例的啟動追蹤
- 存檔 / 資源包 / 世界管理

## 下載

預建置產物發佈於 [Releases](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases) 頁面，檔名形如 `BreezeLauncher_0.1.0_*`：

| 平台 | 格式 |
|------|------|
| Windows x64 | `.exe` 安裝器（NSIS）、`.msi` |
| Linux x64 | `.deb`、`.rpm`、`.AppImage` |
| macOS 通用 | `.dmg`（Intel + Apple Silicon） |

最新建置始終附在 [`artifact`](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/tag/artifact) 滾動發行上。

### macOS 首次開啟

產物未以 Apple 開發者憑證簽名與公證，Gatekeeper 會攔截首次啟動。右鍵 `BreezeLauncher.app` → **打開**，或在終端機移除隔離標記：

```bash
xattr -dr com.apple.quarantine /Applications/BreezeLauncher.app
```

## 開源致謝

BreezeLauncher 基於以下開源專案建置：

**執行階段 / 語言**
- [Rust](https://www.rust-lang.org/) — 後端語言
- [Tauri 2](https://tauri.app/) — 桌面應用框架

**前端**
- [React 19](https://react.dev/) — UI 函式庫
- [Fluent UI React v9](https://react.fluentui.dev/) — 微軟 Fluent 設計系統元件
- [Fluent System Icons](https://github.com/microsoft/fluentui-system-icons) — MIT 圖示集
- [Vite](https://vite.dev/) — 建置工具
- [React Router](https://reactrouter.com/) — 路由
- [i18next / react-i18next](https://www.i18next.com/) — 國際化
- [dnd-kit](https://dndkit.com/) — 拖曳排序
- [TanStack Virtual](https://tanstack.com/virtual) — 列表虛擬化
- [Framer Motion](https://motion.dev/) — 動畫

**打包**
- [Tauri bundler](https://tauri.app/) — `.msi` / NSIS / `.deb` / `.rpm` / `.AppImage` / `.dmg`

## 授權

版權所有 © 2026 wisebreeze。保留所有權利。

未經版權所有者事先書面許可，嚴禁以任何形式複製、修改、發佈或逆向工程本軟體的全部或部分內容。
