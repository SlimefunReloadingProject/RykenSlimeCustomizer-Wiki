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
  tier: 2
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
  actions:
  - "link https://rsc.himcs.top/#/README"
  - "console say 我自由了！"
example_locked_group:
  type: "locked"
  parents:
    - slimefun:basic_machines
  item:
    name: "&l示例锁定物品组"
    material: REPEATER
    amount: 1       
```

| 内容 | 描述 |
| -------- | -------- |
| `example_normal_group` | 分类的ID，每个分类的ID不能相同。<br>**仅支持字母、数字、下划线!**<br>新分类系统不再强制使用小写字母，但从物品引用分类时，请注意分类ID的大小写。 |
| type | (**必填**) 分类的类型。可用类型详见下方注意事项。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加`modelId`、`lore`、`glow`等。 |
| tier | (*可选*) 分类的优先级，默认为3。<br>分类的优先级是一个整数，低优先级的分类将优先显示。 |
| parent | (分类类型为子分类`sub`时**必填**) 父分类的ID。<br>只能是自定义附属中定义的父分类ID。 |
| month | (分类类型为季节性分类`seasonal`时**必填**) 季节性分类的显示月份，范围为1-12。 |
| parents | (分类类型为锁定分类`locked`时**必填**) 锁定分类所需的其他分类的`NamespacedKey`列表。<br>详见[Slimecustomizer wiki](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Categories) 。 |
| actions | 格式见下 |
```yaml
actions:
- "link 链接" # 被玩家点击此分类后在聊天栏弹出可点击链接
- "console 指令" # 被玩家点击此分类后在控制台执行命令
```
## 注意事项

1、分类的默认类型为normal

| 类型             | 描述                     |
| -------------- | ---------------------- |
| normal         | 普通物品组                  |
| locked         | 锁定物品组                  |
| seasonal       | 季节性物品组                 |
| nested, parent | 嵌套物品组(父物品组)            |
| sub            | 子物品组（必须在parent栏写父物品组名） |

2、**当物品组类型为锁定物品组时，需要填入父分类的**`NamespacedKey`**，而不是直接引用附属内的物品组。**

