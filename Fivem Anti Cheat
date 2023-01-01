function checkForCheating(player) {
// Check for aimbot
if (player.aimDirection != player.target.position) {
reportCheating(player, "Aimbot");
}
// Check for wall hacks
if (player.canSeeThroughWalls) {
reportCheating(player, "Wall hacks");
}
// Check for speed hacks
if (player.movementSpeed > normalSpeed) {
reportCheating(player, "Speed hacks");
}
}

function reportCheating(player, cheatType) {
// Add player to banned list
bannedList.push(player.steamID);
// Notify server administrators of cheating activity
notifyAdmins(player.name + " has been caught using " + cheatType);
}

while (true) {
// Check all players for cheating behavior
for (var i = 0; i < playerList.length; i++) {
checkForCheating(playerList[i]);
}
// Wait 5 minutes before checking again
sleep(300000);
}
