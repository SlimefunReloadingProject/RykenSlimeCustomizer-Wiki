# 物品

**示例：**
```yaml
EXAMPLE_ITEM:
  item_group: example_sub_group
  placeable: false
  item:
    name: "&a示例物品"
    material: DIAMOND
    amount: 1
  recipe_type: ENHANCED_CRAFTING_TABLE  
  recipe:
    1:
      material: APPLE
      amount: 1
EXAMPLE_ITEM_2:
  item_group: example_normal_group
  placeable: false
  item:
    name: "&a示例物品2"
    material: NETHERITE_INGOT
    amount: 1
  recipe_type: ENHANCED_CRAFTING_TABLE  
  script: "example_item_2"
  recipe:
    1:
      material_type: slimefun
      material: EXAMPLE_ITEM
      amount: 1
```
| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_ITEM` | 物品的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](groups.md)的ID。 |
| item.# | [通用物品格式](../format/universal-item-format.md)| 可选择性添加modelId、lore、glow等 |
| placeable | 物品是否可放置。**不要让工具等本来就无法放置的物品可放置！** |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](recipe_type.md)。 |
| script | 物品引用的脚本，设置物品对应的脚本文件，双引号内填脚本对应的文件名称 |
| recipe | 设置物品的配方。详见[**配方**](../format/recipe.md) |

## 注意事项

关于item.#后的标签，本页仅以name、material、amount为示例，可以在amount后添加更多标签，详见[通用物品格式](../format/universal-item-format.md)

注意name与material为必填，如果不填material_type，则默认检测material为原版物品

### 关于本页引用的示例脚本example_item_2
详见[脚本基础-物品](../scripts-basic/items.md)
