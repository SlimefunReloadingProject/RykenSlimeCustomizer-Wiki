# 工作台(workbenches.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义任意合成栏大小的工作台(类似于无尽工作台)。

## 示例(此处简要的引用尘世百味的一个工作台作为示例)：

```yaml
WT_BWWYL:
  lateInit: false
  item_group: ws_jiqi
  item:
    name: '&6&l百味万用炉'
    material_type: skull_hash
    material: 2f5cffcc555c21e17a68f411ad5c19f089d36f42c9e04cd5c5ee6cd77439970e
  click: 34
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    '1':
      amount: 1
      material_type: slimefun
      material: WT_NAMITUDOU
  capacity: 36000
  energyPerCraft: 18000
  recipes:
    '1':
      seconds: 1
      input:
        '1':
          amount: 1
          material_type: slimefun
          material: WT_JIJUXIE
          slot: 0
          noConsume: true # 此时仅单个物品不消耗，其它输入物品正常消耗
        '2':
          amount: 1
          material_type: mc
          material: GOLD_NUGGET
          slot: 1
        '3':
          amount: 1
          material_type: mc
          material: GOLD_NUGGET
          slot: 2
      output:
        '1':
          amount: 1
          material_type: slimefun
          material: WT_KANGXING
          slot: 25
      chooseOne: false
      forDisplay: false
      hide: false
    '2':
      seconds: 1
      noConsume: true  # 此时所有的输入物品在输出产物时将不再消耗
      input:
        '1':
          amount: 1
          material_type: slimefun
          material: WT_JIJUXIE
          slot: 0
        '2':
          amount: 1
          material_type: mc
          material: APPLE
          slot: 1
      output:
        '1':
          amount: 1
          material_type: slimefun
          material: WT_KANGXING
          slot: 25
      chooseOne: false
      forDisplay: false
      hide: false
  input: [0, 1, 2, 3, 4, 5, 9, 10, 11, 12, 13, 14, 18, 19, 20, 21, 22, 23, 27, 28,
    29, 30, 31, 32, 36, 37, 38, 39, 40, 41, 45, 46, 47, 48, 49, 50]
  output: [25]

```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_RECIPE_MACHINE` | 机器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加`modelId`、`lore`、`glow`等。 |
| recipe_type | 见[配方类型](file/recipe_type.md)。 |
| recipe | 设置机器的配方。详见[**配方**](../format/recipe.md) |
| \*input | 物品输入的对应槽位。<br>**请不要在菜单中为这些槽位设置物品！** |
| \*output | 物品输出的对应槽位。<br>**请不要在菜单中为这些槽位设置物品！** |
| \*energyPerCraft | 机器每粘液刻消耗的电量。 |
| \*capacity | 设置机器可储存的能量，最大为 2147483647。 |
| \*click | 合成物品时，玩家需要点击的槽位，有效范围：0~53。 |
| hideAllRecipes | 隐藏所有输入输出配方。 |
| recipes.#.seconds | 合成所需时间，最大为 2147483647。 **实际合成时间(单位：粘液刻)：(秒数×2) / 机器运行速度** |
| recipes.#.chooseOne | 当随机出多个产物的时候从中选一个作为最终产物。 |
| recipes.#.forDisplay | 仅供展示的配方，可以用于在配方中写关于机器的描述/使用方法等。类似于乱码科技。 |
| recipes.#.hide | 隐藏此输入输出配方。 |
| recipes.#.noConsume | 当设置为true时，所有的输入物品在输出产物时将不再消耗。注意：amount不能为0 |
| recipes.#.input/output.slot | 输入/输出物品对应的槽位。有效范围：0~53。 |
| recipes.#.input.noConsume | 当设置为true时，仅单个相应槽位的物品不消耗，其它输入物品正常消耗。 |