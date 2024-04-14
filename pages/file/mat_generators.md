# 材料生成器

```yaml
EXAMPLE_MATERIAL_GENERATOR:
  item_group: example_sub_group
  item:
    name: "&c示例材料生成器"
    material: IRON_BLOCK
  capacity: 10000
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: EXAMPLE_ITEM
  output: [12]
  outputItem:
    material_type: slimefun
    material: EXAMPLE_ITEM
  tickRate: 5
  status: 4
  per: 10
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_MATERIAL_GENERATOR` | 材料生成器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| capacity | 机器可储存的能量，最大为 2147483647，设置为0则是不可充电的机器。 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md) |
| recipe | 设置材料发生器的配方。详见[**配方**](../format/recipe.md) |
| output | 物品输出的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| outputItem | 详见[通用物品格式] |
| tickRate | 每生成一次物品所需时间，最大为 2147483647。 |
| status | 设置显示信息的槽位。 |
| per | 每生成一次物品所耗的能量。 |








