# 脚本基础

这里列出所有脚本中可以方便使用的方法/字段

## [server](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Bukkit.html)

一个字段，用于获取服务器实例

## isPluginLoaded

示例用法:

```js
let pluginLoaded = isPluginLoaded("DyeBench")
```

检查某个插件是否加载

## runOpCommand

示例用法:

```js
runOpCommand(player, "say %player%");
```

让玩家执行op指令

**%player%** 用于获取玩家的名字
<br>此外RSC还支持 [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI) 的变量

## runConsoleCommand

示例用法:

```js
runConsoleCommand("say 我自由了");
```

在后台执行指令

**%player%** 用于获取玩家的名字
<br>此外RSC还支持 [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI) 的变量

## sendMessage

示例用法:

```js
sendMessage(player, "{#114514>}A cool message{#191981<}");
```

向玩家发送消息(支持CMI格式)

## runLater

示例用法:

```js
runLater(runnable, delay);

runLater(() => expression, 20);
runLater(() => {
    // statements
}, 20);
```

在 delay 游戏刻后执行 runnable 代码块

## runRepeating

示例用法:

```js
runRepeating(runnable, delay, period);

runRepeating(() => expression, 20, 10);
runRepeating(() => {
    // statements
}, 20, 10);
```

在 delay 游戏刻后每隔 period 游戏刻执行 runnable 代码块

## runAsync

示例用法:

```js

runAsync(runnable);

runAsync(() => expression);
runAsync(() => {
    // statements
});
```

异步执行 runnable 代码块

## runLaterAsync

示例用法:

```js
runLaterAsync(runnable, delay);

runLaterAsync(() => expression, 20);
runLaterAsync(() => {
    // statements
}, 20);
```

在 delay 游戏刻后异步执行 runnable 代码块

## runRepeatingAsync

示例用法:

```js
runRepeatingAsync(runnable, delay, period);

runRepeatingAsync(() => expression, 20, 10);
runRepeatingAsync(() => {
    // statements
}, 20, 10);
```

在 delay 游戏刻后每隔 period 游戏刻异步执行 runnable 代码块

## getSfItemById

示例用法:

```js
let slimefunItem = getSfItemById("IRON_DUST");
```

通过id获取粘液物品，返回一个SlimefunItem

## getSfItemByItem

示例用法:

```js
let slimefunItem = getSfItemByItem(player.getInventory().getItemInMainHand());
```

通过ItemStack获取粘液物品，返回一个SlimefunItem

## isItemSimilar

示例用法:

```js
let isItemMatch = isItemSimilar(itemStack, sfItem, checkLore);
```

对比物品，相同返回true，不相同返回false  

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|要对比的物品|
|sfItem|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|对比样本，通常为粘液物品|
|checkLore|boolean|是否检查物品lore|

## isRadioactiveItem

示例用法:

```js
let radioactived = isRadioactiveItem(player.getInventory().getItemInMainHand());
```

检测是否为辐射物品

## isSoulbound

示例用法:

```js
let soulbound = isSoulbound(player.getInventory().getItemInMainHand());
```

检测此物品是否为灵魂绑定物品

## canPlayerUseItem

示例用法:

```js
let usable = canPlayerUseItem(player, item, sendMessage);
```

检测玩家是否可以使用此物品  

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|玩家|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|目标物品|
|sendMessage|boolean|如果玩家不能使用物品时向玩家发送消息|

## setData

示例用法:

```js
setData(blockLocation, key, value)
```

往机器设置数据  

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|blockLocation|[Location](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Location.html)|方块位置|
|key|String|键|
|value|String|值|

## getData

示例用法:

```js
let value = getData(blockLocation, key)
```

从机器获取数据  

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|blockLocation|[Location](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Location.html)|方块位置|
|key|String|键|

## randint（随机数）

## randintA

示例用法：

```js
randintA(number);
randintA(10);
```

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|number|int|整数|

返回 0~9 的随机数（0,1,2,3,4,5,6,7,8,9）

## randintB

示例用法：

```js
randintB(number, includeSelf);
randintB(10, true);
```

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|number|int|整数|
|includeSelf|boolean|布尔值|

如果`includeSelf: true`，则返回 0~10 的随机数（0,1,2,3,4,5,6,7,8,9,10）
如果`includeSelf: false`，则返回 0~9 的随机数（0,1,2,3,4,5,6,7,8,9）

## randintC

示例用法：

```js
randintC(start, stop);
randintC(2, 10);
```

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|start|int|整数|
|stop|int|整数|

返回 2~9 的随机数（2,3,4,5,6,7,8,9）

## randintD

示例用法：

```js
randintD(start, stop, includeSelf);
randintD(2, 10, true);
```

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|start|int|整数|
|stop|int|整数|
|includeSelf|boolean|布尔值|

如果`includeSelf: true`, 则返回 2~10 的随机数（2,3,4,5,6,7,8,9,10）
如果`includeSelf: false`, 则返回 2~9 的随机数（2,3,4,5,6,7,8,9）

# PDC 操作

RSC 还提供了 [PDC 方法](https://github.com/Slimefun/dough/blob/main/dough-data/src/main/java/io/github/bakedlibs/dough/data/persistent/PersistentDataAPI.java)，用于操作物品的 PDC

```js
let itemMeta = itemStack.getItemMeta();
let namespacedKey = new NamespacedKey("your_instance", "your_key");
PersistentDataAPI.setString(itemMeta, namespacedKey, "your_value");
PersistentDataAPI.getString(itemMeta, namespacedKey);
itemStack.setItemMeta(itemMeta);

```

# 汉化版 Slimefun 方法

RSC 在脚本中自动引入了来自**汉化版Slimefun**中的几个类
<br>[SlimefunItems](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/implementation/SlimefunItems.html) : 包含了所有粘液物品（包括在RSC前加载的附属中的粘液物品）
<br>[SlimefunItem](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/api/items/SlimefunItem.html) : 粘液物品的构造方法
<br>[StorageCacheUtils](https://github.com/SlimefunGuguProject/Slimefun4/blob/master/src/main/java/com/xzavier0722/mc/plugin/slimefun4/storage/util/StorageCacheUtils.java) : 用于访问缓存的粘液方块数据
<br>[SlimefunUtils](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/utils/SlimefunUtils.html) : 包含了粘液的一些工具类方法

使用方法（示例）：

```js
SlimefunItems.ADVANCED_CIRCUIT_BOARD;
new SlimefunItem(itemGroup, slimefunItemStack, recipeType, recipe);
StorageCacheUtils.hasBlock(location);
SlimefunUtils.canPlayerUseItem(player, itemStack, isSendMessage);
```

更多方法请点击链接查看

# NBTAPI 方法

## ! 需安装 NBTAPI 插件 !

示例用法：

```js
NBTAPI.readItem(item)
NBTAPI.getOrCreateCompound(parent, name)
NBTAPI.readBlock(block)
NBTAPI.readEntity(entity)
```

详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|物品|
|parent|NBTCompound|NBT复合|
|name|String|字符串|
|block|[Block](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Block.html)|方块|
|entity|[Entity](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Entity.html)|实体|
