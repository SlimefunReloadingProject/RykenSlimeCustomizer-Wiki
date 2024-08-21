# Script Basics - Items

## onUse

Triggered when the player right-clicks the item

### Method Body

```js
function onUse(event) {

}
```

### Input Parameters

|Field|Type|Description|
|--|---|--|
|event|[PlayerRightClickEvent](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/api/events/PlayerRightClickEvent.html)|Player right-clicks the item event|

## onWeaponHit

Triggered when the player uses the item to fight a monster
<mark>Require item is not placeable</mark>

### Method Body

```js
function onWeaponHit(event, player, item) {

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|event|[EntityDamageByEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageByEntityEvent.html)|Entity damages another entity event|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|Player|The player who triggered|
|item|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|The item used to attack|

## onToolUse

Triggered when the player uses an item to dig a block
<mark>Require item is not placeable</mark>

### Method body

```js
function onToolUse(event, item, fortune, drops) {

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|event|[BlockBreakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBreakEvent.html)|Block break event|
|item|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|The item used to attack|
|fortune|int|The level of fortune enchantment of the item|
|drops|List\<ItemStack\>|Block drops|

## Tips

You can use `e.getPlayer().isSneaking()` to get whether the player is crouching when the method is triggered