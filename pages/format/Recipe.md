# 配方

配方的格式跟SC大致相同，每一格代表一个物品(**写法参考通用物品格式**)。

但是rsc也提供了更多便捷的写配方的方法

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

当你面对类似于动力科技这种会频繁修改粘液物品id的附属，需要在配方中适配来自动力科技不同版本的粘液科技物品id的情况，可使用“ | ”符号

```yaml
recipe:
  1: 
    material: cobblestone
  2:
    material_type: none
  3:
    material_type: slimefun
    material: MATERIAL_HIVE | DT_MATERIAL_HIVE | DYNATECH_MATERIAL_HIVE
```

当MATERIAL_HIVE不存在时，则向后调用DT_MATERIAL_HIVE，当DT_MATERIAL_HIVE不存在时，则向后调用DYNATECH_MATERIAL_HIVE

此方法同样适用于机器的输入与输出

## 应用

详见 [**配置文件-物品**](file/items.md) 。
