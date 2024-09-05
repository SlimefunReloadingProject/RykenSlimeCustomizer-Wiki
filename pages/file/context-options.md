# 内容加载/注册选项(任意.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

本页方法适用于所有配置，你可以为任意物品添加下述条目。

**示例(不要照抄)：**

```yaml
OBJECT_FOR_REGISTER_1:
  lateInit: false
  register:
    warn: false
    conditions:
       - "!hasplugin DynaTech" # 意为：与DynaTech冲突/不兼容
       - "version < 1.18.1" # 意为：需要MC版本低于1.18.1
    unfinished: false
OBJECT_FOR_REGISTER_2:  # 此处ID必须与上面的不同
  id_alias: OBJECT_FOR_REGISTER_1 # 此处ID必须与上面的相同
  lateInit: false
  register:
    warn: false
    conditions:
       - "hasplugin DynaTech" # 意为：需要DynaTech才能加载
       - "version >= 1.18.1" # 意为：需要MC版本高于或等于1.18.1
    unfinished: false
```

| 内容 | 描述 |
| -------- | -------- |
| `OBJECT_FOR_REGISTER_2` | 内容注册的ID，每个注册的ID不能相同。<br>**仅支持字母、数字、下划线!**<br>新分类系统不再强制使用小写字母，但从物品引用分类时，请注意分类ID的大小写。 |
| id_alias | 详见**关于 id_alias**。 |
| lateInit | 判断是否等待**当前addon所有**非延迟加载的内容加载、注册完毕后**再进行加载、注册**（**最先检查**）<br>注意：研究无论如何都是**最后加载** |
| register.warn | 当不满足内容注册条件时发出警告。 |
| register.conditions | 详见**关于 conditions**。 |
| register.unfinished | 设置当前内容是否未完成，如果内容未完成会直接跳过加载。 |

## 关于 id_alias

**使用此参数后的id作为注册id**（可用于为你的附属进行多版本兼容）
<br>即注册id改为`OBJECT_FOR_REGISTER_1`，而不是 `OBJECT_FOR_REGISTER_2`
<br>**注意**：`OBJECT_FOR_REGISTER_1`必须是**注册失败或不存在**

## 关于 conditions

设置内容在注册时所需的条件。

| 条件名        | 解释      | 示例                   |
| ---------- | ------- | -------------------- |
| hasplugin  | 需要某插件   | hasplugin DyeBench   |
| !hasplugin | 与某插件冲突/不兼容 | !hasplugin DynaTech |
| version | 检查MC版本是否达到要求(使用>=,<=,>,<这些符号来判断) | version >= 1.18.1 |
