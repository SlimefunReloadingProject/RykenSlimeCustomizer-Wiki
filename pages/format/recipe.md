# 配方

配方的格式跟SC大致相同，每一格代表一个物品(**写法参考通用物品格式**)。

格式：

```yaml
recipe:
  1: 
    material: cobblestone
  2:
    material_type: none
  3:
    material_type: slimefun
    material: REINFORCED_ALLOY_INGOT
  4:
    ...
  5:
    ...
  6:
    ...
  7:
    ...
  8:
    ...
  9:
    ...
```

如果有些格子不需要放入物品，这样写会更加快捷，如下述示例：

```yaml
recipe:
  1:
    ...
  3:
    ...
  5:
    ...
  7:
    ...
  9:
    ...
```

当然，如果这个物品是不可合成的，可以省略recipe（即不填）。

## 配方隐藏

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| hideAllRecipes | 隐藏机器所有的输入输出配方 | true/false |
| hide | 隐藏机器单个的输入输出配方 | true/false |

示例：

```yaml
RSC_EXAMPLE_RECIPE_MACHINE:
  item_group: rsc_example_normal_group
  item:
    name: "&e示例配方机器"
    material: GREEN_STAINED_GLASS
  recipe_type: ENHANCED_CRAFTING_TABLE
  hideAllRecipes: true #注意缩进
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
  recipes:
    example:
      seconds: 10
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
      output:
      hide: true #注意缩进
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
```

如上述所示，注意缩进！

适用于所有机器类、发电机配置

## 应用

详见 [**配置文件-物品**](file/items.md) 。
