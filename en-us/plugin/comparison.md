# Comparison and Overview

This page will list and compare the features of RykenSlimeCustomizer (**RSC**) and SlimeCustomizer (**SC**).

## Loading

| Feature | SC | RSC |
| --- | --- | --- |
| Custom loading options | ✕ | ✓ |
| Auto update of configurations | ✕ | ✓ |
| Coexistence of multiple configurations | ✕ | ✓ |
| Skip problematic items | ✕ | ✓ |
| Preload addon items | ✕ | ✓ |
| Reference SC items | - | ✓ |

Custom loading options: see [Content loading/registration options](/en-us/file/context-options.md)  
Auto update configurations: see [Addon Information](/en-us/addon/learn-to-write-addons-information.md)
Preload all addon items: In a configuration module, you can reference the items from `machines.yml` in `items.yml`, without having to use `saved item` to save machines.

## Recipes

Regarding recipe configuration, RSC can **omit** recipe slots without items, while SC must write every slot and use `NONE` to represent an empty slot.

```yaml
# Compare
# sc
type: NONE

# rsc
# Yes, nothing needs to be written
```

For referencing vanilla items, SC must fill in `VANILLA` in the `type` field, while RSC only need a `material` field.

```yaml
# Compare
# sc
type: VANILLA
id: BARRIER
amount: 1

# rsc
material: BARRIER
```

## RecipeType

| Feature | SC | RSC |
| --- | ----------- | ----------- |
| Standard RecipeType | ✓ | ✓ |
| Custom RecipeType | ✕ | ✓ |

A RecipeType usually tells the player where to craft the item.

In SC, you cannot add new RecipeTypes. You will have to set recipe type to `NULL`, then save and reference the recipe type item in the recipe.
However in RSC, you can simply add new RecipeTypes by editing `recipe_type.yml`.

## Items

SC only provides 1 configuration file to customize items (`items.yml`), which has less freedom and more limitations.

RSC provides a general item template. All configurations can use more types of items by applying the template.

The following table lists the differences between SC and RSC under various customization requirements in addition to basic customization functions.

| Feature | SC | RSC |
| --- | ----------- | ----------- |
| saved item | ✓ | ✓ |
| placeable | ✓ | ✓ |
| script | ✕ | ✓ |
| player head | hash only | hash, url, base64 |
| glow enchantment effect | ✕ | ✓ |
| radioactive/chargeable item | ✕ | ✓ |
| custom model data | ✕ | ✓ |
| hidden item | ✕ | ✓ |
| drop from block breaking | ✕ | ✓ |

In SC, you can achieve limited functions through the `saved item` function (e.g. radiation, food), while RSC only needs to add a radiation item in the general item template to customize radiation, and customize food through the general script template.
RSC is also beneficial to resource pack makers, they can apply custom model data to custom items directly in RSC, without the need to set up them in Slimefun's item-models.yml.

## Machines

| Feature | SC | RSC |
| --- | ----------- | ----------- |
| Custom machine menu | ✕ | ✓ |
| Use another machine's menu | ✕ | ✓ |
| Custom input and output slots | ✕ | ✓ |
| Slimefun core machine upgrade | ✕ | ✓ |
| Machines that don't need energy | ✕ | ✓ |
| Random output items | ✕ | ✓ |
| Custom energy types | ✕ | ✓ |
| Machine scripts | ✕ | ✓ |

In SC, there is only 1 configuration file for machines (`machine.yml`), and all machines have the same layout, fixed number of input and output slots, and same function, which is relatively simple to write.

In RSC, there are more configuration files for machines:

- `machine.yml` (machine without input and output, scripts required)
- `recipe_machines.yml` (SC type machines)
- `simple_machines.yml` (extended version of Slimefun core machines)

You can also customize the machine layout, input and output slots, energy types (the machine is a consumer, a producer, or a connecting node?), and scripts.

## Multi-block machines

RSC provides **multi-block machines** customization, see [multi-block machines](/en-us/file/multi-block-machine.md) for details.

There is no such feature in SC.

## Solar generators

In RSC, you can customize the **light level** that the solar generator needs to reach. Not available in SC.

## Material generators

In RSC, you can customize **material generators** to generate multiple items. Not available in SC.

## Researches

In RSC, you can customize the research.

You can also set the money requirement (**Vault** required) to unlock the research.

## Scripts

Scripts are a unique feature of RSC, and various items, food, machines, etc. can be customized through scripts.

*You can understand it as writing plug-ins in rsc*

See [Script Introduction](/en-us/scripts-basic/introduction.md) for details.

## Inherited items

Inherited items are a unique feature of RSC. The "inherit" is programming term, which is to extend any `SlimefunItem` class from any addon.

See [Inherited items](/en-us/file/supers.md) for details.
