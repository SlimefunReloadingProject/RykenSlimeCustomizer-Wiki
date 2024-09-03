# Item Groups(Categories)（groups.yml）

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
rsc_example_normal_group:
  item:
    name: "&aExample Normal Group"
    material: GRASS_BLOCK

rsc_example_parent_group:
  type: nested
  item:
    name: "&aExample Parent Group"
    material: OAK_PLANKS

rsc_example_sub_group:
  type: sub
  parent: "rsc_example_parent_group"
  item:
    name: "&eExample Sub Group"
    material: REDSTONE

rsc_example_seasonal_group:
  type: seasonal
  month: 5
  item:
    name: "&bExample Seasonal Group"
    material: OAK_LEAVES

rsc_example_locked_group:
  type: locked
  parents:
    - slimefun:basic_machines
  item:
    name: "&lExample Locked Group"
    material: REPEATER

rsc_example_tier_10086_group:
  type: sub
  parent: rsc_example_parent_group
  tier: 10086
  item:
    name: "&eExample Tier 10086 Group"
    material: IRON_ORE

rsc_example_link_group:
  type: button
  parent: rsc_example_parent_group
  item:
    name: "&eExample Link Group"
    material: COMMAND_BLOCK
  actions:
  - "link https://rsc.himcs.top/#/README"

rsc_example_console_group:
  type: button
  parent: rsc_example_parent_group
  item:
    name: "&eExample Console Command Group"
    material: BEDROCK
  actions:
  - "console say Hello, world!"

```

| Field                    | Description                                                                                                                                                                                                                                                                                |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \*`example_normal_group` | The ID of the category. Each category ID cannot be the same. <br>**Only letters, numbers, and underscores are supported!**<br>The new category system no longer forces lowercase letters, but when referencing categories from items, please pay attention to the case of the category ID. |
| type                     | (**Required**) The type of the category. See the notes below for available types.                                                                                                                                                                                                          |
| \*item.#                 | [Universal Item Format](../en-us/format/universal-item-format.md)                                                                                                                                                                                                                                | Optionally add `modelId`, `lore`, `glow`, etc. |
| tier                     | (*Optional*) The priority of the category. The default is 3. <br>The priority of a category is an integer. Categories with lower priority will be displayed first.                                                                                                                         |
| parent                   | (**Required** when the category type is subcategory `sub`) The ID of the parent category. <br>It can only be the parent category ID defined in the custom attachment.                                                                                                                      |
| month                    | (**Required** when the category type is seasonal category `seasonal`) The month of the seasonal category, ranging from 1 to 12.                                                                                                                                                            |
| parents                  | (**Required** when the category type is locked category `locked`) The `NamespacedKey` list of other categories required for the locked category. <br>See [Slimecustomizer wiki](https://slimefun-addons-wiki.guizhanss.cn/slime-customizer/Categories) for details.                        |
| actions                  | Format as below                                                                                                                                                                                                                                                                            |

```yaml
actions:
- "link THE_LINK_URL" # A clickable link pops up in the chat bar after the player clicks on this category
- "console THE_CONSOLE_COMMAND" # A command is executed in the console after the player clicks on this category
```

## Notes

1. The default type of the category is normal
2. Item group types:

| Type | Description |
| -------------- | ---------------------- |
| normal | Normal item group |
| locked | Locked item group |
| seasonal | Seasonal item group |
| nested, parent | Nested item group (parent item group) |
| sub | Sub-item group (parent item group name must be written in the parent column) |
| button | Button group (actions must be filled in, the rest is the same as the sub-item group) |

3. **When the item group type is a locked item group, you need to fill in the **`NamespacedKey`** of the parent category instead of directly referencing the item group in the attached.**
