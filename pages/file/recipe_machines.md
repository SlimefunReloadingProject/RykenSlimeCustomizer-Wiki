# 配方机器

> 有自定义输入输出的机器。

<mark style="color:red;">**目前仍然不稳定，请不要尝试！**</mark>

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
        #添加更多输入物品。。。（但不要超过9个）
      output:
        1:
          material_type: full_slimefun
          material: EXAMPLE_ITEM_2
        2:
          material_type: full_slimefun
          material: EXAMPLE_GEO_RESOURCE
```

### item\_group,item,recipe\_type,recipe,material\_type,material

详见[**物品**](broken-reference)

### capacity

设置机器能储存多少能量。

### input/output (1次缩进)

设置机器在机器菜单里的位置，详见[ 机器菜单 ](menu.md)。

### energyPerCraft

机器运行时每次合成成功消耗的电量。

### speed

处理速度。

### seconds

合成所需秒数。

### recipes

设置机器的配方。

