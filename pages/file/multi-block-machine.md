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
          material_type: full_slimefun
          material: EXAMPLE_ITEM
      output:
        material_type: full_slimefun
        material: EXAMPLE_ITEM_2
        
```

### item\_group,item,recipe\_type,recipe

详见[**物品**](broken-reference)

### **work**

设置右键后机器配方里的哪个方块让机器工作。

### sound

右键工作方块后合成成功发出的声音，id列表请去 [跳转](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/services/sounds/SoundEffect.html) 。

### recipes

设置机器配方

#### input

设置配方输入

#### output

设置配方输出

### 注意事项

必须要放一个发射器。设置后我们会自动搜索工作方块的上下左右找到发射器。



