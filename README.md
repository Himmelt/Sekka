# Quorra

![Minecraft Forge v10.13.4.1614][forge]
![Minecraft v1.7.10][mc]
![Java JDK v1.8][java]
![Spigot 1.7.10 Snapshot ][spigot]

## Build Requirements
* Java 8u101 JDK or higher
* `JAVA_HOME` defined on your OS

## Building Quorra
* Checkout project
  * You can use IDE or clone from console:
  `git clone https://github.com/Himmelt/Quorra.git`
* Setup
  * Manual:
  `git submodule update --init --recursive`
* Build
  * This process downloads minecraft and apply patches
  * If you have gradle integration in IDE - you can still use gui
  * Manual:
  `./gradlew setupCauldron jar`

All builds will be in `build/distributions`

## Updating sources
* Update sources
  * `git pull origin master`
* Re apply patches & build binaries
  * `./gradlew clean setupCauldron jar`

### 更新日志
```yaml
1.0.7
 - 移除 PlayerInteractEvent 中跳过OP的行为，即使OP，事件该取消的还是要取消
 - 解决 WorldEdit/Residence/CoreProtect 等插件在OP创造模式下左键会直接打掉方块的问题
1.0.6
 - 新增 JVM 启动参数 -Dconfig.charset 可设置 yml 配置文件所使用的字符集，默认 UTF-8
1.0.5
 - 更新 org.bukkit.configuration 包下代码到 1.12.2，并保留旧代码的方法和字段
 - 更新 依赖 org.yaml:snakeyaml:1.21，默认使用 UTF-8 编码
1.0.4
 - 修改 Entity 药水效果更新的执行逻辑，将效果移除放在药水更新的迭代遍历后面，以解决在迭代时触发药水事件，
   而在事件中修改了药水效果，导致迭代器移除药水效果时抛出异常而导致服务器直接崩溃。CustomNpcs Mod 和 某个插件一起运行时导致，原因未查明。
1.0.3
 - 修复命令事件检查机制，解决 worldedit-forge mod 的'//'开头的指令无法触发 CommandEvent 而无法执行的问题
1.0.2
 - 给 net.minecraft.world.World 添加 notify 和 update 两个 NMS 方法，以解决 worldedit 报错问题
1.0.1
 - 应用 Spigot-1.7.10-R0.1-SNAPSHOT [a329bc5536513e67420770f601880b1040de672b]
 - 添加 Spigot 新增的 EntitySpawnEvent/SpawnerSpawnEvent/PlayerItemDamageEvent
 - 解决部分依赖上述 Spigot 专有事件类的插件无法正常运行的问题
1.0.0
 - 继续 Contigo 最后一次提交 [f447164e09958f31fb3abafe992329c5218157a0]
```

[forge]: https://img.shields.io/badge/Minecraft%20Forge-v10.13.4.1614-brightgreen.svg "Minecraft Forge v10.13.4.1614"
[mc]: https://img.shields.io/badge/Minecraft-v1.7.10-brightgreen.svg "Minecraft 1.7.10"
[java]: https://img.shields.io/badge/Java%20JDK-v1.8-blue.svg "Java JDK 8"
[spigot]: https://img.shields.io/badge/Spigot-v1.7.10--R0.1--SNAPSHOT-orange.svg "Spigot 1.7.10-R0.1 Snapshot"
