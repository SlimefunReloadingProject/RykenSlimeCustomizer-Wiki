# 高级道具

此处会介绍如何编写高级道具，给予玩家药水效果并释放粒子效果。


此处引用尘世百味附属的道具示例
```js
function createPotionEffect(type, duration, amplifier, ambient = false) {
    return new org.bukkit.potion.PotionEffect(type, duration, amplifier, ambient);
}

function onUse(event) { 
    var player = event.getPlayer();
    var inv = player.getInventory();
    var itemInMainHand = inv.getItemInMainHand();
    var offHandItem = inv.getItemInOffHand();
    var location = player.getLocation();
    var x1 = location.getX();
    var y1 = location.getY();
    var z1 = location.getZ();
    
    // 检查副手是否持有打火石（可改为其它物品或去除）
    if (offHandItem == null || offHandItem.getType() != org.bukkit.Material.FLINT_AND_STEEL) {
        player.sendMessage("您必须使用主手点烟且副手持有打火石！");
        return;
    }

    // 判断玩家主手中是否有物品，且该物品的数量大于0  
    if (itemInMainHand != null && itemInMainHand.getAmount() > 0) {
        var amount = 1;
        // 将玩家主手中的物品数量设置为已有物品数量 - 1，即消耗了一个物品 
        itemInMainHand.setAmount(itemInMainHand.getAmount() - amount);
        offHandItem.setAmount(offHandItem.getAmount() - amount);
        inv.setItemInMainHand(itemInMainHand); // 更新主手物品

        // 添加药水效果，请务必注意我的世界1.20.4版本及之前的药水效果ID同1.20.5版本及之后的药水效果ID有很大差别
        player.addPotionEffect(createPotionEffect(org.bukkit.potion.PotionEffectType.ABSORPTION, 1400, 2));
        player.addPotionEffect(createPotionEffect(org.bukkit.potion.PotionEffectType.DOLPHINS_GRACE, 1400, 1));
        player.addPotionEffect(createPotionEffect(org.bukkit.potion.PotionEffectType.HUNGER, 800, 1));

      // 生成粒子效果，radius不宜超过3，否则会造成严重卡服
        const radius = 1;
        for (let x = -radius; x <= radius; x++) {
            for (let z = -radius; z <= radius; z++) {
                    player.getWorld().spawnParticle(org.bukkit.Particle.CAMPFIRE_COSY_SMOKE, new org.bukkit.Location(player.getWorld(), x1 + x, y1+1, z1 + z), 1);
            }
        }

        // 播放声音
        var soundName = "item.flintandsteel.use";
        player.getLocation().getWorld().playSound(player.getLocation(), soundName, 1.0, 1.0);
    }
}
```

1.20.4版本及之前的药水效果ID：https://jd.papermc.io/paper/1.20.4/org/bukkit/potion/PotionEffectType.html

1.20.5-1.20.6版本的药水效果ID：https://jd.papermc.io/paper/1.20.5/org/bukkit/potion/PotionEffectType.html

1.21版本的药水效果ID：https://jd.papermc.io/paper/1.21.1/org/bukkit/potion/PotionEffectType.html
