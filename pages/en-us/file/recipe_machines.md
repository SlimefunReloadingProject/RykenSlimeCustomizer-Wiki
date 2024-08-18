# Recipe Machines (recipe_machines.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

> Machines with custom input and output.

## Example:

```yaml
RSC_EXAMPLE_RECIPE_MACHINE:
  item_group: rsc_example_normal_group
  item:
    name: "&eExample Recipe Machine"
    material: GREEN_STAINED_GLASS
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    2:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
  capacity: 1000
  input: [10,11]
  output: [15,16]
  energyPerCraft: 100
  speed: 2
  recipes:
    example:
      seconds: 10
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
        #Additional input items can be added
      output:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
    example_2:
      seconds: 5
      chooseOne: true
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
        #Additional input items can be added
      output:
        1:
          chance: 10
          material_type: slimefun
          material: RSC_EXAMPLE_MACHINE
        2:
          chance: 15
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
```

| Field                       | Description                                                                                                                                                                                                                       | Valid Input                                                               |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| *`RSC_EXAMPLE_RECIPE_MACHINE` | The ID of the machine.<br>This ID must be unique and not match any other item's ID!                                                                                                                                               | **Only uppercase letters, numbers, and underscores are supported!**       |
| *item_group                   | The ID of the [item group (category)](item_groups.md) where the item belongs.                                                                                                                                                     |
| *item.#                       | [Universal Item Format](../format/universal_item_format.md)                                                                                                                                                                       | Optional additions such as `modelId`, `lore`, `glow`, etc. are available. |
| recipe_type                   | See [Recipe Type](recipe_type.md).                                                                                                                                                                                                |
| recipe                        | Sets the recipe for the machine. See [**Recipe**](../format/recipe.md).                                                                                                                                                           |
| *input                        | The corresponding slot positions for item input.<br>**Do not set items for these slots in the menu!**                                                                                                                             |
| *output                       | The corresponding slot positions for item output.<br>**Do not set items for these slots in the menu!**                                                                                                                            |
| *energyPerCraft               | The amount of electricity the machine consumes per Slimefun tick.                                                                                                                                                                 |
| *speed                        | The speed of the machine, with a maximum of 2147483647, the larger the number, the faster the machine runs.<br>That is, you do not need to change the seconds for each work recipe. Changing this item will *upgrade the machine* |
| *capacity                     | Sets the amount of energy the machine can store, with a maximum of 2147483647.                                                                                                                                                    |
| recipes.#.seconds             | The time required for crafting, with a maximum of 2147483647. **Actual crafting time (in Slimefun ticks): (seconds × 2) / machine speed**                                                                                         |
| recipes.#.chooseOne           | When multiple products are randomly produced, choose one as the final product, see Notes.                                                                                                                                         |
| recipes.#.output.chance       | The chance of item output. Valid range 1~100                                                                                                                                                                                      |

## Notes

When `chooseOne: true`
Select one of the `output` for output.

When `chooseOne: false` (default)
Output each `output` item of the current recipe group.
