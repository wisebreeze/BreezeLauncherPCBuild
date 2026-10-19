# BreezeLauncher

[![Build](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml/badge.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild/actions/workflows/build.yml)
[![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue.svg)](https://github.com/wisebreeze/BreezeLauncherPCBuild)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4.svg)](https://dotnet.microsoft.com/)
[![Framework](https://img.shields.io/badge/Avalonia-12-00A2ED.svg)](https://avaloniaui.net/)

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

---

BreezeLauncher 桌面版 — 现代、跨平台的 Minecraft 基岩版启动器。单一代码库，为 Windows 和 Linux 提供原生、精致的体验。

> [!IMPORTANT]
> **免责声明**
>
> BreezeLauncher **不隶属于、不受认可、也不受赞助于** Mojang Studios、Microsoft 或任何第三方。这**不是官方 Minecraft 产品**。Minecraft 是 Mojang Studios 的商标。所有产品名称、徽标和品牌均归其各自所有者所有。

## 系统要求

- **Windows** 10 64 位或更高版本，或 **Linux** x64 / ARM64（glibc 2.28+）
- 当前为 framework-dependent 模式 — 需安装 .NET 10 Desktop Runtime（正式发布时改为 self-contained）

## 功能

### 已实现（v0.1.0）

- **首页** — 应用概览
- **下载游戏** — Minecraft 基岩版版本列表（正式版 / 预览版），支持搜索和过滤
  - 数据源：BMCBL API（主）+ mcappx.com（备）
  - 点击版本 → 弹窗配置：实例名称、安装目录、Xbox Live CDN 服务器选择
  - 10 个 CDN 节点并行测速，颜色区分延迟（绿 / 橄榄 / 橙 / 红）
  - 自动选最快节点，支持重新测试
- **实例管理** — 已安装的游戏实例列表
  - 从本地 `.msixvc` 文件导入安装（解密 + 解压）
  - 自动检测正式版 / 预览版构建类型（试解密）
  - 实例持久化，重启后保留
- **设置**
  - 个性化：主题模式（浅色 / 深色 / 跟随系统）、透明效果
  - 通用：语言（简中 / 繁中 / 英文 / 跟随系统）、游戏目录管理
  - 游戏目录：添加、编辑、删除、拖拽排序、在文件浏览器中打开
  - 关于：版本信息、检查更新

### 计划中

- 微软账号 OAuth 登录 + 购买验证
- 实例详情页（启动游戏、打开目录、删除）
- 存档管理（备份 / 恢复）
- 资源包 / 行为包管理
- 世界管理

## 下载

预构建的安装包发布在 [Releases](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases) 页面：

| 平台 | 格式 | 下载 |
|------|------|------|
| Windows x64 | `.exe` 安装器 | [BreezeLauncher-setup.exe](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-setup.exe) |
| Linux x64 | `.deb` | [breezelauncher_latest_amd64.deb](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/breezelauncher_0.1.0_amd64.deb) |
| Linux x64 | `.rpm` | [BreezeLauncher-latest.x86_64.rpm](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-0.1.0-1.x86_64.rpm) |
| Linux ARM64 | `.deb` | [breezelauncher_latest_arm64.deb](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/breezelauncher_0.1.0_arm64.deb) |
| Linux ARM64 | `.rpm` | [BreezeLauncher-latest.aarch64.rpm](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/download/artifact/BreezeLauncher-0.1.0-1.aarch64.rpm) |

最新构建始终附在 [`artifact`](https://github.com/wisebreeze/BreezeLauncherPCBuild/releases/tag/artifact) 滚动发布上。

## 开源致谢

BreezeLauncher 基于以下开源项目构建：

**运行时 / 语言**
- [.NET 10](https://dotnet.microsoft.com/) — 跨平台运行时和 SDK（LTS，2028-11 到期）
- [C# 14](https://learn.microsoft.com/dotnet/csharp/) — 编程语言

**UI / 框架**
- [Avalonia UI 12.1.4](https://avaloniaui.net/) — 跨平台 XAML UI 框架
- [Avalonia Fluent Theme](https://avaloniaui.net/) — Win11 Fluent 设计主题
- [FluentIcons.Avalonia 2.1.344](https://github.com/dotnetprojects/FluentIcons) — MIT 图标库
- [Inter 字体](https://rsms.me/inter/) — UI 字体族

**打包**
- [Inno Setup 6](https://jrsoftware.org/isinfo.php) — Windows 安装器生成器
- [fpm](https://github.com/jordansissel/fpm) — Linux .deb / .rpm 打包工具

## 许可

版权所有 © 2026 wisebreeze。保留所有权利。

未经版权所有者事先书面许可，严禁以任何形式复制、修改、分发或逆向工程本软件的全部或部分内容。
