# Machine Menus (menus.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

> Common elements that are almost necessary for all machines.

**Example:**

```yaml
RSC_EXAMPLE_MACHINE:
  title: "&aExample Menu"
  script: "example_menu"
  slots:
    0-8:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    18-30:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    32-39:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    40:
      name: "&aWorking Button"
      material: GREEN_STAINED_GLASS_PANE   
    41-44:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
RSC_EXAMPLE_GENERATOR:
  title: "&cExample Generator"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    4:
      name: "&aInformation"
      progressbar: true
      material: GREEN_STAINED_GLASS_PANE
    5-9:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    12-14:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    17-26:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
RSC_EXAMPLE_MATERIAL_GENERATOR:
  title: "&dExample Material Generator"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    # Note, it is not recommended to place items in the 4th slot, as this has been set to display information. 
    # You can modify the `status` parameter in the material generator configuration.
    # 4:
    #   name: "&aInformation"
    #   material: GREEN_STAINED_GLASS_PANE
    5-12:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    14-17:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
RSC_EXAMPLE_RECIPE_MACHINE:
  title: "&cExample Recipe Machine"
  slots:
    0-3:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    4:
      name: "&aInformation"
      material: GREEN_STAINED_GLASS_PANE
      progressbar: true
    5-9:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    12-14:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
    17-26:
      name: "&a"
      material: BLACK_STAINED_GLASS_PANE
```

| Field                  | Description                                                                                                                                         | Valid Input                                                         |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| *`RSC_EXAMPLE_MACHINE` | The ID of the menu, which must match the corresponding machine ID.                                                                                  | **Only uppercase letters, numbers, and underscores are supported!** |
| *title                 | The name of the menu, usually displayed in the top left corner of the chest page.                                                                   |
| slots                  | The slots of the chest page, where an item can be arranged in one or more slots.                                                                    |
| slots.(number)         | The corresponding number of the slot.                                                                                                               |
| progressbar            | Set this item as the machine's progress bar item.                                                                                                   |
| import                 | Import the menu from the machine with the corresponding ID, see notes for details.                                                                  |
| script                 | The script referenced by the menu, set the script file corresponding to the menu, fill in the script's corresponding file name inside double quotes |

## Notes

1. Regarding `import`

```yaml
RSC_EXAMPLE_RECIPE_MACHINE:
  title: "&cExample Recipe Machine"
  import: machine_id
```

If you use `import`, you can omit writing `slots`,
but the corresponding `input` and `output` of the custom machine still need
to fill in the numbers of the corresponding slots.

2. If you want to add a custom menu to a machine, the **machine's `id`** and the **menu's `id`** must be consistent!

### Regarding the example script example_menu referenced on this page
See [Script Basics - Machine Menus](/en-us/scripts-basic/machine_menus.md)
