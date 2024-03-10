# 通用物品格式

<mark style="color:red;">**注意：**</mark>带\*为必填

### 名称\*

设置物品名称。

```
name: "物品名称"
```

### 数量

设置物品数量。

注意：**该功能**仅**在设置**物品、配方、菜单、材料生成器、发电机输入输出时可用，默认为1。

```
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
| full\_slimefun       | 完整粘液物品 |
| none                 | 无物品(材料一栏可不用填)   |
| saveditem            | 保存的物品 |

```
material_type: (材料类型)
```

#### 详解：

1、skull\_base64 需要在material一栏填写头颅的Value

示例：

```
material: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYmIwZjcyMmFlYzI3NDkwY2YwNTZmNTYwYWZkZDQ1N2EwYTc5NGU3MDM1NTZjYzRjM2I1MWE1ODJmNWM1N2FhNCJ9fX0=
```

2、skull\_url 需要在material一栏填写以https开头指向图片的网站

示例：

```
material: http://textures.minecraft.net/texture/bb0f722aec27490cf056f560afdd457a0a794e703556cc4c3b51a582f5c57aa4
```

3、skull\_hash 需要在material一栏填写头颅的Minecraft URL

示例：

```
material: bb0f722aec27490cf056f560afdd457a0a794e703556cc4c3b51a582f5c57aa4
```

4、slimefun与full_slimefun可以修改的粘液物品与不可修改的粘液物品

如果material_type填的是slimefun，你可以在同级的情况下添加glow，修改name和lore，可用于在不改变物品材质的情况下，编辑一个粘液物品，可用于机器的输出项。

如果填的是full_slimefun，那么你仅可以修改数量(amount)，无法额外添加其他标签。

当你没有以上需求时，可以无脑填slimefun

### 材料\*

设置物品材料，填写内容由材料类型决定。

例如slimefun, full\_slimefun类型，这里写粘液物品ID。

头颅那些写url或base64。

```
material: <材料>
```

### 模型ID

设置物品的模型id，这对做材质包的人并不陌生。

```
modelId: (模型id)
```

### 物品描述

设置物品lore。

```
lore:
  - "第一行"
  - "第114514行"
```

### 发光

让物品发光（带有一层附魔特效），若不添加此标签，则默认为false。

```
glow: (true或false)
```

