# 食物(foods.yml)

示例:

```yaml
RSC_EXAMPLE_FOOD:
  item_group: rsc_example_sub_group
  item:
    name: "食物 1"
    material: rotten_flesh
  script: example_food
  recipe_type: MAGIC_WORKBENCH
  recipe:
    1:
      material: birch_planks
      amount: 1
    2:
      material: birch_planks
      amount: 1
    3:
      material: dark_oak_planks
      amount: 1
```

自定义食物的实质就是自定义物品，所以自定义食物跟自定义物品的格式一样，需要在foods.yml中完成,
**前提是物品材料类型必须是可食用的，不然不能触发脚本，也不能吃**

关于食物的特性通过在foods.yml中引用脚本实现，详见[脚本-食物](scripts-basic/foods.md)

格式见[物品](file/items.md)
