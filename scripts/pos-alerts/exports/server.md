# Server Exports

## POS-Alerts Server-Side Exports

This document covers the server-side exports available for POS-Alerts, allowing you to create and manage job alerts and integrate alert functionality into your scripts.

***

## Available Exports

<details>

<summary><strong>🚨 CreateAlert Export</strong></summary>

The main export function for creating job alerts with automatic responder notifications, webhook logging, and comprehensive alert management. This export integrates with the POS-Core system for player information and job management.

### Usage

```lua
local success = exports['POS-Alerts']:CreateAlert(data)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `data` | `table` | Yes | Configuration table containing alert settings |

### Return Value

| Type | Description |
|------|-------------|
| `boolean` | `true` if alert created successfully, `false` if failed |

### Data Configuration

The `data` table supports the following options:

#### Required Settings

| Option | Type | Required | Description |
|--------|------|----------|-------------|
| `id` | `string` | Yes | Alert type identifier matching Config.JobAlerts |
| `source` | `number` | Yes/No | Player server ID creating the alert |
| `coords` | `vector3` | Yes/No | Alert coordinates (defaults to player position) |
| `name` | `string` | Yes/No | Reporter name (defaults to player's first and last name) |

### Examples

#### Basic Alert Creation

```lua
-- Create a basic police alert
local success = exports['POS-Alerts']:CreateAlert({
    id = "police",
    source = source  -- Player who triggered the alert
})

if success then
    print("Police alert created successfully!")
else
    print("Failed to create police alert")
end
```

#### Alert with Custom Coordinates

```lua
-- Create alert at specific location
local success = exports['POS-Alerts']:CreateAlert({
    id = "ems",
    coords = vector3(2635.12, -1224.89, 53.24)
})

if success then
    print("EMS alert created at custom location!")
end
```

#### Alert with Custom Name

```lua
-- Create alert with custom reporter name
local success = exports['POS-Alerts']:CreateAlert({
    id = "fire",
    coords = vector3(2635.12, -1224.89, 53.24),
    name = "Anonymous Caller"
})

if success then
    print("Fire alert created with custom name!")
end
```

#### Integration with Crime System

```lua
-- Example: Bank robbery alert
RegisterNetEvent('pos-crime:bankRobbery')
AddEventHandler('pos-crime:bankRobbery', function(bankLocation)
    local _source = source
    local playerCoords = GetEntityCoords(GetPlayerPed(_source))
    
    -- Create police alert for bank robbery
    local success = exports['POS-Alerts']:CreateAlert({
        id = "police",
        coords = bankLocation,
        name = "Bank Security System"
    })
    
    if success then
        print("Bank robbery alert sent to police!")
        
        -- Additional logic for bank robbery
        TriggerClientEvent('pos-crime:startBankRobbery', _source, bankLocation)
    end
end)
```

#### Integration with Medical System

```lua
-- Example: Medical emergency alert
RegisterNetEvent('pos-medical:emergencyCall')
AddEventHandler('pos-medical:emergencyCall', function(injuryType, location)
    local _source = source
    local playerName = exports['POS-Core']:GetFirstName(_source) .. ' ' .. exports['POS-Core']:GetLastName(_source)
    
    -- Create EMS alert
    local success = exports['POS-Alerts']:CreateAlert({
        id = "ems",
        source = _source,
        coords = location or GetEntityCoords(GetPlayerPed(_source)),
        name = playerName .. " (" .. injuryType .. ")"
    })
    
    if success then
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'success',
            message = 'Emergency services have been notified!'
        })
    else
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'error',
            message = 'Failed to contact emergency services!'
        })
    end
end)
```

#### Integration with Vehicle System

```lua
-- Example: Vehicle theft alert
RegisterNetEvent('pos-vehicles:vehicleStolen')
AddEventHandler('pos-vehicles:vehicleStolen', function(vehicleData)
    local _source = source
    local theftLocation = GetEntityCoords(GetPlayerPed(_source))
    
    -- Create police alert for vehicle theft
    local success = exports['POS-Alerts']:CreateAlert({
        id = "police",
        source = _source,
        coords = theftLocation,
        name = "Vehicle Theft - " .. vehicleData.model
    })
    
    if success then
        -- Set wanted level for player
        TriggerEvent('pos-police:setWantedLevel', _source, 2)
        
        -- Notify nearby players
        TriggerClientEvent('pos-alerts:vehicleTheftAlert', -1, theftLocation, vehicleData)
    end
end)
```

#### Integration with Business System

```lua
-- Example: Store robbery alert
RegisterNetEvent('pos-business:storeRobbery')
AddEventHandler('pos-business:storeRobbery', function(storeId, storeLocation)
    local _source = source
    local storeName = Config.Stores[storeId].name
    
    -- Create police alert
    local success = exports['POS-Alerts']:CreateAlert({
        id = "police",
        source = _source,
        coords = storeLocation,
        name = storeName .. " - Store Robbery"
    })
    
    if success then
        -- Trigger silent alarm
        TriggerClientEvent('pos-business:triggerAlarm', -1, storeId, storeLocation)
        
        -- Increase police response
        TriggerEvent('pos-police:increaseResponse', storeLocation)
    end
end)
```

#### Integration with Fire System

```lua
-- Example: Fire emergency alert
RegisterNetEvent('pos-fire:fireEmergency')
AddEventHandler('pos-fire:fireEmergency', function(fireLocation, fireIntensity)
    local _source = source
    
    -- Create fire department alert
    local success = exports['POS-Alerts']:CreateAlert({
        id = "fire",
        source = _source,
        coords = fireLocation,
        name = "Fire Emergency - Intensity: " .. fireIntensity
    })
    
    if success then
        -- Spawn fire effects
        TriggerClientEvent('pos-fire:spawnFire', -1, fireLocation, fireIntensity)
        
        -- Notify nearby players to evacuate
        TriggerClientEvent('pos-fire:evacuationAlert', -1, fireLocation)
    end
end)
```

#### Automated Alert System

```lua
-- Example: Automated security system
local function checkSecurityBreach(location, securityType)
    local nearbyPlayers = {}
    
    for _, playerId in ipairs(GetPlayers()) do
        local playerCoords = GetEntityCoords(GetPlayerPed(playerId))
        local distance = #(playerCoords - location)
        
        if distance < 50.0 then
            table.insert(nearbyPlayers, playerId)
        end
    end
    
    if #nearbyPlayers > 0 then
        -- Create security alert
        local success = exports['POS-Alerts']:CreateAlert({
            id = "police",
            source = nearbyPlayers[1],  -- Use first nearby player as source
            coords = location,
            name = "Security Breach - " .. securityType
        })
        
        if success then
            print("Security breach alert created for " .. securityType)
        end
    end
end

-- Usage in security system
RegisterNetEvent('pos-security:breachDetected')
AddEventHandler('pos-security:breachDetected', function(location, securityType)
    checkSecurityBreach(location, securityType)
end)
```

#### Conditional Alert Creation

```lua
-- Example: Conditional alert based on time and conditions
local function createConditionalAlert(alertType, playerId, conditions)
    local currentHour = tonumber(os.date("%H"))
    local canCreateAlert = true
    
    -- Check time restrictions
    if alertType == "noise_complaint" and (currentHour >= 6 and currentHour <= 22) then
        canCreateAlert = false  -- No noise complaints during day hours
    end
    
    -- Check weather conditions
    if alertType == "fire" then
        local weather = exports['POS-TimeSync']:GetWeather()
        if weather == "RAIN" or weather == "SHOWER" then
            canCreateAlert = false  -- No fire alerts during rain
        end
    end
    
    -- Check player conditions
    if conditions.playerInjured and alertType ~= "ems" then
        canCreateAlert = false  -- Injured players can only create EMS alerts
    end
    
    if canCreateAlert then
        local success = exports['POS-Alerts']:CreateAlert({
            id = alertType,
            source = playerId,
            coords = conditions.location,
            name = conditions.customName
        })
        
        return success
    else
        TriggerClientEvent('pos-notification:send', playerId, {
            type = 'error',
            message = 'Cannot create alert under current conditions'
        })
        return false
    end
end
```

#### Mass Alert System

```lua
-- Example: Create multiple alerts for major incident
local function createMassIncidentAlerts(incidentLocation, incidentType)
    local alertsCreated = 0
    
    -- Create police alert
    local policeSuccess = exports['POS-Alerts']:CreateAlert({
        id = "police",
        source = nil,  -- System generated
        coords = incidentLocation,
        name = "Major Incident - " .. incidentType
    })
    
    if policeSuccess then alertsCreated = alertsCreated + 1 end
    
    -- Create EMS alert
    local emsSuccess = exports['POS-Alerts']:CreateAlert({
        id = "ems",
        source = nil,
        coords = incidentLocation,
        name = "Mass Casualty - " .. incidentType
    })
    
    if emsSuccess then alertsCreated = alertsCreated + 1 end
    
    -- Create fire alert if needed
    if incidentType == "explosion" or incidentType == "fire" then
        local fireSuccess = exports['POS-Alerts']:CreateAlert({
            id = "fire",
            source = nil,
            coords = incidentLocation,
            name = "Fire Emergency - " .. incidentType
        })
        
        if fireSuccess then alertsCreated = alertsCreated + 1 end
    end
    
    return alertsCreated
end

-- Usage
RegisterNetEvent('pos-incidents:majorIncident')
AddEventHandler('pos-incidents:majorIncident', function(location, type)
    local alertsCreated = createMassIncidentAlerts(location, type)
    print("Created " .. alertsCreated .. " alerts for major incident")
end)
```

### Alert Configuration Dependencies

The CreateAlert export depends on your POS-Alerts configuration:

#### Job Alerts Configuration
Alerts must be configured in `Config.JobAlerts`:

```lua
Config.JobAlerts = {
    ["police"] = {
        name = "Police Emergency",
        jobs = {"police", "sheriff"},
        texts = {
            alert_sent = "Police have been notified!",
            new_alert = "New police alert received!"
        }
    },
    ["ems"] = {
        name = "Medical Emergency",
        jobs = {"ambulance", "doctor"},
        texts = {
            alert_sent = "Medical services have been notified!",
            new_alert = "New medical emergency!"
        }
    }
}
```

#### Duty Requirements
When `Config.Settings.alertsOnlyOnDuty` is enabled, alerts are only sent if responders are on duty.

### Error Handling

The export includes comprehensive error handling:

```lua
-- Safe alert creation with error handling
local function safeCreateAlert(alertData)
    -- Validate required fields
    if not alertData.id then
        print("ERROR: Alert requires 'id' field")
        return false
    end
    
    if not alertData.source then
        print("ERROR: Alert requires 'source' field")
        return false
    end
    
    -- Check if alert type exists
    if not Config.JobAlerts[alertData.id] then
        print("ERROR: Alert type '" .. alertData.id .. "' not configured")
        return false
    end
    
    -- Create alert
    local success = exports['POS-Alerts']:CreateAlert(alertData)
    
    if not success then
        print("ERROR: Failed to create alert")
        return false
    end
    
    return true
end

-- Usage
local success = safeCreateAlert({
    id = "police",
    source = source,
    coords = vector3(100, 200, 30)
})
```

### Integration with Other Systems

#### POS-Core Integration
The export automatically integrates with POS-Core for:
- Player name retrieval
- Job verification
- Permission checks

#### Webhook Integration
Alerts automatically trigger Discord webhooks with:
- Alert details
- Reporter information
- Location coordinates
- Eligible responders count

#### Notification System
The export sends notifications to:
- Alert creator (confirmation)
- Eligible responders (alert notification)

### Best Practices

1. **Always validate data** before calling the export
2. **Use meaningful alert IDs** that match your configuration
3. **Provide context** in custom names for better identification
4. **Handle return values** to ensure alerts were created successfully
5. **Consider responder availability** when creating alerts
6. **Use appropriate coordinates** for accurate location reporting
7. **Test with different scenarios** to ensure proper functionality

### Performance Considerations

- The export checks for existing alerts from the same source and removes duplicates
- Alert creation includes responder eligibility checks
- Webhook notifications are sent asynchronously
- Player notifications are optimized for multiple recipients

### Common Use Cases

1. **Crime Alerts**: Bank robberies, vehicle theft, store robberies
2. **Medical Emergencies**: Injuries, accidents, health crises
3. **Fire Emergencies**: Building fires, vehicle fires, explosions
4. **Security Breaches**: Unauthorized access, alarm triggers
5. **Traffic Incidents**: Accidents, road hazards, pursuits
6. **Environmental Hazards**: Chemical spills, gas leaks, structural damage

### Troubleshooting

**Alert not created:**
- Check if alert ID exists in Config.JobAlerts
- Verify source player ID is valid
- Ensure required data fields are provided

**No responders notified:**
- Check if responders are on duty (if duty requirement enabled)
- Verify job configuration matches responder jobs
- Check player permissions for alert access

**Webhook not sent:**
- Verify webhook configuration in config file
- Check Discord webhook URL validity
- Ensure webhook permissions are correct

**Duplicate alerts:**
- System automatically removes existing alerts from same source
- Check for multiple rapid alert creation calls
- Verify alert deletion logic

</details>

***

## Integration

This export integrates seamlessly with other POS scripts and provides a comprehensive alert system for emergency services, security systems, and player interactions. The alert system automatically handles responder notifications, webhook logging, and duplicate prevention.

