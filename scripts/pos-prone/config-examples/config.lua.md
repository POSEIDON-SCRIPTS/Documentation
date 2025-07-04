# config.lua

```lua
Config = {}

Config.StaminaRequiredToSprint = 4
Config.Functions = {
    ['active_prone'] = function()
        exports['POS-Metabolism']:UpdateStatus('shower', 2)
    end
}

Config.Settings = {
    requireOnlyProneKey = false, -- If true, the player can only toggle prone with the prone key, or they need to have prone and crouch
    proneFunctionInterval = 5000, -- How often the prone function is called (the active_prone function)
}

Config.Controls = {
    ToggleProne = 0x26E9DC00,
    Crouch = 0xDB096B85,
    MoveForward = 0x8FD015D8,
    MoveLeft = 0x7065027D,
    MoveBackward = 0xD27782E3,
    MoveRight = 0xB4E465B4,
    Sprint = 0x8FFC75D6,
    TurnOver = 0xD9D0E1C0
}
```
