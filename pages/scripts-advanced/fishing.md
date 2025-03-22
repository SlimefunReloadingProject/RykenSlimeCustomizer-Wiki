# 自定义钓鱼

自定义钓鱼包含以下几种功能：使用特定鱼竿、鱼饵(鱼饵可以指定摆在玩家背包的特定槽位)，钓出特定物品


此处引用魔法附属的道具示例
```js
function onPlayerFish(event) {

    var caught = event.getCaught();
    var player = event.getPlayer();
    var hook = event.getHook();
    var State = event.getState()


    //获取双手itemstack
    var itemInOffHand = player.getInventory().getItem(17);; //鱼饵需要摆在玩家背包的第17个槽位，即玩家背包右上角的位置
    var itemInMainHand = player.getInventory().getItemInMainHand();
    var sfItem_Main = getSfItemByItem(itemInMainHand);
    var sfItem_Off = getSfItemByItem(itemInOffHand);


    // org.bukkit.Bukkit.broadcastMessage("caught:"+ caught);
    // org.bukkit.Bukkit.broadcastMessage("State:"+ State);

    if (caught !== null && sfItem_Main !== null && sfItem_Off !== null){

        var sfItem_Main_id = sfItem_Main.getId();
        var sfItem_Off_id = sfItem_Off.getId(); 
    
    // 使用特定鱼竿、特定鱼饵
    if (State == "CAUGHT_FISH" && sfItem_Main_id == "TEST_FISHING_ROD" && sfItem_Off_id == "TEST_YUER"){
           
        // //取消事件防止默认行为
        // event.setCancelled(true);
        //删除被捕获的实体
        let amount = 1;
        decreaseItemInWhichHand(itemInOffHand, amount);
        caught.remove();
        
        // 给予玩家粘液物品，此处填粘液ID
        const Slimefun = [
            "ADVANCED_CIRCUIT_BOARD",
            "ADVANCED_INDUSTRIAL_MINER",
            "ALUMINUM_BRASS_INGOT",
            "XP_COLLECTOR",
            "ZINC_DUST",
            "ZINC_INGOT",
        ];



        const selectedItem = Slimefun[Math.floor(Math.random() * Slimefun.length)];
        const slimefunItem = getSfItemById(selectedItem);

        if (slimefunItem == null) {
            return ;
        }

        const itemstack = new org.bukkit.inventory.ItemStack(slimefunItem.getItem().getType());
        itemstack.setItemMeta(slimefunItem.getItem().getItemMeta())
        itemstack.setAmount(1);

        var itemEntity = hook.getWorld().dropItem(hook.getLocation(), itemstack);
        
        // 设置物品不会被立即捡起（10 ticks = 0.5秒）
        itemEntity.setPickupDelay(2);
        
        // 将物品拉向玩家（可选增强效果）
        var playerLocation = player.getLocation().add(0, 1, 0);
        var itemLocation = itemEntity.getLocation();
        var direction = playerLocation.subtract(itemLocation.toVector()).toVector();
        itemEntity.setVelocity(direction.normalize().multiply(1.7));

        sendMessage(player, "§b恭喜你钓到了 " + itemstack.getItemMeta().getDisplayName() + " §b*1");
        
        //发送音效反馈
        player.playSound(player.getLocation(), "entity.experience_orb.pickup", 1.0, 1.0);
            return;
        }
    }



}
//减少物品
function decreaseItemInWhichHand(itemInWitch, amount){

    itemInWitch.setAmount(itemInWitch.getAmount() - amount);

}
```

此脚本需要放在info.yml文件里，以魔法附属的info.yml为示例:
```yaml
id: Magic
name: Magic
depends: []
pluginDepends: 
- Slimefun
scriptListener: 脚本名称  #此处填入js脚本名称
version: Release-0.1.0
authors: 
- magicsolo
repo: Yomicer/Magic_RSC
```

钓竿和鱼饵需要在items.yml文件中添加，此处无需添加脚本:

```yaml
TEST_FISHING_ROD:
  lateInit: false
  item_group: zhenghebao_info
  item:
    name: '&c&l鱼竿'
    lore:
    material_type: mc
    material: FISHING_ROD
    amount: 1
  placeable: true
  recipe_type: 'NULL'
TEST_YUER:
  lateInit: false
  item_group: zhenghebao_info
  item:
    name: '&c&l鱼饵'
    lore:
    material_type: mc
    material: SLIME_BALL
    amount: 1
  placeable: true
  recipe_type: 'NULL'
```