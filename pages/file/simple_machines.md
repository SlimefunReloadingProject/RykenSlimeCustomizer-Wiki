# 简单机器(simple_machines.yml)

```yaml
RSC_EX_ADVANCED_GOLD_PAN:
  item_group: rsc_example_sub_group
  item:
    material: FURNACE
    name: "&b&l超级&7淘金机"
    lore:
      - "&7一个更加快的淘金机"
      - ""
      - "&8⇨ &e⚡ &7速度: 50x"
      - "&8⇨ &e⚡ &71,000 J/s"
  type: ELECTRIC_SMELTERY
  settings:
    capacity: 5000
    consumption: 1000
    speed: 50
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    2:
      material_type: slimefun
      material: GOLD_PAN
    4:
      material_type: slimefun
      material: ELECTRIC_MOTOR
    5:
      material_type: slimefun
      material: ELECTRIC_GOLD_PAN_3
    6:
      material_type: slimefun
      material: ELECTRIC_MOTOR
    7:
      material_type: slimefun
      material: COBALT_INGOT
    8:
      material_type: slimefun
      material: BLISTERING_INGOT_3
    9:
      material_type: slimefun
      material: COBALT_INGOT
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `RSC_EX_ADVANCED_GOLD_PAN` | 机器的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| type | 简单机器类型，详见注意事项。 |
| settings.capacity | 设置机器可储存的能量，最大为 2147483647。 |
| settings.consumption | 机器运行消耗的能量，最大为 2147483647。 |
| settings.speed | 机器运行速度，最大为 2147483647，数值越大，机器运行的越快。 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md)。 |
| recipe | 设置机器的配方。详见[**配方**](format/recipe.md) |

## 注意事项
1、关于简单机器类型(type)

简单机器类型包含以下几种：

```yaml
ELECTRIC_SMELTERY         # 电动冶炼炉  
ELECTRIC_FURNACE          # 电炉  
ELECTRIC_GOLD_PAN         # 电动淘金机 
ELECTRIC_DUST_WASHER      # 电动洗矿机  
ELECTRIC_ORE_GRINDER      # 电动碎矿机  
ELECTRIC_INGOT_FACTORY    # 电动铸锭机  
ELECTRIC_INGOT_PULVERIZER # 电动打粉机  
CHARGING_BENCH            # 充电台 
TREE_GROWTH_ACCELERATOR   # 树木生长加速器
ANIMAL_GROWTH_ACCELERATOR # 动物生长加速器
CROP_GROWTH_ACCELERATOR   # 作物生长加速器
FREEZER                   # 冰箱
CARBON_PRESS              # 碳压机
ELECTRIC_PRESS            # 压缩机
ELECTRIC_CRUCIBLE         # 电动坩埚
FOOD_FABRICATOR           # 食品加工机
HEATED_PRESSURE_CHAMBER   # 加热压力舱
AUTO_ENCHANTER            # 自动附魔机
AUTO_DISENCHANTER         # 自动祛魔机
BOOK_BINDER               # 附魔书整合机
AUTO_ANVIL                # 自动铁砧
AUTO_DRIER                # 自动烘干机
AUTO_BREWER               # 自动酿造机
REFINERY                  # 炼油机
PRODUCE_COLLECTOR         # 全自动收集机
```

2、个别机器类型需包含的参数

```yaml
# 格式
settings:
  radius: 10 # 范围。选填，默认为 1
  repair_factor: 10 # 修理因子。选填，默认为 10
```

| 机器类型 | 参数 | 参数类型 | 是否选填 | 默认值 | 补充说明 |
| - | - | - | - | - | - |
| 自动铁砧 | repair_factor | int | 选填 | 10 | 单次修复的值
| 树木生长加速器 | radius | int | 选填 | 1 | 机器工作生效范围
| 动物生长加速器 | radius | int | 选填 | 1 | 机器工作生效范围
| 作物生长加速器 | radius | int | 选填 | 1 | 机器工作生效范围
