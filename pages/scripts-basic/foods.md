# 脚本基础 - 食物

## onEat

当食物被吃掉时/药水或牛奶被喝完时触发

### 方法体

```js
function onEat(event, player, itemStack) {

}
```

### 示例

```js
function onEat(event, player, itemStack) { 
    var player = event.getPlayer();

    player.setFoodLevel(player.getFoodLevel() + 1);  //恢复饥饿值
    player.setSaturation(player.getSaturation() + 2); //恢复饱和度
    player.setExhaustion(player.getExhaustion() - 1);  //降低消耗度
}
```

### 入参

|字段|类型|描述|
|--|---|--|
|event|[PlayerItemConsumeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemConsumeEvent.html())|物品被消耗事件|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|消耗此物品的玩家|
|itemStack|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|被消耗的物品|

### 给予玩家药水效果

详见[LivingEntity#addPotionEffect(PotionEffect)](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/LivingEntity.html#addPotionEffect(org.bukkit.potion.PotionEffect))  
PotionEffect类文档：<https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffect.html>  
药水效果类型：<https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html>