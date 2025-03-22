# 食物 进阶教程

此篇会给出一个示例，用来自定义类似于异域花园的食物系统。

此脚本可以让玩家在游戏中吃任何东西。

下文给出示例

```js
function onUse(event) { 
    var player = event.getPlayer();
    var inv = player.getInventory();
    var itemInMainHand = inv.getItemInMainHand();
    var offHandItem = inv.getItemInOffHand();
    
    // 判断玩家饥饿值是否大于等于20，如果是，则无法吃东西
    if (player.getFoodLevel() >= 20) {
        return;
    }
    // 防止玩家误食其它物品
    if (offHandItem != null && SlimefunItem.getByItem(offHandItem) != null) {
        player.sendMessage("您必须使用主手进食且副手不能有粘液物品！");
        return;
    }

    // 判断玩家主手中是否有物品，且该物品的数量大于0  
    if (itemInMainHand != null && itemInMainHand.getAmount() > 0) {
        var amount = 1;
        // 将玩家主手中的物品数量设置为已有物品数量 - 1，即消耗了一个物品 
        itemInMainHand.setAmount(itemInMainHand.getAmount() - amount);
        player.setFoodLevel(player.getFoodLevel() + 2); // 增加玩家饥饿值
        player.setSaturation(player.getSaturation() + 2); // 增加玩家饱和度
        player.setExhaustion(player.getExhaustion() - 0.2); // 减少玩家消耗值

        // 使用正确的声音名称
        var soundName = "entity.strider.eat"; //此处引用的是炽足兽吃东西的声音，如果是喝水的声音，则改为entity.generic.drink

        // 播放声音，确保音量和音调参数在0到1之间
        player.getLocation().getWorld().playSound(player.getLocation(), soundName, 1.0, 1.0);
    }
}
```

上述脚本需要在items.yml文件中引用：

```yaml
RSC_EXAMPLE_ITEM_2:
  item_group: rsc_example_normal_group
  item:
    name: "&a一个可以吃的下界合金锭"
    material: NETHERITE_INGOT
  recipe_type: ENHANCED_CRAFTING_TABLE  
  script: 对应脚本的文件名
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM

```