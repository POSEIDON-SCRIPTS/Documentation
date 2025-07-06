# Server Exports

## POS-TimeSync Server-Side Exports

This document covers the server-side exports available for POS-TimeSync, allowing you to retrieve weather information and integrate time/weather functionality into your scripts.

***

## Available Exports

<details>

<summary><strong>🌤️ GetWeather Export</strong></summary>

The main export function for retrieving current weather information from the POS-TimeSync system. This export provides weather data based on your configured weather patterns or real-world weather integration.

### Usage

```lua
local weather = exports['POS-TimeSync']:GetWeather(region)
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `region` | `string` | No | Optional region name for region-specific weather (when using weather patterns) |

### Return Value

| Type | Description |
|------|-------------|
| `string` | Weather type string (e.g., "SUNNY", "RAIN", "SNOW", "FOG", etc.) |

### Weather Types

The export can return the following weather types:

| Weather Type | Description |
|--------------|-------------|
| `SUNNY` | Clear sunny weather |
| `CLEAR` | Clear sky |
| `CLOUDS` | Cloudy weather |
| `OVERCAST` | Overcast sky |
| `RAIN` | Light rain |
| `DRIZZLE` | Light drizzle |
| `THUNDER` | Thunderstorm |
| `RAIN_LIGHT` | Light rain |
| `THUNDER_LIGHT` | Light thunderstorm |
| `SNOW` | Snow weather |
| `BLIZZARD` | Heavy snow/blizzard |
| `SNOW_LIGHT` | Light snow |
| `XMAS` | Christmas weather |
| `HALLOWEEN` | Halloween weather |
| `FOG` | Foggy weather |
| `MISTY` | Misty conditions |
| `SANDSTORM` | Sandstorm weather |
| `HURRICANE` | Hurricane conditions |

### Examples

#### Basic Weather Retrieval

```lua
-- Get current weather without specifying region
local currentWeather = exports['POS-TimeSync']:GetWeather()
print("Current weather: " .. currentWeather)

-- Use weather in your script logic
if currentWeather == "RAIN" then
    -- Handle rain-specific logic
    TriggerClientEvent('pos-farming:setGrowthBonus', -1, 1.5)
elseif currentWeather == "SUNNY" then
    -- Handle sunny weather logic
    TriggerClientEvent('pos-farming:setGrowthBonus', -1, 1.0)
end
```

#### Region-Specific Weather

```lua
-- Get weather for a specific region (when using weather patterns)
local newAustinWeather = exports['POS-TimeSync']:GetWeather("NEWAUSTIN")
local lemoneyneWeather = exports['POS-TimeSync']:GetWeather("LEMOYNE")

print("New Austin weather: " .. newAustinWeather)
print("Lemoyne weather: " .. lemoneyneWeather)

-- Apply different effects based on regional weather
if newAustinWeather == "SANDSTORM" then
    TriggerClientEvent('pos-effects:enableSandstorm', -1, "NEWAUSTIN")
end
```

#### Integration with Farming System

```lua
-- Example: Farming system that responds to weather
RegisterNetEvent('pos-farming:checkWeatherConditions')
AddEventHandler('pos-farming:checkWeatherConditions', function(cropType, location)
    local _source = source
    local weather = exports['POS-TimeSync']:GetWeather(location)
    
    local growthMultiplier = 1.0
    local damageChance = 0
    
    if weather == "RAIN" or weather == "DRIZZLE" then
        growthMultiplier = 1.5  -- 50% faster growth in rain
    elseif weather == "SUNNY" then
        growthMultiplier = 1.2  -- 20% faster growth in sun
    elseif weather == "THUNDER" or weather == "HURRICANE" then
        damageChance = 0.3  -- 30% chance of crop damage
    elseif weather == "SNOW" or weather == "BLIZZARD" then
        growthMultiplier = 0.5  -- 50% slower growth in cold
        damageChance = 0.2  -- 20% chance of frost damage
    end
    
    TriggerClientEvent('pos-farming:updateCropConditions', _source, {
        growth = growthMultiplier,
        damage = damageChance,
        weather = weather
    })
end)
```

#### Integration with Economy System

```lua
-- Example: Dynamic pricing based on weather
local function getWeatherBasedPrice(itemName, basePrice)
    local weather = exports['POS-TimeSync']:GetWeather()
    
    local priceMultiplier = 1.0
    
    if itemName == "water" then
        if weather == "SUNNY" or weather == "SANDSTORM" then
            priceMultiplier = 1.5  -- Water costs more in hot weather
        elseif weather == "RAIN" or weather == "DRIZZLE" then
            priceMultiplier = 0.8  -- Water costs less in rain
        end
    elseif itemName == "umbrella" then
        if weather == "RAIN" or weather == "THUNDER" then
            priceMultiplier = 2.0  -- Umbrellas cost more in rain
        else
            priceMultiplier = 0.5  -- Umbrellas cost less in clear weather
        end
    elseif itemName == "warm_clothes" then
        if weather == "SNOW" or weather == "BLIZZARD" then
            priceMultiplier = 1.8  -- Warm clothes cost more in cold
        else
            priceMultiplier = 0.7  -- Warm clothes cost less in warm weather
        end
    end
    
    return math.floor(basePrice * priceMultiplier)
end

-- Usage in shop system
RegisterNetEvent('pos-shops:getItemPrice')
AddEventHandler('pos-shops:getItemPrice', function(itemName, basePrice)
    local _source = source
    local finalPrice = getWeatherBasedPrice(itemName, basePrice)
    
    TriggerClientEvent('pos-shops:receiveItemPrice', _source, itemName, finalPrice)
end)
```

#### Integration with Activity System

```lua
-- Example: Activity restrictions based on weather
local function canPerformActivity(activityType, location)
    local weather = exports['POS-TimeSync']:GetWeather(location)
    
    local restrictions = {
        fishing = {
            allowed = {"SUNNY", "CLEAR", "CLOUDS", "OVERCAST", "RAIN", "DRIZZLE"},
            bonus = {"RAIN", "DRIZZLE"},  -- Better fishing in rain
            penalty = {"THUNDER", "HURRICANE", "BLIZZARD"}
        },
        hunting = {
            allowed = {"SUNNY", "CLEAR", "CLOUDS", "OVERCAST", "FOG", "MISTY"},
            bonus = {"FOG", "MISTY"},  -- Better hunting in fog
            penalty = {"RAIN", "THUNDER", "SNOW", "BLIZZARD"}
        },
        mining = {
            allowed = {"SUNNY", "CLEAR", "CLOUDS", "OVERCAST", "RAIN", "DRIZZLE", "SNOW"},
            bonus = {},
            penalty = {"THUNDER", "HURRICANE", "BLIZZARD", "SANDSTORM"}
        }
    }
    
    local activityData = restrictions[activityType]
    if not activityData then return true, 1.0 end
    
    -- Check if weather allows activity
    local isAllowed = false
    for _, allowedWeather in ipairs(activityData.allowed) do
        if weather == allowedWeather then
            isAllowed = true
            break
        end
    end
    
    if not isAllowed then
        return false, 0.0, "Weather conditions are too dangerous for this activity"
    end
    
    -- Calculate bonus/penalty
    local multiplier = 1.0
    
    for _, bonusWeather in ipairs(activityData.bonus) do
        if weather == bonusWeather then
            multiplier = 1.5
            break
        end
    end
    
    for _, penaltyWeather in ipairs(activityData.penalty) do
        if weather == penaltyWeather then
            multiplier = 0.7
            break
        end
    end
    
    return true, multiplier, nil
end

-- Usage in activity system
RegisterNetEvent('pos-activities:startActivity')
AddEventHandler('pos-activities:startActivity', function(activityType, location)
    local _source = source
    local canStart, multiplier, errorMessage = canPerformActivity(activityType, location)
    
    if not canStart then
        TriggerClientEvent('pos-notification:send', _source, {
            type = 'error',
            message = errorMessage
        })
        return
    end
    
    local weather = exports['POS-TimeSync']:GetWeather(location)
    TriggerClientEvent('pos-activities:startActivityClient', _source, {
        type = activityType,
        location = location,
        weather = weather,
        multiplier = multiplier
    })
end)
```

#### Integration with Notification System

```lua
-- Example: Weather change notifications
local lastWeather = nil

Citizen.CreateThread(function()
    while true do
        Citizen.Wait(30000)  -- Check every 30 seconds
        
        local currentWeather = exports['POS-TimeSync']:GetWeather()
        
        if lastWeather and lastWeather ~= currentWeather then
            -- Weather changed, notify all players
            local weatherMessages = {
                RAIN = "It's starting to rain. Find shelter!",
                THUNDER = "A thunderstorm is approaching. Take cover!",
                SNOW = "Snow is beginning to fall.",
                BLIZZARD = "A blizzard is incoming! Seek immediate shelter!",
                SUNNY = "The weather is clearing up.",
                SANDSTORM = "A sandstorm is approaching. Find shelter immediately!",
                HURRICANE = "Hurricane conditions detected! Take immediate shelter!"
            }
            
            local message = weatherMessages[currentWeather] or "Weather conditions are changing."
            
            TriggerClientEvent('pos-notification:send', -1, {
                type = 'info',
                message = message,
                duration = 5000
            })
        end
        
        lastWeather = currentWeather
    end
end)
```

### Configuration Dependencies

The GetWeather export behavior depends on your POS-TimeSync configuration:

#### Real Weather Mode
When `Config.CityRealWeather` is set, the export returns real-world weather data:

```lua
Config.CityRealWeather = 'New York'  -- Returns real weather for New York
```

#### Weather Pattern Mode
When `Config.WeatherPattern` is set, the export returns weather based on your configured patterns:

```lua
Config.WeatherPattern = 'Summer'  -- Returns weather from Summer pattern
```

#### Weather Caching
Weather data is cached when `Config.RealWeatherCache` is set:

```lua
Config.RealWeatherCache = 180  -- Cache weather for 3 minutes
```

### Error Handling

The export includes built-in error handling and fallbacks:

```lua
-- Safe weather retrieval with fallback
local function getSafeWeather(region, fallback)
    local weather = exports['POS-TimeSync']:GetWeather(region)
    
    if not weather or weather == "" then
        return fallback or "SUNNY"
    end
    
    return weather
end

-- Usage
local weather = getSafeWeather("NEWAUSTIN", "CLEAR")
```

### Performance Considerations

- Weather data is cached when real-world weather is used
- Regional weather is processed efficiently for pattern-based systems
- The export is optimized for frequent calls

### Integration Examples

#### Weather-Based Spawn Rates
```lua
-- Example: Animal spawn rates based on weather
local function getWeatherSpawnMultiplier(animalType)
    local weather = exports['POS-TimeSync']:GetWeather()
    
    local multipliers = {
        deer = {
            RAIN = 0.8,
            SUNNY = 1.2,
            SNOW = 0.6
        },
        bear = {
            RAIN = 1.3,
            SUNNY = 0.9,
            SNOW = 0.7
        },
        rabbit = {
            RAIN = 0.7,
            SUNNY = 1.1,
            SNOW = 0.5
        }
    }
    
    return multipliers[animalType] and multipliers[animalType][weather] or 1.0
end
```

#### Weather-Based Damage
```lua
-- Example: Environmental damage based on weather
local function applyWeatherDamage(playerId)
    local weather = exports['POS-TimeSync']:GetWeather()
    
    local damages = {
        BLIZZARD = 2,    -- 2 damage in blizzard
        SANDSTORM = 3,   -- 3 damage in sandstorm
        HURRICANE = 5    -- 5 damage in hurricane
    }
    
    local damage = damages[weather]
    if damage then
        TriggerClientEvent('pos-health:takeDamage', playerId, damage, 'environmental')
    end
end
```

### Best Practices

1. **Cache results** when calling frequently to avoid performance issues
2. **Handle nil returns** gracefully with fallback weather
3. **Use appropriate regions** when working with pattern-based weather
4. **Consider weather transitions** when implementing weather-dependent features
5. **Test thoroughly** with different weather configurations

### Notes

- The export returns `nil` if weather system is disabled (`Config.UseWeather = false`)
- Regional weather only works with pattern-based weather systems
- Real-world weather ignores the region parameter
- Weather data is synchronized across all clients automatically

</details>

***

## Integration

This export integrates seamlessly with other POS scripts and can be used to create dynamic, weather-responsive gameplay systems. The weather data is automatically synchronized with all clients through the POS-TimeSync system.