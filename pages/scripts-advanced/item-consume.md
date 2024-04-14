# 道具

制作一个最基础的道具包含以下几步操作：  
1、玩家手持物品右键  
2、执行一段指令  
3、物品被消耗  

上述功能可以通过脚本实现，下文给出示例

```yaml
// 当物品被右键时
function onUse(event) {
    // 定义一个字符串变量sf，其值为一个特定的物品生成指令，此示例代码是用于给予一个生成铁傀儡的苦力怕刷怪蛋  
    var sf = "creeper_spawn_egg{EntityTag:{id:\"minecraft:iron_golem\"}}"; // 材质(此为苦力怕刷怪蛋)+生成蛋(此为生成铁傀儡)

    // 获取触发事件的玩家对象  
    var player = event.getPlayer();

    // 获取该玩家的背包对象  
    var inv = player.getInventory();

    // 获取玩家主手中的物品  
    var itemInMainHand = inv.getItemInMainHand();

    // 判断玩家主手中是否有物品，且该物品的数量大于0  
    if (itemInMainHand != null && itemInMainHand.getAmount() > 0) {
        // // 将转换数量设为玩家主手中物品的数量  
        // var amount = itemInMainHand.getAmount();  

        // 将转换数量设为一个
        var amount = 1;

        // 将玩家主手中的物品数量设置为已有物品数量-1个，即消耗了一个物品 
        itemInMainHand.setAmount(itemInMainHand.getAmount() - 1);

        // 运行op指令
        runOpCommand(player, "give " + player.getName() + " " + sf + " " + amount);
    }
}
```

这里执行的是/give creeper_spawn_egg{EntityTag:{id:"minecraft:iron_golem"}指令，

runOpCommand对应的是以op身份运行此段指令，括号内为指令内容。

请注意，如果指令中包含双引号，请将双引号替换成 **\"**