# Simple Machines (simple_machines.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EX_ADVANCED_GOLD_PAN:
  item_group: rsc_example_sub_group
  item:
    material: FURNACE
    name: "&b&lSuper &7Gold Pan"
    lore:
      - "&7A much faster gold panning machine"
      - ""
      - "&8⇒ &e⚡ &7Speed: 50x"
      - "&8⇒ &e⚡ &7Energy Consumption: 1,000 J/s"
  type: ELECTRIC_SMELTERY
  settings:
    capacity: 5000
    consumption: 1000
    speed: 50
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    2:
      material_type: slimefun
      material: GOLD_PAN
    4:
      material_type: slimefun
      material: ELECTRIC_MOTOR
    5:
      material_type: slimefun
      material: ELECTRIC_GOLD_PAN_3
    6:
      material_type: slimefun
      material: ELECTRIC_MOTOR
    7:
      material_type: slimefun
      material: COBALT_INGOT
    8:
      material_type: slimefun
      material: BLISTERING_INGOT_3
    9:
      material_type: slimefun
      material: COBALT_INGOT
```

| Field | Description | Valid Input |
| --- | ----------- | ----------------- |
| *`RSC_EX_ADVANCED_GOLD_PAN` | The ID of the machine.<br>This ID must be unique and not match any other item's ID! | **Only uppercase letters, numbers, and underscores are supported!** |
| *item_group | The ID of the [item group (category)] where the item belongs. |
| *item.# | [Universal Item Format] | Optional additions such as modelId, lore, glow, etc. are available. |
| *type | Type of simple machine, see notes for details. |
| *settings.capacity | The amount of energy the machine can store, maximum is 2147483647. |
| *settings.consumption | The energy consumption of the machine when operating, maximum is 2147483647. |
| *settings.speed | The speed of the machine, maximum is 2147483647, the larger the number, the faster the machine runs. |
| recipe_type | See [Recipe Type]. |
| recipe | Sets the recipe for the machine. See [**Recipe**]. |

## Notes
1. Regarding simple machine types (type)

Simple machine types include the following:

```yaml
ELECTRIC_SMELTERY          # Electric Smelter
ELECTRIC_FURNACE         # Electric Furnace
ELECTRIC_GOLD_PAN         # Electric Gold Pan
ELECTRIC_DUST_WASHER     # Electric Dust Washer
ELECTRIC_ORE_GRINDER     # Electric Ore Grinder
ELECTRIC_INGOT_FACTORY   # Electric Ingot Factory
ELECTRIC_INGOT_PULVERIZER # Electric Ingot Pulverizer
CHARGING_BENCH           # Charging Bench
TREE_GROWTH_ACCELERATOR  # Tree Growth Accelerator
ANIMAL_GROWTH_ACCELERATOR # Animal Growth Accelerator
CROP_GROWTH_ACCELERATOR  # Crop Growth Accelerator
FREEZER                  # Freezer
CARBON_PRESS             # Carbon Press
ELECTRIC_PRESS           # Electric Press
ELECTRIC_CRUCIBLE        # Electric Crucible
FOOD_FABRICATOR          # Food Fabricator
HEATED_PRESSURE_CHAMBER  # Heated Pressure Chamber
AUTO_ENCHANTER           # Auto Enchanter
AUTO_DISENCHANTER        # Auto Disenchanter
BOOK_BINDER              # Book Binder
AUTO_ANVIL               # Auto Anvil
AUTO_DRIER               # Auto Dryer
AUTO_BREWER             # Auto Brewer
REFINERY                 # Refinery
PRODUCE_COLLECTOR        # Produce Collector
```

2. Parameters required for specific machine types

```yaml
# Format
settings:
  radius: 10 # Range. Optional, default is 1
  repair_factor: 10 # Repair factor. Optionally, default is 10
```

| Machine Type              | Parameter     | Parameter Type | Optional | Default Value | Additional Information         |
|---------------------------|---------------|----------------|----------|---------------|--------------------------------|
| Auto Anvil                | repair_factor | int            | Yes      | 10            | Value for single repair        |
| Tree Growth Accelerator   | radius        | int            | Yes      | 1             | Effective range of the machine |
| Animal Growth Accelerator | radius        | int            | Yes      | 1             | Effective range of the machine |
| Crop Growth Accelerator   | radius        | int            | Yes      | 1             | Effective range of the machine |
