# 附属结构

## 附属结构

RSC使用模块化的结构，不用让你在SC里烦躁的合并机器。结构树：

```
addons
    └─example
        │  generators.yml
        │  geo_resources.yml
        │  groups.yml
        │  info.yml
        │  items.yml
        │  machines.yml
        │  mat_generators.yml
        │  menus.yml
        │  researches.yml
        │
        └─scripts
                example_item_2.js
                example_machine.js
                example_machine_energy.js
        └─saveditems  
```

| 文件夹名称      | 作用     |
| ---------- | ------ |
| addons     | 存放附属   |
| example    | 存放附属内容 |
| scripts    | 存放脚本文件 |
| saveditems | 存放保存的物 |

