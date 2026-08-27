# Flat V2

Flat is a minimal, terrain-only Iris pack for fast, level world generation. It contains one dimension, one region, one plains biome, and one constant-height generator.

## Generation contract

- `flat` uses `SUPERFLAT` mode, which runs only terrain and biome generation.
- The dimension uses the current standard build range of `-64..320` with a logical height of 384.
- `fluidHeight: 0` plus the biome's fixed generator offset of 3 places the grass surface at world Y 3.
- The surface is one grass block over two dirt blocks. The dimension rock palette fills everything below those layers.
- The same biome resolves land, sea, and shore selections, so every column has a valid biome.
- Native structure generation allows only the five `minecraft:village_*` variants. Every other Minecraft 26.2 structure family is denied through `importedStructures.disabled`; village placement, processors, entities, loot, and locate behavior remain native.
- Carving, mantle features, decoration, and post-processing are disabled explicitly.

## Install and validate

Install this entire tree as `flat` under the Iris packs root:

- Bukkit/Paper/Folia: `plugins/Iris/packs/flat/`
- Fabric/Forge/NeoForge: `config/irisworldgen/packs/flat/`

On Bukkit-family servers, validate with:

```text
/iris pack validate pack=flat
/iris pack status pack=flat
```

Create a disposable world with `/iris create name=flat_test type=flat seed=1337`.
