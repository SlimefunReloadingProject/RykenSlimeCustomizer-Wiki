# 让你的附属可更新

示例附属信息文件:

```yaml
id: example
name: "示例附属"
depends: []
pluginDepends: []
version: "1.0"
description: "RSC示例附属"
authors: ["mmmjjkx"]
repo: "SlimefunReloadingProject/rsc-example"
```

## repo

这是附属更新的必填项。

## 更新步骤

1.从**GitHub**获取存储库

2.寻找最新发行版并比对

3.如果最新版跟当前版本不同则下载源码zip

4.解压zip到`addons/附属ID`

## 注意事项

发行版下载下来的版本一定要跟发行版名称相同！

否则会造成**死循环**。


