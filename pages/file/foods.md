# 食物(foods.yml)

> 用于自定义食物/果汁(类似于粘液科技食物分类中的肉干和果汁，无法自定义类似于异域花园的食品)。

> 脚本-进阶中会详细介绍如何自定义类似于异域花园的食品

**示例：**

```yaml
RSC_EXAMPLE_FOOD:
  item_group: rsc_example_sub_group
  item:
    name: "食物 1"
    material: rotten_flesh
  script: "example_food"
  nutrition: 1
  saturation: 0
  eatseconds: 1.6
  always_eatable: false
  recipe_type: MAGIC_WORKBENCH
  recipe:
    1:
      material: birch_planks
      amount: 1
    2:
      material: birch_planks
      amount: 1
    3:
      material: dark_oak_planks
      amount: 1
RSC_EXAMPLE_JUICE:
  item_group: rsc_example_sub_group
  item:
    name: "果汁 1"
    material: POTION
    color: "0,255,0"
  script: "example_food" # 可沿用食物的脚本
  nutrition: 1
  saturation: 0
  eatseconds: 1.6
  always_eatable: false
  recipe_type: JUICER
  recipe:
    1:
      material: birch_planks
      amount: 1
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_ITEM` | 物品的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加`modelId`、`lore`、`glow`等 |
| recipe_type | 见[配方类型](file/recipe_type.md)。 |
| \*script | 物品引用的脚本，设置物品对应的脚本文件，双引号内填脚本对应的文件名称 |
| recipe | 设置物品的配方。详见[**配方**](format/recipe.md) |

## 高级自定义食物

> 以下参数版本需求 1.20.5+， 前置插件 NBTAPI

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| nutrition | 设置物品的饥饿值 | 1 ~ 2147483647 |
| saturation | 设置物品的饱和度 | 0.0 ~ 2147483647.0 |
| eatseconds | 设置物品的食用时间 | 0.0 ~ 2147483647.0 <br> 默认 1.6 |
| always_eatable | 设置物品是否总是可以食用 | true/false，默认false，true 可使在你饱食度满后仍然可以继续食用 |

关于食物的特性通过在foods.yml中引用脚本实现，详见[脚本-食物](scripts-basic/foods.md)
