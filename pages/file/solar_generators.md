# 太阳能发电机(solar_generators.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义无GUI页面的发电机，上方不能有完整方块遮挡。

**示例：**

```yaml
RSC_EXAMPLE_SOLAR_GENERATOR:
  item_group: rsc_example_normal_group
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
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    3:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
    5:
      material_type: slimefun
      material: RSC_EXAMPLE_MACHINE
    7:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
    9:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
```
| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_SOLAR_GENERATOR` | 太阳能发电机的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| \*capacity | 太阳能发电机可储存的能量，最大为 2147483647，设置为0则是不可充电的机器 |
| \*dayEnergy | 太阳能发电机白天的发电量，单位为粘液刻，最大为 2147483647 |
| \*nightEnergy | 太阳能发电机夜晚的发电量，单位为粘液刻，最大为 2147483647 |
| \*lightLevel | 光照等级，机器所处的位置在未达到相应的光照等级时不会工作，最大为15 |
| recipe_type | 见[配方类型](file/recipe_type.md)。 |
| recipe | 设置太阳能发电机的配方。详见[**配方**](format/recipe.md) |
