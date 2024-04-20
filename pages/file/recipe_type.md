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
| material | 原版物品 |
| name | 配方类型的名称| |

在此基础上，你可以自行添加lore、glow等标签，详见[通用物品格式](../format/universal-item-format.md)。

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
此外，RSC 还有 GEO_MINER 配方类型可使用，代表自然资源开采机配方（仅显示）
