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

#### Optional Settings (Player-Based Alert)

When `source` is provided, the alert uses player information:

| Option | Type | Required | Description |
|--------|------|----------|-------------|
| `source` | `number` | No | Player server ID creating the alert |
| `coords` | `vector3` | No | Alert coordinates (defaults to player position if source provided) |
| `name` | `string` | No | Reporter name (defaults to player's first and last name if source provided) |

#### Required Settings (System-Based Alert)

When `source` is NOT provided, these become required:

| Option | Type | Required | Description |
|--------|------|----------|-------------|
| `coords` | `vector3` | Yes | Alert coordinates |
| `name` | `string` | Yes | Reporter name |

### Examples

#### Player-Based Alert (with source)

```lua
-- Create alert using player information
local success = exports['POS-Alerts']:CreateAlert({
    id = "police",
    source = source  -- Player coordinates and name automatically used
})

if success then
    print("Police alert created successfully!")
else
    print("Failed to create police alert")
end
```

#### Player-Based Alert with Custom Coordinates

```lua
-- Create alert with player name but custom location
local success = exports['POS-Alerts']:CreateAlert({
    id = "ems",
    source = source,  -- Player name automatically used
    coords = vector3(2635.12, -1224.89, 53.24)  -- Custom location
})

if success then
    print("EMS alert created at custom location!")
end
```

#### Player-Based Alert with Custom Name

```lua
-- Create alert with player coordinates but custom name
local success = exports['POS-Alerts']:CreateAlert({
    id = "fire",
    source = source,  -- Player coordinates automatically used
    name = "Anonymous Caller"  -- Custom name
})

if success then
    print("Fire alert created with custom name!")
end
```

#### System-Based Alert (without source)

```lua
-- Create alert without player source (system-generated)
local success = exports['POS-Alerts']:CreateAlert({
    id = "police",
    coords = vector3(2635.12, -1224.89, 53.24),  -- Required when no source
    name = "Security Camera System"  -- Required when no source
})

if success then
    print("System alert created successfully!")
end
```

#### Integration with Crime System

```lua
-- Example: Bank robbery alert
RegisterNetEvent('pos-crime:bankRobbery')
AddEventHandler('pos-crime:bankRobbery', function(bankLocation)
    local _source = source
    
    -- Create police alert for bank robbery
    local success = exports['POS-Alerts']:CreateAlert({
        id = "police",
        source = _source,  -- Uses player name
        coords = bankLocation,  -- Custom location
        name = "Bank Security System"  -- Override player name
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
    
    -- Create EMS alert using player information
    local success = exports['POS-Alerts']:CreateAlert({
        id = "ems",
        source = _source,  -- Uses player name and coordinates (if no location provided)
        coords = location,  -- Optional: override player location
        name = injuryType .. " Emergency"  -- Optional: override player name
    })
    
    if success then
        TriggerClientEvent('POS-Core:notify', _source, 'POS-Medical', 'Emergency services have been notified!', 'success', 5000)
    else
        TriggerClientEvent('POS-Core:notify', _source, 'POS-Medical', 'Failed to contact emergency services!', 'error', 5000)
    end
end)
```

#### Integration with Vehicle System

```lua
-- Example: Vehicle theft alert
RegisterNetEvent('pos-vehicles:vehicleStolen')
AddEventHandler('pos-vehicles:vehicleStolen', function(vehicleData)
    local _source = source
    
    -- Create police alert for vehicle theft
    local success = exports['POS-Alerts']:CreateAlert({
        id = "police",
        source = _source,  -- Uses player coordinates and name
        name = "Vehicle Theft - " .. vehicleData.model  -- Override with vehicle info
    })
    
    if success then
        -- Set wanted level for player
        TriggerEvent('pos-police:setWantedLevel', _source, 2)
        
        -- Notify nearby players
        TriggerClientEvent('pos-alerts:vehicleTheftAlert', -1, GetEntityCoords(GetPlayerPed(_source)), vehicleData)
    end
end)
```

#### Automated Alert System (System-Based)

```lua
-- Example: Automated security system
local function checkSecurityBreach(location, securityType)
    -- Create security alert without player source
    local success = exports['POS-Alerts']:CreateAlert({
        id = "police",
        coords = location,  -- Required when no source
        name = "Security System - " .. securityType  -- Required when no source
    })
    
    if success then
        print("Security breach alert created for " .. securityType)
    end
end

-- Usage in security system
RegisterNetEvent('pos-security:breachDetected')
AddEventHandler('pos-security:breachDetected', function(location, securityType)
    checkSecurityBreach(location, securityType)
end)
```

#### Mass Alert System (Mixed Sources)

```lua
-- Example: Create multiple alerts for major incident
local function createMassIncidentAlerts(incidentLocation, incidentType, reportingPlayer)
    local alertsCreated = 0
    
    if reportingPlayer then
        -- Create police alert with player source
        local policeSuccess = exports['POS-Alerts']:CreateAlert({
            id = "police",
            source = reportingPlayer,  -- Uses player name
            coords = incidentLocation,  -- Custom location
            name = "Major Incident - " .. incidentType  -- Override name
        })
        
        if policeSuccess then alertsCreated = alertsCreated + 1 end
    else
        -- Create system-generated alerts
        local policeSuccess = exports['POS-Alerts']:CreateAlert({
            id = "police",
            coords = incidentLocation,  -- Required
            name = "Emergency System - " .. incidentType  -- Required
        })
        
        if policeSuccess then alertsCreated = alertsCreated + 1 end
    end
    
    -- Create EMS alert (system-generated)
    local emsSuccess = exports['POS-Alerts']:CreateAlert({
        id = "ems",
        coords = incidentLocation,  -- Required
        name = "Mass Casualty - " .. incidentType  -- Required
    })
    
    if emsSuccess then alertsCreated = alertsCreated + 1 end
    
    return alertsCreated
end

-- Usage
RegisterNetEvent('pos-incidents:majorIncident')
AddEventHandler('pos-incidents:majorIncident', function(location, type, reportingPlayer)
    local alertsCreated = createMassIncidentAlerts(location, type, reportingPlayer)
    print("Created " .. alertsCreated .. " alerts for major incident")
end)
```

#### Timer-Based Alert System

```lua
-- Example: Automated patrol check-in system
Citizen.CreateThread(function()
    while true do
        Citizen.Wait(300000)  -- 5 minutes
        
        -- Check for overdue patrol check-ins
        local overduePatrols = GetOverduePatrols()  -- Your function
        
        for _, patrol in ipairs(overduePatrols) do
            -- Create alert for missing patrol
            local success = exports['POS-Alerts']:CreateAlert({
                id = "police",
                coords = patrol.lastKnownLocation,  -- Required (no source)
                name = "Patrol Check-In Overdue - " .. patrol.unitId  -- Required (no source)
            })
            
            if success then
                print("Overdue patrol alert created for " .. patrol.unitId)
            end
        end
    end
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
    
    -- Check if system-based alert has required fields
    if not alertData.source then
        if not alertData.coords then
            print("ERROR: Alert without source requires 'coords' field")
            return false
        end
        
        if not alertData.name then
            print("ERROR: Alert without source requires 'name' field")
            return false
        end
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

-- Usage examples
local success1 = safeCreateAlert({
    id = "police",
    source = source  -- Player-based alert
})

local success2 = safeCreateAlert({
    id = "police",
    coords = vector3(100, 200, 30),  -- System-based alert
    name = "Security Camera #1"
})
```

### Integration with Other Systems

#### POS-Core Integration
The export automatically integrates with POS-Core for:
- Player name retrieval (when source provided)
- Player coordinate retrieval (when source provided)
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
- Alert creator (confirmation) - only if source provided
- Eligible responders (alert notification)

### Best Practices

1. **Use player source when possible** - provides automatic name and coordinate retrieval
2. **Always validate data** before calling the export
3. **Use meaningful alert IDs** that match your configuration
4. **Provide context** in custom names for better identification
5. **Handle return values** to ensure alerts were created successfully
6. **Consider responder availability** when creating alerts
7. **Use appropriate coordinates** for accurate location reporting
8. **Test with different scenarios** to ensure proper functionality

### Performance Considerations

- The export checks for existing alerts from the same source and removes duplicates (when source provided)
- Alert creation includes responder eligibility checks
- Webhook notifications are sent asynchronously
- Player notifications are optimized for multiple recipients
- System-based alerts (without source) are processed faster as they skip player data retrieval

### Common Use Cases

#### Player-Based Alerts
1. **Crime Reports**: Player-reported crimes with automatic location
2. **Medical Emergencies**: Player health crises with automatic identification
3. **Fire Emergencies**: Player-reported fires with location data
4. **Traffic Incidents**: Player-reported accidents

#### System-Based Alerts
1. **Security Breaches**: Automated security system alerts
2. **Environmental Monitoring**: Sensor-based alerts
3. **Scheduled Events**: Timer-based system alerts
4. **AI-Generated Alerts**: Automated incident detection

### Troubleshooting

**Alert not created:**
- Check if alert ID exists in Config.JobAlerts
- Verify source player ID is valid (if provided)
- Ensure coords and name are provided when source is not
- Check required data fields are provided

**No responders notified:**
- Check if responders are on duty (if duty requirement enabled)
- Verify job configuration matches responder jobs
- Check player permissions for alert access

**Player information not retrieved:**
- Verify POS-Core is running and accessible
- Check if player source ID is valid
- Ensure player is connected to the server

**Webhook not sent:**
- Verify webhook configuration in config file
- Check Discord webhook URL validity
- Ensure webhook permissions are correct

**Duplicate alerts:**
- System automatically removes existing alerts from same source (player-based only)
- Check for multiple rapid alert creation calls
- Verify alert deletion logic

</details>

***

## Integration

This export integrates seamlessly with other POS scripts and provides a comprehensive alert system for emergency services, security systems, and player interactions. The alert system automatically handles responder notifications, webhook logging, and duplicate prevention. It supports both player-based alerts (with automatic data retrieval) and system-based alerts (with manual data entry).

