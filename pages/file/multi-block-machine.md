# 多方块机器

```yaml
EXAMPLE_MULTIBLOCK_MACHINE:
  item_group: example_normal_group
  item:
    name: "&b示例多方块机器"
    material: CRAFTING_TABLE
  recipe:
    #按照这个设置
    #1 2 3
    #4 5 6
    #7 8 9
    5:
      material: OAK_FENCE_GATE
    #不要漏发射器
    8:
      material: DISPENSER
  work: 5
  sound: ANCIENT_ALTAR_FINISH_SOUND
  recipes:
    example:
      input:
        1:
          material_type: slimefun
          material: EXAMPLE_ITEM
        2:
          material_type: slimefun
          material: EXAMPLE_MACHINE
      output:
        material_type: slimefun
        material: EXAMPLE_ITEM_2
    helmet:
      input:
        3:
          material_type: slimefun
          material: EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: EXAMPLE_HELMET
    chestplate:
      input:
        4:
          material_type: slimefun
          material: EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: EXAMPLE_CHESTPLATE
    leggings:
      input:
        5:
          material_type: slimefun
          material: EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: EXAMPLE_LEGGINGS
    boots:
      input:
        6:
          material_type: slimefun
          material: EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: EXAMPLE_BOOTS
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_ITEM` | 多方块机器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 多方块机器所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加`modelId`、`lore`、`glow`等。 |
| recipe | 设置多方块机器的搭建方式。详见[**配方**](format/recipe.md)，搭建一个多方块机器必须包含一个发射器。 |
| recipe.#.input | 合成输出物品的配方。 |
| recipe.#.output | 多方块机器输出的物品。 |
| work| 设置工作方块，即多方块机器合成一个物品需要右键的方块，填相应方块在recipe中的数字。 |
| sound | 右键工作方块并成功合成物品后发出的声音，详见 [声音](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/services/sounds/SoundEffect.html) 。 |


## 注意事项

多方块机器的recipe必须安排一个发射器。多方块机器搭建完成后会自动搜索工作方块的上下左右找到发射器。

## 如何编写一个只能用多方块机器制作的材料

首先，自定义一个[配方类型](file/recipe_type.md)，配方类型的名字为此台多方块机器的名字，可自行添加lore等内容

然后在items.yml中注册一个物品(详见[物品](file/items.md)，recipe_type填写自定义的配方类型id，在recipe中编写相应的配方(注意：在items文件里编写的配方只是为了展示，并不代表多方块机器真正拥有这个配方)

最后在multi-block-machine.yml编写一个多方块机器，input对应物品的配方（照抄你在items文件里编写的配方），output填你在items.yml文件里自定义的物品id
