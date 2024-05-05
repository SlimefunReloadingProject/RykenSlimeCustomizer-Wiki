# 脚本基础 - 物品
## onUse
当玩家右键该物品时触发
### 方法体
```js
function onUse(event) {

}
``` 
### 入参
|字段|类型|描述|
|--|---|--|
|event|[PlayerRightClickEvent](https://slimefun.github.io/javadocs/Slimefun4/docs/io/github/thebusybiscuit/slimefun4/api/events/PlayerRightClickEvent.html)|玩家右键该物品事件|

## 技巧
你可以在方法被触发时使用`e.getPlayer().isSneaking()`来获取玩家是否蹲下
