# Server Exports

## POS-Metabolism Server-Side Exports

This document covers the server-side exports available for POS-Metabolism, allowing you to manage player metabolism data from server-side scripts and integrate with other server systems.

***

## Available Exports

<details>

<summary><strong>🔄 ResetData Export</strong></summary>

Resets all metabolism data for a player to default values and updates both cache and database.

### Usage

```lua
exports['POS-Metabolism']:ResetData(source)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `source` | `number` | Yes | Player server ID |

### Return Value

None (updates player data and sends to client)

### Default Values Reset

| Status | Default Value |
|--------|---------------|
| `food` | 100 |
| `water` | 100 |
| `piss` | 0 |
| `poop` | 0 |
| `shower` | 0 |
| `health` | 600 |
| `poopedHimself` | false |
| `peedHimself` | false |
| `alcohol` | 0 |
| `deadeye` | 100 |
| `stress` | 0 |

### Examples

```lua
-- Reset player metabolism data
exports['POS-Metabolism']:ResetData(source)

-- Integration with character creation
RegisterNetEvent('pos-character:characterCreated')
AddEventHandler('pos-character:characterCreated', function()
    local _source = source
    
    -- Reset metabolism data for new character
    exports['POS-Metabolism']:ResetData(_source)
    
    TriggerClientEvent('pos-notification:send', _source, {
        type = 'success',
        message = 'Welcome! Your character has been created.'
    })
end)

-- Integration with admin commands
RegisterCommand('resetmetabolism', function(source, args)
    local _source = source
    
    -- Check if player has admin permissions
    if not exports['POS-Core']:IsPlayerAdmin(_source) then
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'error',
            message = 'You don\'t have permission to use this command.'
        })
        return
    end
    
    local targetId = tonumber(args[1]) or _source
    
    if GetPlayerName(targetId) then
        exports['POS-Metabolism']:ResetData(targetId)
        
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'success',
            message = 'Metabolism data reset for player ' .. GetPlayerName(targetId)
        })
        
        TriggerClientEvent('pos-notification:send', targetId, {
            type = 'info',
            message = 'Your metabolism data has been reset by an admin.'
        })
    else
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'error',
            message = 'Player not found.'
        })
    end
end)

-- Integration with respawn system
RegisterNetEvent('pos-respawn:playerRespawned')
AddEventHandler('pos-respawn:playerRespawned', function()
    local _source = source
    
    -- Reset metabolism data on respawn
    exports['POS-Metabolism']:ResetData(_source)
    
    TriggerClientEvent('pos-notification:send', _source, {
        type = 'info',
        message = 'Your metabolism has been restored.'
    })
end)

-- Integration with medical system
RegisterNetEvent('pos-medical:fullRecovery')
AddEventHandler('pos-medical:fullRecovery', function()
    local _source = source
    
    -- Full recovery resets all metabolism
    exports['POS-Metabolism']:ResetData(_source)
    
    TriggerClientEvent('pos-notification:send', _source, {
        type = 'success',
        message = 'You have made a full recovery!'
    })
end)
```

</details>

<details>

<summary><strong>⚙️ SetMultipleStatus Export</strong></summary>

Sets multiple metabolism statuses to exact values simultaneously from server-side.

### Usage

```lua
exports['POS-Metabolism']:SetMultipleStatus(source, statusTable)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `source` | `number` | Yes | Player server ID |
| `statusTable` | `table` | Yes | Table containing status types and exact values to set |

### Return Value

None (updates player data and sends to client)

### Examples

```lua
-- Set multiple statuses at once
exports['POS-Metabolism']:SetMultipleStatus(source, {
    food = 100,
    water = 100,
    stress = 0
})

-- Integration with item usage
RegisterNetEvent('pos-items:useRestorativeItem')
AddEventHandler('pos-items:useRestorativeItem', function(itemData)
    local _source = source
    
    -- Apply item effects
    exports['POS-Metabolism']:SetMultipleStatus(_source, {
        food = itemData.foodRestore or 100,
        water = itemData.waterRestore or 100,
        health = itemData.healthRestore or 600,
        stress = itemData.stressRestore or 0
    })
    
    TriggerClientEvent('pos-notification:send', _source, {
        type = 'success',
        message = 'You used ' .. itemData.label .. ' and feel restored!'
    })
end)

-- Integration with hotel system
RegisterNetEvent('pos-hotel:useDeluxeRoom')
AddEventHandler('pos-hotel:useDeluxeRoom', function()
    local _source = source
    
    -- Deluxe room provides full restoration
    exports['POS-Metabolism']:SetMultipleStatus(_source, {
        food = 100,
        water = 100,
        shower = 0,
        stress = 0,
        poopedHimself = false,
        peedHimself = false
    })
    
    TriggerClientEvent('pos-notification:send', _source, {
        type = 'success',
        message = 'You feel completely refreshed after staying in the deluxe room!'
    })
end)

-- Integration with saloon system
RegisterNetEvent('pos-saloon:orderSpecialMeal')
AddEventHandler('pos-saloon:orderSpecialMeal', function(mealType)
    local _source = source
    
    local mealEffects = {
        ['hearty_stew'] = {
            food = 95,
            water = 80,
            stress = 10
        },
        ['luxury_feast'] = {
            food = 100,
            water = 100,
            stress = 0,
            alcohol = 25
        },
        ['health_tonic'] = {
            health = 600,
            stress = 5
        }
    }
    
    local effects = mealEffects[mealType]
    if effects then
        exports['POS-Metabolism']:SetMultipleStatus(_source, effects)
        
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'success',
            message = 'You enjoyed the ' .. mealType:gsub('_', ' ') .. '!'
        })
    end
end)

-- Integration with event system
RegisterNetEvent('pos-events:specialEvent')
AddEventHandler('pos-events:specialEvent', function(eventType)
    local _source = source
    
    if eventType == 'health_checkup' then
        -- Medical event - restore health and check status
        exports['POS-Metabolism']:SetMultipleStatus(_source, {
            health = 600,
            stress = 0
        })
        
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'success',
            message = 'You received a health checkup and feel great!'
        })
    elseif eventType == 'feast_event' then
        -- Food event - restore hunger and thirst
        exports['POS-Metabolism']:SetMultipleStatus(_source, {
            food = 100,
            water = 100,
            stress = 0
        })
        
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'success',
            message = 'You participated in the feast and feel satisfied!'
        })
    end
end)

-- Integration with job system
RegisterNetEvent('pos-jobs:completeShift')
AddEventHandler('pos-jobs:completeShift', function(jobType, hoursWorked)
    local _source = source
    
    -- Different jobs have different effects
    local jobEffects = {
        ['doctor'] = {
            stress = 20,
            food = 80,
            water = 70
        },
        ['lawman'] = {
            stress = 30,
            food = 60,
            water = 50
        },
        ['miner'] = {
            stress = 40,
            food = 50,
            water = 40,
            shower = 60
        },
        ['farmer'] = {
            stress = 15,
            food = 70,
            water = 60,
            shower = 30
        }
    }
    
    local effects = jobEffects[jobType]
    if effects then
        -- Apply work effects based on hours worked
        local adjustedEffects = {}
        for status, value in pairs(effects) do
            adjustedEffects[status] = math.max(0, value - (hoursWorked * 5))
        end
        
        exports['POS-Metabolism']:SetMultipleStatus(_source, adjustedEffects)
        
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'info',
            message = 'You completed your shift and feel the effects of ' .. hoursWorked .. ' hours of work.'
        })
    end
end)
```

</details>

***

## Integration Examples

### Advanced Admin System

```lua
-- Admin metabolism management commands
RegisterCommand('setplayerhealth', function(source, args)
    local _source = source
    
    if not exports['POS-Core']:IsPlayerAdmin(_source) then
        return
    end
    
    local targetId = tonumber(args[1])
    local healthValue = tonumber(args[2]) or 600
    
    if targetId and GetPlayerName(targetId) then
        exports['POS-Metabolism']:SetMultipleStatus(targetId, {
            health = math.max(0, math.min(600, healthValue))
        })
        
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'success',
            message = 'Set ' .. GetPlayerName(targetId) .. '\'s health to ' .. healthValue
        })
    end
end)

RegisterCommand('healall', function(source)
    local _source = source
    
    if not exports['POS-Core']:IsPlayerAdmin(_source) then
        return
    end
    
    local players = GetPlayers()
    local healedCount = 0
    
    for _, playerId in ipairs(players) do
        local id = tonumber(playerId)
        if id then
            exports['POS-Metabolism']:SetMultipleStatus(id, {
                health = 600,
                food = 100,
                water = 100,
                stress = 0
            })
            healedCount = healedCount + 1
        end
    end
    
    TriggerClientEvent('pos-notification:send', _source, {
        type = 'success',
        message = 'Healed ' .. healedCount .. ' players.'
    })
end)
```

### Scheduled Metabolism Events

```lua
-- Daily metabolism reset event
local function scheduleDailyReset()
    local currentTime = os.time()
    local nextMidnight = currentTime + (86400 - (currentTime % 86400))
    
    local timeUntilMidnight = (nextMidnight - currentTime) * 1000
    
    SetTimeout(timeUntilMidnight, function()
        local players = GetPlayers()
        
        for _, playerId in ipairs(players) do
            local id = tonumber(playerId)
            if id then
                -- Daily reset - restore some basic needs
                exports['POS-Metabolism']:SetMultipleStatus(id, {
                    deadeye = 100,
                    stress = 0
                })
                
                TriggerClientEvent('pos-notification:send', id, {
                    type = 'info',
                    message = 'A new day has begun. You feel refreshed!'
                })
            end
        end
        
        -- Schedule next daily reset
        scheduleDailyReset()
    end)
end

-- Start the daily reset scheduler
scheduleDailyReset()
```

### Anti-Cheat Integration

```lua
-- Validate metabolism data changes
local function validateMetabolismData(source, data)
    local valid = true
    local violations = {}
    
    -- Check for impossible values
    if data.health > 600 then
        table.insert(violations, 'health too high: ' .. data.health)
        valid = false
    end
    
    if data.food > 100 or data.water > 100 then
        table.insert(violations, 'food/water above maximum')
        valid = false
    end
    
    if data.stress < 0 or data.alcohol < 0 then
        table.insert(violations, 'negative values detected')
        valid = false
    end
    
    -- Log violations
    if not valid then
        print('^3[METABOLISM-ANTICHEAT] Player ' .. source .. ' violations: ' .. table.concat(violations, ', ') .. '^0')
        
        -- Reset player data as punishment
        exports['POS-Metabolism']:ResetData(source)
        
        TriggerClientEvent('pos-notification:send', source, {
            type = 'error',
            message = 'Invalid metabolism data detected. Data has been reset.'
        })
    end
    
    return valid
end

-- Monitor for suspicious metabolism changes
RegisterNetEvent('pos-metabolism:dataChanged')
AddEventHandler('pos-metabolism:dataChanged', function(newData)
    local _source = source
    validateMetabolismData(_source, newData)
end)
```

## Best Practices

1. **Always validate source IDs** - Check if player exists before applying changes
2. **Use appropriate value ranges** - Ensure values stay within valid bounds
3. **Log important changes** - Track metabolism resets and major modifications
4. **Handle edge cases** - Account for disconnected players and invalid data
5. **Batch updates efficiently** - Use SetMultipleStatus for multiple changes
6. **Integrate with anti-cheat** - Validate data to prevent exploitation
7. **Provide user feedback** - Send notifications for significant changes
8. **Consider performance** - Avoid excessive frequent updates

## Security Considerations

- Server-side validation prevents client-side tampering
- Data is stored securely in the database
- Changes are logged for administrative oversight
- Anti-cheat systems can monitor for suspicious patterns

## Performance Notes

- Updates are processed asynchronously for better performance
- Database writes are batched when possible
- Client callbacks are used to ensure data consistency
- Cache system reduces database load

## Integration Notes

These exports integrate seamlessly with:
- **POS-Core** for character management
- **POS-Inventory** for item effects
- **POS-Medical** for health systems
- **POS-Jobs** for work-related effects
- **POS-TimeSync** for weather-based changes
- **POS-Notification** for user feedback

The server-side metabolism system provides secure, validated metabolism management with comprehensive logging and anti-cheat integration. It is designed for performance and reliability, ensuring a smooth gameplay experience.

