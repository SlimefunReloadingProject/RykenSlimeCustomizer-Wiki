# Script Basics - Food

## onEat

Triggered when food is eaten

### Method Body

```js
function onEat(event, player, itemStack) {

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|event|[PlayerItemConsumeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemConsumeEvent.html())|Item consumption event|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|The player who consumed this item|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|The item consumed|

### Give the player a potion effect

See [LivingEntity#addPotionEffect(PotionEffect)](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/LivingEntity.html#addPotionEffect(org.bukkit.potion.PotionEffect)) for details
PotionEffect class documentation: <https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffect.html>
Potion effect type: <https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html>