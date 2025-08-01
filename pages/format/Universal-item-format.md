# 通用物品格式

<mark style="color:red;">**注意：**</mark>带\*为必填

### \*名称

设置物品名称。

```yaml
name: "物品名称"
```

### 数量

设置物品数量。

注意：**该功能**仅**在设置**物品、配方、菜单、材料生成器、发电机输入输出时可用，默认为1。
<br>有效范围： -1 ~ 64
<br>RSC不对任何超出原本限制的物品数量做检查
<br>如有任何相关错误，请不要找RSC

小技巧：如果将机器所需输入物品的数量设置为0，那么此物品将不会被消耗，但是需要此物品在输入槽内才能运行。(适用于我的世界1.20.5以前的版本)

```yaml
amount: (数字)
```

### 材料类型

该功能决定了物品的类型，若不添加此标签，则默认为mc。

| 类型                   | 描述             |
| -------------------- | -------------- |
| mc (默认)            | 原版物品 |
| skull\_base64        | 头颅物品 |
| skull\_url           | 头颅物品 |
| skull\_hash          | 头颅物品 |
| slimefun             | 粘液物品 |
| uniitem              | 外部插件物品 |
| none                 | 无物品(材料一栏可不用填)   |
| saveditem            | 保存的物品 |

```yaml
material_type: (材料类型)
```

#### 详解

1、skull\_base64 需要在material一栏填写头颅的Value

示例：

```yaml
material: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYmIwZjcyMmFlYzI3NDkwY2YwNTZmNTYwYWZkZDQ1N2EwYTc5NGU3MDM1NTZjYzRjM2I1MWE1ODJmNWM1N2FhNCJ9fX0=
```

2、skull\_url 需要在material一栏填写以https开头指向图片的网站

示例：

```yaml
material: http://textures.minecraft.net/texture/bb0f722aec27490cf056f560afdd457a0a794e703556cc4c3b51a582f5c57aa4
```

3、skull\_hash 需要在material一栏填写头颅的Minecraft URL

示例：

```yaml
material: bb0f722aec27490cf056f560afdd457a0a794e703556cc4c3b51a582f5c57aa4
```

4、slimefun

当`material_type: slimefun`时，你可以在同级的情况下添加`glow`，修改`name`和`lore`，可用于在不改变物品材质的情况下，编辑一个粘液物品，可用于机器的输出项。

5、mc

在填写原版物品id时，你可以省略`material_type: mc`，为了让rsc附属具备更好的兼容性，rsc默认兼容了以下被修改过的原版物品id

草：旧id：GRASS 新id：SHORT_GRASS
鳞甲：旧id：SCUTE 新id：TURTLE_SCUTE

你可以在填写上述两个原版物品id时随意使用旧id或新id

6、uniitem

引用外部插件的物品id，具体有关UniItem的用法详见[UniItem](https://github.com/ProjectUnified/UniItem)

示例:

```yaml
material_type: uniitem
material: mmoitems::MATERIAL:FLATSTONE
```

用法为namespace::id，支持以下插件

```yaml
  - ItemsAdder
  - Oxaren
  - MMOItems
  - MythicMobs
  - Nova
  - Reforges
  - StatTrackers
  - Talismans
  - ItemEdit
  - HeadDatabase
  - ItemBridge
  - EcoItems
  - EcoPets
  - EcoScrolls
  - EcoCrates
  - EcoArmor
```

### \*材料

设置物品材料，填写内容由材料类型决定。

例如slimefun类型，这里写粘液物品ID。

头颅那些写url或base64。

**注意：请不要设置物品材料为空气！**

```yaml
material: <材料>
```

### 模型ID

设置物品的模型id，这对做材质包的人并不陌生。

```yaml
modelId: (模型id)
```

### 物品描述

设置物品lore。

```yaml
lore:
  - "第一行"
  - "第114514行"
```

### 发光

让物品发光（带有一层附魔特效），若不添加此标签，则默认为false。

```yaml
glow: true/false
```

### 颜色

设置药水/皮革套装/烟火之星的颜色

```yaml
color: "0,255,0"
```

使用RGB颜色值

注意：药水和烟火之星在设置颜色后会隐藏物品描述中的无效果和小型球状