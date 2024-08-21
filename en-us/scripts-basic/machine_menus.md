# Script Basics - Machine Menu

## onOpen

Triggered when the menu is opened

### Method Body

```js
function onOpen(player) {

}
```

### Input Parameters

|Field|Type|Description|
|--|---|--|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|The player who opened this menu|

## onClose

Triggered when the menu is closed

### Method Body

```js
function onClose(player) {

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|The player who closed this menu|

## onClick

Triggered when the menu is clicked

### Method body

```js
function onClick(player, slot, slotItem, clickAction){

}
```

### Input parameters

|Field|Type|Description|
|--|---|--|
|player|[Player](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html)|The player who clicked this menu|
|slot|int|The slot being clicked|
|slotItem|[ItemStack](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemStack.html)|The item being clicked|
|clickAction|[ClickAction](https://slimefun.github.io/javadocs/Slimefun4/docs/me/mrCookieSlime/CSCoreLibPlugin/general/Inventory/ClickAction.html)|Click action|

### About clickAction

Determine the key combination:
*The following uses ca to represent clickAction*

```js
//shift + left click
let shiftWithLeft = !ca.isRightClicked() && ca.isShiftClicked();

//shift + right click
let shiftWithRight = ca.isRightClicked() && ca.isShiftClicked();

//Only left click
let left = !ca.isRightClicked() && !ca.isShiftClicked();

//Only right click
let right = ca.isRightClicked() && !ca.isShiftClicked();
```