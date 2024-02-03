# 编写附属信息

**示例：**
```yml
id: example
name: "示例附属"
depends: []
pluginDepends: []
version: "1.0"
```

## 解析

### id
设置附属的id，这是必不可少的。在保存物品、卸载某个附属、设置附属前置时需要。

### name
设置附属名称，这是必不可少的。

### depends/pluginDepends
设置附属前置。前置前者是rsc附属，后者是服务器插件。

### version
设置附属版本。默认1.0(*~~偷懒写版本不是一个好习惯哦~~*)
