Here is an example of a /loadout command menu for FiveM:

// Define the loadout command
registerCommand("loadout", function(source, args, raw) {
// Check if the player has permission to use the command
if (!hasPermission(source, "loadout")) {
sendError(source, "You do not have permission to use this command.");
return;
}

Copy code
// Define the menu options
var options = [    { label: "Standard loadout", value: "standard" },    { label: "Heavy loadout", value: "heavy" },    { label: "Sniper loadout", value: "sniper" },    { label: "Custom loadout", value: "custom" },    { label: "Clear loadout", value: "clear" }];

// Show the menu to the player
showMenu(source, "Choose a loadout", options, function(source, choice) {
    // Check which option the player chose
    if (choice == "standard") {
        // Give the player a standard loadout
        giveStandardLoadout(source);
        sendMessage(source, "You have received a standard loadout.");
    } else if (choice == "heavy") {
        // Give the player a heavy loadout
        giveHeavyLoadout(source);
        sendMessage(source, "You have received a heavy loadout.");
    } else if (choice == "sniper") {
        // Give the player a sniper loadout
        giveSniperLoadout(source);
        sendMessage(source, "You have received a sniper loadout.");
    } else if (choice == "custom") {
        // Show the custom loadout menu to the player
        showCustomLoadoutMenu(source);
    } else if (choice == "clear") {
        // Clear the player's loadout
        clearLoadout(source);
        sendMessage(source, "Your loadout has been cleared.");
    }
});
});

// Define the giveStandardLoadout function
function giveStandardLoadout(player) {
// Give the player a pistol, a shotgun, and some ammo
giveWeapon(player, "WEAPON_PISTOL", 120);
giveWeapon(player, "WEAPON_SHOTGUN", 20);
}

// Define the giveHeavyLoadout function
function giveHeavyLoadout(player) {
// Give the player a minigun, an RPG, and some ammo
giveWeapon(player, "WEAPON_MINIGUN", 400);
giveWeapon(player, "WEAPON_RPG", 10);
}

// Define the giveSniperLoadout function
function giveSniperLoadout(player) {
// Give the player a sniper rifle, a shotgun, and some ammo
giveWeapon(player, "WEAPON_SNIPERRIFLE", 30);
giveWeapon(player, "WEAPON_SHOTGUN", 20);
}

// Define the showCustomLoadoutMenu function
function showCustomLoadoutMenu(player) {
// Define the menu options
var options = [
{ label: "Pistol", value: "WEAPON_PISTOL" },
{ label: "Shotgun", value: "WE



