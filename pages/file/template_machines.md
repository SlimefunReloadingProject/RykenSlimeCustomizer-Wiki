# 模板机器(template_machines.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义需要插入对应模版产出对应物品的机器(类似于需要插入生物卡片/芯片的机器)。

## 示例：

```yaml
RSC_EXAMPLE_TEMPLATE_MACHINE:
  item_group: rsc_example_sub_group
  item:
    material: GOLD_BLOCK
    name: "&d&l示例模板机器"
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
    2:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
  consumption: 300
  capacity: 3000
  templateSlot: 2
  input: [2, 3, 4, 5, 6, 7, 8]
  output: [18, 19, 20, 21, 22, 23, 24, 25, 26]
  fasterIfMoreTemplates: true
  moreOutputIfMoreTemplates: true
  recipes:
    RSC_EXAMPLE_GEO_RESOURCE:
      item2machine:
        seconds: 5
        input:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM
        output:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_MACHINE
      item22item:
        seconds: 5
        input:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM_2
        output:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM
# 注意：以下示例仅适用于我的世界1.20.5以前的版本
# 此实例展示的是模版机器在不设置输入物品的情况下仅放置模版即可输出相应物品
    RSC_EXAMPLE_ITEM:
      2item:
        seconds: 1
        chooseOne: true
        forDisplay: false
        hide: false
        output:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM
            chance: 15

```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_TEMPLATE_MACHINE` | 机器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加`modelId`、`lore`、`glow`等。 |
| recipe_type | 见[配方类型](file/recipe_type.md)。 |
| recipe | 设置模板机器的合成配方。详见[**配方**](../format/recipe.md) |
| \*input | 物品输入的对应槽位。<br>**请不要在菜单中为这些槽位设置物品！** |
| \*output | 物品输出的对应槽位。<br>**请不要在菜单中为这些槽位设置物品！** |
| \*consumption | 模板机器每粘液刻消耗的电量。 |
| \*capacity | 设置模板机器可储存的能量，最大为 2147483647。 |
| \*templateSlot | 设置模版的槽位，此槽位必须是input槽位的其中一个 |
| \*recipes | 模板机器的自定义配方。 |
| \*recipes."sfid" | 在第一缩进中需要填写识别物的粘液id，识别物只能是粘液物品 |
| \*recipes."sfid".# | 在第二缩进中填写工作配方，同[配方机器](file/recipes_machines.md)，在模板槽的物品与第一缩进的粘液id相同时，便会进入此缩进进行工作配方的匹配 |
| fasterIfMoreTemplates | 存在多个模板在模板槽时，机器是否运行得更快，默认 false |
| moreOutputIfMoreTemplates | 存在多个模板在模板槽时，机器是否输出的物品更多，默认 false |

# 注意

此处同样可以使用配方机器中包含的 **hideAllRecipes，chooseOne，forDisplay，hide和chance**
