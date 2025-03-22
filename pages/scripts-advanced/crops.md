# 自定义农作物

此篇会给出一个示例，用来自定义类似于美食家的农作物系统。

自定义的农作物支持小麦、马铃薯、胡萝卜、甜菜根、西瓜、南瓜、火把花、瓶子草、下界疣、浆果灌木、紫颂花、可可果等。

只要方块状态中含有age变量就可以作为农作物

此处引用尘世百味附属的作物示例

```js
const SlimefunItem = Java.type('io.github.thebusybiscuit.slimefun4.api.items.SlimefunItem');
const Material = Java.type('org.bukkit.Material');
const ItemStack = Java.type('org.bukkit.inventory.ItemStack');
const Ageable = Java.type('org.bukkit.block.data.Ageable');

// 创建存储结构
let lastUseTimes = new java.util.HashMap(); // 存储每个机器的最后使用时间
let machineTickCounters = new java.util.HashMap(); // 存储每个机器的独立计数器
let giftif = new java.util.HashMap(); // 存储植物成熟状态

// 配置参数
var SpawnEntitytick = 2; // 别动这个
var GrowTimems_INFINITE = 60000; // 作物生长周期，单位毫秒(会受粘液刻影响)
var steps = [1/3, 2/3, 1, 4/3, 5/3, 2, 7/3]; // 生长阶段，不同作物需要设置不同的生长状态，否则会报错，下文会详细讲
var smallSteps = [1/10, 1/6, 1/3, 1/2, 2/3, 5/6, 1, 7/6]; // 别动这个

// 生长阶段映射，此处WT_TEST_SEED为在machine.yml中自定义的作物种子ID
var growthStages = {
    "WT_TEST_SEED": {
        stages: smallSteps,
        material: Material.WHEAT,
        maxAge: 7
    }
};

// 主循环逻辑
function tick(info) {
    var machine = info.machine();
    var location = info.block().getLocation();
    var world = location.getWorld();
    var machinesf = machine.getId();
    var block = info.block();

    // 检查植物是否已经成熟，如果成熟则跳过处理
    if (giftif.get(location) === true) {
        return;
    }

    // 获取计数器，如果不存在则初始化为0
    let tickCounter = machineTickCounters.getOrDefault(location, 0);

    if (tickCounter < SpawnEntitytick) {
        machineTickCounters.put(location, tickCounter + 1);
        return;
    }

    const currentTime = new Date().getTime();

    // 初始化最后使用时间
    if (!lastUseTimes.containsKey(location)) {
        lastUseTimes.put(location, currentTime);
        return;
    }

    let lastUseTime = lastUseTimes.get(location);

    // 处理无尽植物生长逻辑
    if (machinesf === "WT_TEST_SEED") {
        handleGrowth(world, location, lastUseTime, currentTime, "WT_TEST_SEED");
    }
}

// 处理生长逻辑
function handleGrowth(world, location, lastUseTime, currentTime, plantId) {
    var config = growthStages[plantId];
    var block = world.getBlockAt(location);

    for (let i = 0; i < config.stages.length; i++) {
        let timeLimit = GrowTimems_INFINITE * config.stages[i];
        if (currentTime - lastUseTime < timeLimit) {
            if (i > 0) {
                setGrowthStage(block, config.material, config.maxAge * (i / config.stages.length));
            }
            return;
        }
    }

    // 成熟处理
    setGrowthStage(block, config.material, config.maxAge);
    giftif.put(location, true);

    // 移除相关记录，避免后续继续更新
    lastUseTimes.remove(location);
    machineTickCounters.remove(location);
}

// 设置方块生长阶段
function setGrowthStage(block, material, age) {
    block.setType(material);
    let blockState = block.getState();
    let blockData = blockState.getBlockData();

    if (blockData instanceof Ageable) {
        blockData.setAge(Math.floor(age));
        blockState.setBlockData(blockData);
        blockState.update(true);
    }
}

// 方块放置事件
function onPlace(event) {
    let location = event.getBlock().getLocation();
    lastUseTimes.remove(location);
    machineTickCounters.remove(location);
    giftif.put(location, false);
}

// 方块破坏事件
function onBreak(event, itemStack, drops) {
    let player = event.getPlayer();
    let location = event.getBlock().getLocation();
    let world = player.getWorld();

    // 清理记录
    lastUseTimes.remove(location);
    machineTickCounters.remove(location);

    if (giftif.get(location) === true) {
        handleHarvest(world, location);
    }

    giftif.put(location, false);
}

// 处理成熟植物掉落
function handleHarvest(world, location) {
    let sfItem = StorageCacheUtils.getSfItem(location);
    // 判断是否为对应的作物种子
    if (sfItem.getId() === "WT_TEST_SEED") {
        let dropItem = (itemId) => {
            let slimefunItem = getSfItemById(itemId);
            let itemStack = new ItemStack(slimefunItem.getItem().getType());
            itemStack.setItemMeta(slimefunItem.getItem().getItemMeta());
            world.dropItemNaturally(location, itemStack);
        };

        let Infinite_Yes_1 = Math.random(); //获取一个随机数，范围0-1
        if (Infinite_Yes_1 < 1) { // 若设置为1，则100%概率掉落下述物品
            dropItem("WT_ZONGYE");  // 掉落的作物，作物在items.yml中自定义
            dropItem("WT_TEST_SEED");  // 掉落的作物种子，作物种子在machine.yml中自定义
        }
    }
}
```

以下是常用农作物的作物生长阶段（需要严格按照此周期进行配置，否则会导致报错）：

- 草荚果：1/3, 2/3, 2/3, 2/3, 1, 1, 4/3
- 火把花：0, 0, 0, 0, 0, 0, 1/3
- 可可果：1/3或者0, 1/3, 1/3, 1/3, 1/3, 1/3, 2/3
- 甜菜根：1/3, 1/3, 1/3, 2/3, 2/3, 2/3, 1
- 西瓜/南瓜梗：1/3, 2/3, 1, 4/3, 5/3, 5/3, 2
- 下界疣：1/3, 1/3, 1/3, 2/3, 2/3, 2/3, 1
- 小麦/马铃薯/胡萝卜：1/3, 2/3, 1, 4/3, 5/3, 2, 7/3
- 紫颂花：1/3, 2/3, 1, 1, 4/3, 4/3, 5/3

上述脚本需要在items.yml和machine.yml文件中分别自定义作物和作物种子：

以下展示如何自定义作物种子，需要在machine.yml中编写(脚本在此处引用)：
```yaml
WT_TEST_SEED:
  item_group: ws_zhongzi
  item:
    name: "&f&l示例种子"
    material_type: skull_hash
    material: 6e7aaf0bfdce2fd034540a362205746ae1333d886da98e7acbdcb17047f9d044
    lore: 
      - ""
      - "&7需种植在耕地上"
      - "&6生长时间: &7约5分钟"
    glow: false
  recipe: 
    5:
      material_type: slimefun
      material: WT_QGDZZ
      amount: 1
  recipe_type: WUWEI_ZZJDY
  script: 农作物的js脚本名称
```
请勿添加有关电力能源的配置，否则，作物将需要通电才能生长

以下展示如何自定义作物，需要在items.yml中编写(其实就是正常编写一个物品)：
```yaml
WT_ZONGYE:
  item_group: ws_zuowu
  item:
    name: "&f&l粽叶"
    material_type: skull_hash
    material: efaf9ab70ad407148e2ae0b4af81ed817a0bf99ce6a087b69286ec6caa03a39d
  placeable: false
  script: 1
  recipe_type: WUWEI_SHOUHUOZUOWU
  recipe:
    5:
      material_type: slimefun
      material: WT_TEST_SEED
      amount: 1
```