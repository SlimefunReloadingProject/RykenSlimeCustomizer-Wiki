# 脚本基础
这里列出所有脚本中可以方便使用的方法/字段
## [server](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Bukkit.html)
类型：字段  
获取服务器实例

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
sendMessage(player, "<rainbow>A cool message</rainbow>");
```
向玩家发送消息(支持MiniMessage格式)

## getSfItemById
示例用法:
```js
let slimefunItem = getSfItemById("IRON_DUST");
```
通过id获取粘液物品
返回一个SlimefunItem

## getSfItemByItem
示例用法:
```js
let slimefunItem = getSfItemByItem(player.getInventory().getItemInMainHand());
```
通过ItemStack获取粘液物品
返回一个SlimefunItem

## isItemSimilar
示例用法:
```js
let isItemMatch = isItemSimilar(item, sfItem, checkLore);
```

详细入参说明:
|入参名称|类型|说明|
|---|---|---|
|item|ItemStack|要对比的物品1|
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
检测此物品是可以灵魂绑定

## canPlayerUseItem
示例用法:
```js
let usable = canPlayerUseItem(player, item, sendMessage);
```

详细入参说明:
|入参名称|类型|说明|
|---|---|---|
|player|Player|玩家|
|item|ItemStack|目标物品|
|sendMessage|boolean|如果玩家不能使用物品时向玩家发送消息|

## setData
示例用法:
```js
setData(blockLocation, key, value)
```

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

详细入参说明:
|入参名称|类型|说明|
|---|---|---|
|blockLocation|Location|方块位置|
|key|String|键|