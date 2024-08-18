# Generators (generators.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

> Essential power generation equipment.

**Example:**

```yaml
RSC_EXAMPLE_GENERATOR:
  item_group: example_normal_group
  item:
    name: "&cExample Generator"
    material: GOLD_BLOCK
  capacity: 100000
  production: 100
  input: [10,11]
  output: [15,16]
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    3:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    5:
      material_type: slimefun
      material: RSC_EXAMPLE_MACHINE
    7:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    9:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
  fuels:
    example_fuel:
      item:
        material: OAK_WOOD
      seconds: 10
      output:
        material: CHARCOAL
```
| Field               | Description                                                                                             | Valid Input                                                         |
|-----------------------|---------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| \*`EXAMPLE_GENERATOR` | The ID of the generator. <br>This ID cannot be the same as any other item's ID!                         | **Only uppercase letters, numbers, and underscores are supported!** |
| \*item_group          | The ID of the [item group (category)](groups.md) that the item belongs to.                              |
| \*item.#              | [Universal Item Format](../format/universal-item-format.md)                                             | Optionally add modelId, lore, glow, etc.                            |
| \*capacity            | The amount of energy the generator can store, up to 2147483647, set to 0 for a non-rechargeable machine |
| \*production          | The amount of electricity the generator can produce, in slime ticks, up to 2147483647                   |
| recipe_type           | See [recipe type](recipe_type.md).                                                                      |
| recipe                | Set the recipe for the generator. See [**Recipe**](../format/recipe.md) for details                     |
| \*input               | The corresponding slots for item input. (Please do not set items for these slots in the menu!)          |
| \*output              | The corresponding slots for item output. (Please do not set items for these slots in the menu!)         |
| \*fuels               | Set the fuel for the generator.                                                                         |
| \*fuels.#.seconds     | The generation time of this fuel, in seconds, with a maximum of 2147483647.                             |
| \*fuels.#.item        | The required fuel.                                                                                      |
| \*fuels.#.output      | The output product after the fuel is generated.                                                         |
