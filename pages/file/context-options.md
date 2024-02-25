# 内容加载/注册选项

示例(不要照抄):

```yaml
EXAMPLE_FOR_REGISTER:
  lateInit: false
  register:
    warn: false
    conditions:
       - "hasplugin DyeBench"
       - "!hasplugin DynaTech"
```

## lateInit

设置内容是否等待所有**非延迟加载的内容加载、注册**完毕后再进行加载、注册（**最先检查**）

## register

设置内容注册选项。

### conditions

设置内容在注册时所需的条件。

| 条件名        | 解释      | 示例                   |
| ---------- | ------- | -------------------- |
| hasplugin  | 需要某插件   | hasplugin DyeBench   |
| !hasplugin | 不要某插件出现 | !hasplugin DynaBench |

### warn

设置当不满足内容注册条件时发出警告

### unfinished

设置内容是否未完成，如果内容未完成会直接跳过加载。


