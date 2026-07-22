# NOTICE — Game-derived map data

## SCS Software

**Euro Truck Simulator 2**, **American Truck Simulator**, and all related game
assets, map data, trademarks, and branding are the property of **SCS Software**.

This repository is an **unofficial**, community-oriented distribution of
**derived map-pack files** (e.g. road network / city point GeoJSON exported via
open tooling such as ts-map class parsers) for use with **TruckBridge** and
similar fan tools.

- This is **not** affiliated with, endorsed by, or sponsored by SCS Software.
- Packs do **not** replace owning a legal copy of the game.
- Do **not** present pack contents as original SCS downloadable content (DLC).
- Redistributors should keep this NOTICE with the pack.

## What we license (MIT)

The MIT `LICENSE` in this repository covers materials we authored as
**packaging**, for example:

- This README and documentation text  
- `map-pack-index.json` structure and our URL catalog  
- `manifest.json` field layout as used by TruckBridge  
- Any scripts we publish here that only wrap export/upload  

## What we do **not** claim to own

- Geometry, names, or topology derived from the game install  
- SCS textures, models, audio, or binaries  
- Right to commercially re-sell game map data as a product  

**Use at your own risk.** Packs are provided **AS IS**. Respect SCS Terms of
Service and local law.

## Build provenance

Typical pipeline:

1. Legal game install on the builder’s machine  
2. `tb-tsmap-export export-3d` (or equivalent)  
3. Zip + sha256 → GitHub Release  

End users download Releases; they do not need the game **to open** the pack
files, but the data remains game-derived.
