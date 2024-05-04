# 脚本基础 - 机器菜单
## onOpen
当菜单被打开时触发
### 方法体
```js
function onOpen(player) {

}
```
### 入参
|字段|类型|描述|
|--|---|--|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|打开此菜单的玩家|

## onClose
当菜单被关闭时触发
### 方法体
```js
function onClose(player) {

}
```
### 入参
|字段|类型|描述|
|--|---|--|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|关闭此菜单的玩家|

## onClick
当菜单被点击时触发
### 方法体
```js
function onClick(player, slot, slotItem, clickAction){

}
```
### 入参
|字段|类型|描述|
|--|---|--|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|点击此菜单的玩家|
|slot|int|点击的槽位|
|slotItem|ItemStack|被点击的物品|
|clickAction|[ClickAction](https://slimefun.github.io/javadocs/Slimefun4/docs/me/mrCookieSlime/CSCoreLibPlugin/general/Inventory/ClickAction.html)|点击动作|

### 关于clickAction
判断按键组合:  
*以下使用ca代表clickAction*
```js
//shift + 左键
let shiftWithLeft = !ca.isRightClicked() && ca.isShiftClicked();

//shift + 右键
let shiftWithRight = ca.isRightClicked() && ca.isShiftClicked();

//仅左键
let left = !ca.isRightClicked() && !ca.isShiftClicked();

//仅右键
let right = ca.isRightClicked() && !ca.isShiftClicked();
```