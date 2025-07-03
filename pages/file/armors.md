# 盔甲(armors.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义盔甲套装(类似于粘液原版的套装/无尽套)。

**示例：**

```yaml
rsc_example_armor:
  protection_types:
    - BEES
    - RADIATION
    - FLYING_INTO_WALL
  fullSet: true
  item_group: rsc_example_normal_group
  helmet:
    id: RSC_EXAMPLE_HELMET
    material: LEATHER_HELMET
    name: "&d示例头盔"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      3:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
  chestplate:
    id: RSC_EXAMPLE_CHESTPLATE
    material: LEATHER_CHESTPLATE
    name: "&d示例胸甲"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      4:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
  leggings:
    id: RSC_EXAMPLE_LEGGINGS
    material: LEATHER_LEGGINGS
    name: "&d示例护腿"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      5:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
  boots:
    id: RSC_EXAMPLE_BOOTS
    material: LEATHER_BOOTS
    name: "&d示例靴子"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      6:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
    potion_effects:
      - "SPEED 5"
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`rsc_example_armor` | 套装的NamespacedKey。 |  |
| \*item_group | 盔甲所在[物品组（分类）](file/groups.md)的ID。 |
| fullSet | 是否需要盔甲组成套装才能使保护类型与药水效果生效 |
| protection_types | 保护类型，详见下文 |
| \*helmet/chestplate/leggings/boots | 头盔/胸甲/护腿/靴子，遵循[通用物品格式](format/universal-item-format.md) |
| potion_effects | 穿上盔甲时给予的药水效果格式为 药水效果ID + 药水等级 **(数字+1)级** |
| recipe等 | 遵循[通用物品格式](format/universal-item-format.md) |

## 有关potion_effects

potion_effects的id改动较多，需要根据服务器的我的世界版本自行调整

以下列出受过更改的药水效果id，可通过使用rsc的[注册选项](file/context-options.md)功能来适配不同我的世界版本的盔甲

| 药水名称 | 1.20.5之前的id | 1.20.5之后的id |
| --- | ----------- | ----------------- |
| 急迫 | FAST_DIGGING | HASTE |
| 瞬间伤害 | HARM | INSTANT_DAMAGE |
| 瞬间治疗 | HEAL | INSTANT_HEALTH |
| 跳跃提升 | JUMP | JUMP_BOOST |
| 挖掘疲劳 | SLOW_DIGGING | MINING_FATIGUE |
| 反胃 | CONFUSION | NAUSEA |
| 抗性提升 | DAMAGE_RESISTANCE | RESISTANCE |
| 力量 | INCREASE_DAMAGE | STRENGTH |


## 保护类型

保护类型详见[盔甲保护类型](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/attributes/ProtectionType.html)