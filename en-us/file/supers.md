# Super Items (supers.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_SUPER_ITEM:
  item_group: rsc_example_sub_group
  item:
    material: MUSIC_DISC_PIGSTEP
    name: "&b&lSuper&7Storage Cell"
    lore:
      - "&eSuper test item"
  class: "me.ddggdd135.slimeae.core.slimefun.MEItemStorageCell" # From an addon
  args: [50000]
  register:
    conditions:
       - "hasplugin SlimeAE"
```

| Field                    | Description                                                                                         | Valid Input                                                            |
|----------------------------|-----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
| \*`RSC_EXAMPLE_SUPER_ITEM` | The ID of the inherited item. <br>This ID cannot be the same as any other item's ID!                | **Only uppercase letters, numbers, underscores are supported!**        |
| \*item_group               | The ID of the [item group (category)](/en-us/file/groups.md) that the item belongs to.                     |
| \*item.#                   | [Universal Item Format](/en-us/format/universal-item-format.md)                                            | Optionally add `modelId`, `lore`, `glow`, etc.                         |
| recipe_type                | See [Recipe Type](/en-us/file/recipe_type.md).                                                             |
| recipe                     | Set the recipe for the inherited item. See [**Recipe**](/en-us/format/recipe.md) for details               |
| \*class                    | Set which item to inherit. Here you need to fill in the full class name of the item to be inherited | org.example.project.ExampleClass                                       |
| \*args                     | Complete other construction parameters of the inherited item                                        |
| ctor                       | Set which constructor of the inherited item to use. The position starts from 0                      |
| arg_template               | Set the input position of the default construction parameter                                        | [group, item, recipe_type, recipe]                                     |
| method                     | Some methods of this inherited item can be used to modify some values                               | See **Use method to modify some values** below for details             |
| field                      | Modify some fields of this inherited item                                                           | See **Use field to modify the value of some fields** below for details |

## Use method to modify some values
Suppose we inherit a slime original machine, here we use [CarbonPress (Carbon Press)](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/implementation/items/electric/machines/CarbonPress.html) as an example

The current configuration is as follows:

```yaml
RSC_EXAMPLE_SUPER_CARBON_PRESS:
  item_group: example_sub_group
  item:
    material: FURNACE
    name: "&b&lSuper &7Carbon Press"
  class: "io.github.thebusybiscuit.slimefun4.implementation.items.electric.machines.CarbonPress"
```

At this time, if you need to set its efficiency, energy capacity, etc., you can do this:

```yaml
RSC_EXAMPLE_SUPER_CARBON_PRESS:
  item_group: example_sub_group
  item:
    material: FURNACE
    name: "&b&lSuper &7Carbon Press"
  class: "io.github.thebusybiscuit.slimefun4.implementation.items.electric.machines.CarbonPress"
  #Added code
  method:
    setCapacity: 50000
    setProcessingSpeed: 20
```
Then you get a super carbon press with an energy capacity of 50,000 and an efficiency of 20x

## Use field to modify the value of some fields
There is no good class, for example, at present...
Waiting for supplement...

**Note: You cannot modify constants (variables modified by final in class) and static variables (variables modified by static)**