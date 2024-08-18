# Solar Generators (solar_generators.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_SOLAR_GENERATOR:
  item_group: rsc_example_normal_group
  item:
    name: "&cExample Solar Generator"
    material: GOLD_BLOCK
    lore:
      - "&eDaytime Energy Generation: 1000J/t"
      - "&bNighttime Energy Generation: 100J/t"
  capacity: 100000
  dayEnergy: 1000
  nightEnergy: 100
  lightLevel: 14
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
    3:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
    5:
      material_type: slimefun
      material: RSC_EXAMPLE_MACHINE
    7:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM_2
    9:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
```

| Field                        | Description                                                                                                                                             | Valid Input                                                         |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| *`RSC_EXAMPLE_SOLAR_GENERATOR` | The ID of the solar generator.<br>This ID must be unique and not match any other item's ID!                                                             | **Only uppercase letters, numbers, and underscores are supported!** |
| *item_group                    | The ID of the [item group (category)](groups.md) where the item belongs.                                                                                |
| *item.#                        | [Universal Item Format](../format/universal-item-format.md)                                                                                             | Optional additions such as modelId, lore, glow, etc. are available. |
| *capacity                      | The amount of energy the solar generator can store, with a maximum of 2147483647. Set to 0 for a machine that cannot be charged.                        |
| *dayEnergy                     | The energy generation rate of the solar generator during the day, in Joules per tick, with a maximum of 2147483647.                                     |
| *nightEnergy                   | The energy generation rate of the solar generator at night, in Joules per tick, with a maximum of 2147483647.                                           |
| *lightLevel                    | The light level required for the machine to operate; it will not function if the light level at its location is below this value, with a maximum of 15. |
| recipe_type                    | See [Recipe Type](recipe_type.md).                                                                                                                      |
| recipe                         | Sets the recipe for the solar generator. See [**Recipe**](../format/recipe.md).                                                                         |