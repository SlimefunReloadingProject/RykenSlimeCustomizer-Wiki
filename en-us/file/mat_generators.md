# Material Generators (mat_generators.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_MATERIAL_GENERATOR:
  item_group: rsc_example_sub_group
  item:
    name: "&cExample Material Generator"
    material: IRON_BLOCK
  capacity: 10000
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_WITHER_PROOF_STONE
  output: [13]
  outputItem:
    material_type: slimefun
    material: RSC_EXAMPLE_ITEM
  outputs:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
  tickRate: 5
  status: 4
  per: 10
```

| Field                             | Description                                                                                                              | Valid Input                                                         |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| *`RSC_EXAMPLE_MATERIAL_GENERATOR` | The ID of the material generator.<br>This ID must be unique and not match any other item's ID!                           |
| *item_group                       | The ID of the [item group (category)](file/groups.md) where the item belongs.                                            |
| *item.#                           | [Universal Item Format](format/universal-item-format.md)                                                                 | Optional additions such as modelId, lore, glow, etc. are available. |
| *capacity                         | The amount of energy the machine can store, with a maximum of 2147483647. Set to 0 for a machine that cannot be charged. |
| recipe_type                       | See [Recipe Type](file/recipe_type.md).                                                                                  |
| recipe                            | Sets the recipe for the material generator. See [**Recipe**](format/recipe.md) for details.                              |
| *output                           | The corresponding slot for item output. (Please do not set items in these slots in the menu!)                            |
| outputItem                        | See [Universal Item Format](format/universal-item-format.md), cannot coexist with `outputs`                              |
| outputs.#                         | See [Universal Item Format](format/universal-item-format.md), cannot coexist with `outputItem`                           |
| *tickRate                         | The time required to generate one item, with a maximum of 2147483647.                                                    |
| *status                           | Sets the slot for display information.                                                                                   |
| *per                              | The amount of energy consumed per item generated.                                                                        |
