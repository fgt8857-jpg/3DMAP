# 3DMAP — TruckBridge 3D map packs (GitHub distribution)

Public **map content** for [TruckBridge](https://github.com/fgt8857-jpg) (or your app monorepo).  
**Not** the TruckBridge application itself — only **3D semantic packs** (road network, cities, …).

## Why this repo

| Goal | How |
|---|---|
| Small app installer | Full Europe map data is **not** inside the app MSI |
| Game updates | Rebuild packs with `tb-tsmap-export export-3d` after Steam updates |
| User pull | Download a **Release** zip → install into `%LOCALAPPDATA%/TruckBridge/maps/3d/...` |

## License (read this)

| File | Meaning |
|---|---|
| **`LICENSE`** | **MIT** on **our** packaging: `manifest.json` schema, README, index JSON, scripts we authored |
| **`NOTICE.md`** | **SCS Software** owns Euro Truck Simulator 2 / ATS game data. Packs are **derived** community exports for personal/tool use. **Not** an official SCS product. |

**Why not “No license”?**  
On GitHub, no license ≈ **all rights reserved** — others cannot safely download, mirror, or use the packs.  
**Why MIT (not GPL)?** Map packs should stay easy to consume next to a permissive desktop app.  
**Why not claim CC0 on roads.geojson?** We do **not** own SCS map data; we only license **our packaging layer**.

If you need a different SPDX later, change `LICENSE` in a new commit and tag.

## Current pack (example)

| Field | Value |
|---|---|
| packId | `ets2-3d-base` |
| track | `3d` |
| gameId | `ETS2` |
| contentVersion | see latest Release tag |
| layers | `road_network`, `cities_poi` (+ empty buildings/lights placeholders) |

**Do not commit multi‑MB GeoJSON into git history by default.**  
Prefer **GitHub Releases** assets:

- `ets2-3d-base-<version>.zip`
- `ets2-3d-base-<version>.zip.sha256`
- optional root `manifest.json` copy for inspection

## Repo layout (source, light)

```text
README.md
LICENSE
NOTICE.md
map-pack-index.json          # catalog for apps (URLs point at Releases)
.github/                     # optional
```

## Operator: rebuild after game update

On a machine with ETS2 installed and TruckBridge monorepo tools:

```powershell
.\tools\map-pack-kit\publish-3d-from-game.ps1 `
  -GamePath "D:\...\Euro Truck Simulator 2" `
  -Game ets2
```

Then upload the zip + sha256 to a new Release (Web UI or `gh release create`).

## map-pack-index.json

Apps (later) fetch this file to list available packs.  
Update `latestContentVersion` and URLs when you cut a new Release.

## Related

- Pack contract: TruckBridge `docs/architecture/map-data-packs.md`
- Layers / ETS2LA-class toggles: `docs/architecture/map-3d-layers-and-github-packs.md`
- Tool: `tools/tb-tsmap-export` → `export-3d`
