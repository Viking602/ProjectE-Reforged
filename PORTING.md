# Porting notes

Target: Minecraft 26.1.2 · NeoForge 26.1.2.114 · Java 25.

Release: `26.1.2-1.1.0`

Based on [ProjectE](https://github.com/sinkillerj/ProjectE).

## API compatibility

The mod ID and resource namespace remain `projecte`. The Java API package remains `moze_intel.projecte`.

The port updates registration, equipment components, transactional item/fluid transfers, block entity persistence, recipe serializers, network codecs, and rendering. Inventory and EMC save keys are retained.

Upstream update notifications are disabled because those releases target another game version.

## Gameplay and EMC

- Klein Star fuel use and Repair Talisman repairs write changes back to inventory and Curios slots.
- Divining Rod modes stay within their tier's range. Mind Stones consume only the XP they can store.
- Ignition places fire beside the clicked block and retains campfire/TNT ignition.
- Fixed EMC seeds and custom conversions act as upper bounds. Crafting, cooking, stonecutting, and returned ingredients are checked for positive EMC loops.
- Returned repairable tools contribute no durability cost, since free repair could otherwise create EMC.
- Firework costs account for all three rockets produced by the recipe.
- With Mekanism and CakeStickLib installed together, coal/charcoal conversion uses a 1:1 ratio to avoid an amplification loop.

EMC values can decrease from upstream defaults. Free and fractional-value outputs may lose EMC while keeping their recipes. For example, Prefab dirt/grass stairs require fractional EMC under their conversion recipes and receive no positive integer EMC.

Custom overrides are validated too. Pregenerated maps receive item-recipe checks; regenerate them after changing chemical recipes to refresh the full graph.

## Integrations

JEI, Curios, Jade, The One Probe, and WTHIT use pinned compile-only dependencies from Modrinth. They are not bundled.

CraftTweaker and EMI integrations have not been ported. Mekanism chemical mapping requires a compatible Mekanism build.

## Build and test

Run `bash ./gradlew build` with JDK 25, or `.\gradlew.bat build` on Windows. The build compiles the mod and API and runs the unit suite. Dependencies come from public repositories.

The 103 unit tests cover graph mapping, custom conversions, normalized stacks, codecs, persisted data, integer EMC validation, and transactional transfers. GitHub Actions runs the same build in a clean environment.

The checked-in files under `src/datagen/generated` are the current resources. The old Java data generator is retained for reference and is excluded from the build.

`src/smoke` contains reference integration fixtures. Running them requires matching companion mods and a prepared test environment; they are excluded from the distributable and regular build.

Optional developer mirrors can be selected with `-PportLocalMaven=/path/to/mirror`.
