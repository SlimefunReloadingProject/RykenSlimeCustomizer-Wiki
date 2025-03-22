# 机器菜单(menus.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义玩家点开机器/发电机显示的GUI页面，是每个机器必不可少的内容

**示例：**

```yaml
RSC_EXAMPLE_MACHINE:
  title: "&a示例菜单"
  script: "example_menu"
  slots:
    0-8:
     name: "&a"
     material: BLACK_STAINED_GLASS_PANE
    18-30:
     name: "&a"
     material: BLACK_STAINED_GLASS_PANE
    32-39:
     name: "&a"
     material: BLACK_STAINED_GLASS_PANE
    40:
     name: "&a一个工作按钮"
     material: GREEN_STAINED_GLASS_PANE   
    41-44:
     name: "&a"
     material: BLACK_STAINED_GLASS_PANE
RSC_EXAMPLE_GENERATOR:
  title: "&c示例发电机"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    4:
      name: "&a信息"
      progressbar: true
      material: GREEN_STAINED_GLASS_PANE
    5-9:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    12-14:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    17-26:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
RSC_EXAMPLE_MATERIAL_GENERATOR:
  title: "&d示例材料生成器"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    # 注意，不推荐在第4格放置物品，因为这已经设置成了用来展示信息的位置，你可以在材料生成器的配置中修改 `status` 参数
    5-12:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    14-17:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
RSC_EXAMPLE_RECIPE_MACHINE:
  title: "&c示例配方机器"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    4:
      name: "&a信息"
      material: GREEN_STAINED_GLASS_PANE
      progressbar: true
    5-9:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    12-14:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    17-26:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE

```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_MACHINE` | 菜单的ID，必须与对应的机器ID相同。 | **仅支持大写字母、数字、下划线!** |
| \*title | 菜单的名称，通常会显示在箱子页面的左上角。 |
| slots | 箱子页面的槽，可以将一个物品安排在一个或多个槽内。 |
| slots.(number) | 槽对应的数字。 |
| progressbar | 设置该物品为机器的进度条物品。|
| import | 从ID对应的机器中获取菜单并导入至此机器，详见注意事项。|
| script | 菜单引用的脚本，设置菜单对应的脚本文件，双引号内填脚本对应的文件名称 |

## 注意事项

1. 关于`import`

```yaml
RSC_EXAMPLE_RECIPE_MACHINE:
  title: "&c示例配方机器"
  import: 机器id
```

如果你使用了`import`，则`slots`可忽略不写，但是自定义的机器相应的`input`和`output`依然需要填写对应槽的数字

2. 如果你想给一个机器添加自定义菜单时，**机器的`id`** 与 **菜单的`id`**必须一致！

### 关于本页引用的示例脚本example_menu
详见[脚本基础-机器菜单](scripts-basic/machine_menus.md)
