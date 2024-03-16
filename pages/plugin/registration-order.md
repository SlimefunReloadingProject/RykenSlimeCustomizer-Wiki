# 配置注册顺序

所有分类/物品都需要注册后才能显示到粘液科技指南中。

注册有先后顺序，同一文件内靠前的物品ID将优先注册，并且可以在较晚注册的物品配方中直接引用其ID。

靠后的物品ID将较晚注册，并且无法在其之前的物品配方中引用其ID。

也就是说，在最先加载的配置中自定义的ID可以直接在其之后加载的配置中引用

以下为配置注册顺序

  - [内容加载/注册选项](file/context-options.md)
  - [物品组（分类）](file/groups.md)
  - [配方类型](file/recipe_type.md)
  - [生物掉落物](file/mob_drops.md)
  - [GEO资源](file/geo.md)
  - [物品](file/items.md)
  - [电容](file/capacitors.md)
  - [食物](file/foods.md)
  - [机器菜单](file/menu.md)
  - [发电机](file/generators.md)
  - [太阳能发电机](file/solar_generators.md)
  - [材料生成器](file/mat\_generators.md)
  - [机器](file/machine.md)
  - [配方机器](file/recipe_machines.md)
  - [简单机器](file/simple_machines.md)
  - [多方块机器](file/multi-block-machine.md)
  - [研究](file/research.md)