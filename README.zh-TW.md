# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4.svg)](https://dotnet.microsoft.com/)
[![Framework](https://img.shields.io/badge/Avalonia-12-00A2ED.svg)](https://avaloniaui.net/)

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

---

BreezeLauncher 桌面版 — 現代、跨平台的 Minecraft 基岩版啟動器。單一程式碼庫，為 Windows 和 Linux 提供原生、精緻的體驗。

> [!IMPORTANT]
> **免責聲明**
>
> BreezeLauncher **不隸屬於、不受認可、也不受贊助於** Mojang Studios、Microsoft 或任何第三方。這**不是官方 Minecraft 產品**。Minecraft 是 Mojang Studios 的商標。所有產品名稱、徽標和品牌均歸其各自所有者所有。

## 系統需求

- **Windows** 10 64 位元或更新版本，或 **Linux** x64 / ARM64（glibc 2.28+）
- 目前為 framework-dependent 模式 — 需安裝 .NET 10 Desktop Runtime（正式發布時改為 self-contained）

## 功能

### 已實現（v0.1.0）

- **首頁** — 應用概覽
- **下載遊戲** — Minecraft 基岩版版本列表（正式版 / 預覽版），支援搜尋和過濾
  - 資料來源：BMCBL API（主）+ mcappx.com（備）
  - 點擊版本 → 彈窗設定：實例名稱、安裝目錄、Xbox Live CDN 伺服器選擇
  - 10 個 CDN 節點並行測速，顏色區分延遲（綠 / 橄欖 / 橙 / 紅）
  - 自動選最快節點，支援重新測試
- **實例管理** — 已安裝的遊戲實例列表
  - 從本地 `.msixvc` 檔案匯入安裝（解密 + 解壓縮）
  - 自動偵測正式版 / 預覽版建置類型（試解密）
  - 實例持久化，重啟後保留
- **設定**
  - 個人化：主題模式（淺色 / 深色 / 跟隨系統）、透明效果
  - 一般：語言（簡中 / 繁中 / 英文 / 跟隨系統）、遊戲目錄管理
  - 遊戲目錄：新增、編輯、刪除、拖曳排序、在檔案瀏覽器中開啟
  - 關於：版本資訊、檢查更新

### 計畫中

- 微軟帳號 OAuth 登入 + 購買驗證
- 實例詳情頁（啟動遊戲、開啟目錄、刪除）
- 存檔管理（備份 / 還原）
- 資源包 / 行為包管理
- 世界管理

## 下載

預先建置的安裝包發布在 [Releases](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases) 頁面：

| 平台 | 格式 | 下載 |
|------|------|------|
| Windows x64 | `.exe` 安裝器 | [BreezeLauncher-setup.exe](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-setup.exe) |
| Linux x64 | `.deb` | [breezelauncher_latest_amd64.deb](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/breezelauncher_0.1.0_amd64.deb) |
| Linux x64 | `.rpm` | [BreezeLauncher-latest.x86_64.rpm](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-0.1.0-1.x86_64.rpm) |
| Linux ARM64 | `.deb` | [breezelauncher_latest_arm64.deb](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/breezelauncher_0.1.0_arm64.deb) |
| Linux ARM64 | `.rpm` | [BreezeLauncher-latest.aarch64.rpm](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-0.1.0-1.aarch64.rpm) |

最新建置始終附在 [`artifact`](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/tag/artifact) 滾動發布上。

## 開源致謝

BreezeLauncher 基於以下開源專案建置：

**執行階段 / 語言**
- [.NET 10](https://dotnet.microsoft.com/) — 跨平台執行階段和 SDK（LTS，2028-11 到期）
- [C# 14](https://learn.microsoft.com/dotnet/csharp/) — 程式語言

**UI / 框架**
- [Avalonia UI 12.1.4](https://avaloniaui.net/) — 跨平台 XAML UI 框架
- [Avalonia Fluent Theme](https://avaloniaui.net/) — Win11 Fluent 設計主題
- [FluentIcons.Avalonia 2.1.344](https://github.com/dotnetprojects/FluentIcons) — MIT 圖示庫
- [Inter 字體](https://rsms.me/inter/) — UI 字體族

**打包**
- [Inno Setup 6](https://jrsoftware.org/isinfo.php) — Windows 安裝器產生器
- [fpm](https://github.com/jordansissel/fpm) — Linux .deb / .rpm 打包工具

## 授權

版權所有 © 2026 wisebreeze。保留所有權利。

未經版權所有者事先書面許可，嚴禁以任何形式複製、修改、分發或逆向工程本軟體的全部或部分內容。
