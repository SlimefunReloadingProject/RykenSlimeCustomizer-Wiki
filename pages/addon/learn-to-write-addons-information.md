# 编写附属信息(info.yml)

<mark style="color:red;background:transparent">注意：带*均为必填</mark>

**示例：**

```yaml
id: example
name: "示例附属"
depends: []
pluginDepends: []
version: "1.0"
authors: ["mmmjjkx"]
repo: ""
```

| 内容 | 描述 |
| --- | ----------- |
| \*id | 附属的id，在保存物品、卸载某个附属、设置附属前置时需要 |
| \*name | 附属的名称。 |
| \*depends | 依赖的其它用RykenSlimeCustomizer编辑的自定义附属id |
| pluginDepends | 依赖的插件名称，即在plugin.yml中定义的名称。 |
| version | 附属的版本，默认为1.0 |
| description | 附属的描述。 |
| \*authors | 附属的作者。 |
| repo | 附属的github仓库。 |
