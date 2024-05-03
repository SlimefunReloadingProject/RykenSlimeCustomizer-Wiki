# 继承物品(supers.yml)

示例：

```yaml
EXAMPLE_SUPER_ITEM:
  item_group: example_sub_group
  item:
    material: MUSIC_DISC_PIGSTEP
    name: "&b&l超级&7存储元件"
    lore:
      - "&e继承测试"
  class: "me.ddggdd135.slimeae.core.slimefun.MEItemStorageCell" # 来自 SlimeAE
  args: [50000]
  register:
    conditions:
       - "hasplugin SlimeAE"
```
