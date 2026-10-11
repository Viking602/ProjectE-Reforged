# ProjectE Reforged · 等价交换·重铸

**适用于 Minecraft 26.1.2 的 EMC 等价交换模组。**

把多余物品转化为 EMC，再换成需要的物品。包含转换桌、能量收集器、能量凝聚器、物质工具和炼金装备。

**[下载模组](https://github.com/Viking602/ProjectE-Reforged/releases/latest)** · [English](README.md) · [反馈问题](https://github.com/Viking602/ProjectE-Reforged/issues)

## 运行要求

| Minecraft | 加载器 | Java |
| --- | --- | --- |
| 26.1.2 | NeoForge 26.1.2.114+ | 25 |

请选择对应 Minecraft 26.1.2 的 NeoForge。

## 安装

1. 下载 `ProjectE-Reforged-26.1.2-1.1.0.jar`。
2. 放入实例的 `mods` 文件夹。
3. 启动游戏。多人游戏的服务端也需要安装。

同一实例只安装一个 ProjectE 实现。`-sources.jar` 是开发用源码包。

## 可选集成

| 模组 | 功能 |
| --- | --- |
| JEI | 查看物品与配方 |
| Curios | 饰品槽位 |
| Jade / The One Probe / WTHIT | 显示 EMC 信息 |

按需单独安装。WTHIT 还需要 Bad Packets。暂不支持 CraftTweaker 和 EMI。

## 从源码编译

安装 JDK 25 后运行：

```powershell
.\gradlew.bat build
```

Linux / macOS 使用 `bash ./gradlew build`。产物位于 `build/libs/`。

API 兼容、EMC 调整与测试说明见[移植说明](PORTING.md)。

## 上游与协议

基于 [ProjectE](https://github.com/sinkillerj/ProjectE)，采用 [MIT 协议](LICENSE)。

[第三方许可说明](THIRD_PARTY_NOTICES.md)
