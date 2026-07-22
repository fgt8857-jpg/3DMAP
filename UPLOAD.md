# Upload first Release (no gh CLI required)

## 1. Push light files (LICENSE + README + index)

On GitHub: upload via Web, or:

```powershell
cd D:\MapWork\3DMAP
# if empty clone:
# git clone https://github.com/fgt8857-jpg/3DMAP.git .
Copy-Item D:\MapWork\3DMAP-scaffold\* . -Force
git add README.md LICENSE NOTICE.md map-pack-index.json
git commit -m "docs: MIT packaging license, NOTICE for game-derived data, index"
git push -u origin main
```

## 2. Create Release on GitHub Web

1. Open https://github.com/fgt8857-jpg/3DMAP/releases/new  
2. Tag: `v20260721.0` (match pack `contentVersion` when possible)  
3. Title: `ETS2 3D base 20260721.0`  
4. Attach files from TruckBridge machine:

```text
D:\AJN\truck-bridge\map-packs\staging\ets2-3d-base-20260721.0.zip
D:\AJN\truck-bridge\map-packs\staging\ets2-3d-base-20260721.0.zip.sha256
D:\MapWork\ets2-3d-raw\manifest.json
```

5. Publish release.

## 3. After next game update

```powershell
.\tools\map-pack-kit\publish-3d-from-game.ps1 -GamePath "<ETS2>" -Game ets2
# new zip → new tag → new Release → bump map-pack-index.json
```
