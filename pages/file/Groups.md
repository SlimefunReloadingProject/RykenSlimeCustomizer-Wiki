# 物品组（分类）

**示例：**

```yaml
example_normal_group:
  item:
    name: "&a示例普通物品组"
    material: GRASS_BLOCK
    amount: 1
example_parent_group:
  type: "nested"
  item:
    name: "&a示例父物品组"
    material: OAK_PLANKS
    amount: 1
example_sub_group:
  type: "sub"
  parent: "example_parent_group"
  item:
    name: "&e示例子物品组"
    material: REDSTONE
    amount: 1
    lore: 
      - "&aHello?"
example_seasonal_group:
  type: "seasonal"
  month: 1
  item:
    name: "&b示例季节性物品组"
    material: OAK_LEAVES
    amount: 1
example_locked_group:
  type: "locked"
  parents:
    - slimefun:basic_machines
  item:
    name: "&l示例锁定物品组"
    material: REPEATER
    amount: 1       
```

格式与SC大致相同。

## 设置

### type

设置物品组类型。默认类型为normal

| 类型             | 描述                     |
| -------------- | ---------------------- |
| normal         | 普通物品组                  |
| locked         | 锁定物品组                  |
| seasonal       | 季节性物品组                 |
| nested, parent | 嵌套物品组(父物品组)            |
| sub            | 子物品组（必须在parent栏写父物品组名） |

### parent/parents

设置物品组的父分类。

**注意：当物品组类型为锁定物品组时，需要填入父分类的**`NamespacedKey`**，而不是直接引用附属内的物品组。**

### month

设置季节性物品组出现的月份。

### item

请至 [通用物品格式](../format/universal-item-format.md) 内查看，之后内容不再写。
