# 附属配置文件

附属作者们可以通过编写配置文件来让服主合理调配附属内容

## 制作默认配置文件
1. 首先在附属内容所在文件夹创建`default_config.yml`，然后写上一些选项
2. 保存`default_config.yml`（**注意:编码应该是UTF-8**）

## 注意事项
1. RSC会把附属里的`default_config.yml`复制出来，然后粘贴到`RykenSlimeCustomizer/addon_configs/(附属id)/config.yml`里
2. 不要修改附属里的`default_config.yml`, 那个文件只是作为模板，真正读取的内容在`addon_configs`那个文件夹里的配置文件
   (更新附属会把`default_config.yml`覆盖掉)
3. 不要删除`default_config.yml`, 否则附属可能无法正常使用

## 与脚本的联动
详见[脚本 - 基础](scripts-basic/basic.md#附属配置文件)

## 使用作为内容的注册条件
详见[内容注册/加载选项](context-options.md#关于-conditions)

## 验证配置文件
如果你想要限制某个配置选项的值在某个范围，那么你可以这样做：
1. 在附属脚本文件夹里创建一个名为`configHandler.js`的文件
2. 写一个名为`onConfigReload`的函数，就像这样

```js
function onConfigReload(config) {

}

```
config这个入参是指附属的配置文件，类型为[YamlConfiguration](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/configuration/file/YamlConfiguration.html)