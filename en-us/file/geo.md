# GEO Resources (geo_resources.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_GEO_RESOURCE:
  item_group: rsc_example_normal_group
  item:
    name: "&aExample Geo Resource Item"
    material: DIAMOND
  recipe_type: GEO_MINER
  max_deviation: 1
  obtain_from_geo_miner: true
  geo_name: "RSC Example Geo Resource"
  supply:
    normal:
      plains: 10
      ocean: 5
      others: 4
    nether: 1
    the_end: 2
  drop_from: PODZOL
  drop_chance: 10
  drop_amount: 3-5
```

| Field                        | Description                                                                                                 | Valid Input                                                     |
|------------------------------|-------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| \*`RSC_EXAMPLE_GEO_RESOURCE` | The ID of the natural resource. <br>This ID cannot be the same as any other item's ID!                      | **Only uppercase letters, numbers, underscores are supported!** |
| \*item_group                 | The ID of the [item group (category)](file/groups.md) that the natural resource belongs to.                 |
| \*item.#                     | [Universal Item Format](format/universal-item-format.md)                                                    | Optionally add modelId, lore, glow, etc.                        |
| recipe_type                  | See [Recipe Type](format/universal-item-format.md).                                                         |
| \*max-deviation              | Maximum deviation in the amount of the natural resource per block.                                          | Positive integer                                                |
| obtain_from_geo_miner        | Sets whether the natural resource can be mined from the GEO miner.                                          |
| \*geo_name                   | Set the name of the natural resource.                                                                       |
| \*supply                     | Set the default amount of natural resources in each world environment and biome, see the notes for details. |
| drop_from                    | Mining blocks drops, see below for details                                                                  |

### Block drops

```yaml
drop_from: PODZOL
```

Similar to borax, here this slime item is dropped by mining ash soil (refer to the above variable soil)

You can also set the drop probability and amount (same level as drop_from):

```yaml
drop_chance: <1-100> # Optional, default 100
drop_amount: 1 # Optional, default 1, support drop_amount: 3-5 This range format
```

## Notes

1. About supply
normal, nether, the\_end represents the three dimensions of the main world, the nether, and the end.
Plains and ocean represent the biomes of the Minecraft overworld.
Others represent other biomes in the Minecraft overworld, such as jungle, swamp, and desert.
The same applies to the biomes of the Nether and the End.
