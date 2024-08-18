# No input and output machines(machines.yml)

!> The script feature in here is completely unusable! So you can only use it for some other machines' recipe.

<mark style="color:red;">**Note: Fields with * are required**</mark>

<b>Note:</b> This configuration custom machine cannot customize input and output items! (To customize a machine with custom input and output items, see [Recipe Machines](file/recipe_machines.md) for details, or check the recipe in the script)

**Example:**

```yaml
RSC_EXAMPLE_MACHINE:
  item_group: rsc_example_sub_group
  item:
    name: "&bExample Machine"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_ITEM3
  input: [9, 10, 11, 12, 13, 14, 15, 16, 17]
  output: [31]
  script: "example_machine"
  work: 0
RSC_EXAMPLE_MACHINE_ENERGY:
  item_group: rsc_example_sub_group
  item:
    name: "&bExample Energy Machine"
    material: DIAMOND_BLOCK
  recipe_type: ENHANCED_CRAFTING_TABLE
  energy:
    capacity: 100000
    type: NONE
  recipe:
    1:
      material_type: slimefun
      material: RSC_EXAMPLE_MACHINE
  input: []
  output: []
  script: "example_machine_energy"
```

| Field                   | Description                                                                                                                                                  | Valid Input                                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| \*`RSC_EXAMPLE_MACHINE` | The ID of the machine. <br>This ID cannot be the same as any other item's ID!                                                                                | **Only uppercase letters, numbers, and underscores are supported!** |
| \*item_group            | The ID of the [item group (category)](groups.md) that the item belongs to.                                                                                   |
| \*item.#                | [Universal Item Format](../format/universal-item-format.md)                                                                                                  | Optionally add modelId, lore, glow, etc.                            |
| recipe_type             | See [Recipe Type](recipe_type.md).                                                                                                                           |
| script                  | The script referenced by the item, set the script file corresponding to the item, and fill the double quotes with the file name corresponding to the script. |
| recipe                  | Set the recipe for the machine. See [**Recipe**](../format/recipe.md) for details                                                                            |
| \*input                 | The corresponding slots for item input. (Please do not set items for these slots in the menu!)                                                               |
| \*output                | The corresponding slots for item output. (Please do not set items for these slots in the menu!)                                                              |
| energy                  | Set the energy of the machine. If this is not set or loading/reading fails, it will be automatically set to a non-powered machine.                           |
| energy.capacity         | Set the energy that the machine can store, with a maximum of 2147483647.                                                                                     |
| energy.type             | The type of the machine as an energy component. For details, see the notes                                                                                   |
| work                    | Set the work button slot of the non-powered machine. If this tag is not available, the default is -1 (not set).                                              |

## Notes

1. If you set a script file, the `function will be called when calculating the slime tick tick(info)`, the parameter passed is [**MachineInfo**](https://github.com/SlimefunReloadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/machine/MachineInfo.java) (the powerless machine is [**SmallerMachineInfo**](https://github.com/SlimefunRe loadingProject/RykenSlimeCustomizer/blob/main/src/main/java/org/lins/mmmjjkx/rykenslimefuncustomizer/objects/m achine/SmallerMachineInfo.java))

2. work is a label exclusive to non-powered machines. If the corresponding script file is set, you can get the `working` object (check whether it is working) and set the machine working status through `setWorking(Boolean value)`. If you click the working button once, `working=true`

3. For energy.type, see [**EnergyNetComponentType**](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/networks/energy/EnergyNetComponentType.html) for all available items

The following is the explanation of EnergyNetComponentType

| Type      | Description                                                          |
|-----------|----------------------------------------------------------------------|
| CAPACITOR | Capacitor, used to store energy in the energy network                |
| CONNECTOR | Connector, used to transmit energy                                   |
| CONSUMER  | Electrical appliance, consumes energy from the energy network        |
| GENERATOR | Generator, in the energy network that generates and transmits energy |
| NONE      | None, the machine cannot be classified as any of the above options   |

4. About machine energy settings

If **energy is not set** or **load/read fails**, it will automatically be set to a non-powered machine

## Others

If you want to customize the machine menu in machine.yml, see [Machine Menu](menu.md) for details.