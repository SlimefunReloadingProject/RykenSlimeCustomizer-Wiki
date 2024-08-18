# Listening

## Introduction
RSC offers a variety of listening events.  
For information on how to listen to events, see [Information](../addon/learn-to-write-addons-information.md).

<br>

In the listening script file, you can set to listen to the following events (see below for details).

| Event Name | Listening Event |
| ------- | -------- |
| EntityDeathEvent | Listen to the entity death event |
| EntityDamageByEntityEvent | Listen to the entity being attacked by an entity event |
| EntitySpawnEvent | Listen to the entity spawn event |
| EntityExplodeEvent | Listen to the entity explosion event |
| PlayerJoinEvent | Listen to the player joining the server event |
| PlayerQuitEvent | Listen to the player leaving the server event |
| PlayerDropItemEvent | Listen to the player dropping an item event |
| EntityPickupItemEvent | Listen to the entity picking up an item event |
| PlayerPickupArrowEvent | Listen to the player picking up an arrow event |
| EntityShootBowEvent | Listen to the entity shooting a bow event |
| EntityTeleportEvent | Listen to the entity teleportation event |
| PlayerTeleportEvent | Listen to the player teleportation event |
| PlayerDeathEvent | Listen to the player death event |
| SpawnerSpawnEvent | Listen to the mob spawner spawning mob event |
| ProjectileHitEvent | Listen to the projectile hitting an entity event |
| ProjectileLaunchEvent | Listen to the projectile launch event |
| PlayerItemConsumeEvent | Listen to the player using an item event |
| PlayerItemHeldEvent | Listen to the player changing the held item event |
| PlayerItemBreakEvent | Listen to the player's held item breaking event |
| PlayerAdvancementDoneEvent | Listen to the player achieving an advancement event |
| PlayerGameModeChangeEvent | Listen to the player's game mode change event |
| PlayerBedEnterEvent | Listen to the player getting into bed event |
| PlayerBedLeaveEvent | Listen to the player getting out of bed event |
| PlayerBucketEmptyEvent | Listen to the player using a bucket event |
| PlayerBucketFillEvent | Listen to the player filling a bucket event |
| PlayerChangedWorldEvent | Listen to the player changing worlds event |
| PlayerExpChangeEvent | Listen to the player's experience change event |
| PlayerLevelChangeEvent | Listen to the player's experience level change event |
| PlayerRespawnEvent | Listen to the player respawn event |
| PlayerInteractEntityEvent | Listen to the player interacting with an entity event |
| PlayerItemMendEvent | Listen to the player mending an item event |
| PlayerItemDamageEvent | Listen to the player's item damage event |
| PlayerToggleFlightEvent | Listen to the player toggling flight event |
| PlayerToggleSneakEvent | Listen to the player toggling sneaking event |
| PlayerToggleSprintEvent | Listen to the player toggling sprinting event |
| PlayerUnleashEntityEvent | Listen to the player unleashing an entity event |
| WeatherChangeEvent | Listen to the weather change event |
| ThunderChangeEvent | Listen to the thunder change event |
| BlockFormEvent | Listen to the block form change event |
| LightningStrikeEvent | Listen to the lightning strike event |
| BlockIgniteEvent | Listen to the block ignite event |
| BlockPlaceEvent | Listen to the block place event |
| BlockBreakEvent | Listen to the block break event |
| BlockDispenseEvent | Listen to the block dispense event |
| BlockBurnEvent | Listen to the block burn event |
| BlockExplodeEvent | Listen to the block explode event |
| BlockFadeEvent | Listen to the block fade event |
| BlockGrowEvent | Listen to the block grow event |
| LeavesDecayEvent | Listen to the leaves decay event |
| SignChangeEvent | Listen to the sign change event |
| NotePlayEvent | Listen to the note play event |
| CauldronLevelChangeEvent | Listen to the cauldron level change event |
| EnchantItemEvent | Listen to the enchant item event |
| BrewingStandFuelEvent | Listen to the brewing stand fuel change event |
| BlockPistonExtendEvent | Listen to the piston extend event |
| PlayerInteractEvent | Listen to the player interact event |
| PlayerFishEvent | Listen to the player fish event |
| PlayerHarvestBlockEvent | Listen to the player harvest block event |
| ArrowBodyCountChangeEvent | Listen to the arrow body count change event |
| EntityCombustEvent | Listen to the entity combust event |
| EntityPotionEffectEvent | Listen to the entity potion effect event |
| PlayerMoveEvent | Listen to the player move event |
| PlayerSwapHandItemsEvent | Listen to the player swap hand items event |

## Code Writing

In the listening file specified in `info.yml`,
you can write the following functions to listen to the corresponding events.
If there is an `EntityDeathEvent`, then its listening function name is `onEntityDeath`.

You can listen to multiple events in this specified file:

```js
/*EntityDeathEvent*/
function onEntityDeath(event) {

}
/*EntityDamageByEntityEvent*/
function onEntityDamageByEntity(event) {

}
```

## Event Details

```js
/*EntityDeathEvent*/
function onEntityDeath(event) {

}
```

| Input Parameter Name | Type                 |
| --- |----------------------|
| event | [EntityDeathEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDeathEvent.html) |

| Trigger Condition | Example |
| --- | --- |
| Triggered when an `Entity` dies. | Zombie death |

```js
/*EntityDamageByEntityEvent*/
function onEntityDamageByEntity(event) {

}
```

| Input Parameter Name | Type                                  |
| --- |---------------------------------------|
| event | [EntityDamageByEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageByEntityEvent.html) |

| Trigger Condition | Example |
| --- | --- |
| Triggered when an `Entity` is attacked by another `Entity`. | Player hit by an arrow |

```js
/*EntitySpawnEvent*/
function onEntitySpawn(event) {

}
```

```js
/*EntitySpawnEvent*/
function onEntitySpawn(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EntitySpawnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntitySpawnEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Entity` (entity) is generated|Spawn|

```js
/*EntityExplodeEvent*/
function onEntityExplode(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EntityExplodeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityExplodeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Entity` (entity) explodes|TNT explosion|

```js
/*PlayerJoinEvent*/
function onPlayerJoin(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerJoinEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerJoinEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) joins the server|Player joins|

```js
/*PlayerQuitEvent*/
function onPlayerQuit(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerQuitEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerQuitEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) quits the server|Player quits|

```js
/*PlayerDropItemEvent*/
function onPlayerDropItem(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerDropItemEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerDropItemEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) drops an item|Player drops an item|

```js
/*EntityPickupItemEvent*/
function onEntityPickupItem(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EntityPickupItemEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityPickupItemEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Entity` (entity) picks up `Item` (item)|Zombie picks up item|

```js
/*PlayerPickupArrowEvent*/
function onPlayerPickupArrow(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerPickupArrowEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerPickupArrowEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) picks up `Arrow` (arrow)|Player picks up arrow|

```js
/*EntityShootBowEvent*/
function onEntityShootBow(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EntityShootBowEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityShootBowEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) shoots an arrow|Player shoots an arrow|

```js
/*EntityTeleportEvent*/
function onEntityTeleport(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EntityTeleportEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityTeleportEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Entity` (entity) teleports|Player teleports|

```js
/*PlayerTeleportEvent*/
function onPlayerTeleport(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerTeleportEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerTeleportEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) teleports|Player teleports|

```js
/*PlayerDeathEvent*/
function onPlayerDeath(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerDeathEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/PlayerDeathEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) dies|Player death|

```js
/*SpawnerSpawnEvent*/
function onSpawnerSpawn(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[SpawnerSpawnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/SpawnerSpawnEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the spawner generates an `Entity` (entity)|The spawner generates creatures|

```js
/*ProjectileHitEvent*/
function onProjectileHit(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[ProjectileHitEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/ProjectileHitEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Projectile` (projectile) hits `Entity` (entity)|Arrow hits entity|

```js
/*ProjectileLaunchEvent*/
function onProjectileLaunch(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[ProjectileLaunchEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/ProjectileLaunchEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Projectile` (projectile) is fired|Arrow fired|

```js
/*PlayerItemConsumeEvent*/
function onPlayerItemConsume(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerItemConsumeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemConsumeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) finishes eating an item (food, potion, milk bucket). |Player eats food|

```js
/*PlayerItemHeldEvent*/
function onPlayerItemHeld(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerItemHeldEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemHeldEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) switches the held item. |Player switches holding items|

```js
/*PlayerItemBreakEvent*/
function onPlayerItemBreak(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerItemBreakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemBreakEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) destroys the holding item. |Iron Pickaxe Damage|

```js
/*PlayerAdvancementDoneEvent*/
function onPlayerAchievementDone(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerAdvancementDoneEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerAdvancementDoneEvent.html)|

|Trigger Condition|Example|
|---|---|
|Triggered when `Player` (player) completes an achievement. |Player completes an achievement|

```js
/*PlayerGameModeChangeEvent*/
function onPlayerGameModeChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerGameModeChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerGameModeChangeEvent.html)|

|Trigger Condition|Example|
|---|---|
|Triggered when `Player` switches game mode. |Player switches game mode|

```js
/*PlayerBedEnterEvent*/
function onPlayerBedEnter(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerBedEnterEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBedEnterEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` goes to bed. |Player goes to bed|

```js
/*PlayerBedLeaveEvent*/
function onPlayerBedLeave(event) {

}
```

| Input Parameter Name | Type                                                                                                             |
|----------------------|------------------------------------------------------------------------------------------------------------------|
| event                | [PlayerBedLeaveEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBedLeaveEvent.html) |

| Trigger condition                        | Example                |
|------------------------------------------|------------------------|
| Triggered when `Player` gets out of bed. | Player gets out of bed |

```js
/*PlayerBucketEmptyEvent*/
function onPlayerBucketEmpty(event) {

}
```

| Input Parameter Name | Type                                                                                                                   |
|----------------------|------------------------------------------------------------------------------------------------------------------------|
| event                | [PlayerBucketEmptyEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBucketEmptyEvent.html) |

| Trigger condition                                                      | Example                                                       |
|------------------------------------------------------------------------|---------------------------------------------------------------|
| Triggered when `Player` (player) causes `Bucket` (bucket) to be empty. | Player uses water bucket, lava bucket, fine snow, milk bucket |

```js
/*PlayerBucketFillEvent*/
function onPlayerBucketFill(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerBucketFillEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerBucketFillEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` causes `Bucket` to fill up. |Player uses buckets of water, lava, fine snow, milk|

```js
/*PlayerChangedWorldEvent*/
function onPlayerChangedWorld(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerChangedWorldEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerChangedWorldEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) switches worlds. |Player switches world|

```js
/*PlayerExpChangeEvent*/
function onPlayerExpChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerExpChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerExpChangeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) experience value changes. |Player experience value increases|

```js
/*PlayerLevelChangeEvent*/
function onPlayerLevelChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerLevelChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerLevelChangeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the `Player` (player) level changes. |Player experience level increase|

```js
/*PlayerRespawnEvent*/
function onPlayerRespawn(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerRespawnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerRespawnEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) respawns. |Player respawn|

```js
/*PlayerShearEntityEvent*/
function onPlayerShearEntity(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerShearEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerShearEntityEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) successfully uses shears on a creature | Player shears sheep's wool |

```js
/*PlayerInteractEntityEvent*/
function onPlayerInteractEntity(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerInteractEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerInteractEntityEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) right-clicks `Entity` (entity). |Player mends the iron golem|

```js
/*PlayerItemMendEvent*/
function onPlayerItemMend(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerItemMendEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemMendEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) repairs an item with the Mending enchantment. |The player repairs an item with the Mending enchantment|

```js
/*PlayerArmorStandManipulateEvent*/
function onPlayerArmorStandManipulate(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerArmorStandManipulateEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerArmorStandManipulateEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) interacts with `ArmorStand` (armor stand). |Player makes the armor stand hold an item|

```js
/*PlayerItemDamageEvent*/
function onPlayerItemDamage(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerItemDamageEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerItemDamageEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the durability of the item held by `Player` (player) decreases. |The player uses an iron pickaxe to mine a block|

```js
/*PlayerToggleFlightEvent*/
function onPlayerToggleFlight(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerToggleFlightEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerToggleFlightEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) switches to flying state. |Player switches flying state|

```js
/*PlayerToggleSneakEvent*/
function onPlayerToggleSneak(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerToggleSneakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerToggleSneakEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) switches sneaking state. |Player switches sneak state|

```js
/*PlayerToggleSprintEvent*/
function onPlayerToggleSprint(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerToggleSprintEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerToggleSprintEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) switches sprint state. |Player switches sprint state|

```js
/*PlayerUnleashEntityEvent*/
function onPlayerUnleashEntity(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerUnleashEntityEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerUnleashEntityEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when `Player` (player) unleashes the leash with `Entity` (entity). |Player unleashes the entity|

```js
/*WeatherChangeEvent*/
function onWeatherChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[WeatherChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/weather/WeatherChangeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the weather in a world changes. |Weather changes|

```js
/*ThunderChangeEvent*/
function onThunderChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[ThunderChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/weather/ThunderChangeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the lightning state of a world changes. |Lightning state changes|

```js
/*LightningStrikeEvent*/
function onLightningStrike(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[LightningStrikeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/weather/LightningStrikeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when lightning strikes a certain location. |Lightning strikes|

```js
/*BlockFormEvent*/
function onBlockForm(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockFormEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockFormEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a block changes due to world state or environmental factors. |Grass block spread|

```js
/*BlockIgniteEvent*/
function onBlockIgnite(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockIgniteEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockIgniteEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the block is ignited. |Player ignites leaves|

``js
/*BlockPlaceEvent*/
function onBlockPlace(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockPlaceEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockPlaceEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a block is placed. |Player places a block|

```js
/*BlockBreakEvent*/
function onBlockBreak(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockBreakEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBreakEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a block is destroyed. |Player destroys blocks|

```js
/*BlockDispenseEvent*/
function onBlockDispense(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockDispenseEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockDispenseEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when an item is thrown. |Throwing items from a dropper|

```js
/*BlockBurnEvent*/
function onBlockBurn(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockBurnEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockBurnEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the block is burned. |Leaves burned by fire|

```js
/*BlockExplodeEvent*/
function onBlockExplode(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockExplodeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockExplodeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a block explodes. |Blocks are destroyed by TNT|

```js
/*BlockFadeEvent*/
function onBlockFade(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockFadeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockFadeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a block fades, melts, or disappears, depending on world conditions|Snow melts. <br>Ice melts. <br>Fire burns for a while and then goes out without destroying blocks. <br>Coral becomes dead coral. <br>Eggs burst when turtles hatch|

```js
/*BlockGrowEvent*/
function onBlockGrow(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockGrowEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockGrowEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a block grows. |Crops grow, turtle eggs grow|

```js
/*LeavesDecayEvent*/
function onLeavesDecay(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[LeavesDecayEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/LeavesDecayEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when leaves fall. |Leaves fall|

```js
/*SignChangeEvent*/
function onSignChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[SignChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/SignChangeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the player changes `Sign` (sign). |The player changed the sign|

```js
/*NotePlayEvent*/
function onNotePlay(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[NotePlayEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/NotePlayEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when a note block is triggered. |Redstone trigger note block|

```js
/*CauldronLevelChangeEvent*/
function onCauldronLevelChange(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[CauldronLevelChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/CauldronLevelChangeEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the water level of the cauldron changes. |Cauldron water level changes|

```js
/*EnchantItemEvent*/
function onEnchantItem(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EnchantItemEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/enchantment/EnchantItemEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the player enchants an item. |Player enchanted items|

```js
/*BrewingStandFuelEvent*/
function onBrewingStandFuel(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BrewingStandFuelEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/inventory/BrewingStandFuelEvent.html)|

|Trigger condition|Example|
|Trigger when the fuel of the brewing stand is replenished|Fuel replenishment in the brewing stand|

```js
/*BlockPistonExtendEvent*/
function onBlockPistonExtend(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[BlockPistonExtendEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/BlockPistonExtendEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the block is pushed by a piston. |Block is pushed by piston|

```js
/*PlayerInteractEvent*/
function onPlayerInteract(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerInteractEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerInteractEvent.html)|

|Trigger condition|Example|
|Triggered when player interacts with air|Player right-clicks air while holding an item|

```js
/*PlayerFishEvent*/
function onPlayerFish(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerFishEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerFishEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the player fishes|Player fishing|

```js
/*PlayerHarvestBlockEvent*/
function onPlayerHarvestBlock(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerHarvestBlockEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerHarvestBlockEvent.html)|

| Trigger condition | Example |
|-----------------------------------------------------------|--------|
| Fired when the player harvests a block. <br>"Harvest" means a block drops an item (usually some kind of crop) and changes state, but is not damaged in order to drop the item. | Player harvests crop |

```js
/*ArrowBodyCountChangeEvent*/
function onArrowBodyCountChange(event) {

}
```

| Input Parameter Name | Type                                                                                                                         |
|------------|------------------------------------------------------------------------------------------------------------------------------|
| event      | [ArrowBodyCountChangeEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/ArrowBodyCountChangeEvent.html) |

| Trigger condition                                              | Example                                                |
|----------------------------------------------------------------|--------------------------------------------------------|
| Fired when an arrow enters or exists in the body of an entity. | When the arrow enters or exists the body of the entity |

```js
/*EntityCombustEvent*/
function onEntityCombust(event) {

}
```

| Input Parameter Name | Type                                                                                                           |
|----------------------|----------------------------------------------------------------------------------------------------------------|
| event                | [EntityCombustEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityCombustEvent.html) |

| Trigger condition               | Example                     |
|---------------------------------|-----------------------------|
| Triggered when an entity burns. | Zombies burn during the day |

```js
/*EntityPotionEffectEvent*/
function onEntityPotionEffect(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[EntityPotionEffectEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityPotionEffectEvent.html)|

|Trigger condition|Example|
|---|---|
|Called when the potion effect on the entity is modified. |Player gets potion effect|

```js
/*PlayerMoveEvent*/
function onPlayerMove(event) {

}
```

|Input Parameter Name|Type|
|---|---|
|event|[PlayerMoveEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerMoveEvent.html)|

|Trigger condition|Example|
|---|---|
|Triggered when the player moves. |Player movement|

```js
/*PlayerSwapHandItemsEvent*/
function onPlayerSwapHandItems(event) {}
```

| Input Parameter Name | Type                                                                                                                       |
|----------------|----------------------------------------------------------------------------------------------------------------------------|
| event          | [PlayerSwapHandItemsEvent](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/player/PlayerSwapHandItemsEvent.html) |

| Trigger condition                      | Example            |
|----------------------------------------|--------------------|
| Triggered when the player swaps items. | Player swaps items |