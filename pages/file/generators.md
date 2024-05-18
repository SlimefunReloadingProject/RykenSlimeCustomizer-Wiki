# 发电机(generators.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 必不可少的发电装置。

**示例：**

```yaml
RSC_EXAMPLE_GENERATOR:
  item_group: example_normal_group
  item:
    name: "&c示例发电机"
    material: GOLD_BLOCK
  capacity: 100000
  production: 100
  input: [10,11]
  output: [15,16]
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    3:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    5:
      material_type: slimefun
      material: RSC_EXAMPLE_MACHINE
    7:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    9:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
  fuels:
    example_fuel:
      item:
        material: OAK_WOOD
      seconds: 10
      output:
        material: CHARCOAL
```
| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`EXAMPLE_GENERATOR` | 发电机的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| \*capacity | 发电机可储存的能量，最大为 2147483647，设置为0则是不可充电的机器 |
| \*production | 发电机的发电量，单位为粘液刻，最大为 2147483647 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md) |
| recipe | 设置发电机的配方。详见[**配方**](format/recipe.md) |
| \*input | 物品输入的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| \*output | 物品输出的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| \*fuels | 设置发电机燃料。 |
| \*fuels.#.seconds | 此燃料的发电时间，单位为秒，最大为 2147483647。 |
| \*fuels.#.item | 所需燃料。 |
| \*fuels.#.output | 燃料发电完成后的输出产物。 |
