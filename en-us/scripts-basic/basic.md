# Script Basics

Here are all the methods/fields that can be used conveniently in the script

## [server](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Bukkit.html)

A field used to get the server instance

## isPluginLoaded

Example usage:

```js
let pluginLoaded = isPluginLoaded("DyeBench")
```

Check whether a plugin is loaded

## runOpCommand

Example usage:

```js
runOpCommand(player, "say %player%");
```

Let the player execute the op command

**%player%** is used to get the player's name
<br>In addition, RSC also supports variables of [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI)

## runConsoleCommand

Example usage:

```js
runConsoleCommand("say I'm free");
```

Execute commands in the background

**%player%** is used to get the player's name
<br>In addition, RSC also supports variables from [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI)

## sendMessage

Example usage:

```js
sendMessage(player, "{#114514>}A cool message{#191981<}");
```

Send a message to the player (supports CMI format)

## runLater

Example usage:

```js
runLater(runnable, delay);

runLater(() => expression, 20);
runLater(() => {
// statements
}, 20);
```

Execute the runnable code block after delay game ticks

## runRepeating

Example usage:

```js
runRepeating(runnable, delay, period);

runRepeating(() => expression, 20, 10);
runRepeating(() => {
// statements
}, 20, 10);
```

Execute the runnable code block every period game ticks after delay game ticks

## runAsync

Example usage:

```js

runAsync(runnable);

runAsync(() => expression);
runAsync(() => {
// statements
});
```

Asynchronously execute the runnable code block

## runLaterAsync

Example usage:

```js
runLaterAsync(runnable, delay);

runLaterAsync(() => expression, 20);
runLaterAsync(() => {
// statements
}, 20);
```

Execute the runnable code block every period game ticks after delay game ticks

## runAsync

Example usage:

```js
runLaterAsync(runnable, delay);

runLaterAsync(() => expression, 20);
runLaterAsync(() => {
// statements
}, 20);
``` 
Asynchronously execute the runnable code block after the game tick

## runRepeatingAsync

Example usage:

```js
runRepeatingAsync(runnable, delay, period);

runRepeatingAsync(() => expression, 20, 10);
runRepeatingAsync(() => {
// statements
}, 20, 10);
```

Asynchronously execute the runnable code block every period game ticks after delay game ticks

## getSfItemById

Example usage:

```js
let slimefunItem = getSfItemById("IRON_DUST");
```

Get the slime item by id and return a SlimefunItem

## getSfItemByItem

Example usage:

```js
let slimefunItem = getSfItemByItem(player.getInventory().getItemInMainHand());
```

Get slime items through ItemStack and return a SlimefunItem

## isItemSimilar

Example usage:

```js
let isItemMatch = isItemSimilar(itemStack, sfItem, checkLore);
```

Compare items, return true if they are the same, false if they are not the same

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|Item to compare|
|sfItem|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|Sample for comparison, usually slime item|
|checkLore|boolean|Whether to check item lore|

## isRadioactiveItem

Example usage:

```js
let radioactived = isRadioactiveItem(player.getInventory().getItemInMainHand());
```

Check whether it is a radioactive item

## isSoulbound

Example usage:

```js
let soulbound = isSoulbound(player.getInventory().getItemInMainHand());
```

Check if this item is a soulbound item

## canPlayerUseItem

Example usage:

```js
let usable = canPlayerUseItem(player, item, sendMessage);
```

Check if the player can use this item

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|Player|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|Target item|
|sendMessage|boolean|Send a message to the player if the player cannot use the item|

## setData

Example usage:

```js
setData(blockLocation, key, value)
```

Set data to the machine

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|blockLocation|[Location](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Location.html)|Block location|
|key|String|Key|
|value|String|Value|

## getData

Example usage:

```js
let value = getData(blockLocation, key)
```

Get data from the machine

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|blockLocation|[Location](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Location.html)|Block location|
|key|String|Key|

## randint（random number）

## randintA

Example usage:

```js
randintA(number);
randintA(10);
```

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|number|int|Integer|

Returns a random number from 0 to 9 (0,1,2,3,4,5,6,7,8,9)

## randintB

Example usage:

```js
randintB(number, includeSelf);
randintB(10, true);
```

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|number|int|Integer|
|includeSelf|boolean|Boolean|

If `includeSelf: true`, a random number from 0 to 10 is returned (0,1,2,3,4,5,6,7,8,9,10)
If `includeSelf: false`, a random number from 0 to 9 is returned (0,1,2,3,4,5,6,7,8,9)

## randintC

Example usage:

```js
randintC(start, stop);
randintC(2, 10);
```

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|start|int|Integer|
|stop|int|Integer|

Returns a random number from 2 to 9 (2,3,4,5,6,7,8,9)

## randintD

Example usage:

```js
randintD(start, stop, includeSelf);
randintD(2, 10, true);
```

Detailed parameter description:

|Parameter name|Type|Description|
|---|---|---|
|start|int|Integer|
|stop|int|Integer|
|includeSelf|boolean|Boolean value|

If `includeSelf: true`, return 2 to 10 =random number (2,3,4,5,6,7,8,9,10)
If `includeSelf: false`, then return a random number from 2 to 9 (2,3,4,5,6,7,8,9)

# PDC operation

RSC also provides [PDC method](https://github.com/Slimefun/dough/blob/main/dough-data/src/main/java/io/github/bakedlibs/dough/data/persistent/PersistentDataAPI.java) for operating the PDC of items

```js
let itemMeta = itemStack.getItemMeta();
let namespacedKey = new NamespacedKey("your_instance", "your_key");
PersistentDataAPI.setString(itemMeta, namespacedKey, "your_value");
PersistentDataAPI.getString(itemMeta, namespacedKey);
itemStack.setItemMeta(itemMeta);

```

# Slimefun methods

RSC automatically imports several classes from **Chinese version of Slimefun** in the script
<br>[SlimefunItems](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/implementation/SlimefunItems.html): contains all Slimefun items (including slime items in addons loaded before RSC)
<br>[SlimefunItem](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/api/items/SlimefunItem.html) : Slimefun item construction method
<br>[BlockStorage](https://slimefun.github.io/javadocs/Slimefun4/docs/me/mrCookieSlime/Slimefun/api/BlockStorage.html) : Used to access cached Slimefun block storage data
<br>[SlimefunUtils](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/utils/SlimefunUtils.html): Contains some utility methods for slime

Usage (example):

```js
SlimefunItems.ADVANCED_CIRCUIT_BOARD;
new SlimefunItem(itemGroup,slimefunItemStack,recipeType,recipe);
BlockStorage.hasBlockInfo(location);
SlimefunUtils.canPlayerUseItem(player,itemStack, isSendMessage);
```

Click the link above to view more methods

# NBTAPI method

## NBTAPI plugin needs to be installed!

Example usage:

```js
NBTAPI.readItem(item)
NBTAPI.getOrCreateCompound(parent, name)
NBTAPI.readBlock(block)
NBTAPI.readEntity(entity)
```

Detailed parameter description:

| Parameter name | Type                                                                                      | Description  |
|----------------|-------------------------------------------------------------------------------------------|--------------|
| itemStack      | [ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html) | Item         |
| parent         | NBTCompound                                                                               | NBT compound |
| name           | String                                                                                    | String       |
| block          | [Block](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Block.html)             | Block        |
| entity         | [Entity](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Entity.html)          | Entity       |