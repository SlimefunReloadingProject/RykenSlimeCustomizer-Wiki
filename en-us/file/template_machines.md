# Template Machines (template_machines.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

> More advanced machines with customizable input and output.

## Example:

```yaml
RSC_EXAMPLE_TEMPLATE_MACHINE:
  item_group: rsc_example_sub_group
  item:
    material: GOLD_BLOCK
    name: "&d&lExample Template Machine"
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
    2:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
  consumption: 300
  capacity: 3000
  templateSlot: 0
  input: [2, 3, 4, 5, 6, 7, 8]
  output: [18, 19, 20, 21, 22, 23, 24, 25, 26]
  fasterIfMoreTemplates: true
  moreOutputIfMoreTemplates: true
  recipes:
    RSC_EXAMPLE_GEO_RESOURCE:
      item2machine:
        seconds: 5
        input:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM
        output:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_MACHINE
      item22item:
        seconds: 5
        input:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM_2
        output:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM
    RSC_EXAMPLE_ITEM:
      2item:
        seconds: 1
        chooseOne: true
        output:
          1:
            material_type: slimefun
            material: RSC_EXAMPLE_ITEM
            chance: 15
```

| Field                         | Description                                                                                                                                                                                                                                                       | Valid Input                                                               |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| *`RSC_EXAMPLE_TEMPLATE_MACHINE` | The ID of the machine.<br>This ID must be unique and not match any other item's ID!                                                                                                                                                                               | **Only uppercase letters, numbers, and underscores are supported!**       |
| *item_group                     | The ID of the [item group (category)](groups.md) where the item belongs.                                                                                                                                                                                          |
| *item.#                         | [Universal Item Format](../format/universal-item-format.md)                                                                                                                                                                                                       | Optional additions such as `modelId`, `lore`, `glow`, etc. are available. |
| recipe_type                     | See [Recipe Type](recipe_type.md).                                                                                                                                                                                                                                |
| recipe                          | Sets the crafting recipe for the template machine. See [**Recipe**](../format/recipe.md)                                                                                                                                                                          |
| *input                          | The corresponding slot positions for item input.<br>**Do not set items for these slots in the menu!**                                                                                                                                                             |
| *output                         | The corresponding slot positions for item output.<br>**Do not set items for these slots in the menu!**                                                                                                                                                            |
| *consumption                    | The amount of electricity the template machine consumes per Slimefun tick.                                                                                                                                                                                        |
| *capacity                       | Sets the amount of energy the template machine can store, with a maximum of 2147483647.                                                                                                                                                                           |
| *recipes                        | The custom recipes for the template machine.                                                                                                                                                                                                                      |
| *recipes."sfid"                 | The Slimefun ID of the identifiable item must be filled in the first indentation, identifiable items can only be Slimefun items.                                                                                                                                  |
| *recipes."sfid".#               | The working recipes are filled in the second indentation, similar to [Recipe Machines](recipe_machines.md), when the item in the template slot matches the Slimefun ID in the first indentation, it will enter this indentation for matching the working recipes. |
| fasterIfMoreTemplates           | Whether the machine runs faster when there are multiple templates in the template slot, default is false                                                                                                                                                          |
| moreOutputIfMoreTemplates       | Whether more items are output when there are multiple templates in the template slot, default is false                                                                                                                                                            |
