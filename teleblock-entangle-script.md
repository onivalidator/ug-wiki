# Teleblock/Entangle Script

This script will automatically choose between Teleblock and Entangle based on wilderness level:
- **Entangle**: Used when above wilderness level 30
- **Teleblock**: Used when at wilderness level 30 or below

## Script Code

```apache
prayer:Protect Item:on
prayer:Augury:on

if(WildernessLevel > 30) {
    CastOnTarget:Entangle
    WaitForAnimating:1161
    LastTarget:Walk here
    log:We Cast Entangle on %targetname%
} else {
    CastOnTarget:Tele Block
    WaitForAnimating:1820
    LastTarget:Walk here
    log:We Cast Teleblock on %targetname%
}
```

## How it works

1. **Prayer Setup**: Activates Protect Item and Augury for protection and magic accuracy
2. **Wilderness Level Check**: Uses conditional logic to determine which spell to cast
3. **Spell Casting**: Casts the appropriate spell on your current target
4. **Animation Wait**: Waits for the specific animation ID to complete
   - Entangle: Animation ID 1161
   - Teleblock: Animation ID 1820
5. **Follow Target**: Walks to target's location after casting
6. **Logging**: Records which spell was cast and on whom

## Usage Notes

- Make sure you have a target selected before running the script
- Ensure you have the required runes for both spells
- The script will automatically detect your wilderness level
- Target name will be logged for tracking purposes

## Rune Requirements

**For Entangle:**
- 5x Earth runes
- 5x Water runes
- 1x Nature rune

**For Teleblock:**
- 1x Law rune
- 1x Death rune
- 1x Chaos rune 