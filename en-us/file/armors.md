# Armors(armors.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
rsc_example_armor:
  protection_types:
    - BEES
    - RADIATION
    - FLYING_INTO_WALL
  fullSet: true
  item_group: rsc_example_normal_group
  helmet:
    id: RSC_EXAMPLE_HELMET
    material: LEATHER_HELMET
    name: "&dExample Helmet"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      3:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
  chestplate:
    id: RSC_EXAMPLE_CHESTPLATE
    material: LEATHER_CHESTPLATE
    name: "&dExample Chestplate"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      4:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
  leggings:
    id: RSC_EXAMPLE_LEGGINGS
    material: LEATHER_LEGGINGS
    name: "&dExample Leggings"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      5:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
  boots:
    id: RSC_EXAMPLE_BOOTS
    material: LEATHER_BOOTS
    name: "&dExample Boots"
    recipe_type: RSC_EXAMPLE_MULTIBLOCK_MACHINE_RECIPE_TYPE
    recipe:
      6:
        material_type: slimefun
        material: RSC_EXAMPLE_ITEM_2
    potion_effects:
      - "SPEED 5"
```

| Fields                             | Description                                                                                                             | Valid inputs |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------|--------------|
| \*`rsc_example_armor`              | NamespacedKey of the armor set.                                                                                         |              |
| \*item_group                       | ID of the [item group (category)](../en-us/file/groups.md) that the armor belongs to.                                         |
| fullSet                            | Whether the armor is required to form a set for the protection type and potion effect to take effect                    |
| protection_types                   | Protection types, see below                                                                                             |
| \*helmet/chestplate/leggings/boots | Helmets/chestplates/leggings/boots, follow the [universal item format](../en-us/format/universal-item-format.md)              |
| potion_effects                     | The potion effect given when wearing the armor is in the format of potion effect ID + potion level **(number+1) level** |
| recipe, etc.                       | Follow the [universal item format](../en-us/format/universal-item-format.md)                                                  |

## Protection Types

See [armor protection types](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/core/attributes/ProtectionType.html)