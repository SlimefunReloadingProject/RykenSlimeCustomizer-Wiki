# 太阳能发电机

```yaml
EXAMPLE_SOLAR_GENERATOR:
  item_group: example_normal_group
  item:
    name: "&c示例太阳能发电机"
    material: GOLD_BLOCK
    lore:
      - "&e白天发电量: 1000J/t"
      - "&b夜晚发电量: 100J/t"
  capacity: 100000
  dayEnergy: 1000
  nightEnergy: 100
  lightLevel: 14
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: full_slimefun
      material: EXAMPLE_ITEM
    3:
      material_type: full_slimefun
      material: EXAMPLE_ITEM_2
    5:
      material_type: full_slimefun
      material: EXAMPLE_MACHINE
    7:
      material_type: full_slimefun
      material: EXAMPLE_ITEM_2
    9:
      material_type: full_slimefun
      material: EXAMPLE_ITEM
```
| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_SOLAR_GENERATOR` | 太阳能发电机的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| capacity | 太阳能发电机可储存的能量，最大为 2147483647，设置为0则是不可充电的机器 |
| dayEnergy | 太阳能发电机白天的发电量，单位为粘液刻，最大为 2147483647 |
| nightEnergy | 太阳能发电机夜晚的发电量，单位为粘液刻，最大为 2147483647 |
| lightLevel | 光照等级，机器所处的位置在未达到相应的光照等级时不会工作，最大为15 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md)。 |
| recipe | 设置太阳能发电机的配方。详见[**配方**](../format/recipe.md) |
