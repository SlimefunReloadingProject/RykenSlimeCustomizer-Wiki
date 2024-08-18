# Multi-block Machines (mb_machines.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_MULTIBLOCK_MACHINE:
  item_group: rsc_example_normal_group
  item:
    name: "&bExample Multi-block Machine"
    material: CRAFTING_TABLE
  recipe:
    #Arrange like this:
    #1 2 3
    #4 5 6
    #7 8 9
    5:
      material: OAK_FENCE_GATE
    #Remember the dispenser
    8:
      material: DISPENSER
  work: 5
  sound: ANCIENT_ALTAR_FINISH_SOUND
  recipes:
    example:
      input:
        1:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM
        2:
          material_type: slimefun
          material: RSC_EXAMPLE_MACHINE
      output:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
    helmet:
      input:
        3:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: RSC_EXAMPLE_HELMET
    chestplate:
      input:
        4:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: RSC_EXAMPLE_CHESTPLATE
    leggings:
      input:
        5:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: RSC_EXAMPLE_LEGGINGS
    boots:
      input:
        6:
          material_type: slimefun
          material: RSC_EXAMPLE_ITEM_2
      output:
        material_type: slimefun
        material: RSC_EXAMPLE_BOOTS
```

| Field             | Description                                                                                                                                                                                                                                                      | Valid Input                                                               |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| *`RSC_EXAMPLE_ITEM` | The ID of the multi-block machine.<br>This ID must be unique and not match any other item's ID!                                                                                                                                                                  | **Only uppercase letters, numbers, and underscores are supported!**       |
| *item_group         | The ID of the [item group (category)](groups.md) where the multi-block machine belongs.                                                                                                                                                                          |
| *item.#             | [Universal Item Format](../format/universal-item-format.md)                                                                                                                                                                                                      | Optional additions such as `modelId`, `lore`, `glow`, etc. are available. |
| *recipe             | Sets up the structure of the multi-block machine. See [**Recipe**](../format/recipe.md) for details. A dispenser must be included when constructing a multi-block machine.                                                                                       |
| recipes.#.input     | The recipe for the output item of the machine.                                                                                                                                                                                                                   |
| recipes.#.output    | The item output by the multi-block machine.                                                                                                                                                                                                                      |
| *work               | Sets the working block, i.e., the block that needs to be right-clicked to craft an item in the multi-block machine, fill in the corresponding block number in the recipe.                                                                                        |
| *sound              | The sound that is played after right-clicking the working block and successfully crafting an item, see [Sound Effects](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/services/sounds/SoundEffect.html) for details. |

## Notes

A dispenser must be included in the recipe of a multi-block machine.
After the multi-block machine is constructed,
it will automatically search for the working block by looking around the dispenser.

## How to Write a Material That Can Only Be Made with a Multi-block Machine

First, customize a [Recipe Type](recipe_type.md) with the name of this multi-block machine,
and you can add lore and other content.

Then, register an item in the items.yml (see [Items](items.md)), and fill in the custom recipe type id in the recipe_type, and write the corresponding recipe in the recipe (Note: The recipe written in the items file is only for display and does not represent that the multi-block machine really has this recipe).

Finally, write a multi-block machine in the multi-block-machine.yml,
the input corresponds to the recipe of the item (copy the recipe you wrote in the items.yml file),
and the output fills in the custom item id you defined in the items.yml file.

### Script
See [Script Basics - Multi-block](../scripts-basic/multiblock_machines.md) for details.
