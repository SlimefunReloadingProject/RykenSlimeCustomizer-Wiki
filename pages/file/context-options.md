# 内容加载/注册选项(任意.yml)
你可以为给附属添加的物品、机器等添加这些选项

示例(不要照抄):

```yaml
EXAMPLE_FOR_REGISTER:
  lateInit: false
  register:
    warn: false
    conditions:
       - "hasplugin DyeBench"
       - "!hasplugin DynaTech"
    unfinished: false
```

| 内容 | 描述 |
| -------- | -------- |
| `EXAMPLE_FOR_REGISTER` | 内容注册的ID，每个注册的ID不能相同。<br>**仅支持字母、数字、下划线!**<br>新分类系统不再强制使用小写字母，但从物品引用分类时，请注意分类ID的大小写。 |
| lateInit | 判断是否等待当前**addon所有**非延迟加载的内容加载、注册完毕后**再进行加载、注册（**最先检查**）。 |
| register.# | 设置注册选项。 |
| register.warn | 当不满足内容注册条件时发出警告。 |
| register.conditions | 详见**关于conditions**。 |
| register.unfinished | 设置当前内容是否未完成，如果内容未完成会直接跳过加载。 |

## 关于conditions

设置内容在注册时所需的条件。

| 条件名        | 解释      | 示例                   |
| ---------- | ------- | -------------------- |
| hasplugin  | 需要某插件   | hasplugin DyeBench   |
| !hasplugin | 与某插件冲突/不兼容 | !hasplugin DynaTech |
| version | 检查MC版本是否达到要求(使用>=,<=,>,<这些符号来判断) | version >= 1.20.1 |