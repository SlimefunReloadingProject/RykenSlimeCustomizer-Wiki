# 实体生成类道具

此处会介绍如何编写脚本来使多个物品生成对应的生物。


此处引用魔法附属的道具示例
```js
// 可使多个物品共用一个脚本，并触发不同的效果（例如：生成不同生物）
// 定义一个常量数组，存储所有可召唤的实体配置
const ENTITY_TYPES = [
  { id: "MAGIC_EGG_BEE", type: Java.type('org.bukkit.entity.EntityType').BEE },
  { id: "MAGIC_PIG_1", type: Java.type('org.bukkit.entity.EntityType').PIG }, 
  { id: "MAGIC_SHEEP_1", type: Java.type('org.bukkit.entity.EntityType').SHEEP },
  { id: "MAGIC_CHICKEN_1", type: Java.type('org.bukkit.entity.EntityType').CHICKEN }, 
  { id: "MAGIC_COW_1", type: Java.type('org.bukkit.entity.EntityType').COW }, 
  { id: "MAGIC_OCELOT_1", type: Java.type('org.bukkit.entity.EntityType').OCELOT }, 
  { id: "MAGIC_CAT_1", type: Java.type('org.bukkit.entity.EntityType').CAT },
  { id: "MAGIC_DONKEY_1", type: Java.type('org.bukkit.entity.EntityType').DONKEY }, 
  { id: "MAGIC_FOX_1", type: Java.type('org.bukkit.entity.EntityType').FOX }, 
  { id: "MAGIC_FROG_1", type: Java.type('org.bukkit.entity.EntityType').FROG }, 
  { id: "MAGIC_GOAT_1", type: Java.type('org.bukkit.entity.EntityType').GOAT }, 
  { id: "MAGIC_HOGLIN_1", type: Java.type('org.bukkit.entity.EntityType').HOGLIN }, 
  { id: "MAGIC_HORSE_1", type: Java.type('org.bukkit.entity.EntityType').HORSE }, 
  { id: "MAGIC_LLAMA_1", type: Java.type('org.bukkit.entity.EntityType').LLAMA }, 
  { id: "MAGIC_TRADER_LLAMA_1", type: Java.type('org.bukkit.entity.EntityType').TRADER_LLAMA }, 
  { id: "MAGIC_MOOSHROOM_1", type: Java.type('org.bukkit.entity.EntityType').MUSHROOM_COW }, 
  { id: "MAGIC_MULE_1", type: Java.type('org.bukkit.entity.EntityType').MULE }, 
  { id: "MAGIC_PANDA_1", type: Java.type('org.bukkit.entity.EntityType').PANDA }, 
  { id: "MAGIC_RABBIT_1", type: Java.type('org.bukkit.entity.EntityType').RABBIT }, 
  { id: "MAGIC_STRIDER_1", type: Java.type('org.bukkit.entity.EntityType').STRIDER }, 
  { id: "MAGIC_TURTLE_1", type: Java.type('org.bukkit.entity.EntityType').TURTLE }, 
  { id: "MAGIC_WOLF_1", type: Java.type('org.bukkit.entity.EntityType').WOLF } 
];

// 当玩家使用物品时触发的函数
function onUse(event) {
  // 获取玩家对象
  let player = event.getPlayer();

  // 检查玩家是否使用的是主手物品
  if (event.getHand() !== org.bukkit.inventory.EquipmentSlot.HAND) {
    // 如果不是主手，提示玩家
    player.sendMessage("主手请持物品");
    return; // 结束函数
  }

  // 获取玩家使用的物品
  var onUseItem = event.getItem();

  // 获取物品对应的自定义物品配置（假设有一个函数getSfItemByItem用于获取自定义物品配置）
  var itemStack = getSfItemByItem(onUseItem);

  // 获取自定义物品的ID
  var sfitemid = itemStack.getId();

  // 在ENTITY_TYPES数组中查找与物品ID匹配的实体配置
  let entityConfig = ENTITY_TYPES.find(entity => entity.id === sfitemid);

  // 如果找到匹配的实体配置
  if (entityConfig) {
    // 获取对应的实体类型
    var entityTYPE = entityConfig.type;
  } else {
    // 如果没有找到匹配的实体配置，则直接返回，不执行后续操作
    return;
    // org.bukkit.Bukkit.broadcastMessage("未找到匹配的实体配置");
  }

  // 获取玩家使用的物品
  let item = event.getItem();

  // 减少物品的数量（使用一次后减少1）
  item.setAmount(item.getAmount() - 1);

  // 获取玩家目标方块（玩家朝向的方块）
  let block = player.getTargetBlock(null, 1);

  // 获取目标方块的位置，并在该位置上方生成实体
  let location = block.getLocation().add(0, 1, 0);

  // 获取世界对象
  let world = location.getWorld();

  // 在指定位置生成实体
  let entity = world.spawnEntity(location, entityTYPE);

  // 设置实体的年龄为-24000，使其成为幼年实体
  entity.setAge(-24000);
}
```
