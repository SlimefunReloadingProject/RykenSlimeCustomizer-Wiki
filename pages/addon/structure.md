# 附属结构

## 附属结构

RSC使用模块化的结构，不用让你在SC里烦躁的合并机器。结构树：

```
addons
    └─example
        |  armors.yml
        │  capacitors.yml
        │  generators.yml
        │  geo_resources.yml
        │  groups.yml
        │  info.yml
        │  items.yml
        │  machines.yml
        │  mat_generators.yml
        │  mb_machines.yml
        │  menus.yml
        │  mob_drops.yml
        │  recipe_machines.yml
        │  recipe_types.yml
        │  researches.yml
        │  solar_generators.yml
        │
        ├─saveditems
        │
        └─scripts
                example_item_2.js
                example_item_3.js
                example_machine.js
                example_machine_energy.js
                example_menu.js
```

| 文件夹名称      | 作用     |
| ---------- | ------ |
| addons     | 存放附属   |
| example    | 存放附属内容 |
| scripts    | 存放脚本文件 |
| saveditems | 存放保存物品 |
