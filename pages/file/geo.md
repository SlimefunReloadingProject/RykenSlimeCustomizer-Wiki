# GEO资源

**示例：**

```yaml
EXAMPLE_GEO_RESOURCE:
  item_group: example_normal_group
  item:
    name: "&a示例GEO资源"
    material: DIAMOND
  recipe_type: GEO_MINER
  max_deviation: 1
  obtain_from_geo_miner: true
  geo_name: "RSC示例GEO资源"
  supply:
    world:
      plains: 10
      ocean: 5
      others: 4
    nether: 1
    the_end: 2
```

## 设置

### item\_group,item,recipe\_type,recipe

详见[**物品**](broken-reference)

### max\_deviation

设置每个区块自然资源数量的最大偏差。

### obtain\_from\_geo\_miner

设置自然资源是否可以从GEO矿机中挖到。

### geo\_name

设置自然资源名称

### supply

设置自然资源在各个世界环境、生物群系的默认数量。

world、nether、the\_end代表了世界环境。

plains、ocean代表了在主世界环境的生物群系。

others代表在主世界其他存在的生物群系。
