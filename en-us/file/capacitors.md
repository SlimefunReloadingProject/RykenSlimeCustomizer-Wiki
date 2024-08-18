# Capacitors(capacitors.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_CAPACITOR:
  item_group: rsc_example_sub_group
  item:
    name: "&aExample Capacitor"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  capacity: 10000
  recipe:
    1:
      material: APPLE
      amount: 1
    2:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
```

| Field                     | Description                                                                         | Valid Inputs                                                        |
|---------------------------|-------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| \*`RSC_EXAMPLE_CAPACITOR` | ID of the capacitor. <br>This ID cannot be the same as any other item's ID!         | **Only uppercase letters, numbers, and underscores are supported!** |
| \*item_group              | The ID of the [item group (category)](../file/groups.md) that the item belongs to.  |
| \*item.#                  | [Universal Item Format](../format/universal-item-format.md)                         | Optionally add modelId, lore, glow, etc.                            |
| recipe_type               | See [Recipe Type](recipe_type.md).                                                  |
| \*capacity                | The amount of energy that a capacitor can store, up to 2147483647.                  |
| recipe                    | Set the recipe for the capacitor. See [**Recipe**](../format/recipe.md) for details |

