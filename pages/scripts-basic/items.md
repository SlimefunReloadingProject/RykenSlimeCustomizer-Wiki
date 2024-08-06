# 脚本基础 - 物品

## onUse

当玩家右键该物品时触发

### 方法体

```js
function onUse(event) {

}
```

### 入参

|字段|类型|描述|
|--|---|--|
|event|[PlayerRightClickEvent](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/api/events/PlayerRightClickEvent.html)|玩家右键该物品事件|

## onWeaponHit

当玩家拿物品打怪时触发

### 方法体

```js
function onWeaponHit(event, player, item) {

}
```

### 入参

|字段|类型|描述|
|--|---|--|
|event|[EntityDamageByEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageByEntityEvent.html)|实体伤害另一实体事件|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|玩家|触发的玩家|
|item|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|用来攻击的物品|

## onToolUse

当玩家用物品挖方块时触发

### 方法体

```js
function onToolUse(event, item, fortune, drops) {

}
```

### 入参

|字段|类型|描述|
|--|---|--|
|event|[EntityDamageByEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageByEntityEvent.html)|实体伤害另一实体事件|
|item|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|用来攻击的物品|
|fortune|int|物品的时运附魔等级|
|drops|List<ItemStack>|方块掉落物|

## 技巧

你可以在方法被触发时使用`e.getPlayer().isSneaking()`来获取玩家是否蹲下
