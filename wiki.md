# UG Advanced Swapper WIKI

## How to share a script with someone on Discord

```
It will make the script look like this on discord.
```

Using the format above helps everyone to read your script easily and properly. Below is a list of arguments compatible with the advanced swapper.

## General Action Commands

Equipment:
hat,amulet,body,cape,boots,ring
(Just use easy setup for these in the equipment tab)

```apache
Chat:hi
```
Sends a chat with hi instantly.

```apache
OverheadText:hi
```
The same as Chat: but only you see it.

```apache
Type:A
```
Presses A on the keyboard.
- Supports tags such as [esc] and [enter]

```apache
SpaceBar
```
Presses the spacebar on your keyboard.

```apache
Enter
```
Presses enter on thekeyboard.

```apache
Logout
```
Logs you out instantly if possible.

```apache
FastLogout
```
Same as logout but faster.

```apache
Loot:1K:2B:RADIUS:ALLOW_OTHER_PEOPLES_DROPS (0/1)
Example
Loot:1K:2B:5:1
```
Loots items from 1K up to 2B, within a distance of 5 tiles, takes other peoples drops and waits for it a bit

```apache
Login:Username:Password
```
Logs your accout int, keep in mind repeater does not run on the login screen, so you'd need to hande both logout + login in the same script.

```apache
Sound:500
```
Plays sound ID 500

```apache
PauseAutoEat
```
Pauses the auto-eat plugin's functionality temporarily

```apache
PauseAutoEat:5
```
Pauses the auto-eat plugin's functionality for 5 ticks

```apache
PausePlugins
```
Pauses all other UG plugins like tempoross, player scouter, bank stander and all other ones.

```apache
ResumePlugins
```
Resumes all other UG plugins like tempoross, player scouter, bank stander and all other ones.

```apache
Stop
```
Stops the script immediately, this can also be used inside a condition.

```apache
Npc:Banker:Bank
```
Interacts with an NPC with the desired action given.

```apache
Object:Gate:Open
```
Interacts with a game object with the desired action given.

```apache
Prayer:Protect Item:On
```
Activates or Deactivates the specified prayer given.

```apache
LastTarget:Attack
```
Attacks the most recent target you were in combat with.

```apache
HoveredOrLastTarget:Attack
```
Interacts with either the most recent target you were in combat with, or the one being hovered over with your cursor.

```apache
CastOnTarget:Ice Barrage
```
Casts a spell on your current target.

```apache
Vengeance
```
Casts the Vengeance spell.

```apache
SpecialAttack
```
Performs a special attack.

```apache
Move:Up:10
```
Moves a given number of tiles in the desired direction.

```apache
MoveTarget:10
```
Moves a specified number of tiles AWAY from your target, useful for 10-tiling in PvP.

```apache
MoveTargetDiagonal:2
```
Moves a specified number of tiles AWAY from your target, and also forcing being diagonal of said target.

```apache
log:message you want to log
```
logs a message in the game chat.

## Target Commands

```apache
ClearTarget
```
Removes your target

```apache
LastTarget:Attack
```
Attacks the most recent target you were in combat with. (This can also be used to trade, follow e.t.c)

```apache
HoveredOrLastTarget:Attack
```
Interacts with either the most recent target you were in combat with, or the one being hovered over with your cursor.

```apache
HoveredTarget:Attack
```
Interacts with either the target your hovering.

```apache
CastOnTarget
```
Casts a spell on your current target.

```apache
SetHoveredTarget:0:0:0
```
Sets the hovered player as your target.

```apache
SetHoveredNpc
```
The same as SetHoveredTarget but for an NPC.

```apache
FindTarget:0:0:0
```
Finds a target if you don't have one.

```apache
SmartTarget:0:0:0
```
Prioritizes the closest player targeting you or your last target otherwise.

```apache
Npc:Banker:Bank
Npc:Banker:Bank:20//Max distance 20 tiles
```
Uses the an option on a NPC, in this example Bank on a Banker.

```apache
SmartNpc:Banker:Bank
SmartNpc:Banker:Bank:20//Max distance 20 tiles
```
Uses the an option on a NPC but prioritises your current targeted NPC if possible, in this example Bank on a Banker.

```apache
Player:Zezima:Trade
```
Uses an action on a specific player.

```
0:0:0
```
Explained: 0=OFF 1=ON, 1st parameter: Ignore friends, 2nd parameter: Ignore friends chat, 3rd parameter: Ignore clan.

## Magic Skillcape Spellbook Swap Commands

```apache
Spellbook:Standard
```
Swaps to the Standard spellbook.

```apache
Spellbook:Ancient
```
Swaps to the Ancient spellbook.

```apache
Spellbook:Arceuus
```
Swaps to the Arceuus spellbook.

```apache
Spellbook:Lunar
```
Swaps to the Lunar spellbook.

## Delay Commands

```apache
Wait:100:200
```
This will wait a random number of MS between 100 and 200  before continuing to the next command.

```apache
Tick:1:3
```
This will wait a random number of ticks between 1 and 3 before continuing to the next command, 1 tick is around 550 milliseconds.

```apache
RandomAfkChance
```
Usually does nothing but sometimes adds in some ticks as a delay.

```apache
WaitForBankHandler
```
Waits for the bank handler plugin to finish what its doing, if its running and the bank is open.

## Item Commands

```apache
Item:Shark
```
Uses the first option of the shark which in this case is Eat.

```apache
Item:Shark:Eat
```
The third parameter the item action is the item action (such as, Drop, Eat, Drink).

```apache
Item:Anglerfish,Shark:Eat
```
Eats an anglerfish or a shark if there is no anglerfish, this can also be used without the Eat parameter to do the first action of the item.

```apache
ItemOnNpc:Plank:Phials
```
Uses an item on an NPC.

```apache
ItemOnObject:Bones:Altar
```
Uses an item on an Object.

```apache
CombineItem:Logs:Tinderbox
```
Uses one inventory item on another inventory item.

```apache
GroundItem:Flax:Take
```
Interacts with an item on the ground.

```apache
ItemWithSpell:Magic Longbow:High Level Alchemy
```
Uses a spell on an item.

```apache
Telegrab:Item Name,Item Name2
```
Uses the Telekinetic Grab spell on an item.

```apache
Item:Royal seed pod:Commune
```
Uses the commune option to teleport on this item.

## Banking Commands

```apache
Withdraw:Anglerfish:All
```
Withdraws a specified item from the bank. You can use numbers to specify how many, or use "all" to fill your inventory.

```apache
Deposit:Anglerfish:All
```
Deposits a specified item from the bank. You can use numbers to specify how many, or use "all"

```apache
OpenBank
```
Opens the bank interface.

```apache
CloseBank
```
Closes the bank interface.

## Advanced Conditions 1/2

For the following conditions: "Log:" is just used as an example command. It should be replaced by a string of your desired commands.
For example,if your Target's weapon is Dragon claws, you might want to change "log:Target has dragon claws." to "Prayer:Protect From Melee:On"

## Operators: 
- OR: ||
- AND: &&

```apache
if(HasItem_Shark || HasItem_Manta Ray) {
log:We have a shark or a manta ray in our inventory.
}
```

Using a command (like Item: as conditional), this works with ALL commands.

```apache
if(Item:Anglerfish,Shark) {
Achievement:You ate a shark or a anglerfish.
}
```

```apache
if(Npc:Cow:Attack) {
Achievement:You attacked a cow!
}
```

```apache
if(IdleTicks > 5) { 
log:You've been idle at lesat 6 ticks.
}
```

```apache
if(damage > 25)
{
log:You did %dmg% damage this hit and we received %exp% exp!
log:This command checks the highest DAMAGE you received in the last 100 ms or returns 0.
}
```

```apache
if(exp > 25)
{
log:You did %dmg% damage this hit and we received %exp% exp!
log:This command checks the highest EXP you received in the last 100 ms or returns 0.
}
```

```apache
if(WildernessLevel > 30)
{
log:We're at wildy level 31 or higher.
}
```

```apache
if(TargetPraying_Melee) { 
log:Melee
}
```

```apache
if(TargetPraying_Ranged) { 
log:RANGED 
}
```

```apache
if(TargetPraying_Magic) { 
log:MAGIC 
}
```

```apache
if(TargetPraying_null) { 
log:NO PRAYER 
}
```

```apache
if(TargetRisk > 5M) { 
log:Target is risking more then 5M.
}
```

```apache
if(EmptySlots > 2)
{
log:Your inventory has more then 2 empty slots.
}
```

```apache
if(StandingOn_1234,1235,1236) //Checks if standing on a certain GFX or Object
{
MoveObject:1234,1235,1236//Move away from said object.
}
```

## Advanced Contions 2/2

```apache
if(SkillAbove_Prayer_80) { 
log:Your Prayer points are 81 or higher. 
}
```

```apache
if(SkillLvlAbove_Prayer_80) { 
log:Your Prayer level is 81 or higher. 
}
```

```apache
if(CurrentWeapon_Dragon Claws) { 
log:You have dragon claws. 
}
```

```apache
if(TargetWeapon_Dragon Claws) { 
log:Target has dragon claws. 
}
```

```apache
if(TargetWeaponIds,1234,5678) { 
log:Target has 1234 or 5678 as weapon. 
}
```

```apache
if(TargetAnimation_1234) { 
log:Target is doing animation 1234. 
}
```

```apache
if(SpecialAttackAbove_49) { 
log:Special attack is 50 or higher. 
}
```

```apache
if(SpecialAttackBelow_50) { 
log:Special attack is below 50. 
}
```

```apache
if(pid) { 
log:you currently have pid. 
}
```

```apache
if(CombatLevel > 30) { 
log:Your combat level is above 30.
}
```

```apache
if(TargetCombatLevel > 30) { 
log:Your targets combat level is above 30.
}
```

```apache
if(TargetName_Zezima,Goblin) { 
log:Your targeting either zezima or a goblin.
}
```

```apache
if(TargetName_Zezima,Goblin) { 
log:Your targeting either zezima or a goblin.
}
```

```apache
if(InCombat) { 
log:you are currently in combat. 
}
```

```apache
if(TargetVenged) { 
log:the target has Vengeance active.
}
```

```apache
if(Frozen) { 
log:We are currently frozen.
}
```

```apache
if(TargetFrozen) { 
log:the target is frozen. 
}
```

```apache
if(TargetFrozenOrImmune) { 
log:the target is either frozen or immune to being frozen. 
}
```

```apache
if(TargetTeleblocked) { 
log:the target is tele blocked. 
}
```

```apache
if(TargetTeleblockedOrImmune) { 
log:the target is either teleblocked or immune to being teleblocked. 
}
```

```apache
if(TargetSkulled) { 
log:the target is skulled. 
}
```

```apache
if(InventoryFull) { 
log:your inventory is full. 
}
```

```apache
if(HasItem_Dragon Dagger) { 
log:you have a Dragon Dagger in your inventory. 
}
```

```apache
if(TargetHasItem_Dragon Boots) { 
log:the target is wielding Dragon Boots. 
}
```

```apache
if(TargetHasItem_Dragon Boots,*Bow) { 
log:the target is wielding Dragon Boots or any type of Bow. 
}
```

```apache
if(HasAnyItem_Prayer Potion,Super Restore) { 
log:you have either a Prayer Potion or Super Restore in your inventory. 
}
```

```apache
if(HasItemAmount_Item Name_Amount) { 
log:you have a specified amount of a particular item in your inventory. 
}
```

```apache
if(IsEquipped_Item Name) { 
log:you are wearing a specified item. 
}
```

```apache
if(moving) { 
log:you are currently moving. 
}
```

```apache
if(Smiting) { 
log:your Smite prayer is active. 
}
```

```apache
if(animation == 1234) { 
log:your current animation ID is 1234. 
}
```

```apache
if(gfx == 1234) { 
log:your current graphic ID is 1234. 
}
```

```apache
if(pose == 1234) { 
log:your current pose ID is 1234. 
}
```

```apache
if(energy < 30) { 
log:your run energy is below 30. 
}
```

```apache
if(RegionId == 1234) { 
log:Yoor in regionId 1234 
}
```

```apache
if(PlayerX == 1234) { 
log:your X-coordinate is 1234. 
}
```

```apache
if(PlayerY == 1234) { 
log:your Y-coordinate is 1234. 
}
```

```apache
if(PlayerZ == 0) { 
log:your Z-coordinate is 0. 
}
```

```apache
if(hp < 80) { 
log:your hitpoints are below 80. 
}
```

```apache
if(targetHP > 50) { 
log:the target's hitpoints are above 50. 
}
```

```apache
if(SpecialAttack > 50) { 
log:your special attack energy is above 50. 
}
```

```apache
if(TargetSpec > 50) { 
log:the target's special attack energy is above 50. 
}
```

```apache
if(TargetDistance < 2) { 
log:the distance to the target is less than 2. 
}
```

```apache
if(TargetIsDiagonal) {
log:Target is diag.
}
```

```apache
if(Walking) { 
log:you are currently walking. 
}
```

```apache
if(RandomChancePercent_50) { 
log:a random chance (percent) is 50. 
}
```

```apache
if(Spellbook == Lunar) { 
log:your current spellbook is set to Lunar (other values: Standard, Lunar, Ancient, Arceuus). 
}
```

```apache
if(SpecialAttackBar) {
log:The current weapon has a special attack bar, this can't be checked in 0t scripts.
}
```

## Misc actions

**Object**
- Interacts with a game object with the desired action given.

Example: 
```apache
Object:Gate:Open
```

**SmartObject**
- Interacts with a game object with the desired action given, BUT will only interact with objects you can reach.

Example: 
```apache
SmartObject:Tree:Chop-down
```

**Prayer**
Activates or Deactivates the specified prayer given

Example: 
```apache
Prayer:Protect Item:On
```

```apache
Prayer:Protect Item:Off
```

**QuickPrayer**
- Activates or Deactivates the specified quick prayer given
- This does not toggle quickPrayer itself for you.

Example: 
```apache
QuickPrayer:Protect Item:On
```

```apache
QuickPrayer:Protect Item:Off
```

```apache
Vengeance
```
Casts the Vengeance spell.

```apache
SpecialAttack
```
PerforMS a special attack.

```apache
Move
```
Moves a given number of tiles in the desired direction.
Example: Move:Up:2 or Move:X-OFFSET:Y-OFFSET

```apache
MoveTarget:10
```
Moves a specified number of tiles AWAY from your target, usefull for 10-tiling in PvP.

```apache
MoveTargetDiagonal:2
```
Moves a specified number of tiles AWAY from your target, and also forcing being diagonal of said target.

**World walking**
```apache
worldwalk:X:Y:Z
worldwalk:X:Y:Z:2
```
Random at end by -2, -1 or + 1,+ 2 <- Explv's Map

```apache
if(isWorldWalking)
{
log:Your currently world walking.
}
```

```apache
WaitForWorldWalk
```
Waits for the world walk to complete.

https://explv.github.io/?centreX=3037&centreY=3381&centreZ=0&zoom=9

Game Message Trigger:
ChatUser:CopyTarget <- Set the user of the triggers target as your target, returns true if set.
ChatUser:Target <- Sets the user of the trigger as your target, returns true if set.

__This section is qutie advanced, if you don't know Advanced Swapper that well don't touch these.__

## Varbits [OPEN Varbit Id's list](https://plugins.qa/toolkits/Varbits.html)

```apache
if(Varbit 8121 == 1) { //PVP_SPEC_ORB
log:We're in a PvP area. 
}
```

```apache
if(Varbit 2450 == 1) { //VENGEANCE_ACTIVE
log:Vengeance is currently active. 
}
```

```apache
if(Varbit 2451 == 1) { //VENGEANCE_COOLDOWN 
log:Your vengeance is on cooldown. 
}
```

```apache
if(Varbit 1777 == 3) { //ACCOUNT_TYPE
log:Account is a ultimate ironman. 
}
```

```apache
if(Varbit 5361 == 0) { //IMBUED_HEART_COOLDOWN
Item:Imbued Heart:Invigorate 
}
```

**To check the current value use:**
```apache
logvarbit:VARBITID
```

## VarPlayer [OPEN VarPlayer Id's list](https://plugins.qa/toolkits/VarPlayer.html)

```apache
if(VarPlayer 3 < 3) { //CANNON AMMO=3
log:Our cannon has less than 3 bullets! 
}
```

To check the current value use:

```apache
logvarplayer:VARPLAYERID
```

**Plugin Memory**
```apache
Memory:Example:ABC
if(getmemory_Example_ABC)
{
log:Example matches ABC at this time.
}
```

**Turn off/on triggers**
```apache
memory:config-toggleOwnAnimation:true
memory:config-toggleOwnAnimation:false
```

```apache
SetTickTimer:5
if(TickTimer == 0)//To be used in another script or later in a script.
{
log:Stop because a timer you've set is still active.
stop
}
```

**Blind Dialog command**
⚠️ (One of the few unchecked actions, which will blindly run so don't use it without properly knowing what it does)
This command is to choose a dialog option before it even shows up.
There is a normal variant of this command (Dialog:Option in text), the real use of this command is to 0t certain dialogs.

You can see below that we only use the BlindDialog if the combat bracelet is actually used, so that it does not do an unneeded blind dialog.

```apache
if(!Gloves:Warriors' Guild)
{
log:There is no equipped combat bracelet, attempting to use inventory..
if(Item:Combat bracelet*:Rub)
{
log:Using a blind dialog because the combat bracelet was inside the inventory and used.
log:Don't use a blind invoke without checking the item.
BlindDialog:1
}
}
```

