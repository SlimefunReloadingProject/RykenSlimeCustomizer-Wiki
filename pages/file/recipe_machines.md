# 配方机器(recipe_machines.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义含自定义输入输出的机器。

## 示例：

```yaml
RSC_EXAMPLE_RECIPE_MACHINE:
  item_group: rsc_example_normal_group
  item:
    name: "&e示例配方机器"
    material: GREEN_STAINED_GLASS
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    2:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
  capacity: 1000
  input: [10,11]
  output: [15,16]
  energyPerCraft: 100
  speed: 2
  hideAllRecipes: false
  recipes:
    example:
      chooseOne: true
      forDisplay: false
      hide: false
      seconds: 10
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
        #可添加更多输入物品
      output:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
    example_2:
      seconds: 5
      chooseOne: true
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
        #可添加更多输入物品
      output:
        1:
          chance: 10
          material_type: slimefun
          material: RSC_EXAMPLE_MACHINE
        2:
          chance: 15
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
    example_3:
      seconds: 5
      noConsume: true
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
          amount: 1
        # 此时输入物品不消耗
      output:
        1:
          chance: 10
          material_type: slimefun
          material: RSC_EXAMPLE_MACHINE
        2:
          chance: 15
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
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
| hideAllRecipes | 隐藏所有输入输出配方。 |
| \*speed | 机器运行速度，最大为 2147483647，数值越大，机器运行的越快。<br>即你不需要更改每个工作配方的seconds。更改此项即可 *升级机器* |
| \*capacity | 设置机器可储存的能量，最大为 2147483647。 |
| recipes.#.seconds | 合成所需时间，最大为 2147483647。 **实际合成时间(单位：粘液刻)：(秒数×2) / 机器运行速度** |
| recipes.#.noConsume | 当设置为true时，所有的输入物品在输出产物时将不再消耗。注意：amount不能为0 |
| recipes.#.chooseOne | 当随机出多个产物的时候从中选一个作为最终产物，详见注意事项。 |
| recipes.#.forDisplay | 仅供展示的配方，可以用于在配方中写关于机器的描述/使用方法等。类似于乱码科技。 |
| recipes.#.hide | 隐藏此输入输出配方。 |
| recipes.#.output.chance | 物品产出的概率。有效范围 1~100 |

## 注意事项

当`chooseOne: true`时
选择`output`的其中一个进行输出

当`chooseOne: false`时（默认）
输出当前配方组的每个`output`的物品
