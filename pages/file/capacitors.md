# 电容(capacitors.yml)

```yaml
EXAMPLE_CAPACITOR:
  item_group: example_sub_group
  item:
    name: "&a示例电容"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  capacity: 10000
  recipe:
    1:
      material: APPLE
      amount: 1
    2:
      material_type: full_slimefun
      material: EXAMPLE_ITEM
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_CAPACITOR` | 电容的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md)。 |
| capacity | 电容可储存的能量，最大为 2147483647。 |
| recipe | 设置电容的配方。详见[**配方**](format/recipe.md) |