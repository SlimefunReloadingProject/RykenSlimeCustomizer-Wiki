# 配方类型(recipe_types.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 这是仅作显示的配方类型。

**示例：**

```yaml
RSC_EXAMPLE_RECIPE_TYPE:
  material: "DIAMOND_BLOCK"
  name: "&e示例配方类型"
RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE:
  name: "&b示例多方块机器"
  material: CRAFTING_TABLE
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_RECIPE_TYPE` | 配方类型的ID。<br>该ID不能与任何其他配方类型的ID相同!（其它情况下见`特别注意`） | **仅支持大写字母、数字、下划线!** |
| \*material | 原版物品 | CRAFTING_TABLE |
| \*name | 配方类型的名称| "&b示例多方块机器" |

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

你可以设置配方类型为这些（粘液自带），但并不代表此配方一定存在，不过你仍然可以设置recipe来解释说明

[参考代码](https://github.com/StarWishsama/Slimefun4/blob/master/src/main/java/io/github/thebusybiscuit/slimefun4/api/recipes/RecipeType.java)

```yaml
# 自动设置配方的类型
ARMOR_FORGE # 盔甲锻造台
GRIND_STONE # 磨石
SMELTERY # 冶炼炉
ORE_CRUSHER # 碎矿机
COMPRESSOR # 压缩机
PRESSURE_CHAMBER # 压力机
MAGIC_WORKBENCH # 魔法工作台
ORE_WASHER # 洗矿机
ENHANCED_CRAFTING_TABLE # 增强型工作台
ANCIENT_ALTAR # 远古祭坛
JUICER # 榨汁机
HEATED_PRESSURE_CHAMBER # 加热压力舱
MOB_DROP # 生物掉落

# 仅展示的类型
MULTIBLOCK # 多方块结构
GOLD_PAN # 淘金
BARTER_DROP # 猪灵交易
INTERACT # 交互
FOOD_FABRICATOR # 食品加工机
FOOD_COMPOSTER # 食品堆肥机
FREEZER # 冰箱
REFINERY # 炼油机
GEO_MINER # 自然资源开采机
NUCLEAR_REACTOR # 核反应堆
NULL # 无配方
```

### 以下配方类型仅支持数量为1的物品输入

- ENHANCED_CRAFTING_TABLE <u>增强型工作台</u>
- MAGIC_WORKBENCH <u>魔法工作台</u>
- ARMOR_FORGE <u>盔甲锻造台</u>
- PRESSURE_CHAMBER <u>压力机</u>
- ANCIENT_ALTAR <u>古代祭坛</u>

### 以下配方类型的合成配方仅第1格物品有效

- COMPRESSOR <u>压缩机</u>
- PRESSURE_CHAMBER <u>压力机</u>
- ORE_CRUSHER <u>矿石粉碎机</u>
- GRIND_STONE <u>磨石</u>
- ORE_WASHER <u>洗矿机</u>
- HEATED_PRESSURE_CHAMBER <u>加热压力舱</u>
- JUICER <u>榨汁机</u>

### 以下配方类型的合成配方必须所有9格都有物品

- ANCIENT_ALTAR <u>古代祭坛</u>

### 以下配方类型的合成配方的第5格必须是生物蛋或空

- MOB_DROP <u>生物掉落</u>
