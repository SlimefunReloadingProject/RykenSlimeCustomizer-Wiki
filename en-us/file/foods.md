# Food(foods.yml)

**Example:**

```yaml
RSC_EXAMPLE_FOOD:
  item_group: rsc_example_sub_group
  item:
    name: "Food 1"
    material: rotten_flesh
  script: "example_food"
  nutrition: 1
  saturation: 0
  eatseconds: 1.6
  always_eatable: false
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

| Field | Description | Valid Input |
| --- | ----------- | ----------------- |
| \*`RSC_EXAMPLE_ITEM` | The ID of the item. <br>This ID cannot be the same as any other item's ID! | **Only uppercase letters, numbers, and underscores are supported!** |
| \*item_group | The ID of the [item group (category)](/en-us/file/groups.md) that the item belongs to. |
| \*item.# | [Universal Item Format](/en-us/format/universal-item-format.md)| Optionally add `modelId`, `lore`, `glow`, etc. |
| recipe_type | See [Recipe Type](/en-us/file/recipe_type.md). |
| \*script | The script referenced by the item, set the script file corresponding to the item, and fill the file name corresponding to the script in double quotes |
| recipe | Set the recipe of the item. See [**Recipe**](/en-us/format/recipe.md) for details |

## Advanced Custom Food

> The following parameter version requirements 1.20.5+ and the plugin [NBTAPI](https://www.spigotmc.org/resources/nbt-api.7939/)(needs to be installed and enabled)

| Field | Description | Valid input |
| --- | ----------- | ----------------- |
| nutrition | Set the hunger value of the item | 1 ~ 2147483647 |
| saturation | Set the saturation of the item | 0.0 ~ 2147483647.0 |
| eatseconds | Set the eating time of the item | 0.0 ~ 2147483647.0 <br> Default 1.6 |
| always_eatable | Set whether the item is always edible | true/false, default false, true allows you to continue eating after your satiety is full |

The characteristics of food are implemented by referencing scripts in foods.yml,
see [Scripts-Foods](../en-us/scripts-basic/foods.md) for details
