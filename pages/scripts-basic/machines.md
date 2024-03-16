# 脚本基础 - 机器
## onPlace
当方块被放置时触发
### 方法体
```js
function onPlace(e) {

}
```
### 入参
|字段|类型|描述|
|--|---|--|
|e|[BlockPlaceEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockPlaceEvent.html)|方块被放置事件|

## onBreak
当方块被破坏时触发
### 方法体
```js
function onBreak(e, is, drops) {

}
```
### 入参
|字段|类型|描述|
|--|---|--|
|e|[BlockPlaceEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBreakEvent.html)|方块被破坏事件|
|is|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|貌似是方块的物品形式|
|drops|[List](https://doc.qzxdp.cn/jdk/17/zh/api/java.base/java/util/List.html)<ItemStack\>|掉落物|

## tick
粘液计算刻的时候触发
### 方法体
```js
function tick(info) {

}
```
### 入参
|字段|类型|描述|
|--|---|--|
|info|[SmallerMachineInfo](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/SmallerMachineInfo.java)(无电机器) \| [MachineInfo]()(能源机器) |能获取机器当前状态和机器的实例等|