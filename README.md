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

[forge]: https://img.shields.io/badge/Minecraft%20Forge-v10.13.4.1614-brightgreen.svg "Minecraft Forge v10.13.4.1614"
[mc]: https://img.shields.io/badge/Minecraft-v1.7.10-brightgreen.svg "Minecraft 1.7.10"
[java]: https://img.shields.io/badge/Java%20JDK-v1.8-blue.svg "Java JDK 8"
[spigot]: https://img.shields.io/badge/Spigot-v1.7.10--R0.1--SNAPSHOT-orange.svg "Spigot 1.7.10-R0.1 Snapshot"
