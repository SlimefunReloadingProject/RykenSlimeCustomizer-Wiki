# Items (items.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_ITEM:
  item_group: rsc_example_sub_group
  item:
    name: "&aExample Item "
    material: DIAMOND
  recipe_type: ENHANCED_CRAFTING_TABLE  
  recipe:
    1:
      material: APPLE
      amount: 1
RSC_EXAMPLE_ITEM_2:
  item_group: rsc_example_normal_group
  item:
    name: "&aExample Item 2"
    material: NETHERITE_INGOT
  recipe_type: ENHANCED_CRAFTING_TABLE  
  script: example_script_item
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM
RSC_EXAMPLE_ITEM_3:
  item_group: rsc_example_normal_group
  item:
    name: "&aExample Item 3"
    material: GOLD_INGOT
  recipe_type: ENHANCED_CRAFTING_TABLE
  energy_capacity: 1000
  script: example_chargeable_item
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM2
RSC_SYNTHETIC_STONE:
  item_group: rsc_example_sub_group
  placeable: false
  item:
    name: "&7Synthetic Stone"
    material: STONE
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material: COBBLESTONE
    2:
      material: COBBLESTONE
    4:
      material_type: slimefun
      material: STONE_CHUNK
    5:    
      material_type: slimefun
      material: STONE_CHUNK
  vanilla: true
RSC_WITHER_PROOF_STONE:
  item_group: rsc_example_sub_group
  item:
    name: "&7&lAnti-Wither Stone"
    material: STONE
  anti_wither: true  
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material: COBBLESTONE
    2:
      material: COBBLESTONE
    3:
      material_type: slimefun
      material: MOD_PLATE_DUMMY #From SlimeTinker, if you don't install it, it will change to a stone.
RSC_CHANGEABLE_DIRT:
  item_group: rsc_example_normal_group
  item:
    name: "&6&lChangeable Dirt"
    material: DIRT
  piglin_trade_chance: 10
  drop_from: PODZOL
  drop_chance: 10
  drop_amount: 1
  rainbow: CUSTOM
  rainbow_materials:
    - DIRT      
    - GRASS_BLOCK
    - PODZOL  
RSC_HIDDEN_ITEM:
  item_group: rsc_example_normal_group
  item:
    name: "&6&lHidden Item"
    material: BARRIER
  piglin_trade_chance: 10
  hidden: true
  radiation: VERY_DEADLY
```

| Field                | Description                                                                                                                                                 | Valid Input                                                         |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| \*`RSC_EXAMPLE_ITEM` | The ID of the item. <br>This ID cannot be the same as any other item's ID!                                                                                  | **Only uppercase letters, numbers, and underscores are supported!** |
| \*item_group         | The ID of the [item group (category)](../en-us/file/groups.md) that the item belongs to.                                                                          |
| \*item.#             | [Universal Item Format](../en-us/format/universal-item-format.md)                                                                                                 | Optionally add `modelId`, `lore`, `glow`, etc.                      |
| placeable            | Whether the item is placeable. **Don't make tools and other items that are not placeable! **                                                                |
| recipe_type          | See [recipe type](../en-us/file/recipe_type.md).                                                                                                                  |
| script               | The script referenced by the item, set the script file corresponding to the item, and fill the double quotes with the file name corresponding to the script |
| recipe               | Set the recipe of the item. See [**Recipe**](../en-us/format/recipe.md) for details                                                                               |
| energy_capacity      | Charge capacity of rechargeable items, see below                                                                                                            |
| radiation            | Radiation level, see below                                                                                                                                  |
| rainbow              | Rainbow blocks, see below                                                                                                                                   |
| rainbow_materials    | Custom rainbow blocks, see below                                                                                                                            |
| anti_wither          | Anti-wither, see below                                                                                                                                      |
| soulbound            | Soulbound, see below                                                                                                                                        |
| piglin_trade_chance  | Piglin trade items, see below                                                                                                                               |
| vanilla              | Man-made items, see below                                                                                                                                   |
| hidden               | Hidden items, see below                                                                                                                                     |
| drop_from            | Drop from mining blocks, see below                                                                                                                          |

### Rechargeable items

```yaml
energy_capacity: <capacity>
```

The maximum capacity is 2,147,483,647.

*Tip: Rechargeable items that only add energy_capacity have no function. If you want rechargeable items to have other functions, you need to use scripts*

### Radiation

```yaml
radiation: <radiation level>
```

For details about the radiation level, see [Radiation](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/attributes/Radioactivity.html)

### Rainbow Blocks and Custom Rainbow Blocks

```yaml
rainbow: <type>
```

Rainbow block types include:

```yaml
GLASS_PANE (glass pane)
GLASS (glass)
STAINED_GLASS (stained glass)
STAINED_GLASS_PANE (stained glass pane)
WOOL (wool)
TERRACOTTA
TERRACOTTA_ALL
GLAZED_TERRACOTTA
```

```yaml
rainbow_materials:
- GRASS_BLOCK
- DIRT
```

Custom rainbow blocks, add block IDs in the above format

### Anti-Wither

```yaml
anti_wither: true/false
```

Note: Only blocks can set this option
When `anti_wither: true`, the block will not be destroyed by the wither

### Soul Binding

```yaml
soulbound: true/false
```

When `soulbound: true`, the item will not drop after the player dies

### Piglin Trade Items

```yaml
piglin_trade_chance: <1-100>
```

Set the item to be traded with piglins.
<br>When this option is set, RSC will automatically add recipe_type:
<br>Even if you set a different recipe_type

```yaml
recipe_type: BARTER_DROP # Piglin Trade
```

### Artificial Items

```yaml
vanilla: true/false
```

Similar to artificial diamonds, when `vanilla: true`, this item can be used as a vanilla item as a material for crafting items on a vanilla workbench

### Hidden Items

```yaml
hidden: true/false
```

When `hidden: true`, this item will not be displayed in the slime book

### Block Drops

```yaml
drop_from: PODZOL
```

Similar to Borax, this slime item is dropped by mining ash (see above Variable Soil ）
You can also set the drop chance and amount (same level as drop_from):

```yaml
drop_chance: <1-100> # Optional, default 100
drop_amount: 1 # Optional, default 1, supports drop_amount: 3-5 range
```

## Notes

Regarding the tags after item.#, this page only uses name, material, and amount as examples.
You can add more tags after amount.
For details, see [Universal Item Format](../en-us/format/universal-item-format.md)

Note that name and material are required.
If material_type is not filled in, the default detected material is the original item

### About the example script example_item_2 referenced on this page

See [Script Basics - Items](../en-us/scripts-basic/items.md) for details