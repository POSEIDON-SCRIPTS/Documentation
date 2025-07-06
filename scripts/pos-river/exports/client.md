# Client Exports

## POS-River Client-Side Exports

This document covers the client-side exports available for POS-River, allowing you to check player poison status and integrate with other systems.

***

## Available Exports

<details>

<summary><strong>🤒 IsPoisoned Export</strong></summary>

The main export function for checking if a player is currently poisoned by contaminated water. This export allows other scripts to detect poison status and respond accordingly.

### Usage

```lua
local isPoisoned = exports['POS-River']:IsPoisoned()
```

### Parameters

None

### Return Value

| Type | Description |
|------|-------------|
| `boolean` | `true` if player is currently poisoned, `false` if not poisoned |

### Examples

#### Basic Poison Status Check

```lua
-- Check if player is poisoned
local poisoned = exports['POS-River']:IsPoisoned()

if poisoned then
    print("Player is currently poisoned!")
else
    print("Player is not poisoned.")
end
```

#### Integration with Medical System

```lua
-- Medical system checking for poison status
RegisterNetEvent('pos-medical:checkPlayerHealth')
AddEventHandler('pos-medical:checkPlayerHealth', function()
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    if isPoisoned then
        TriggerEvent('POS-Core:notify', 'POS-Medical', 'Patient shows signs of water poisoning!', 'warning', 5000)
        
        -- Suggest treatment
        TriggerEvent('POS-Core:notify', 'POS-Medical', 'Recommend administering antidote or inducing vomiting.', 'info', 7000)
    else
        TriggerEvent('POS-Core:notify', 'POS-Medical', 'No signs of poisoning detected.', 'success', 5000)
    end
end)
```

#### Integration with Activity System

```lua
-- Prevent certain activities while poisoned
RegisterNetEvent('pos-activities:tryStartActivity')
AddEventHandler('pos-activities:tryStartActivity', function(activityType)
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    local restrictedActivities = {
        'hunting',
        'fishing',
        'mining',
        'crafting'
    }
    
    if isPoisoned then
        for _, activity in ipairs(restrictedActivities) do
            if activityType == activity then
                TriggerEvent('POS-Core:notify', 'POS-Activities', 'You feel too sick to perform this activity.', 'error', 5000)
                return
            end
        end
    end
    
    -- Continue with activity if not restricted
    TriggerEvent('pos-activities:startActivity', activityType)
end)
```

#### Integration with Item Usage

```lua
-- Check poison status before using consumables
RegisterNetEvent('pos-items:useConsumable')
AddEventHandler('pos-items:useConsumable', function(itemData)
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    if isPoisoned and itemData.category == 'food' then
        -- Chance to vomit up food when poisoned
        if math.random(100) <= 60 then
            TriggerEvent('POS-Core:notify', 'POS-Items', 'You vomited up the food due to poisoning!', 'error', 5000)
            return -- Don't apply food effects
        end
    end
    
    -- Apply normal item effects
    TriggerEvent('pos-items:applyEffects', itemData)
end)
```

#### Integration with Job System

```lua
-- Doctor job - diagnose poison
RegisterNetEvent('pos-jobs:doctor:diagnosePatient')
AddEventHandler('pos-jobs:doctor:diagnosePatient', function(targetPlayerId)
    -- Check if target player is poisoned (would need server-side implementation)
    TriggerServerEvent('pos-river:checkPlayerPoison', targetPlayerId)
end)

-- Response from server
RegisterNetEvent('pos-river:poisonDiagnosis')
AddEventHandler('pos-river:poisonDiagnosis', function(targetName, isPoisoned)
    if isPoisoned then
        TriggerEvent('POS-Core:notify', 'POS-Jobs', targetName .. ' is suffering from water poisoning.', 'warning', 5000)
        TriggerEvent('POS-Core:notify', 'POS-Jobs', 'Treatment: Administer antidote or wait for natural recovery.', 'info', 7000)
    else
        TriggerEvent('POS-Core:notify', 'POS-Jobs', targetName .. ' shows no signs of poisoning.', 'success', 5000)
    end
end)
```

#### Integration with HUD System

```lua
-- HUD system showing poison status
Citizen.CreateThread(function()
    while true do
        local isPoisoned = exports['POS-River']:IsPoisoned()
        
        if isPoisoned then
            -- Show poison indicator on HUD
            TriggerEvent('pos-hud:showStatusIcon', 'poison', true)
            TriggerEvent('pos-hud:setStatusText', 'poison', 'POISONED')
        else
            -- Hide poison indicator
            TriggerEvent('pos-hud:showStatusIcon', 'poison', false)
        end
        
        Citizen.Wait(1000) -- Check every second
    end
end)
```

#### Integration with Chat Commands

```lua
-- Chat command to check poison status
RegisterCommand('checkpoison', function()
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    if isPoisoned then
        TriggerEvent('POS-Core:notify', 'POS-River', 'You are currently poisoned from contaminated water.', 'error', 5000)
        TriggerEvent('POS-Core:notify', 'POS-River', 'Find a cure item or wait for natural recovery.', 'info', 5000)
    else
        TriggerEvent('POS-Core:notify', 'POS-River', 'You are not poisoned.', 'success', 5000)
    end
end)
```

#### Integration with Notification System

```lua
-- Monitor poison status and notify on changes
local lastPoisonStatus = false

Citizen.CreateThread(function()
    while true do
        local currentPoisonStatus = exports['POS-River']:IsPoisoned()
        
        if currentPoisonStatus ~= lastPoisonStatus then
            if currentPoisonStatus then
                TriggerEvent('POS-Core:notify', 'POS-River', 'You have been poisoned by contaminated water!', 'error', 8000)
                TriggerEvent('POS-Core:notify', 'POS-River', 'Vomit to reduce poison effects or find antidote.', 'info', 6000)
            else
                TriggerEvent('POS-Core:notify', 'POS-River', 'You have recovered from water poisoning.', 'success', 5000)
            end
            
            lastPoisonStatus = currentPoisonStatus
        end
        
        Citizen.Wait(2000) -- Check every 2 seconds
    end
end)
```

#### Integration with Store System

```lua
-- Store system - recommend cure items when poisoned
RegisterNetEvent('pos-store:openStore')
AddEventHandler('pos-store:openStore', function(storeType)
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    if isPoisoned and storeType == 'general' then
        TriggerEvent('POS-Core:notify', 'POS-Store', 'You look unwell. We have antidotes available.', 'info', 5000)
        
        -- Highlight cure items in store
        TriggerEvent('pos-store:highlightItems', {
            'antidote',
            'health_cure',
            'herbal_remedy'
        })
    end
end)
```

#### Integration with Vehicle System

```lua
-- Prevent driving while severely poisoned
RegisterNetEvent('pos-vehicles:tryEnterVehicle')
AddEventHandler('pos-vehicles:tryEnterVehicle', function(vehicle, seat)
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    if isPoisoned and seat == -1 then -- Driver seat
        TriggerEvent('POS-Core:notify', 'POS-Vehicles', 'You feel too sick to drive safely.', 'error', 5000)
        return false -- Prevent entering driver seat
    end
    
    return true -- Allow entering as passenger
end)
```

#### Integration with Crafting System

```lua
-- Crafting system - create antidotes
RegisterNetEvent('pos-crafting:craftItem')
AddEventHandler('pos-crafting:craftItem', function(itemName, ingredients)
    if itemName == 'antidote' then
        local isPoisoned = exports['POS-River']:IsPoisoned()
        
        if isPoisoned then
            TriggerEvent('POS-Core:notify', 'POS-Crafting', 'Crafting antidote for immediate use.', 'info', 5000)
            
            -- Auto-use antidote if player is poisoned
            Citizen.SetTimeout(3000, function()
                TriggerEvent('POS-Core:notify', 'POS-Crafting', 'Antidote crafted and administered!', 'success', 5000)
                TriggerEvent('POS-River:Client:UseItem', 'antidote')
            end)
        else
            TriggerEvent('POS-Core:notify', 'POS-Crafting', 'Antidote crafted for future use.', 'success', 5000)
        end
    end
end)
```

#### Integration with Weather System

```lua
-- Weather affects poison duration
RegisterNetEvent('pos-weather:weatherChanged')
AddEventHandler('pos-weather:weatherChanged', function(weatherType)
    local isPoisoned = exports['POS-River']:IsPoisoned()
    
    if isPoisoned then
        if weatherType == 'rain' then
            TriggerEvent('POS-Core:notify', 'POS-Weather', 'The rain makes you feel worse.', 'warning', 5000)
        elseif weatherType == 'sunny' then
            TriggerEvent('POS-Core:notify', 'POS-Weather', 'The warm sun helps with recovery.', 'info', 5000)
        end
    end
end)
```

### Advanced Usage Examples

#### Poison Status Monitoring System

```lua
-- Advanced poison monitoring with detailed tracking
local PoisonMonitor = {
    isActive = false,
    startTime = 0,
    vomitCount = 0,
    lastCheck = 0
}

function PoisonMonitor:Start()
    if not self.isActive then
        self.isActive = true
        self.startTime = GetGameTimer()
        self.vomitCount = 0
        self:Monitor()
    end
end

function PoisonMonitor:Stop()
    self.isActive = false
    self.startTime = 0
    self.vomitCount = 0
end

function PoisonMonitor:Monitor()
    Citizen.CreateThread(function()
        while self.isActive do
            local isPoisoned = exports['POS-River']:IsPoisoned()
            
            if not isPoisoned then
                local duration = GetGameTimer() - self.startTime
                local minutes = math.floor(duration / 60000)
                local seconds = math.floor((duration % 60000) / 1000)
                
                TriggerEvent('POS-Core:notify', 'POS-River', 
                    string.format('Recovered from poisoning after %dm %ds. Vomited %d times.', 
                    minutes, seconds, self.vomitCount), 'success', 8000)
                
                self:Stop()
                break
            end
            
            Citizen.Wait(1000)
        end
    end)
end

function PoisonMonitor:IncrementVomitCount()
    self.vomitCount = self.vomitCount + 1
end

-- Usage
RegisterNetEvent('pos-river:poisonStarted')
AddEventHandler('pos-river:poisonStarted', function()
    PoisonMonitor:Start()
end)

RegisterNetEvent('pos-river:playerVomited')
AddEventHandler('pos-river:playerVomited', function()
    PoisonMonitor:IncrementVomitCount()
end)
```

### Poison Status Effects

When `IsPoisoned()` returns `true`, the player experiences:

1. **Visual Effects**
   - Screen distortion and hallucination effects
   - Drunk-like visual impairment

2. **Movement Effects**
   - Reduced movement stability
   - Ragdoll effects when running/sprinting
   - Increased chance of falling

3. **Interactive Effects**
   - Periodic vomiting prompts
   - Restricted activities
   - Potential health damage

4. **Recovery Methods**
   - Natural recovery through vomiting (3 times)
   - Using cure items (antidotes)
   - Medical treatment by doctors

### Best Practices

1. **Regular Monitoring** - Check poison status regularly for time-sensitive actions
2. **User Feedback** - Provide clear notifications when poison status changes
3. **Activity Restrictions** - Prevent dangerous activities while poisoned
4. **Integration Planning** - Consider poison effects in all related systems
5. **Performance Optimization** - Avoid excessive checking in tight loops

### Performance Considerations

- The export is lightweight and returns a simple boolean value
- Safe to call frequently as it only checks a local variable
- No network calls or expensive operations involved
- Suitable for real-time monitoring systems

### Integration Notes

The `IsPoisoned` export integrates seamlessly with:
- **POS-Medical** for health diagnostics
- **POS-Items** for cure item usage
- **POS-Jobs** for doctor roleplay
- **POS-HUD** for status display
- **POS-Activities** for activity restrictions
- **POS-Stores** for item recommendations

### Related Functions

The poison system also includes:
- Automatic poison detection from contaminated water
- Vomiting mechanics for recovery
- Cure item integration
- Visual and movement effects
- Configurable poison chances and durations

</details>

***

## Integration

This export provides essential poison status information for creating immersive survival and medical roleplay experiences. The poison system adds realistic consequences to drinking contaminated water while providing multiple recovery paths for players.

