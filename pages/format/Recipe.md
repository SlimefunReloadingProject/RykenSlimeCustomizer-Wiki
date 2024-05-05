# 配方

配方的格式跟SC大致相同，每一格代表一个物品(**写法参考通用物品格式**)。

格式：

```yaml
recipe:
  1: 
    material: cobblestone
  2:
    material_type: none
  3:
    material_type: slimefun
    material: REINFORCED_ALLOY_INGOT
  4:
    ...
  5:
    ...
  6:
    ...
  7:
    ...
  8:
    ...
  9:
    ...
```

如果有些格子不需要放入物品，这样写会更加快捷，如下述示例：

```yaml
recipe:
  1:
    ...
  3:
    ...
  5:
    ...
  7:
    ...
  9:
    ...
```

当然，如果这个物品是不可合成的，可以省略recipe（即不填）。

## 应用

详见 [**配置文件-物品**](file/items.md) 。
