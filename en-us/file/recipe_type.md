# Recipe Types (recipe_types.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

> These are recipe types for display purposes only.

**Example:**

```yaml
RSC_EXAMPLE_RECIPE_TYPE:
  material: "DIAMOND_BLOCK"
  name: "&eExample Recipe Type"
RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE:
  name: "&bExample Multi-block Machine"
  material: CRAFTING_TABLE
```

| Field                    | Description                                                                                                                         | Valid Input                                                         |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| *`RSC_EXAMPLE_RECIPE_TYPE` | The ID of the recipe type.<br>This ID must be unique and not match any other recipe type's ID! (See `Special Notes` for exceptions) | **Only uppercase letters, numbers, and underscores are supported!** |
| *material                  | Vanilla item                                                                                                                        | CRAFTING_TABLE                                                      |
| *name                      | The name of the recipe type                                                                                                         | "&bExample Multi-block Machine"                                     |

On this basis, you can add tags such as `modelId`, `lore`, `glow`, etc., see [Universal Item Format](../format/universal-item-format.md).

The recipe type ID here can be directly used for reference in `recipe_type`.

## Special Notes

In RSC, NULL corresponds to SC's NONE, that is:

```yaml
# SlimeCustomizer
recipe_type: NONE
```

In RSC, the following modification is needed:

```yaml
# RykenSlimeCustomizer
recipe_type: NULL
```

## More Recipe Types

You can set the recipe type to these (which are included with Slimefun),
but it does not mean that this recipe necessarily exists; however, you can still set a recipe to explain it.

[Reference Code](https://github.com/Slimefun/Slimefun4/blob/master/src/main/java/io/github/thebusybiscuit/slimefun4/api/recipes/RecipeType.java)

# Automatically set the type of recipe
```yaml
ARMOR_FORGE # Armor Forge
GRIND_STONE # Grindstone
SMELTERY # Smelting Furnace
ORE_CRUSHER # Ore Crusher
COMPRESSOR # Compressor
PRESSURE_CHAMBER # Pressure Chamber
MAGIC_WORKBENCH # Magic Workbench
ORE_WASHER # Ore Washer
ENHANCED_CRAFTING_TABLE # Enhanced Crafting Table
ANCIENT_ALTAR # Ancient Altar
JUICER # Juicer
HEATED_PRESSURE_CHAMBER # Heated Pressure Chamber
MOB_DROP # Mob Drop
```

# Display only types
```yaml
MULTIBLOCK # Multi-block Structure
GOLD_PAN # Gold Panning
BARTER_DROP # Barter Trade
INTERACT # Interaction
FOOD_FABRICATOR # Food Fabricator
FOOD_COMPOSTER # Food Composter
FREEZER # Freezer
REFINERY # Refinery
GEO_MINER # Geo Miner
NUCLEAR_REACTOR # Nuclear Reactor
NULL # None
```

# Recipe types that only support one item input
```yaml
- ENHANCED_CRAFTING_TABLE #Enhanced Crafting Table
- MAGIC_WORKBENCH #Magic Workbench
- ARMOR_FORGE #Armor Forge
- PRESSURE_CHAMBER #Pressure Chamber
- ANCIENT_ALTAR #Ancient Altar
```

# Recipe types where only the first slot item is valid for crafting
```yaml
- COMPRESSOR #Compressor
- PRESSURE_CHAMBER #Pressure Chamber
- ORE_CRUSHER #Ore Crusher
- GRIND_STONE #Grindstone
- ORE_WASHER #Ore Washer
- HEATED_PRESSURE_CHAMBER #Heated Pressure Chamber
- JUICER #Juicer
```


# Recipe type where all nine slots must have items for crafting
```yaml
- ANCIENT_ALTAR #Ancient Altar
```

# Recipe type where the fifth slot must be a spawn egg or empty
```yaml
- MOB_DROP Mob Drop
```