# Script Basics - Machine

!> The script in here is completely unusable!

## onPlace

Triggered when a block is placed

### Method Body

```js
function onPlace(event) {

}
```

### Input Parameters

|Field|Type|Description|
|--|---|--|
|event|[BlockPlaceEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockPlaceEvent.html)|Block Placed Event|

## onBreak

Triggered when a block is destroyed

### Method Body

```js
function onBreak(event, itemStack, drops) {

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|event|[BlockPlaceEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBreakEvent.html)|Block destruction event|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|It seems to be the item form of the block or the item used to destroy the block|
|drops|[List](https://doc.qzxdp.cn/jdk/17/zh/api/java.base/java/util/List.html)<ItemStack\>|Drops|

## tick

Triggered when the slime is calculated

### Method body

```js
function tick(info) {

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|info|[SmallerMachineInfo](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/SmallerMachineInfo.java)(Non-powered machine) \| [MachineInfo]()(Energy machine) |Can get the current state of the machine and the instance of the machine, etc.|

## For non-powered machines

### working

This is a field used to mark whether the machine should work

### setWorking(b)

Set whether the machine is working

The input parameter `b` represents a Boolean value (true/false)