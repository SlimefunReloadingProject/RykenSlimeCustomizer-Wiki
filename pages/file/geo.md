# GEO资源(geo_resources.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义需要用GEO矿机挖掘的物品。

**示例：**

```yaml
RSC_EXAMPLE_GEO_RESOURCE:
  item_group: rsc_example_normal_group
  item:
    name: "&a示例GEO资源"
    material: DIAMOND
  recipe_type: GEO_MINER
  max_deviation: 1
  obtain_from_geo_miner: true
  geo_name: "RSC示例GEO资源"
  supply:
    normal:
      plains: 10
      ocean: 5
      others: 4
    nether: 1
    the_end: 2
  drop_from: PODZOL
  drop_chance: 10
  drop_amount: 3-5
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_GEO_RESOURCE` | 自然资源的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| \*item_group| 自然资源所在[物品组（分类）](file/groups.md)的ID。 |
| \*item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| recipe_type | 见[配方类型](format/universal-item-format.md)。 |
| \*max-deviation | 每个区块自然资源数量的最大偏差。 | 正整数 |
| obtain_from_geo_miner | 设置自然资源是否可以从GEO矿机中挖到。|
| \*geo_name | 设置自然资源的名称。 |
| \*supply | 设置自然资源在各个世界环境、生物群系的默认数量，详见注意事项。 |
| drop_from | 挖掘方块掉落，详见下文 |

### 方块掉落物品

```yaml
  drop_from: PODZOL
```

类似于硼砂，在这里是挖掘灰化土掉落这个粘液物品（参考上面 可变泥土 ）
你还可以设置掉落的几率以及数量（与drop_from同级）：

```yaml
  drop_chance: <1-100> # 可选，默认100
  drop_amount: 1 # 可选，默认1，支持 drop_amount: 3-5 这种范围形式
```

## 注意事项

1、关于supply

normal、nether、the\_end代表着主世界、下界、末地三个维度。

plains、ocean代表主世界的生物群系。

others代表在主世界的其它生物群系。

下界与末地的生物群系同理

2、有关geo的更多信息，详见[Slimecustomizer wiki](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Geo-Resources)
