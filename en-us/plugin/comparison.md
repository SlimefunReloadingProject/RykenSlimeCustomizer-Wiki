# Comparison and Overview

This page will systematically sort out the functions of RykenSlimeCustomizer (hereinafter referred to as **rsc**) and SlimeCustomizer (hereinafter referred to as **sc**), and simply and clearly list the advantages of rsc. You can also find the functions you want on this page

## Loading Differences

| Content | sc | rsc |
| --- | --- | --- |
| Custom loading options | ✕ | ✓ |
| Automatic update of addons | ✕ | ✓ |
| Coexistence of multiple configurations | ✕ | ✓ |
| Skip incorrect configuration | ✕ | ✓ |
| Preload all addon items | ✕ | ✓ |
| Reference sc items | - | ✓ |

Custom loading options: see [Content loading/registration options](/en-us/file/context-options.md)
<br>Automatically update addons: see [WWrite Addon Information](/en-us/addon/learn-to-write-addons-information.md)
<br>Preload all addon items: In the same addon, you can reference the contents of the following `machines.yml` in `items.yml`, without having to use `saveditem`
## Recipe writing class

Regarding recipe writing, rsc can **omit** recipe grids without items, while sc must write them step by step in a unified format

```yaml
# Compare
# sc
type: NONE

# rsc
# Yes, nothing needs to be written
```
For referencing vanilla items, sc must fill in VANILLA in the type column, while rsc only needs to fill in mc in the material_type column or directly ignore material_type

```yaml
# Compare
# sc
type: VANILLA
id: BARRIER
amount: 1

# rsc
material: BARRIER
```

## Recipe Tips

| Content | sc | rsc |
| --- | ----------- | ----------- |
| Original Slimefun Recipe Tips | ✓ | ✓ |
| Custom Recipe Tips | ✕ | ✓ |

rsc provides customizable recipe tips. If you want to implement this function in sc, you need to write an additional item to describe the recipe and then insert it into the synthesis recipe. The process is cumbersome.

## Item Class

sc only provides one configuration for item customization, which has less freedom and greater limitations.

rsc provides a general item template. All configurations can apply a unified template as long as they involve items.

And this template provides more diverse customization options.

The following table lists the differences between rsc and sc under various customization requirements in addition to basic customization functions.

| Content | sc | rsc |
| --- | ----------- | ----------- |
| saveitem (save item) | ✓ | ✓ |
| placeable (placeable item) | ✓ | ✓ |
| script (script) | ✕ | ✓ |
| reference skull block | hash only | hash, url, Base64 |
| glow enchantment effect | ✕ | ✓ |
| radiation/charged item | ✕ | ✓ |
| material model ID | ✕ | ✓ |
| hidden item | ✕ | ✓ |
| mining block drop | ✕ | ✓ |

sc can only realize radiation, food and other functions through the save item function, while rsc only needs to add one radiation item in the general item format to customize radiation, and customize food through the general script format

rsc is also beneficial to material makers, who can apply special materials to custom items

## Machine class

| Content | sc | rsc |
| --- | ----------- | ----------- |
| Custom machine menus | ✕ | ✓ |
| Apply another machine's menu | ✕ | ✓ |
| Custom input and output slots | ✕ | ✓ |
| Slimefun vanilla machine upgrade | ✕ | ✓ |
| Non-powered machines | ✕ | ✓ |
| Random output items | ✕ | ✓ |
| Custom energy types | ✕ | ✓ |
| Machine scripts | ✕ | ✓ |

The configuration of machines in sc only includes `machine.yml`, and the machine menu is single, the number of inputs and outputs is single, and the function is single, but the writing is relatively simple

The configuration of machines in rsc includes `machine.yml` (machine without input and output, script template required), `recipe_machines.yml` (recipe machine), `simple_machines.yml` (simple machine), which can customize the machine menu and has various functions

rsc can customize energy types such as energy nodes by editing energy types (`energy.type`) in `machine.yml`

`simple_machines.yml` in rsc provides the author with a simple advanced version of the slime original machine, while adding similar machines in sc is particularly cumbersome, and the input and output items need to be filled in one by one

## Multi-block machine class

rsc can customize **multi-block machines**, see [multi-block machines](/en-us/file/multi-block-machine.md) for details, but sc cannot

## Solar generator class

rsc can customize the **light intensity limit** that the solar generator needs to reach, but sc cannot

## Material generator class

rsc can customize the **slot** that displays information, but sc cannot

## Research class

rsc can customize the **Vault economy** required to unlock the research, but sc cannot

## Script class

Scripts are a unique feature of rsc, and various props, food, machines, etc. can be customized through scripts

*You can understand it as writing plug-ins in rsc*

See [Script-Introduction](/en-us/scripts-basic/introduction.md) for details

## Inherited item class

Inherited items are a unique feature of rsc, and the mechanism of other attached items or machines can be copied through inherited items

See [Inherited items](/en-us/file/supers.md) for details