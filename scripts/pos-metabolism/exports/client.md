# Client Exports

## POS-Metabolism Client-Side Exports

This document covers the client-side exports available for POS-Metabolism, allowing you to manage player status values, retrieve metabolism data, and integrate metabolism functionality into your scripts.

***

## Available Exports

<details>

<summary><strong>📊 GetStatus Export</strong></summary>

Retrieves the current value of a specific metabolism status.

### Usage

```lua
local value = exports['POS-Metabolism']:GetStatus(statusType)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `statusType` | `string` | Yes | The status type to retrieve |

### Return Value

| Type | Description |
|------|-------------|
| `number/boolean/nil` | Current value of the status, or `nil` if not found |

### Available Status Types

| Status Type | Type | Range | Description |
|-------------|------|-------|-------------|
| `food` | `number` | 0-100 | Player's food level |
| `water` | `number` | 0-100 | Player's water/thirst level |
| `piss` | `number` | 0-100 | Player's bladder level |
| `poop` | `number` | 0-100 | Player's bowel level |
| `shower` | `number` | 0-100 | Player's cleanliness level |
| `health` | `number` | 0-600 | Player's health points |
| `poopedHimself` | `boolean` | true/false | Whether player has soiled themselves |
| `peedHimself` | `boolean` | true/false | Whether player has wet themselves |
| `alcohol` | `number` | 0-100 | Player's alcohol level |
| `deadeye` | `number` | 0-100 | Player's deadeye level |
| `stress` | `number` | 0-100 | Player's stress level |

### Examples

```lua
-- Get player's food level
local foodLevel = exports['POS-Metabolism']:GetStatus('food')
if foodLevel then
    print("Food level: " .. foodLevel)
else
    print("Food level not available")
end

-- Check if player needs to eat
local food = exports['POS-Metabolism']:GetStatus('food')
if food and food < 25 then
    TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You are getting hungry!', 'warning', 5000)
end

-- Check alcohol level before driving
local alcohol = exports['POS-Metabolism']:GetStatus('alcohol')
if alcohol and alcohol > 50 then
    TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You are too drunk to drive!', 'error', 5000)
    return
end
```

</details>

<details>

<summary><strong>📋 GetData Export</strong></summary>

Retrieves the complete metabolism data table for the player.

### Usage

```lua
local data = exports['POS-Metabolism']:GetData()
```

### Parameters

None

### Return Value

| Type | Description |
|------|-------------|
| `table/nil` | Complete metabolism data table, or `nil` if not available |

### Examples

```lua
-- Get all metabolism data
local metabolismData = exports['POS-Metabolism']:GetData()
if metabolismData then
    print("Food: " .. metabolismData.food)
    print("Water: " .. metabolismData.water)
    print("Health: " .. metabolismData.health)
else
    print("Metabolism data not available")
end

-- Check multiple statuses at once
local data = exports['POS-Metabolism']:GetData()
if data then
    if data.food < 20 or data.water < 20 then
        TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You need food or water!', 'warning', 5000)
    end
    
    if data.piss > 80 or data.poop > 80 then
        TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You should find a bathroom!', 'info', 5000)
    end
end
```

</details>

<details>

<summary><strong>🔄 UpdateStatus Export</strong></summary>

Updates a specific metabolism status by adding or subtracting a value.

### Usage

```lua
exports['POS-Metabolism']:UpdateStatus(statusType, value)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `statusType` | `string` | Yes | The status type to update |
| `value` | `number` | Yes | Amount to add/subtract (can be negative) |

### Return Value

None (triggers server-side update)

### Examples

```lua
-- Increase food by 25 points
exports['POS-Metabolism']:UpdateStatus('food', 25)

-- Decrease water by 10 points
exports['POS-Metabolism']:UpdateStatus('water', -10)

-- Increase stress by 5 points
exports['POS-Metabolism']:UpdateStatus('stress', 5)

-- Restore deadeye by 15 points
exports['POS-Metabolism']:UpdateStatus('deadeye', 15)

-- Integration with item usage
RegisterNetEvent('pos-items:useFood')
AddEventHandler('pos-items:useFood', function(itemData)
    local foodValue = itemData.nutrition or 20
    
    exports['POS-Metabolism']:UpdateStatus('food', foodValue)
    
    TriggerEvent('POS-Core:notify', 'POS-Items', 'You ate ' .. itemData.label .. ' (+' .. foodValue .. ' food)', 'success', 5000)
end)
```

</details>

<details>

<summary><strong>🔄 UpdateMultipleStatus Export</strong></summary>

Updates multiple metabolism statuses simultaneously by adding or subtracting values.

### Usage

```lua
exports['POS-Metabolism']:UpdateMultipleStatus(statusTable)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `statusTable` | `table` | Yes | Table containing status types and values to update |

### Return Value

None (triggers server-side update)

### Examples

```lua
-- Update multiple statuses at once
exports['POS-Metabolism']:UpdateMultipleStatus({
    food = 15,
    water = 10,
    stress = -5
})

-- Simulate drinking alcohol
exports['POS-Metabolism']:UpdateMultipleStatus({
    alcohol = 20,
    water = 5,
    stress = -10
})

-- Recovery from medical treatment
exports['POS-Metabolism']:UpdateMultipleStatus({
    health = 100,
    stress = -20,
    food = 10,
    water = 10
})

-- Integration with complex item usage
RegisterNetEvent('pos-items:useAlcohol')
AddEventHandler('pos-items:useAlcohol', function(itemData)
    local alcoholValue = itemData.alcoholContent or 15
    local thirstValue = itemData.thirstValue or 5
    
    exports['POS-Metabolism']:UpdateMultipleStatus({
        alcohol = alcoholValue,
        water = thirstValue,
        stress = -5
    })
    
    TriggerEvent('POS-Core:notify', 'POS-Items', 'You drank ' .. itemData.label, 'info', 5000)
end)
```

</details>

<details>

<summary><strong>⚙️ SetStatus Export</strong></summary>

Sets a specific metabolism status to an exact value.

### Usage

```lua
exports['POS-Metabolism']:SetStatus(statusType, value)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `statusType` | `string` | Yes | The status type to set |
| `value` | `number/boolean` | Yes | Exact value to set |

### Return Value

None (triggers server-side update)

### Examples

```lua
-- Set food to maximum
exports['POS-Metabolism']:SetStatus('food', 100)

-- Set player as having soiled themselves
exports['POS-Metabolism']:SetStatus('poopedHimself', true)

-- Reset stress to zero
exports['POS-Metabolism']:SetStatus('stress', 0)

-- Set specific health amount
exports['POS-Metabolism']:SetStatus('health', 450)

-- Integration with medical system
RegisterNetEvent('pos-medical:fullHeal')
AddEventHandler('pos-medical:fullHeal', function()
    exports['POS-Metabolism']:SetStatus('health', 600)
    
    TriggerEvent('POS-Core:notify', 'POS-Medical', 'You have been fully healed!', 'success', 5000)
end)
```

</details>

<details>

<summary><strong>⚙️ SetMultipleStatus Export</strong></summary>

Sets multiple metabolism statuses to exact values simultaneously.

### Usage

```lua
exports['POS-Metabolism']:SetMultipleStatus(statusTable)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `statusTable` | `table` | Yes | Table containing status types and exact values to set |

### Return Value

None (triggers server-side update)

### Examples

```lua
-- Reset all basic needs
exports['POS-Metabolism']:SetMultipleStatus({
    food = 100,
    water = 100,
    piss = 0,
    poop = 0
})

-- Set player as clean and reset accidents
exports['POS-Metabolism']:SetMultipleStatus({
    shower = 0,
    poopedHimself = false,
    peedHimself = false
})

-- Set combat-ready state
exports['POS-Metabolism']:SetMultipleStatus({
    health = 600,
    deadeye = 100,
    stress = 0
})

-- Integration with respawn system
RegisterNetEvent('pos-respawn:playerRespawned')
AddEventHandler('pos-respawn:playerRespawned', function()
    exports['POS-Metabolism']:SetMultipleStatus({
        health = 600,
        food = 75,
        water = 75,
        alcohol = 0,
        stress = 10
    })
end)
```

</details>

<details>

<summary><strong>🚿 ShowerEvent Export</strong></summary>

Triggers a shower event that cleans the player and resets cleanliness-related statuses.

### Usage

```lua
exports['POS-Metabolism']:ShowerEvent()
```

### Parameters

None

### Return Value

None

### Effects

- Sets `shower` to 0 (clean)
- Sets `poopedHimself` to false
- Sets `peedHimself` to false
- Clears ped environmental dirt
- Clears ped damage decals
- Clears ped blood damage
- Cleans ped dirt visually

### Examples

```lua
-- Basic shower usage
exports['POS-Metabolism']:ShowerEvent()

-- Integration with bathing system
RegisterNetEvent('pos-bathing:useBath')
AddEventHandler('pos-bathing:useBath', function()
    exports['POS-ProgressBar']:StartProgress({
        time = 10000,
        title = "Taking a bath...",
        canStop = true,
        freeze = true,
        animation = {
            type = "scenario",
            scenario = "WORLD_HUMAN_WASH_CLOTHES_BUCKET",
            time = 10000
        }
    }, function(status)
        if status then
            exports['POS-Metabolism']:ShowerEvent()
            TriggerEvent('POS-Core:notify', 'POS-Bathing', 'You feel clean and refreshed!', 'success', 5000)
        end
    end)
end)

-- Integration with hotel system
RegisterNetEvent('pos-hotel:useShower')
AddEventHandler('pos-hotel:useShower', function()
    local shower = exports['POS-Metabolism']:GetStatus('shower')
    
    if shower < 50 then
        exports['POS-Metabolism']:ShowerEvent()
        TriggerEvent('POS-Core:notify', 'POS-Hotel', 'You took a refreshing shower!', 'success', 5000)
    else
        TriggerEvent('POS-Core:notify', 'POS-Hotel', 'You don\'t need a shower right now.', 'info', 5000)
    end
end)
```

</details>

***

## Integration Examples

### Advanced Health Management

```lua
-- Monitor player health and provide feedback
Citizen.CreateThread(function()
    while true do
        Citizen.Wait(30000) -- Check every 30 seconds
        
        local health = exports['POS-Metabolism']:GetStatus('health')
        if health then
            if health < 100 then
                TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You are critically injured!', 'error', 5000)
            elseif health < 200 then
                TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You are badly injured.', 'warning', 5000)
            elseif health < 400 then
                TriggerEvent('POS-Core:notify', 'POS-Metabolism', 'You have some injuries.', 'info', 5000)
            end
        end
    end
end)
```

### Survival Mechanics

```lua
-- Advanced survival system
local function checkSurvivalNeeds()
    local data = exports['POS-Metabolism']:GetData()
    if not data then return end
    
    local warnings = {}
    
    -- Check food
    if data.food < 20 then
        table.insert(warnings, "You are starving!")
        -- Apply hunger effects
        if data.food < 10 then
            exports['POS-Metabolism']:UpdateStatus('health', -1)
        end
    end
    
    -- Check water
    if data.water < 20 then
        table.insert(warnings, "You are dehydrated!")
        -- Apply thirst effects
        if data.water < 10 then
            exports['POS-Metabolism']:UpdateStatus('health', -2)
        end
    end
    
    -- Check bathroom needs
    if data.piss > 90 then
        table.insert(warnings, "You really need to urinate!")
        -- Risk of accident
        if math.random(1, 100) <= 5 then
            exports['POS-Metabolism']:SetStatus('peedHimself', true)
            table.insert(warnings, "You wet yourself!")
        end
    end
    
    if data.poop > 90 then
        table.insert(warnings, "You really need to defecate!")
        -- Risk of accident
        if math.random(1, 100) <= 3 then
            exports['POS-Metabolism']:SetStatus('poopedHimself', true)
            table.insert(warnings, "You soiled yourself!")
        end
    end
    
    -- Check hygiene
    if data.shower > 80 then
        table.insert(warnings, "You smell terrible!")
    end
    
    -- Send warnings
    for _, warning in ipairs(warnings) do
        TriggerEvent('POS-Core:notify', 'POS-Metabolism', warning, 'warning', 5000)
    end
end

-- Run survival checks every 2 minutes
Citizen.CreateThread(function()
    while true do
        Citizen.Wait(120000)
        checkSurvivalNeeds()
    end
end)
```

### Restaurant Integration

```lua
-- Restaurant meal system
RegisterNetEvent('pos-restaurant:orderMeal')
AddEventHandler('pos-restaurant:orderMeal', function(mealData)
    exports['POS-ProgressBar']:StartProgress({
        time = 5000,
        title = "Eating " .. mealData.name .. "...",
        canStop = true,
        freeze = true,
        animation = {
            type = "scenario",
            scenario = "WORLD_HUMAN_SITTING_EATING",
            time = 5000
        }
    }, function(status)
        if status then
            exports['POS-Metabolism']:UpdateMultipleStatus({
                food = mealData.nutrition,
                water = mealData.hydration,
                stress = -mealData.comfort
            })
            
            TriggerEvent('POS-Core:notify', 'POS-Restaurant', 'You enjoyed the ' .. mealData.name .. '!', 'success', 5000)
        end
    end)
end)
```

### Medical System Integration

```lua
-- Medical treatment system
RegisterNetEvent('pos-medical:applyBandage')
AddEventHandler('pos-medical:applyBandage', function()
    local health = exports['POS-Metabolism']:GetStatus('health')
    
    if health < 600 then
        exports['POS-ProgressBar']:StartProgress({
            time = 8000,
            title = "Applying bandage...",
            canStop = true,
            freeze = true,
            animation = {
                type = "anim",
                animDict = "amb_misc@world_human_bum_slumped@male@base",
                anim = "base",
                flags = 1
            }
        }, function(status)
            if status then
                exports['POS-Metabolism']:UpdateStatus('health', 50)
                TriggerEvent('POS-Core:notify', 'POS-Medical', 'Bandage applied. Health restored.', 'success', 5000)
            end
        end)
    else
        TriggerEvent('POS-Core:notify', 'POS-Medical', 'You don\'t need medical attention.', 'info', 5000)
    end
end)
```

### Status Monitoring System

```lua
-- Status monitoring with visual feedback
local statusLevels = {
    critical = 10,
    low = 25,
    medium = 50,
    good = 75
}

local function getStatusLevel(value)
    if value <= statusLevels.critical then
        return "critical"
    elseif value <= statusLevels.low then
        return "low"
    elseif value <= statusLevels.medium then
        return "medium"
    else
        return "good"
    end
end

RegisterNetEvent('pos-metabolism:checkAllStatuses')
AddEventHandler('pos-metabolism:checkAllStatuses', function()
    local data = exports['POS-Metabolism']:GetData()
    if not data then return end
    
    local statusReport = {}
    
    -- Check all numeric statuses
    for status, value in pairs(data) do
        if type(value) == "number" and status ~= "health" then
            local level = getStatusLevel(value)
            table.insert(statusReport, {
                name = status,
                value = value,
                level = level
            })
        end
    end
    
    -- Send status report to UI
    TriggerEvent('pos-ui:updateStatusReport', statusReport)
end)
```

## Best Practices

1. **Always check return values** - GetStatus and GetData can return nil
2. **Use appropriate update methods** - UpdateStatus for relative changes, SetStatus for absolute values
3. **Validate status types** - Ensure you're using correct status names
4. **Handle edge cases** - Check for nil values before performing operations
5. **Use UpdateMultipleStatus** - More efficient than multiple individual updates
6. **Monitor critical statuses** - Implement warnings for low health, food, water
7. **Integrate with progress bars** - Use POS-ProgressBar for actions that affect metabolism
8. **Test thoroughly** - Verify all metabolism interactions work as expected

## Common Status Ranges

- **Good**: 75-100
- **Medium**: 50-74
- **Low**: 25-49
- **Critical**: 0-24

## Performance Considerations

- Status updates are processed server-side for security
- Use UpdateMultipleStatus for batch updates
- Avoid excessive frequent updates
- Cache status values when possible for UI updates

## Integration Notes

This export system integrates seamlessly with:
- **POS-ProgressBar** for timed actions
- **POS-Inventory** for item consumption
- **POS-Medical** for health management
- **POS-Core** for character data management

The metabolism system provides a comprehensive foundation for survival mechanics, health management, and player status tracking in your RedM server.

