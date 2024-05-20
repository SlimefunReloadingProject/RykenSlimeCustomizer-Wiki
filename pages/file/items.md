# 物品(items.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

**示例：**

```yaml
RSC_EXAMPLE_ITEM:
  item_group: rsc_example_sub_group
  item:
    name: "&a示例物品"
    material: DIAMOND
  recipe_type: ENHANCED_CRAFTING_TABLE  
  recipe:
    1:
      material: APPLE
      amount: 1
RSC_EXAMPLE_ITEM_2:
  item_group: rsc_example_normal_group
  item:
    name: "&a示例物品2"
    material: NETHERITE_INGOT
  recipe_type: ENHANCED_CRAFTING_TABLE  
  script: example_script_item
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
RSC_EXAMPLE_ITEM_3:
  item_group: rsc_example_normal_group
  item:
    name: "&a示例物品3"
    material: GOLD_INGOT
  recipe_type: ENHANCED_CRAFTING_TABLE
  energy_capacity: 1000
  script: example_chargeable_item
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM2
RSC_SYNTHETIC_STONE:
  item_group: rsc_example_sub_group
  placeable: false
  item:
    name: "&7人造石头"
    material: STONE
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material: COBBLESTONE
    2:
      material: COBBLESTONE
    4:
      material_type: slimefun
      material: STONE_CHUNK
    5:    
      material_type: slimefun
      material: STONE_CHUNK
  vanilla: true
RSC_WITHER_PROOF_STONE:
  item_group: rsc_example_sub_group
  item:
    name: "&7&l防凋零石头"
    material: STONE
  anti_wither: true  
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material: COBBLESTONE
    2:
      material: COBBLESTONE
    3:
      material_type: slimefun
      material: MOD_PLATE_DUMMY # 来自匠魂，未安装此附属会自动转为石头
RSC_CHANGEABLE_DIRT:
  item_group: rsc_example_normal_group
  item:
    name: "&6&l可变泥土"
    material: DIRT
  piglin_trade_chance: 10
  drop_from: PODZOL
  drop_chance: 10
  drop_amount: 1
  rainbow: CUSTOM
  rainbow_materials:
    - DIRT      
    - GRASS_BLOCK
    - PODZOL  
RSC_HIDDEN_ITEM:
  item_group: rsc_example_normal_group
  item:
    name: "&6&l隐藏物品"
    material: BARRIER
  piglin_trade_chance: 10
  hidden: true
  radiation: VERY_DEADLY
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_ITEM` | 物品的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加`modelId`、`lore`、`glow`等 |
| placeable | 物品是否可放置。**不要让工具等本来就无法放置的物品可放置！** |
| recipe_type | 见[配方类型](file/recipe_type.md)。 |
| script | 物品引用的脚本，设置物品对应的脚本文件，双引号内填脚本对应的文件名称 |
| recipe | 设置物品的配方。详见[**配方**](format/recipe.md) |
| energy_capacity | 可充电物品的充电量，详见下文 |
| radiation | 辐射等级，详见下文 |
| rainbow | 彩虹方块，详见下文 |
| rainbow_materials | 自定义彩虹方块，详见下文 |
| anti_wither | 防凋灵，详见下文 |
| soulbound | 灵魂绑定，详见下文 |
| piglin_trade_chance | 猪灵交易物品，详见下文 |
| vanilla | 人造类物品，详见下文 |
| hidden | 隐藏物品，详见下文 |
| drop_from | 挖掘方块掉落，详见下文 |

### 可充电物品

```yaml
energy_capacity: <容量>
```

容量最大为 2147483647 。

*提示：仅通过添加energy_capacity的可充电物品是没有任何功能的，如果想让可充电物品拥有其它功能，需要搭配脚本使用*

### 辐射

```yaml
 radiation: <辐射等级>
```

辐射等级详见[辐射](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/attributes/Radioactivity.html)

### 彩虹方块与自定义彩虹方块

```yaml
 rainbow: <类型>
```

彩虹方块类型包括：

```yaml
GLASS_PANE（玻璃板）
GLASS（玻璃）
STAINED_GLASS（彩色玻璃）
STAINED_GLASS_PANE（彩色玻璃板）
WOOL（羊毛） 
TERRACOTTA（陶瓦）
TERRACOTTA_ALL（所有陶瓦）
GLAZED_TERRACOTTA（带釉陶瓦）
```

```yaml
 rainbow_materials:
    - GRASS_BLOCK
    - DIRT
```

自定义彩虹方块，按照上述格式添加方块ID

### 防凋灵

```yaml
 anti_wither: true/false
```

注意：只有方块可以设置这个选项
当`anti_wither: true`时，该方块将无法被凋灵破坏

### 灵魂绑定

```yaml
 soulbound: true/false
```

当`soulbound: true`时，该物品将不会在玩家死亡后掉落

### 猪灵交易物品

```yaml
  piglin_trade_chance: <1-100>
```

设置此物品的获取方式为猪灵交易物品。
<br>当你设置了这个选项，RSC会自动帮你补充 recipe_type:
<br>尽管你自己设置了其他的 recipe_type

```yaml
recipe_type: BARTER_DROP # 猪灵交易
```

### 人造类物品

```yaml
 vanilla: true/false
```

类似于人造钻石，当`vanilla: true`时，此物品可以被当做原版物品作为原版工作台合成物品时的材料

### 隐藏物品

```yaml
 hidden: true/false
```

当`hidden: true`时，此物品不会在粘液书中显示

### 方块掉落物品

```yaml
  drop_from: PODZOL
```

类似于硼砂，在这里是挖掘灰化土掉落这个粘液物品（参考上面 可变泥土 ）
你还可以设置掉落的几率以及数量（与drop_from同级）：

```yaml
  drop_chance: <1-100> # 可选，默认100
  drop_amount: 1 # 可选，默认1
```

## 注意事项

关于item.#后的标签，本页仅以name、material、amount为示例，可以在amount后添加更多标签，详见[通用物品格式](format/universal-item-format.md)

注意name与material为必填，如果不填material_type，则默认检测material为原版物品

### 关于本页引用的示例脚本example_item_2

详见[脚本基础-物品](scripts-basic/items.md)
