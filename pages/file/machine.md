# 无输入输出机器(machines.yml)

<b>注：</b>该配置自定义的机器无法自定义输入与输出的物品！（若要自定义含自定义输入和输出物品的机器，详见[ 配方机器 ](file/recipe_machines.md)）

**示例：**

```yaml
RSC_EXAMPLE_MACHINE:
  item_group: rsc_example_sub_group
  item:
    name: "&b示例机器"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM3
  input: [9, 10, 11, 12, 13, 14, 15, 16, 17]
  output: [31]
  script: "example_machine"
  work: 0
RSC_EXAMPLE_MACHINE_ENERGY:
  item_group: rsc_example_sub_group
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
      material: RSC_EXAMPLE_MACHINE
  input: []
  output: []
  script: "example_machine_energy"
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `RSC_EXAMPLE_MACHINE` | 机器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md) |
| script | 物品引用的脚本，设置物品对应的脚本文件，双引号内填脚本对应的文件名称。 |
| recipe | 设置机器的配方。详见[**配方**](format/recipe.md) |
| input | 物品输入的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| output | 物品输出的对应槽位。（请不要在菜单中为这些槽位设置物品！） |
| energy | 设置机器的能源，如果没有设置这个或者加载/读取失败则自动设置为无电机器 |
| energy.capacity | 设置机器可储存的能量，最大为 2147483647。 |
| energy.totalTicks | 设置每次输出物品的间隔时间，单位为粘液刻，最大为 2147483647。 |
| energy.type | 机器作为能源组件的类型，具体内容详见注意事项 |
| work | 设置无电机器的工作按钮槽位，如果没有此标签，则默认为-1（不设置）。 |

## 注意事项

1、如果您设置了脚本文件，那么当计算粘液刻时会调用`function tick(info)`，传参是[**MachineInfo**](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/MachineInfo.java)(无电机器是[**SmallerMachineInfo**](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/SmallerMachineInfo.java))

2、work为无电机器专属标签，如果设置了对应的脚本文件，你可以获取`working`对象(检查是否处于工作)，并且通过`setWorking(布尔值)`设置机器工作状态，若点击一次工作按钮则`working=true`

3、关于energy.type，所有可用项详见[**EnergyNetComponentType**](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/networks/energy/EnergyNetComponentType.html)

以下为EnergyNetComponentType汉化版

| 常数 | 描述 |
| --- | ----------- |
| CAPACITOR | 电容，用于储存能源网络的能量 |
| CONNECTOR | 连接器，用于传输能量 |
| CONSUMER | 用电器，从能源网络中消耗能量 |
| GENERATOR | 发电机，产生能量并输送的能源网络中 |
| NONE | 无，机器无法被分类为以上任何选项|

4、关于机器能源设置

如果**没有设置energy**或者**加载/读取失败**则自动设置为无电机器

## 其它

如果想自定义machine.yml里的机器菜单(menu），详见 [机器菜单](file/menu.md) 。
