# Client Exports

## POS-ProgressBar Client-Side Exports

This document covers the client-side exports available for POS-ProgressBar, allowing you to create interactive progress bars with animations, props, and various customization options.

***

## StartProgress Export

The main export function for creating progress bars with advanced features including animations, props, and player controls.

### Usage

```lua
exports['POS-ProgressBar']:StartProgress(data, callback)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `data` | `table` | Configuration table containing progress bar settings |
| `callback` | `function` | Callback function executed when progress completes or is cancelled |

### Data Configuration

The `data` table supports the following options:

#### Basic Settings

| Option | Type | Required | Description |
|--------|------|----------|-------------|
| `time` | `number` | Yes | Duration of the progress bar in milliseconds |
| `title` | `string` | Yes | Text displayed on the progress bar |
| `item` | `string` | No | Item name or identifier (optional) |
| `percentage` | `number` | No | Starting percentage (0-100), defaults to 0 |
| `canStop` | `boolean` | No | Whether the progress can be cancelled by key press |
| `freeze` | `boolean` | No | Whether to freeze the player during progress |

#### Animation Settings

| Option | Type | Required | Description |
|--------|------|----------|-------------|
| `animation` | `table` | No | Animation configuration table |
| `animation.type` | `string` | No | Animation type: "scenario" or "anim" |
| `animation.scenario` | `string` | No | Scenario name (if type is "scenario") |
| `animation.animDict` | `string` | No | Animation dictionary (if type is "anim") |
| `animation.anim` | `string` | No | Animation name (if type is "anim") |
| `animation.flags` | `number` | No | Animation flags, defaults to 0 |
| `animation.time` | `number` | No | Animation duration (for scenarios) |

#### Prop Settings

| Option | Type | Required | Description |
|--------|------|----------|-------------|
| `prop` | `table` | No | Prop configuration table |
| `prop.model` | `string/hash` | No | Prop model name or hash |
| `prop.bone` | `string/number` | No | Bone name or index to attach prop |
| `prop.coords` | `table` | No | Prop position offset {x, y, z} |
| `prop.rotation` | `table` | No | Prop rotation {x, y, z} |

### Examples

#### Basic Progress Bar

```lua
exports['POS-ProgressBar']:StartProgress({
    time = 5000,
    title = "Drinking Water...",
    canStop = true,
    freeze = true
}, function(cancelled)
    if not cancelled then
        print("Successfully drank water!")
    else
        print("Drinking was cancelled!")
    end
end)
```

#### Progress Bar with Animation

```lua
exports['POS-ProgressBar']:StartProgress({
    time = 8000,
    title = "Crafting Item...",
    canStop = true,
    freeze = true,
    animation = {
        type = "anim",
        animDict = "amb_work@world_human_bartender@male@base",
        anim = "base",
        flags = 49
    }
}, function(cancelled)
    if not cancelled then
        -- Give crafted item
        TriggerServerEvent('pos-crafting:giveItem', 'crafted_item')
    end
end)
```

#### Progress Bar with Scenario

```lua
exports['POS-ProgressBar']:StartProgress({
    time = 10000,
    title = "Washing Clothes...",
    canStop = true,
    freeze = true,
    animation = {
        type = "scenario",
        scenario = "WORLD_HUMAN_WASH_CLOTHES_BUCKET",
        time = 10000
    }
}, function(cancelled)
    if not cancelled then
        print("Clothes washed successfully!")
    end
end)
```

#### Progress Bar with Prop

```lua
exports['POS-ProgressBar']:StartProgress({
    time = 6000,
    title = "Drinking from Bottle...",
    canStop = true,
    freeze = true,
    prop = {
        model = "p_bottlebeer01a",
        bone = "SKEL_R_HAND",
        coords = {x = 0.0, y = 0.0, z = 0.0},
        rotation = {x = 0.0, y = 0.0, z = 0.0}
    },
    animation = {
        type = "anim",
        animDict = "amb_rest_drunk@world_human_drinking@bottle@male@idle_a",
        anim = "idle_a",
        flags = 49
    }
}, function(cancelled)
    if not cancelled then
        -- Apply drinking effects
        TriggerServerEvent('pos-metabolism:updateThirst', 25)
    end
end)
```

#### Complex Progress Bar with All Features

```lua
exports['POS-ProgressBar']:StartProgress({
    time = 15000,
    title = "Preparing Medicine...",
    item = "medicine_kit",
    percentage = 0,
    canStop = true,
    freeze = true,
    prop = {
        model = "p_package04x",
        bone = "SKEL_L_HAND",
        coords = {x = 0.1, y = 0.0, z = 0.0},
        rotation = {x = 0.0, y = 90.0, z = 0.0}
    },
    animation = {
        type = "anim",
        animDict = "amb_work@world_human_bartender@male@base",
        anim = "base",
        flags = 49
    }
}, function(cancelled)
    if not cancelled then
        TriggerServerEvent('pos-medical:createMedicine', 'advanced_medicine')
        TriggerEvent('pos-notification:send', {
            type = 'success',
            message = 'Medicine prepared successfully!'
        })
    else
        TriggerEvent('pos-notification:send', {
            type = 'error',
            message = 'Medicine preparation was cancelled!'
        })
    end
end)
```

### Callback Function

The callback function receives one parameter:

| Parameter | Type | Description |
|-----------|------|-------------|
| `cancelled` | `boolean` | `true` if the progress was cancelled, `false` if completed |

### Common Bone Names

Here are some commonly used bone names for prop attachment:

| Bone Name | Description |
|-----------|-------------|
| `SKEL_R_HAND` | Right hand |
| `SKEL_L_HAND` | Left hand |
| `SKEL_R_FINGER00` | Right hand fingers |
| `SKEL_L_FINGER00` | Left hand fingers |
| `SKEL_HEAD` | Head |
| `SKEL_NECK_1` | Neck |
| `SKEL_SPINE3` | Upper torso |

### Animation Flags

Common animation flags for different behaviors:

| Flag | Description |
|------|-------------|
| `0` | Default animation |
| `1` | Loop animation |
| `2` | Hold last frame |
| `16` | Upper body only |
| `32` | Enable player control |
| `49` | Repeat + Upper body only |

### Best Practices

1. **Always use freeze** for actions that should prevent player movement
2. **Set canStop to true** for longer actions to allow player cancellation
3. **Choose appropriate animations** that match the action being performed
4. **Use realistic timing** - match progress bar duration to animation length
5. **Handle cancellation** properly in your callback function
6. **Test prop positioning** thoroughly as different player models may vary
7. **Preload animations** if using the same ones frequently

### Integration with Other POS Scripts

```lua
-- Example integration with POS-Inventory
local function craftItem(itemName, requiredItems)
    -- Check if player has required items
    local hasItems = exports['POS-Inventory']:HasItems(requiredItems)
    
    if hasItems then
        exports['POS-ProgressBar']:StartProgress({
            time = 8000,
            title = "Crafting " .. itemName .. "...",
            canStop = true,
            freeze = true,
            animation = {
                type = "scenario",
                scenario = "WORLD_HUMAN_HAMMERING",
                time = 8000
            }
        }, function(cancelled)
            if not cancelled then
                -- Remove required items and give crafted item
                TriggerServerEvent('pos-crafting:completeItem', itemName, requiredItems)
            end
        end)
    else
        TriggerEvent('pos-notification:send', {
            type = 'error',
            message = 'You don\'t have the required items!'
        })
    end
end
```

### Error Handling

The progress bar system includes built-in error handling, but you should still validate your data:

```lua
local function safeStartProgress(data, callback)
    -- Validate required fields
    if not data.time or not data.title then
        print("ERROR: Progress bar requires 'time' and 'title' fields")
        return false
    end
    
    -- Validate animation data
    if data.animation and data.animation.type == "anim" then
        if not data.animation.animDict or not data.animation.anim then
            print("ERROR: Animation type 'anim' requires 'animDict' and 'anim' fields")
            return false
        end
    end
    
    -- Start progress bar
    exports['POS-ProgressBar']:StartProgress(data, callback)
    return true
end
```

### Troubleshooting

**Progress bar not appearing:**
- Check that POS-ProgressBar is loaded and running
- Verify all required fields are provided
- Check browser console for JavaScript errors

**Animation not playing:**
- Ensure animation dictionary and name are correct
- Check that animation flags are appropriate
- Verify the animation is compatible with RedM

**Prop not attaching:**
- Confirm prop model exists and is loaded
- Check bone name spelling and case
- Adjust coords and rotation values
- Test with different bone indices

**Progress bar not finishing:**
- Ensure the progress bar system is receiving proper updates
- Check for script errors in console
- Verify callback function is properly defined

This export provides a comprehensive solution for creating interactive progress bars with full animation and prop support, perfect for crafting, medical, and other interactive systems in your RedM server.

