# 脚本基础
这里列出所有脚本中可以方便使用的方法/字段

## [server](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Bukkit.html)
一个字段，用于获取服务器实例

## %player%

获取玩家的名字，也支持 PlaceholderAPI 的变量

## isPluginLoaded
示例用法:
```js
let pluginLoaded = isPluginLoaded("DyeBench")
```
检查某个插件是否加载

## runOpCommand
示例用法:
```js
runOpCommand(player, "say 我自由了");
```
让玩家执行op指令

## runConsoleCommand
示例用法:
```js
runConsoleCommand("say 我自由了");
```
在后台执行指令

## sendMessage
示例用法:
```js
sendMessage(player, "&rainbow&A cool message&r");
```
向玩家发送消息(支持MineDown格式)

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
|itemStack|ItemStack|要对比的物品|
|sfItem|ItemStack|对比样本，通常为粘液物品|
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
|player|Player|玩家|
|itemStack|ItemStack|目标物品|
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
|blockLocation|Location|方块位置|
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
|blockLocation|Location|方块位置|
|key|String|键|

## randint（随机数）

# randintA
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

# randintB
示例用法：
```js
randintB(number, self);
randintB(10, true);
```
详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|number|int|整数|
|self|boolean|布尔值|

如果第2个参数为 true，则返回 0~10 的随机数（0,1,2,3,4,5,6,7,8,9,10）
如果第3个参数为 false，则返回 0~9 的随机数（0,1,2,3,4,5,6,7,8,9）

# randintC
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

# randintD
示例用法：
```js
randintD(start, stop, self);
randintD(2, 10, true);
```
详细入参说明:

|入参名称|类型|说明|
|---|---|---|
|start|int|整数|
|stop|int|整数|
|self|boolean|布尔值|

如果第3个参数为 true, 则返回 2~10 的随机数（2,3,4,5,6,7,8,9,10）
如果第3个参数为 false, 则返回 2~9 的随机数（2,3,4,5,6,7,8,9）

# NBTAPI

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
|itemStack|ItemStack|物品|
|parent|NBTCompound|NBT复合|
|name|String|字符串|
|block|Block|方块|
|entity|Entity|实体|
