# 配方机器

> 含自定义输入输出的机器。

## 示例：

```yaml
EXAMPLE_RECIPE_MACHINE:
  item_group: example_normal_group
  item:
    name: "&e示例配方机器"
    material: "GREEN_STAINED_GLASS"
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: full_slimefun
      material: EXAMPLE_ITEM
    2:
      material_type: full_slimefun
      material: EXAMPLE_ITEM_2
  capacity: 1000
  input: [10,11]
  output: [15,16]
  energyPerCraft: 100
  speed: 2
  recipes:
    example:
      seconds: 10
      input:
        1:
          material_type: full_slimefun
          material: EXAMPLE_ITEM
        #可添加更多输入物品
      output:
        1:
          material_type: full_slimefun
          material: EXAMPLE_ITEM_2
    example_2:
      seconds: 5
	  chooseOne: true
      input:
        1:
          material_type: full_slimefun
          material: EXAMPLE_ITEM_2
        #可添加更多输入物品
      output:
        1:
          chance: 10
          material_type: full_slimefun
          material: EXAMPLE_MACHINE
        1:
          chance: 15
          material_type: full_slimefun
          material: EXAMPLE_ITEM
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_ITEM` | 机器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md)。 |
| recipe | 设置机器的配方。详见[**配方**](../format/recipe.md) |
| input | 物品输入的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| output | 物品输出的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| energyPerCraft | 机器每次成功产出物品消耗的电量。 |
| speed | 机器运行速度，最大为 2147483647，数值越大，机器运行的越快。 |
| capacity | 设置机器可储存的能量，最大为 2147483647。 |
| recipes.#.seconds | 合成所需时间，最大为 2147483647。 **实际合成时间(单位：粘液刻)：(秒数×2) / 机器运行速度** |
| recipes.#.chooseOne | 当随机出多个产物的时候从中选一个作为最终产物，详见注意事项。 |
| recipes.#.output.#.chance | 物品产出的概率，最大为100。 |

## 注意事项

1、当chooseOne为true时，用通俗点的话来说就是如果两个物品都中了奖，那么两个物品选一个产出。当chooseOne为false时，那就是如果两个物品都中了奖，那么两个物品同时产出

