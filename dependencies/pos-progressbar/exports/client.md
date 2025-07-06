# Client Exports

## POS-ProgressBar Client-Side Exports

This document covers the client-side exports available for POS-ProgressBar, allowing you to create interactive progress bars with animations, props, and various customization options.

***

## Available Exports

<details>

<summary><strong>🎯 StartProgress Export</strong></summary>

The main export function for creating progress bars with advanced features including animations, props, and player controls. This export can be used both **synchronously** and **asynchronously**.

### Usage

#### Asynchronous Usage (with callback)
```lua
exports['POS-ProgressBar']:StartProgress(data, callback)
```

#### Synchronous Usage (without callback)
```lua
local result = exports['POS-ProgressBar']:StartProgress(data)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `data` | `table` | Yes | Configuration table containing progress bar settings |
| `callback` | `function` | No | Callback function executed when progress completes or is cancelled |

### Return Value

| Type | Description |
|------|-------------|
| `boolean` | `true` if completed successfully, `false` if cancelled |

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

#### Synchronous Usage Examples

```lua
-- Basic synchronous progress bar
local success = exports['POS-ProgressBar']:StartProgress({
    time = 5000,
    title = "Drinking Water...",
    canStop = true,
    freeze = true
})

if success then
    print("Successfully drank water!")
    TriggerServerEvent('pos-metabolism:updateThirst', 25)
else
    print("Drinking was cancelled!")
end
```

```lua
-- Synchronous crafting example
local function craftItem(itemName)
    local success = exports['POS-ProgressBar']:StartProgress({
        time = 8000,
        title = "Crafting " .. itemName .. "...",
        canStop = true,
        freeze = true,
        animation = {
            type = "anim",
            animDict = "amb_work@world_human_bartender@male@base",
            anim = "base",
            flags = 49
        },
        prop = {
            model = "p_hammer01x",
            bone = "SKEL_R_HAND",
            coords = {x = 0.0, y = 0.0, z = 0.0},
            rotation = {x = 0.0, y = 0.0, z = 0.0}
        }
    })
    
    if success then
        TriggerServerEvent('pos-crafting:giveItem', itemName)
        TriggerEvent('POS-Core:notify', 'POS-Crafting', 'Item crafted successfully!', 'success', 5000)
        return true
    else
        TriggerEvent('POS-Core:notify', 'POS-Crafting', 'Crafting was cancelled!', 'error', 5000)
        return false
    end
end
```

#### Asynchronous Usage Examples

```lua
-- Basic asynchronous progress bar
exports['POS-ProgressBar']:StartProgress({
    time = 5000,
    title = "Drinking Water...",
    canStop = true,
    freeze = true
}, function(status)
    if status then
        print("Successfully drank water!")
        TriggerServerEvent('pos-metabolism:updateThirst', 25)
    else
        print("Drinking was cancelled!")
    end
end)
```

```lua
-- Progress Bar with Animation
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
}, function(status)
    if status then
        TriggerServerEvent('pos-crafting:giveItem', 'crafted_item')
    end
end)
```

```lua
-- Progress Bar with Scenario
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
}, function(status)
    if status then
        print("Clothes washed successfully!")
    end
end)
```

```lua
-- Progress Bar with Prop
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
}, function(status)
    if status then
        TriggerServerEvent('pos-metabolism:updateThirst', 25)
    end
end)
```

```lua
-- Complex Progress Bar with All Features
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
}, function(status)
    if status then
        TriggerServerEvent('pos-medical:createMedicine', 'advanced_medicine')
        TriggerEvent('POS-Core:notify', 'POS-Medical', 'Medicine prepared successfully!', 'success', 5000)
    else
        TriggerEvent('POS-Core:notify', 'POS-Medical', 'Medicine preparation was cancelled!', 'error', 5000)
    end
end)
```

### When to Use Each Method

#### Use Synchronous Mode When:
- You need to wait for the result before continuing
- You want cleaner, more readable code flow
- You're using the result immediately after completion
- You need to return a value based on the progress result

#### Use Asynchronous Mode When:
- You want non-blocking execution
- You're handling complex completion logic
- You're triggering multiple events after completion
- You prefer callback-style programming

### Advanced Examples

#### Chained Synchronous Progress Bars
```lua
local function performComplexTask()
    -- Step 1: Gather materials
    local step1 = exports['POS-ProgressBar']:StartProgress({
        time = 5000,
        title = "Gathering Materials...",
        canStop = true,
        freeze = true
    })
    
    if not step1 then
        return false, "Material gathering cancelled"
    end
    
    -- Step 2: Process materials
    local step2 = exports['POS-ProgressBar']:StartProgress({
        time = 8000,
        title = "Processing Materials...",
        canStop = true,
        freeze = true,
        animation = {
            type = "scenario",
            scenario = "WORLD_HUMAN_HAMMERING",
            time = 8000
        }
    })
    
    if not step2 then
        return false, "Processing cancelled"
    end
    
    -- Step 3: Final assembly
    local step3 = exports['POS-ProgressBar']:StartProgress({
        time = 6000,
        title = "Final Assembly...",
        canStop = true,
        freeze = true
    })
    
    if not step3 then
        return false, "Assembly cancelled"
    end
    
    return true, "Task completed successfully"
end

-- Usage
local success, message = performComplexTask()
if success then
    print("All steps completed: " .. message)
    TriggerServerEvent('pos-crafting:completeComplexTask')
else
    print("Task failed: " .. message)
end
```

#### Integration with Other POS Scripts
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
        }, function(status)
            if status then
                TriggerServerEvent('pos-crafting:completeItem', itemName, requiredItems)
            end
        end)
    else
        TriggerEvent('POS-Core:notify', 'POS-Inventory', 'You don\'t have the required items!', 'error', 5000)
    end
end
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

### Error Handling

The progress bar system includes built-in error handling, but you should still validate your data:

```lua
-- Synchronous error handling
local function safeProgressSync(data)
    if not data.time or not data.title then
        print("ERROR: Progress bar requires 'time' and 'title' fields")
        return false
    end
    
    local success = exports['POS-ProgressBar']:StartProgress(data)
    return success
end

-- Asynchronous error handling
local function safeProgressAsync(data, callback)
    if not data.time or not data.title then
        print("ERROR: Progress bar requires 'time' and 'title' fields")
        if callback then callback(true) end -- Call as cancelled
        return
    end
    
    exports['POS-ProgressBar']:StartProgress(data, callback)
end
```

### Best Practices

1. **Choose the right method** - Use synchronous for sequential operations, asynchronous for parallel operations
2. **Always validate data** before calling the export
3. **Handle cancellation properly** in both modes
4. **Use appropriate timing** - match progress bar duration to the actual task
5. **Provide user feedback** for both successful and cancelled operations
6. **Test thoroughly** - both completion and cancellation scenarios
7. **Always use freeze** for actions that should prevent player movement
8. **Set canStop to true** for longer actions to allow player cancellation
9. **Choose appropriate animations** that match the action being performed
10. **Test prop positioning** thoroughly as different player models may vary

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

</details>

***

## Notes

The callback parameter is **optional** - when omitted, the function operates synchronously and returns the result directly. This flexibility allows you to choose the programming style that best fits your specific use case.

This export provides a comprehensive solution for creating interactive progress bars with full animation and prop support, perfect for crafting, medical, and other interactive systems in your RedM server.