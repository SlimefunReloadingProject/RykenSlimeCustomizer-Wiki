# Mob Drops (mob_drops.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
RSC_EXAMPLE_MOB_DROP:
  item_group: rsc_example_sub_group
  entity: IRON_GOLEM
  chance: 60
  item:
    name: "&aExample Mob Drop Item"
    material: IRON_INGOT
```

| Field                 | Description                                                                                                                              | Valid Input                                                         |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| *`RSC_EXAMPLE_MOB_DROP` | The ID of the mob drop.<br>This ID must be unique and not match any other item's ID!                                                     | **Only uppercase letters, numbers, and underscores are supported!** |
| *item_group             | The ID of the [item group (category)](groups.md) where the item belongs.                                                                 |
| *entity                 | The [entity type](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html) that needs to be killed to drop this item. |
| *chance                 | The drop chance of the item (percentage), value range: 1 - 100                                                                           |
| *item.#                 | See [Universal Item Format](../format/universal_item_format.md)                                                                          | Optional additions such as modelId, lore, glow, etc. are available. |
