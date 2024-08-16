# 监听

## 简单介绍
rsc 提供了丰富的监听事件，关于如何监听事件见[信息](file/info.md)
<br>
<br>
监听脚本文件中，你可以设置监听以下事件 (详见下文)
<br>

| 事件名称 | 监听事件 |
| ------- | -------- |
| EntityDeathEvent | 监听实体死亡事件 |
| EntityDamageByEntityEvent | 监听实体被实体攻击事件 |
| EntitySpawnEvent | 监听实体生成事件 |
| EntityExplodeEvent | 监听实体爆炸事件 |
| PlayerJoinEvent | 监听玩家加入服务器事件 |
| PlayerQuitEvent | 监听玩家退出服务器事件 |
| PlayerDropItemEvent | 监听玩家丢弃物品事件 |
| EntityPickupItemEvent | 监听实体拾取物品事件 |
| PlayerPickupArrowEvent | 监听玩家拾取箭头事件 |
| EntityShootBowEvent | 监听实体射箭事件 |
| EntityTeleportEvent | 监听实体传送事件 |
| PlayerTeleportEvent | 监听玩家传送事件 |
| PlayerDeathEvent | 监听玩家死亡事件 |
| SpawnerSpawnEvent | 监听刷怪笼生成生物事件 |
| ProjectileHitEvent | 监听投射物击中实体事件 |
| ProjectileLaunchEvent | 监听投射物射出事件 |
| PlayerItemConsumeEvent | 监听玩家使用物品事件 |
| PlayerItemHeldEvent | 监听玩家更改手持物品事件 |
| PlayerItemBreakEvent | 监听玩家手持物品损坏事件 |
| PlayerAdvancementDoneEvent | 监听玩家达成成就事件 |
| PlayerGameModeChangeEvent | 监听玩家游戏模式切换事件 |
| PlayerBedEnterEvent | 监听玩家上床事件 |
| PlayerBedLeaveEvent | 监听玩家下床事件 |
| PlayerBucketEmptyEvent | 监听玩家使用桶事件 |
| PlayerBucketFillEvent | 监听玩家装桶事件 |
| PlayerChangedWorldEvent | 监听玩家切换世界事件 |
| PlayerExpChangeEvent | 监听玩家经验值变化事件 |
| PlayerLevelChangeEvent | 监听玩家经验等级变化事件 |
| PlayerRespawnEvent | 监听玩家重生事件 |
| PlayerInteractEntityEvent | 监听玩家与实体交互事件 |
| PlayerItemMendEvent | 监听玩家修理物品事件 |
| PlayerItemDamageEvent | 监听玩家物品损坏事件 |
| PlayerToggleFlightEvent | 监听玩家飞行状态切换事件 |
| PlayerToggleSneakEvent | 监听玩家潜行状态切换事件 |
| PlayerToggleSprintEvent | 监听玩家疾跑状态切换事件 |
| PlayerUnleashEntityEvent | 监听玩家解除栓实体事件 |
| WeatherChangeEvent | 监听天气变化事件 |
| ThunderChangeEvent | 监听雷电变化事件 |
| BlockFormEvent | 监听方块形态变化事件 |
| LightningStrikeEvent | 监听雷电叽萝事件 |
| BlockIgniteEvent | 监听方块着火事件 |
| BlockPlaceEvent | 监听方块放置事件 |
| BlockBreakEvent | 监听方块破坏事件 |
| BlockDispenseEvent | 监听方块发射事件 |
| BlockBurnEvent | 监听方块燃烧事件 |
| BlockExplodeEvent | 监听方块爆炸事件 |
| BlockFadeEvent | 监听方块变化事件 |
| BlockGrowEvent | 监听方块生长事件 |
| LeavesDecayEvent | 监听树叶腐烂事件 |
| SignChangeEvent | 监听告示牌改变事件 |
| NotePlayEvent | 监听音符播放事件 |
| CauldronLevelChangeEvent | 监听炼药锅水位变化事件 |
| EnchantItemEvent | 监听附魔物品事件 |
| BrewingStandFuelEvent | 监听酿造台燃料变化事件 |
| BlockPistonExtendEvent | 监听活塞拉伸事件 |
| PlayerInteractEvent | 监听玩家交互事件 |
| PlayerFishEvent | 监听玩家钓鱼事件 |
| PlayerHarvestBlockEvent | 监听玩家收获方块事件 |
| ArrowBodyCountChangeEvent | 监听玩家受击的箭的数量变化事件 |
| EntityCombustEvent | 监听实体燃烧事件 |
| EntityPotionEffectEvent | 监听实体药水效果事件 |
| PlayerMoveEvent | 监听玩家移动事件 |
| PlayerSwapHandItemsEvent | 监听玩家交换手持物品事件 |

## 代码书写

在`info.yml`中指定的监听文件中可以写入以下函数以监听对应的事件
如果有一个 `EntityDeathEvent`， 那么他的监听函数名为`onEntityDeath`

你在这个指定的文件中可以监听多个事件：

```js
/*EntityDeathEvent*/
function onEntityDeath(event) {

}
/*EntityDamageByEntityEvent*/
function onEntityDamageByEntity(event) {

}
```

## Event 详解

```js
/*EntityDeathEvent*/
function onEntityDeath(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityDeathEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDeathEvent.html)|

|触发条件|示例|
|---|---|
|`Entity` ( 实体 ) 死亡时触发|僵尸死亡|

```js
/*EntityDamageByEntityEvent*/
function onEntityDamageByEntity(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityDamageByEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageByEntityEvent.html)|

|触发条件|示例|
|---|---|
|`Entity` ( 实体 ) 被 `Entity` ( 实体 ) 攻击时触发|玩家被箭射中|

```js
/*EntitySpawnEvent*/
function onEntitySpawn(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntitySpawnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntitySpawnEvent.html)|

|触发条件|示例|
|---|---|
|`Entity` ( 实体 ) 生成时触发|刷怪|

```js
/*EntityExplodeEvent*/
function onEntityExplode(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityExplodeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityExplodeEvent.html)|

|触发条件|示例|
|---|---|
|`Entity` ( 实体 ) 爆炸时触发|TNT爆炸|

```js
/*PlayerJoinEvent*/
function onPlayerJoin(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerJoinEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerJoinEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 加入服务器时触发|玩家加入|

```js
/*PlayerQuitEvent*/
function onPlayerQuit(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerQuitEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerQuitEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 退出服务器时触发|玩家退出|

```js
/*PlayerDropItemEvent*/
function onPlayerDropItem(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerDropItemEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerDropItemEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 丢弃物品时触发|玩家丢弃物品|

```js
/*EntityPickupItemEvent*/
function onEntityPickupItem(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityPickupItemEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityPickupItemEvent.html)|

|触发条件|示例|
|---|---|
|`Entity` ( 实体 ) 拾取 `Item` ( 物品 ) 时触发|僵尸拾取物品|

```js
/*PlayerPickupArrowEvent*/
function onPlayerPickupArrow(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerPickupArrowEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerPickupArrowEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 拾取 `Arrow` ( 箭 ) 时触发|玩家拾取箭|

```js
/*EntityShootBowEvent*/
function onEntityShootBow(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityShootBowEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityShootBowEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 射箭时触发|玩家射箭|

```js
/*EntityTeleportEvent*/
function onEntityTeleport(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityTeleportEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityTeleportEvent.html)|

|触发条件|示例|
|---|---|
|`Entity` ( 实体 ) 传送时触发|玩家传送|

```js
/*PlayerTeleportEvent*/
function onPlayerTeleport(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerTeleportEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerTeleportEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 传送时触发|玩家传送|

```js
/*PlayerDeathEvent*/
function onPlayerDeath(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerDeathEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/PlayerDeathEvent.html)|

|触发条件|示例|
|---|---|
|`Player` ( 玩家 ) 死亡时触发|玩家死亡|

```js
/*SpawnerSpawnEvent*/
function onSpawnerSpawn(event) {

}
```

|入参名称|类型|
|---|---|
|event|[SpawnerSpawnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/SpawnerSpawnEvent.html)|

|触发条件|示例|
|---|---|
|刷怪笼生成 `Entity` ( 实体 ) 时触发|刷怪笼生成生物|

```js
/*ProjectileHitEvent*/
function onProjectileHit(event) {

}
```

|入参名称|类型|
|---|---|
|event|[ProjectileHitEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/ProjectileHitEvent.html)|

|触发条件|示例|
|---|---|
|`Projectile` ( 投射物 ) 击中 `Entity` ( 实体 ) 时触发|箭击中实体|

```js
/*ProjectileLaunchEvent*/
function onProjectileLaunch(event) {

}
```

|入参名称|类型|
|---|---|
|event|[ProjectileLaunchEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/ProjectileLaunchEvent.html)|

|触发条件|示例|
|---|---|
|`Projectile` ( 投射物 ) 射出时触发|箭射出|

```js
/*PlayerItemConsumeEvent*/
function onPlayerItemConsume(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerItemConsumeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemConsumeEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 吃完一件物品（食物、药水、牛奶桶）时触发。|玩家吃食物|

```js
/*PlayerItemHeldEvent*/
function onPlayerItemHeld(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerItemHeldEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemHeldEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 切换手持物品时触发。|玩家切换手持物品|

```js
/*PlayerItemBreakEvent*/
function onPlayerItemBreak(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerItemBreakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemBreakEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 破坏手持物品时触发。|铁镐损坏|

```js
/*PlayerAdvancementDoneEvent*/
function onPlayerAchievementDone(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerAdvancementDoneEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerAdvancementDoneEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 完成成就时触发。|玩家完成成就|

```js
/*PlayerGameModeChangeEvent*/
function onPlayerGameModeChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerGameModeChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerGameModeChangeEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 切换游戏模式时触发。|玩家切换游戏模式|

```js
/*PlayerBedEnterEvent*/
function onPlayerBedEnter(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerBedEnterEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBedEnterEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 上床时触发。|玩家上床|

```js
/*PlayerBedLeaveEvent*/
function onPlayerBedLeave(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerBedLeaveEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBedLeaveEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 下床时触发。|玩家下床|

```js
/*PlayerBucketEmptyEvent*/
function onPlayerBucketEmpty(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerBucketEmptyEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBucketEmptyEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 导致了 `Bucket` ( 桶 ) 为空时触发。|玩家使用水桶、岩浆桶、细雪、喝奶桶|

```js
/*PlayerBucketFillEvent*/
function onPlayerBucketFill(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerBucketFillEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBucketFillEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 导致了 `Bucket` ( 桶 ) 填满时触发。|玩家使用桶装水、岩浆、细雪、牛奶|

```js
/*PlayerChangedWorldEvent*/
function onPlayerChangedWorld(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerChangedWorldEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerChangedWorldEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 切换世界时触发。|玩家切换世界|

```js
/*PlayerExpChangeEvent*/
function onPlayerExpChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerExpChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerExpChangeEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 经验值改变时触发。|玩家经验值增加|

```js
/*PlayerLevelChangeEvent*/
function onPlayerLevelChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerLevelChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerLevelChangeEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 等级改变时触发。|玩家经验等级提升|

```js
/*PlayerRespawnEvent*/
function onPlayerRespawn(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerRespawnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerRespawnEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 重生时触发。|玩家重生|

```js
/*PlayerShearEntityEvent*/
function onPlayerShearEntity(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerShearEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerShearEntityEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 成功对生物使用剪刀后触发 | 玩家剪羊的羊毛 |

```js
/*PlayerInteractEntityEvent*/
function onPlayerInteractEntity(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerInteractEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerInteractEntityEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 右键 `Entity` ( 实体 ) 时触发。|玩家给铁傀儡补血|

```js
/*PlayerItemMendEvent*/
function onPlayerItemMend(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerItemMendEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemMendEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 通过经验修补附魔修复物品时触发。|玩家通过经验修补附魔修复物品|

```js
/*PlayerArmorStandManipulateEvent*/
function onPlayerArmorStandManipulate(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerArmorStandManipulateEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerArmorStandManipulateEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 与 `ArmorStand` ( 盔甲架 ) 交互时触发。|玩家使盔甲架手持物品|

```js
/*PlayerItemDamageEvent*/
function onPlayerItemDamage(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerItemDamageEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemDamageEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 手持物品耐久值降低时触发。|玩家使用铁镐挖掘方块|

```js
/*PlayerToggleFlightEvent*/
function onPlayerToggleFlight(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerToggleFlightEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerToggleFlightEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 切换飞行状态时触发。|玩家切换飞行状态|

```js
/*PlayerToggleSneakEvent*/
function onPlayerToggleSneak(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerToggleSneakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerToggleSneakEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 切换潜行状态时触发。|玩家切换潜行状态|

```js
/*PlayerToggleSprintEvent*/
function onPlayerToggleSprint(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerToggleSprintEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerToggleSprintEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 切换疾跑状态时触发。|玩家切换疾跑状态|

```js
/*PlayerUnleashEntityEvent*/
function onPlayerUnleashEntity(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerUnleashEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerUnleashEntityEvent.html)|

|触发条件|示例|
|---|---|
|当`Player` ( 玩家 ) 解除与`Entity` ( 实体 ) 的栓绳时触发。|玩家解除与实体的栓绳|

```js
/*WeatherChangeEvent*/
function onWeatherChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[WeatherChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/weather/WeatherChangeEvent.html)|

|触发条件|示例|
|---|---|
|当某个世界的天气改变时触发。|天气变化|

```js
/*ThunderChangeEvent*/
function onThunderChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[ThunderChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/weather/ThunderChangeEvent.html)|

|触发条件|示例|
|---|---|
|当某个世界的闪电状态改变时触发。|闪电状态改变|

```js
/*LightningStrikeEvent*/
function onLightningStrike(event) {

}
```

|入参名称|类型|
|---|---|
|event|[LightningStrikeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/weather/LightningStrikeEvent.html)|

|触发条件|示例|
|---|---|
|当闪电击中某个位置时触发。|闪电击落|

```js
/*BlockFormEvent*/
function onBlockForm(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockFormEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockFormEvent.html)|

|触发条件|示例|
|---|---|
|当某个方块因世界状态或环境因素改变时触发。|草方块蔓延|

```js
/*BlockIgniteEvent*/
function onBlockIgnite(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockIgniteEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockIgniteEvent.html)|

|触发条件|示例|
|---|---|
|当方块被点燃时触发。|玩家点燃树叶|

```js
/*BlockPlaceEvent*/
function onBlockPlace(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockPlaceEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockPlaceEvent.html)|

|触发条件|示例|
|---|---|
|当方块被放置时触发。|玩家放置方块|

```js
/*BlockBreakEvent*/
function onBlockBreak(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockBreakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBreakEvent.html)|

|触发条件|示例|
|---|---|
|当方块被破坏时触发。|玩家破坏方块|

```js
/*BlockDispenseEvent*/
function onBlockDispense(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockDispenseEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockDispenseEvent.html)|

|触发条件|示例|
|---|---|
|当物品被投掷时触发。|投掷器投掷物品|

```js
/*BlockBurnEvent*/
function onBlockBurn(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockBurnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBurnEvent.html)|

|触发条件|示例|
|---|---|
|当方块被烧毁后触发。|树叶被火烧毁|

```js
/*BlockExplodeEvent*/
function onBlockExplode(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockExplodeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockExplodeEvent.html)|

|触发条件|示例|
|---|---|
|当方块爆炸时触发。|方块被TNT炸毁|

```js
/*BlockFadeEvent*/
function onBlockFade(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockFadeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockFadeEvent.html)|

|触发条件|示例|
|---|---|
|根据世界条件，当一个块褪色、融化或消失时触发|雪融化。<br>冰融化。<br>火燃烧一段时间后熄灭，并且没有破坏方块。<br>珊瑚变为死珊瑚。<br>海龟孵化时蛋爆裂|

```js
/*BlockGrowEvent*/
function onBlockGrow(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockGrowEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockGrowEvent.html)|

|触发条件|示例|
|---|---|
|当方块生长时触发。|作物生长，海龟蛋生长|

```js
/*LeavesDecayEvent*/
function onLeavesDecay(event) {

}
```

|入参名称|类型|
|---|---|
|event|[LeavesDecayEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/LeavesDecayEvent.html)|

|触发条件|示例|
|---|---|
|当树叶凋谢时触发。|树叶凋谢|

```js
/*SignChangeEvent*/
function onSignChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[SignChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/SignChangeEvent.html)|

|触发条件|示例| 
|---|---|
|当玩家改变了`Sign` ( 告示牌 ) 时触发。|玩家改变了告示牌|

```js
/*NotePlayEvent*/
function onNotePlay(event) {

}
```

|入参名称|类型|
|---|---|
|event|[NotePlayEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/NotePlayEvent.html)|

|触发条件|示例|
|---|---|
|当音符盒被触发时触发。|红石触发音符盒|

```js
/*CauldronLevelChangeEvent*/
function onCauldronLevelChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[CauldronLevelChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/CauldronLevelChangeEvent.html)|

|触发条件|示例|
|---|---|
|当炼药锅的水位改变时触发。|炼药锅水位改变|

```js
/*EnchantItemEvent*/
function onEnchantItem(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EnchantItemEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/enchantment/EnchantItemEvent.html)|

|触发条件|示例|
|---|---|
|当玩家附魔物品时触发。|玩家附魔物品|

```js
/*BrewingStandFuelEvent*/
function onBrewingStandFuel(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BrewingStandFuelEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/inventory/BrewingStandFuelEvent.html)|

|触发条件|示例|
|当酿造台的燃料被补充时触发|酿造台内燃料补充|

```js
/*BlockPistonExtendEvent*/
function onBlockPistonExtend(event) {

}
```

|入参名称|类型|
|---|---|
|event|[BlockPistonExtendEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockPistonExtendEvent.html)|

|触发条件|示例|
|---|---|
|当方块被活塞推动时触发。|方块被活塞推动|

```js
/*PlayerInteractEvent*/
function onPlayerInteract(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerInteractEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerInteractEvent.html)|

|触发条件|示例|
|当玩家和空气交互时触发|玩家手持物品右键空气|

```js
/*PlayerFishEvent*/
function onPlayerFish(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerFishEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerFishEvent.html)|

|触发条件|示例|
|---|---|
|当玩家钓鱼时触发|玩家钓鱼|

```js
/*PlayerHarvestBlockEvent*/
function onPlayerHarvestBlock(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerHarvestBlockEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerHarvestBlockEvent.html)|

|触发条件|示例|
|---|---|
|玩家收获方块时触发。<br>“收获”是指一个块掉落一个物品（通常是某种作物）并改变状态，但为了掉落物品而没有损坏。|玩家收获作物

```js
/*ArrowBodyCountChangeEvent*/
function onArrowBodyCountChange(event) {

}
```

|入参名称|类型|
|---|---|
|event|[ArrowBodyCountChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/ArrowBodyCountChangeEvent.html)|

|触发条件|示例|
|---|---|
|当箭头进入或存在实体的主体时触发。|当箭头进入或存在实体的主体时触发|

```js
/*EntityCombustEvent*/
function onEntityCombust(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityCombustEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityCombustEvent.html)|

|触发条件|示例|
|---|---|
|当实体燃烧时触发。|僵尸在白天燃烧|

```js
/*EntityPotionEffectEvent*/
function onEntityPotionEffect(event) {

}
```

|入参名称|类型|
|---|---|
|event|[EntityPotionEffectEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityPotionEffectEvent.html)|

|触发条件|示例|
|---|---|
|当实体上的药剂效果被修改时调用。|玩家获得药水效果|

```js
/*PlayerMoveEvent*/
function onPlayerMove(event) {

}
```

|入参名称|类型|
|---|---|
|event|[PlayerMoveEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerMoveEvent.html)|

|触发条件|示例|
|---|---|
|当玩家移动时触发。|玩家移动|

```js
/*PlayerSwapHandItemsEvent*/
function onPlayerSwapHandItems(event) {}
```

|入参名称|类型|
|---|---|
|event|[PlayerSwapHandItemsEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerSwapHandItemsEvent.html)|

|触发条件|示例|
|---|---|
|当玩家交换手持物品时触发。|玩家交换手持物品|
