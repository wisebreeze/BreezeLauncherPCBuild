# BreezeLauncherPCBuild

Public CI host for **BreezeLauncherPC** — builds self-contained desktop installers (Windows / Linux) from the private source repo.

## Why a separate public repo?

GitHub Actions gives **unlimited minutes for public repos** but caps private repos at 2000 min/month. This repo exists purely to host the CI workflow; the actual source code lives in the private [`BreezeLauncherPC`](https://github.com/wisebreeze/BreezeLauncherPC) repo and is cloned at build time.

## How it works

```
push to BreezeLauncherPC (private)
  ↓ GitHub webhook
BreezeLauncherBackend (Cloudflare Worker) webhook relay
  ↓ repository_dispatch (event_type: upstream-changed)
BreezeLauncherPCBuild (this repo) — workflow triggers
  ↓ git clone private repo (PRIVATE_REPO_TOKEN secret)
  ↓ dotnet publish --self-contained
  ↓ package: Windows → exe (Inno Setup), Linux → deb + rpm (fpm)
  ↓ upload to `artifact` rolling release
```

## Build outputs

| Platform | RID | Format | Asset name |
|----------|-----|--------|------------|
| Windows | `win-x64` | exe (Inno Setup) | `BreezeLauncher-setup.exe` |
| Linux | `linux-x64` | deb | `breeze-launcher_<ver>_amd64.deb` |
| Linux | `linux-x64` | rpm | `breeze-launcher-<ver>-1.x86_64.rpm` |
| Linux | `linux-arm64` | deb | `breeze-launcher_<ver>_arm64.deb` |
| Linux | `linux-arm64` | rpm | `breeze-launcher-<ver>-1.aarch64.rpm` |

All assets are published to the [`artifact`](../../releases/tag/artifact) rolling release.

## Secrets

| Secret | Purpose |
|--------|---------|
| `PRIVATE_REPO_TOKEN` | PAT with read access to `BreezeLauncherPC`. Used to clone the private source repo. |
| `GITHUB_TOKEN` | Auto-provided by GitHub. Used to create the `artifact` release and upload assets. |

## Caching

NuGet packages (`~/.nuget/packages`) are cached per-RID, keyed on the `.csproj` hash.
