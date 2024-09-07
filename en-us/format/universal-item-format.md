# Universal item format

<mark style="color:red;">**Note:**</mark>Fields with \* are required

### \*Name

Set the item name.

```yaml
name: "Item Name"
```

### Amount

Set the item amount.

Note:
**This function** is only available** when setting** items,
recipes, menus, material generators, generator inputs and outputs.
The default value is 1.
<br>Valid range: -1 ~ 64
<br>RSC does not check any item amount that exceeds the original limit
<br>If there are any related errors, please do not contact RSC's developers and support teams.

```yaml
amount: (number)
```

### Material type

This function determines the type of the item. If this tag is not added, the default value is mc.

| Type          | Description            |
|---------------|------------------------|
| mc (default)  | Vanilla Minecraft item |
| skull\_base64 | Skull item             |
| skull\_url    | Skull item             |
| skull\_hash   | Skull item             |
| slimefun      | Slimefun item             |
| none          | No item                |
| saveditem     | Saved item             |

```yaml
material_type: (material type)
```

#### Detailed explanation

1. skull\_base64 needs you to fill in the skull's Value in the material column

Example:

```yaml
material: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYmIwZjcyMmFlYzI3NDkwY2YwNTZmNTYwYWZkZDQ1N2EwYTc5NGU3MDM1NTZjYzRjM2I1MWE1ODJmNWM1N2FhNCJ9fX0=
```

2. skull_url needs you to fill in the website that starts with https and points to the image in the material column

Example:

```yaml
material: http://textures.minecraft.net/texture/bb0f722aec27490cf056f560afdd457a0a794e703556cc4c3b51a582f5c57aa4
```

3. skull\_hash needs you to fill in the Minecraft URL of the skull in the material column

Example:

```yaml
material: bb0f722aec27490cf056f560afdd457a0a794e703556cc4c3b51a582f5c57aa4
```

4. slimefun

When `material_type: slimefun`, you can add `glow` at the same level,
modify `name` and `lore`, which can be used to edit a slime item without changing the material of the item,
which can be used as the output item of the machine.

### \*Material

Set the material of the item. The content is determined by the material type.

For example, for `slimefun` material type, write the Slimefun item ID here.

For heads, write url or base64 or hash.

**Note: Please do not set the item material to air! **

```yaml
material: <material>
```

### Model ID

Set the model id of the item. This is not unfamiliar to people who make texture packs.

```yaml
modelId: (model id)
```

### Item description

Set the item lore.

```yaml
lore:
- "First line"
- "Line 114514"
```

### Glow

Make the item glow (with a layer of enchantment effect). If this tag is not added, the default value is false.

```yaml
glow: true/false
```