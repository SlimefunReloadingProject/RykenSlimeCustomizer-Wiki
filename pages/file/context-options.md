# 内容加载/注册选项(任意.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于适配引用了其它附属内物品的相关自定义物品/机器等（当一个附属不是你设置的depend时）。

> 也可用于适配特定我的世界版本可加载的物品，即我的世界版本适配。

> 这些选项适用于所有配置文件

**示例(不要照抄)：**

```yaml
OBJECT_FOR_REGISTER_2:
  id_alias: OBJECT_FOR_REGISTER_1
  lateInit: false
  register:
    warn: false
    conditions:
       - "hasplugin DyeBench"
       - "!hasplugin DynaTech"
       - "version >= 1.18.1"
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
| config.boolean | 检查配置文件某一项的布尔值是否为true(真) | config.boolean isSomethingEnabled |
| config.int | 检查配置文件某一项的数字值是否达到要求(使用>=,<=,>,<这些符号来判断) | config.int theIntValue >= 64 |
| config.string | 检查配置文件某一项的值是否跟目标字符串相同 | config.string theStringValue 你好 |