# 物品

**示例：**

```yaml
EXAMPLE_ITEM:
  item_group: example_sub_group
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

## 设置

### ID\*

就跟上面的示例中`EXAMPLE_ITEM`, `EXAMPLE_ITEM_2`一样，这些代表了物品的id，/sf give时也会用到。

### item\_group\*

这是设置物品所在的物品组。这是必填项，而且只能引用附属内的物品组，不能引用其他的附属的物品组。

### item

设置粘液物品外表是什么样子，填写时**请使用通用物品格式编写物品。**

### recipe\_type

设置配方类型。

### recipe

设置物品配方。写法请参考[**配方**](../format/recipe.md)**。**

### script

编写脚本你需要一些编程基础。

这个是设置物品对应的脚本文件。当物品右键时会执行脚本文件里的内容。

```
function onUse(e) {
    
}
```

其中 e 代表 [**PlayerRightClickEvent(玩家右键事件)**](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/api/events/PlayerRightClickEvent.html) 。
