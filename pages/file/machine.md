---
description: 粘液附属必不可少的东西
---

# 机器

**注：**该功能暂未出自定义输入输出！（~~需等到1.1版本~~  请到[ 配方机器 ](formula-machine.md)实现）

**示例：**

```yaml
EXAMPLE_MACHINE:
  item_group: example_sub_group
  item:
    name: "&b示例机器"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
     material_type: slimefun
     material: EXAMPLE_ITEM
  input: [9, 10, 11, 12, 13, 14, 15, 16, 17]
  output: [31]
  script: "example_machine"
  work: 0
EXAMPLE_MACHINE_ENERGY:
  item_group: example_sub_group
  item:
    name: "&b示例能源机器"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  energy:
    capacity: 100000
    totalTicks: 10
    type: NONE
  recipe:
    1:
     material_type: slimefun
     material: EXAMPLE_ITEM
  input: []
  output: []
  script: "example_machine_energy"
  work: 0
```

## 设置

### item\_group,item,recipe\_type,recipe

详见[**物品**](broken-reference)

### **input/output**

设置物品输入输出的位置（不要在菜单中给这些槽位设置物品！）

### script

设置对应脚本文件。当计算粘液刻时会调用`function tick(info)`，传参是[**MachineInfo**](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/MachineInfo.java)(无电机器是[**SmallerMachineInfo**](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/SmallerMachineInfo.java))

### work(无电机器专属)

设置无电机器的工作按钮槽位，默认为-1（不设置）。

如果设置了对应脚本文件，你可以获取`working`对象(检查是否处于工作)和使用`setWorking(布尔值)`(设置机器工作状态)，点击一次工作按钮则`working=true`

### energy

设置机器的能源设置，如果**没有设置这个**或者**加载/读取失败**会自动转为无电机器

#### capacity

设置机器能储存多少能量。

#### type

设置机器作为能源组件的类型。查看所有可用项详见[**EnergyNetComponentType**](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/networks/energy/EnergyNetComponentType.html)

#### totalTicks

设置机器每次完成任务的总粘液刻数。

### 其他

在machine.yml里的机器如果想写menu，详见 [机器菜单](menu.md) 。
