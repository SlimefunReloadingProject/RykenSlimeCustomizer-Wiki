# 机器菜单

> 一般机器必不可少的东西

**示例：**

```yaml
EXAMPLE_MACHINE:
  title: "&a示例菜单"
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
EXAMPLE_GENERATOR:
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
EXAMPLE_MATERIAL_GENERATOR:
  title: "&d示例材料生成器"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    #注意，不推荐在第4格放置物品，因为这已经设置成了用来展示信息的位置
    5-11:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    13-17:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
EXAMPLE_RECIPE_MACHINE:
  title: "&c示例配方机器"
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
```

### title

菜单标题。

### slots

物品放的位置，槽位**以0开头，53结尾**，对应过来就是1\~54。

e.g.：**0-8意思是**从第1格到第9格都是放这个物品。

### progressbar

设置这个物品为机器的进度条物品。

### import

设置从哪个机器获取菜单并导入至此机器。

### 其他

如果你想给机器添加自定义菜单时，请注意，两处的id必须一致！
