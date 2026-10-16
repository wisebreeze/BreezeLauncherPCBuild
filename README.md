# BreezeLauncherPCBuild

Public CI host for **BreezeLauncherPC** — builds self-contained desktop binaries (Windows / Linux) from the private source repo.

## Why a separate public repo?

GitHub Actions gives **unlimited minutes for public repos** but caps private repos at 2000 min/month. This repo exists purely to host the CI workflow; the actual source code lives in the private [`BreezeLauncherPC`](https://github.com/wisebreeze/BreezeLauncherPC) repo and is cloned at build time.

## How it works

```
push to BreezeLauncherPC (private)
  ↓ GitHub webhook
BreezeLauncherBackend (Cloudflare Worker) webhook relay
  ↓ repository_dispatch (event_type: upstream-changed)
BreezeLauncherPCBuild (this repo) — workflow triggers
  ↓ git clone private repo (using PRIVATE_REPO_TOKEN secret)
  ↓ dotnet publish --self-contained (3 RIDs in parallel)
  ↓ upload to `artifact` rolling release
```

## Triggers

- **`repository_dispatch`** (auto) — fired by the webhook relay when the private repo is pushed.
- **`workflow_dispatch`** (manual) — run from the Actions tab for ad-hoc builds.

## Build matrix

| RID | OS | Asset |
|-----|----|----|
| `win-x64` | `windows-latest` | `BreezeLauncher-win-x64.zip` |
| `linux-x64` | `ubuntu-22.04` | `BreezeLauncher-linux-x64.tar.gz` |
| `linux-arm64` | `ubuntu-22.04` | `BreezeLauncher-linux-arm64.tar.gz` |

All assets are published to the [`artifact`](../../releases/tag/artifact) rolling release — the latest build is always at a stable download URL.

## Secrets

| Secret | Purpose |
|--------|---------|
| `PRIVATE_REPO_TOKEN` | PAT with `repo` scope (or fine-grained: Contents: Read on `BreezeLauncherPC`). Used to clone the private source repo. |
| `GITHUB_TOKEN` | Auto-provided by GitHub. Used to create the `artifact` release and upload assets to this repo. |

## Caching

NuGet packages (`~/.nuget/packages`) are cached per-RID, keyed on the `.csproj` hash. A dependency bump invalidates the cache; a source-only change reuses the cache.
