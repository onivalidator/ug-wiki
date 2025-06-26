# UG Advanced Swapper API Documentation

A comprehensive scripting API for automating RuneScape gameplay through the UG Advanced Swapper plugin.

## Table of Contents

- [Getting Started](#getting-started)
- [Script Formatting](#script-formatting)
- [Core Commands](#core-commands)
- [Equipment & Items](#equipment--items)
- [Combat & Targeting](#combat--targeting)
- [Magic & Prayers](#magic--prayers)
- [Banking System](#banking-system)
- [Movement & Navigation](#movement--navigation)
- [Conditional Logic](#conditional-logic)
- [Advanced Features](#advanced-features)
- [Best Practices](#best-practices)

## Getting Started

The UG Advanced Swapper allows you to create automated scripts for RuneScape using a command-based syntax. Each command performs a specific action in the game.

## Basic Syntax Rules
- Commands are case-sensitive
- Parameters are separated by colons `:`
- Multiple item options use commas `,`
- Comments can be added with `//`

## Core Commands

## Chat & Communication
```apache
Chat:hello world
```
Sends a chat message instantly.

```apache
OverheadText:private message
```
Displays overhead text (only visible to you).

### Keyboard Input
```apache
Type:A
```
Presses a keyboard key. Supports special tags like `[esc]` and `[enter]`.

```apache
SpaceBar
```
Presses the spacebar.

```apache
Enter
```
Presses the Enter key.

### Session Management
```apache
Logout
```
Logs out of the game instantly.

```apache
FastLogout
```
Performs a faster logout.

```apache
Login:Username:Password
```
Logs into an account (Note: Repeater doesn't run on login screen).

### Audio & Plugins
```apache
Sound:500
```
Plays sound with ID 500.

```apache
PauseAutoEat
```
Temporarily pauses auto-eat functionality.

```apache
PauseAutoEat:5
```
Pauses auto-eat for 5 ticks.

```apache
PausePlugins
```
Pauses all other UG plugins.

```apache
ResumePlugins
```
Resumes all UG plugins.

```apache
Stop
```
Immediately stops the script execution.

## Equipment & Items

### Equipment Slots
Supported equipment slots: `hat`, `amulet`, `body`, `cape`, `boots`, `ring`
(Use easy setup in the equipment tab for these)

### Item Interactions
```apache
Item:Shark
```
Uses the primary action of an item (e.g., Eat for food).

```apache
Item:Shark:Eat
```
Uses a specific action on an item.

```apache
Item:Anglerfish,Shark:Eat
```
Uses the first available item from a list (prioritizes Anglerfish, falls back to Shark).

### Item Combinations & Usage
```apache
ItemOnNpc:Plank:Phials
```
Uses an item on an NPC.

```apache
ItemOnObject:Bones:Altar
```
Uses an item on a game object.

```apache
CombineItem:Logs:Tinderbox
```
Combines two inventory items.

```apache
ItemWithSpell:Magic Longbow:High Level Alchemy
```
Uses a spell on an inventory item.

### Ground Items
```apache
GroundItem:Flax:Take
```
Interacts with items on the ground.

```apache
Loot:1K:2B:5:1
```
Loots items worth 1K-2B within 5 tiles, including other players' drops.

```apache
Telegrab:Item Name,Item Name2
```
Uses Telekinetic Grab spell on ground items.

## Combat & Targeting

### Target Management
```apache
ClearTarget
```
Removes current target.

```apache
LastTarget:Attack
```
Attacks the most recent target.

```apache
HoveredOrLastTarget:Attack
```
Attacks either hovered target or last target.

```apache
HoveredTarget:Attack
```
Attacks the currently hovered target.

```apache
SetHoveredTarget:0:0:0
```
Sets hovered player as target.
- Parameters: `ignoreFriends:ignoreFriendsChat:ignoreClan` (0=OFF, 1=ON)

```apache
SetHoveredNpc
```
Sets hovered NPC as target.

```apache
FindTarget:0:0:0
```
Automatically finds a target if none exists.

```apache
SmartTarget:0:0:0
```
Prioritizes closest player targeting you, or last target otherwise.

### Combat Actions
```apache
CastOnTarget:Ice Barrage
```
Casts a spell on current target.

```apache
Vengeance
```
Casts the Vengeance spell.

```apache
SpecialAttack
```
Performs a special attack.

### NPC & Player Interactions
```apache
Npc:Banker:Bank
Npc:Banker:Bank:20
```
Interacts with an NPC (optional max distance parameter).

```apache
SmartNpc:Banker:Bank:20
```
Prioritizes targeted NPC, with fallback to nearest NPC.

```apache
Player:Zezima:Trade
```
Performs action on specific player.

## Magic & Prayers

### Spellbook Management
```apache
Spellbook:Standard
Spellbook:Ancient
Spellbook:Arceuus
Spellbook:Lunar
```
Swaps to different spellbooks (requires Magic Skillcape).

### Prayer Control
```apache
Prayer:Protect Item:On
Prayer:Protect Item:Off
```
Activates or deactivates prayers.

```apache
QuickPrayer:Protect Item:On
QuickPrayer:Protect Item:Off
```
Manages quick prayer settings (doesn't toggle quick prayer itself).

## Banking System

### Bank Operations
```apache
OpenBank
```
Opens the bank interface.

```apache
CloseBank
```
Closes the bank interface.

```apache
Withdraw:Anglerfish:All
```
Withdraws items from bank. Use numbers or "All".

```apache
Deposit:Anglerfish:All
```
Deposits items to bank.

```apache
WaitForBankHandler
```
Waits for bank handler plugin to complete operations.

## Movement & Navigation

### Basic Movement
```apache
Move:Up:10
```
Moves in specified direction for given tiles.

```apache
Move:X-OFFSET:Y-OFFSET
```
Moves using coordinate offsets.

### Combat Movement
```apache
MoveTarget:10
```
Moves specified tiles away from target (useful for PvP).

```apache
MoveTargetDiagonal:2
```
Moves away from target while maintaining diagonal position.

### World Walking
```apache
worldwalk:X:Y:Z
worldwalk:X:Y:Z:2
```
Advanced pathfinding to specific coordinates. Optional randomization parameter.

```apache
WaitForWorldWalk
```
Waits for world walking to complete.

```apache
if(isWorldWalking) {
    log:Currently world walking
}
```
Check if world walking is active.

**Map Reference:** [Explv's Map](https://explv.github.io/?centreX=3037&centreY=3381&centreZ=0&zoom=9)

### Object Interactions
```apache
Object:Gate:Open
```
Interacts with game objects.

```apache
SmartObject:Tree:Chop-down
```
Only interacts with reachable objects.

## Conditional Logic

### Basic Syntax
```apache
if(condition) {
    // Commands to execute
}
```

### Logical Operators
- OR: `||`
- AND: `&&`
- Equals: `==`
- Greater than: `>`
- Less than: `<`

### Example Conditions
```apache
if(HasItem_Shark || HasItem_Manta Ray) {
    log:We have food available
}

if(IdleTicks > 5) {
    log:Been idle for 6+ ticks
}

if(damage > 25) {
    log:Dealt %dmg% damage, gained %exp% exp
}
```

### Common Condition Types

#### Health & Stats
```apache
if(hp < 80) { /* Low health */ }
if(targetHP > 50) { /* Target health check */ }
if(SpecialAttack > 50) { /* Special attack energy */ }
if(energy < 30) { /* Run energy */ }
```

#### Combat State
```apache
if(InCombat) { /* Currently fighting */ }
if(Frozen) { /* Player is frozen */ }
if(TargetFrozen) { /* Target is frozen */ }
if(TargetVenged) { /* Target has vengeance */ }
```

#### Prayer Detection
```apache
if(TargetPraying_Melee) { /* Target protecting melee */ }
if(TargetPraying_Ranged) { /* Target protecting ranged */ }
if(TargetPraying_Magic) { /* Target protecting magic */ }
if(TargetPraying_null) { /* Target not praying */ }
```

#### Equipment & Items
```apache
if(HasItem_Dragon Dagger) { /* Item in inventory */ }
if(IsEquipped_Item Name) { /* Item equipped */ }
if(CurrentWeapon_Dragon Claws) { /* Weapon check */ }
if(TargetWeapon_Dragon Claws) { /* Target weapon */ }
if(InventoryFull) { /* Inventory space */ }
if(EmptySlots > 2) { /* Available inventory slots */ }
```

#### Position & Environment
```apache
if(WildernessLevel > 30) { /* Wilderness level */ }
if(PlayerX == 1234) { /* X coordinate */ }
if(PlayerY == 1234) { /* Y coordinate */ }
if(PlayerZ == 0) { /* Z coordinate (floor) */ }
if(RegionId == 1234) { /* Game region */ }
if(TargetDistance < 2) { /* Distance to target */ }
```

#### Skill Levels
```apache
if(SkillAbove_Prayer_80) { /* Prayer points > 80 */ }
if(SkillLvlAbove_Prayer_80) { /* Prayer level > 80 */ }
if(CombatLevel > 30) { /* Combat level */ }
if(TargetCombatLevel > 30) { /* Target combat level */ }
```

#### Animations & States
```apache
if(animation == 1234) { /* Animation ID */ }
if(gfx == 1234) { /* Graphic effect ID */ }
if(pose == 1234) { /* Pose/stance ID */ }
if(moving) { /* Player is moving */ }
if(Walking) { /* Player is walking */ }
```

#### Random & Utility
```apache
if(RandomChancePercent_50) { /* 50% chance */ }
if(pid) { /* Player has PID advantage */ }
if(Spellbook == Lunar) { /* Current spellbook */ }
if(SpecialAttackBar) { /* Weapon has spec bar */ }
```

## Advanced Features

### Timing & Delays
```apache
Wait:100:200
```
Random delay between 100-200 milliseconds.

```apache
Tick:1:3
```
Random delay between 1-3 ticks (~550ms per tick).

```apache
RandomAfkChance
```
Occasionally adds random delay for more human-like behavior.

### Varbits (Game Variables)
```apache
if(Varbit 8121 == 1) { /* PVP_SPEC_ORB - In PvP area */ }
if(Varbit 2450 == 1) { /* VENGEANCE_ACTIVE */ }
if(Varbit 2451 == 1) { /* VENGEANCE_COOLDOWN */ }
if(Varbit 1777 == 3) { /* ACCOUNT_TYPE - Ultimate Ironman */ }

logvarbit:VARBITID  // Check current varbit value
```

### VarPlayer (Player Variables)
```apache
if(VarPlayer 3 < 3) { /* CANNON_AMMO - Cannon ammo < 3 */ }

logvarplayer:VARPLAYERID  // Check current varplayer value
```

### Memory System
```apache
Memory:Example:ABC
if(getmemory_Example_ABC) {
    log:Memory value matches ABC
}
```

### Configuration Toggle
```apache
memory:config-toggleOwnAnimation:true
memory:config-toggleOwnAnimation:false
```

### Timers
```apache
SetTickTimer:5
if(TickTimer == 0) {
    log:Timer expired
    stop
}
```

### Dialog Handling
```apache
BlindDialog:1
```
⚠️ **Advanced Feature**: Chooses dialog option before it appears. Use with caution and proper validation.

### Chat Triggers
```apache
ChatUser:CopyTarget  // Copy trigger user's target
ChatUser:Target      // Set trigger user as target
```

## Best Practices

### Safety Guidelines
1. Always validate conditions before using `BlindDialog`
2. Use appropriate delays to avoid detection
3. Include safety stops in combat scripts
4. Test scripts in safe environments first

### Performance Tips
1. Use `SmartNpc` and `SmartObject` for better pathfinding
2. Combine related conditions with logical operators
3. Use memory system for persistent state tracking
4. Implement proper error handling with conditional stops

### Code Organization
1. Group related commands logically
2. Use meaningful variable names in conditions
3. Add comments to explain complex logic
4. Structure scripts with clear entry/exit points

### Debugging
1. Use `log:` commands to trace execution
2. Check varbit/varplayer values during development
3. Use `logvarbit:` and `logvarplayer:` for debugging
4. Test individual commands before complex scripts

---

**Resources:**
- [Varbit IDs](https://plugins.qa/toolkits/Varbits.html)
- [VarPlayer IDs](https://plugins.qa/toolkits/VarPlayer.html)
- [Explv's Map Tool](https://explv.github.io/?centreX=3037&centreY=3381&centreZ=0&zoom=9)

This API provides comprehensive automation capabilities for RuneScape. Always follow game rules and use responsibly. 