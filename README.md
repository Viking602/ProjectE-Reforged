# ProjectE Reforged

**EMC transmutation for Minecraft 26.1.2.**

Turn spare items into EMC, then use it to create the items you need. Includes transmutation tables, collectors, condensers, matter tools, and alchemical equipment.

**[Download the mod](https://github.com/Viking602/ProjectE-Reforged/releases/latest)** · [简体中文](README_zh.md) · [Report a bug](https://github.com/Viking602/ProjectE-Reforged/issues)

## Requirements

| Minecraft | Loader | Java |
| --- | --- | --- |
| 26.1.2 | NeoForge 26.1.2.114+ | 25 |

Use a NeoForge build for Minecraft 26.1.2.

## Install

1. Download `ProjectE-Reforged-26.1.2-1.1.0.jar`.
2. Put it in your instance's `mods` folder.
3. Start Minecraft. For multiplayer, install it on the server too.

Install one ProjectE implementation at a time. The `-sources.jar` is for development.

## Optional integrations

| Mod | Support |
| --- | --- |
| JEI | Recipes and item lookup |
| Curios | Accessory slots |
| Jade / The One Probe / WTHIT | EMC information |

Install the integrations you want separately. WTHIT also needs Bad Packets. CraftTweaker and EMI are not supported yet.

## Build from source

With JDK 25 installed:

```sh
bash ./gradlew build
```

On Windows, run `.\gradlew.bat build`. Artifacts are written to `build/libs/`.

[Porting notes](PORTING.md) cover API compatibility, EMC changes, and testing.

## Source and license

Based on [ProjectE](https://github.com/sinkillerj/ProjectE). Licensed under [MIT](LICENSE).

[Third-party notices](THIRD_PARTY_NOTICES.md)
