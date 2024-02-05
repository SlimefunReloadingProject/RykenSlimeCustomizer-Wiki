# 多方块机器

```yaml
EXAMPLE_MULTIBLOCK_MACHINE:
  item_group: example_normal_group
  item:
    name: "&b示例多方块机器"
    material: CRAFTING_TABLE
  recipe:
    #按照这个设置
    #0 1 2
    #3 4 5
    #6 7 8
    4:
      material: OAK_FENCE_GATE
    #不要漏发射器
    8:
      material: DISPENSER
  work: 4
  sound: ANCIENT_ALTAR_FINISH_SOUND
  recipes:
    example:
      input:
        1:
          material_type: full_slimefun
          material: EXAMPLE_ITEM
      output:
        material_type: full_slimefun
        material: EXAMPLE_ITEM_2           
```

### item\_group,item,recipe\_type,recipe,material\_type,material

详见[**物品**](broken-reference)

### **work**

设置按照机器配方里的哪个方块工作。

### sound

右键工作方块后合成成功发出的声音，id列表请去 [跳转](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/services/sounds/SoundEffect.html) 。







