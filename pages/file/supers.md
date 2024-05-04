# 继承物品(supers.yml)

示例：

```yaml
EXAMPLE_SUPER_ITEM:
  item_group: example_sub_group
  item:
    material: MUSIC_DISC_PIGSTEP
    name: "&b&l超级&7存储元件"
    lore:
      - "&e继承测试"
  class: "me.ddggdd135.slimeae.core.slimefun.MEItemStorageCell" # 来自 SlimeAE
  args: [50000]
  register:
    conditions:
       - "hasplugin SlimeAE"
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `EXAMPLE_SUPER_ITEM` | 继承物品的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |
| recipe_type | 见 SlimeCustomizer wiki[合成配方](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Crafting-Recipe) ，可填自定义的recipe_type详见[配方类型](file/recipe_type.md)。 |
| recipe | 设置继承物品的配方。详见[**配方**](format/recipe.md) |
| class | 设置继承什么物品，这里需要填写要继承的物品的完整类名 | org.example.project.ExampleClass |
| args | 补全继承物品的其他构造参数 |
| ctor | (*可选参数*) 设置用继承物品的哪个构造器，位置从0开始 | 0 |
| arg_template | (*可选参数*) 设置默认构造参数的输入位置 | [group, item, recipe_type, recipe] |
| method | (*可选参数*) 可使用此继承物品的一些方法来修改一些值 | 详见下面**使用method修改部分值** |
| field| (*可选参数*) 修改此继承物品的部分字段 | 详见下面**使用field修改部分字段的值** |

## 使用method修改部分值
假设我们继承了一个粘液原版机器，这里用[CarbonPress(碳压机)](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/implementation/items/electric/machines/CarbonPress.html)作为例子

现在的配置是这样的:
```yml
EXAMPLE_SUPER_ITEM:
  item_group: example_sub_group
  item:
    material: FURNACE
    name: "&b&l超级&7碳压机"
  class: "io.github.thebusybiscuit.slimefun4.implementation.items.electric.machines.CarbonPress"
```
此时如果你需要设置他的效率、能源容量等等，你可以这样:
```yml
EXAMPLE_SUPER_ITEM:
  item_group: example_sub_group
  item:
    material: FURNACE
    name: "&b&l超级&7碳压机"
  class: "io.github.thebusybiscuit.slimefun4.implementation.items.electric.machines.CarbonPress"
  #新增部分
  method:
    setCapacity: 50000
    setProcessingSpeed: 20
```
那么你就获得了一个能源容量为50000、效率20x的超级碳压机

## 使用field修改部分字段的值
这里用无尽的GEO矿机做例子  
源代码：<https://github.com/Mooy1/InfinityExpansion/blob/master/src/main/java/io/github/mooy1/infinityexpansion/items/machines/GeoQuarry.java>

现在的配置是这样的：
```yml
EXAMPLE_SUPER_ITEM:
  item_group: example_sub_group
  item:
    material: FURNACE
    name: "&b&l超级&7GEO矿机"
  class: "io.github.mooy1.infinityexpansion.items.machines.GeoQuarry"
```

那我们修改ticksPerOutput来增加geo矿机的输出时间:
```yml
EXAMPLE_SUPER_ITEM:
  item_group: example_sub_group
  item:
    material: FURNACE
    name: "&b&l超级&7GEO矿机"
  class: "io.github.mooy1.infinityexpansion.items.machines.GeoQuarry"
  #新增部分
  field:
    ticksPerOutput: 2
```
此时你就获得了一个一秒输出一个的超级GEO矿机  

**注意: 你不能修改常量(被final修饰的变量)**