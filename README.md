# Universal Anti-Cheat Bypass

This is a comprehensive anti-cheat bypass solution designed to prevent detection from various anti-cheat systems in Roblox games. It combines multiple bypass techniques to provide robust protection for your scripts.

## Features

- **Property Spoofing**: Prevents detection of modified character properties like WalkSpeed and JumpPower
- **Remote Event Blocking**: Blocks suspicious remote events that might be used by anti-cheat systems
- **Debug Function Hooking**: Hides your scripts from detection by modifying debug functions
- **Anti-Cheat Connection Disabling**: Disables event connections used by anti-cheat systems
- **Anti-Cheat Function Hooking**: Finds and neutralizes anti-cheat functions in memory
- **GUI Detection Prevention**: Hides your GUI elements from anti-cheat scans
- **New Script Monitoring**: Automatically disables new anti-cheat scripts as they're added
- **Safe Input Simulation**: Provides a safer way to simulate keyboard input that's harder to detect

## Files

- `universalbypass.lua`: The main bypass module with all the bypass techniques
- `bypass_loader.lua`: Example loader script that shows how to use the bypass
- `README.md`: This documentation file

## How to Use

### Basic Usage

1. Load the bypass_loader.lua script:
```lua
loadstring(readfile("Bypass/bypass_loader.lua"))()
```

2. The loader will automatically:
   - Enable the bypass
   - Set up cleanup when you leave the game
   - Load the stronghit_safe.lua script as an example

### Advanced Usage

If you want more control, you can use the bypass module directly:

```lua
-- Load the bypass module
local bypass = loadstring(readfile("Bypass/universalbypass.lua"))()

-- Enable debug mode (optional)
bypass.setDebugMode(true)

-- Enable the bypass
bypass.enable()

-- Use safer input simulation
bypass.simulateInput(Enum.KeyCode.Space, false)

-- Disable the bypass when done
bypass.disable()
```

## How It Works

The bypass uses several techniques to avoid detection:

1. **Metamethod Hooking**: Intercepts and modifies function calls that anti-cheats use to detect cheating
2. **Function Replacement**: Replaces anti-cheat functions with harmless versions
3. **Event Connection Disabling**: Prevents anti-cheat event handlers from running
4. **Property Spoofing**: Returns original values when anti-cheats check for modified properties
5. **Remote Event Blocking**: Prevents anti-cheat remote events from reporting violations
6. **Script Hiding**: Removes references to your scripts in debug information

## Supported Anti-Cheat Systems

This bypass is designed to work with multiple anti-cheat systems, including:

- **IAC (IndexAntiCheat)**: Blocks the iac-respond remote event
- **Adonis Anti-Cheat**: Hooks the Detected and Kill functions
- **Property-Based Anti-Cheats**: Spoofs humanoid properties to prevent detection
- **Remote-Based Anti-Cheats**: Blocks suspicious remote events
- **GUI-Based Anti-Cheats**: Hides GUI elements from detection
- **Memory-Scanning Anti-Cheats**: Hooks debug functions to hide scripts

## Troubleshooting

If you encounter issues:

1. Enable debug mode to see detailed logs:
```lua
bypass.setDebugMode(true)
```

2. Check if your executor supports all required functions:
   - hookmetamethod
   - getgc
   - getconnections
   - newcclosure

3. Some games may use custom anti-cheat systems that require additional bypassing. In these cases, you may need to modify the bypass module.

## Safety Tips

1. Always use the safer input simulation method (`bypass.simulateInput()`) instead of VirtualInputManager
2. Don't make obvious or extreme modifications to character properties
3. Use the bypass's cleanup function when your script terminates
4. Keep the bypass module updated as anti-cheat systems evolve

## Limitations

- Some advanced anti-cheat systems may still detect the bypass
- The bypass may not work on all games or executors
- Future Roblox updates may break some bypass techniques

## Credits

This bypass combines techniques from multiple sources and adds new methods to create a comprehensive solution.

## Disclaimer

This tool is provided for educational purposes only. Use at your own risk. The developers are not responsible for any consequences resulting from the use of this tool.
