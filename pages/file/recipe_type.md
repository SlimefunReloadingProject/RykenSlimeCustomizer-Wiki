# 配方类型

> 这是仅作显示的配方类型。

示例:

```yaml
EXAMPLE_RECIPE_TYPE:
  material: "DIAMOND_BLOCK"
  name: "&e示例配方类型"
EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE:
  name: "&b示例多方块机器"
  material: CRAFTING_TABLE
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_RECIPE_TYPE` | 配方类型的ID。<br>该ID不能与任何其他配方类型的ID相同!（其它情况下见`特别注意`） | **仅支持大写字母、数字、下划线!** |
| material | 原版物品 | CRAFTING_TABLE |
| name | 配方类型的名称| "&b示例多方块机器" |

在此基础上，你可以自行添加`modelId`、`lore`、`glow`等标签，详见[通用物品格式](format/universal-item-format.md)。

此处的配方类型ID可直接用于recipe_type的引用。

## 特别注意
在RSC中，NULL对应SC中的NONE，即：
```yaml
# SlimeCustomizer
recipe_type: NONE
```
在RSC中需要做如下修改
```yaml
# RykenSlimeCustomizer
recipe_type: NULL
```
## 更多配方类型
你可以设置配方类型为这些，但并不代表此配方一定存在，不过你仍然可以设置recipe来解释说明

[参考代码](https://github.com/StarWishsama/Slimefun4/blob/master/src/main/java/io/github/thebusybiscuit/slimefun4/api/recipes/RecipeType.java)
```yaml
MULTIBLOCK # 多方块结构
ARMOR_FORGE # 盔甲锻造台
GRIND_STONE # 磨石
SMELTERY # 冶炼炉
ORE_CRUSHER # 碎矿机
GOLD_PAN # 淘金
COMPRESSOR # 压缩机
PRESSURE_CHAMBER # 压力机
MAGIC_WORKBENCH # 魔法工作台
ORE_WASHER # 洗矿机
ENHANCED_CRAFTING_TABLE # 增强型工作台
JUICER # 榨汁机
ANCIENT_ALTAR # 远古祭坛
MOB_DROP # 生物掉落
BARTER_DROP # 猪灵交易
INTERACT # 交互
HEATED_PRESSURE_CHAMBER # 加热压力舱
FOOD_FABRICATOR # 食品加工机
FOOD_COMPOSTER # 食品堆肥机
FREEZER # 冰箱
REFINERY # 炼油机
GEO_MINER # 自然资源开采机
NUCLEAR_REACTOR # 核反应堆
NULL # 无配方
```
