# Props

Making a basic prop includes the following steps:
1. The player holds the item and right-clicks it
2. Executes a command
3. The item is consumed

The above functions can be implemented through scripts, and examples are given below

```js
// When the item is right-clicked
function onUse(event) {
// Define a string variable item, whose value is a specific item generation command. This example code is used to give a creeper spawn egg that generates an iron golem
var item = "creeper_spawn_egg{EntityTag:{id:\"minecraft:iron_golem\"}}";
// Material (this is a creeper spawn egg) Generated entity (this is an iron golem)

// Get the player object that triggered the event
var player = event.getPlayer();

// Get the player's backpack object
var inv = player.getInventory();

// Get the items in the player's main hand
var itemInMainHand = inv.getItemInMainHand();

// You can also write this way
// var itemInMainHand = player.getInventory().getItemInMainHand();

// Check if there is an item in the player's main hand, and the number of the item is greater than 0
if (itemInMainHand != null && itemInMainHand.getAmount() > 0) {
// Set the conversion amount to the number of items in the player's main hand
// var amount = itemInMainHand.getAmount();

// Set the conversion amount to one
var amount = 1;

// Set the number of items in the player's main hand to the number of existing items - 1, that is, consume one item
itemInMainHand.setAmount(itemInMainHand.getAmount() - 1);

// Run op command
runOpCommand(player, "give " + player.getName() + " " + item + " " + amount);
}
}
```

Here is the `/give creeper_spawn_egg{EntityTag:{id:"minecraft:iron_golem"}` command,

runOpCommand corresponds to running this command as an op, and the command content is in brackets.

Please note that if the command contains double quotes, please replace the `"` with `\"` to escape it.