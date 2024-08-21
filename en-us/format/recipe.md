# Recipe

The format of the recipe is roughly the same as SC, with each grid representing an item
(**For writing method, refer to the universal item format**).

Format:

```yaml
recipe:
1:
  material: cobblestone
2:
  material_type: none
3:
  material_type: slimefun
  material: REINFORCED_ALLOY_INGOT
4:
  ...
5:
  ...
6:
  ...
7:
  ...
8:
  ...
9:
  ...
```

If some grids do not need to be filled with items, it will be faster to write like this,
as shown in the following example:

```yaml
recipe:
1:
  ...
3:
  ...
5:
  ...
7:
  ...
9:
  ...
```

Of course, if the item is not craft able, the recipe can be omitted (i.e., left blank).

## Application

See [**Configuration file - items**](/en-us/file/items.md) for details.