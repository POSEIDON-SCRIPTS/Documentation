# Client Exports

## POS-TimeSync Client-Side Exports

This document covers the client-side exports available for POS-TimeSync, allowing you to retrieve weather and time information directly from the client for UI elements, gameplay mechanics, and visual effects.

***

## Available Exports

<details>

<summary><strong>🌤️ GetWeather Export</strong></summary>

The client-side export function for retrieving current weather information from the POS-TimeSync system. This export provides the current weather state as displayed on the client.

### Usage

```lua
local weather = exports['POS-TimeSync']:GetWeather()
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| None | - | - | This export takes no parameters |

### Return Value

| Type | Description |
|------|-------------|
| `string` | Weather type string (e.g., "SUNNY", "RAIN", "SNOW", "FOG", etc.) |

### Weather Types

The export can return the following weather types:

| Weather Type | Description |
|--------------|-------------|
| `SUNNY` | Clear sunny weather |
| `CLOUDS` | Cloudy weather |
| `MISTY` | Misty conditions |
| `FOG` | Foggy weather |
| `OVERCASTDARK` | Dark overcast sky |
| `OVERCAST` | Overcast sky |
| `THUNDER` | Thunderstorm |
| `THUNDERSTORM` | Heavy thunderstorm |
| `DRIZZLE` | Light drizzle |
| `RAIN` | Rain weather |
| `SHOWER` | Heavy rain shower |
| `HURRICANE` | Hurricane conditions |
| `SNOWLIGHT` | Light snow |
| `SNOW` | Snow weather |
| `GROUNDBLIZZARD` | Ground-level blizzard |
| `SANDSTORM` | Sandstorm weather |

### Examples

#### Basic Weather Display

```lua
-- Get current weather for UI display
local currentWeather = exports['POS-TimeSync']:GetWeather()
SendNUIMessage({
    action = "updateWeather",
    weather = currentWeather
})

-- Display weather icon based on type
local weatherIcons = {
    SUNNY = "☀️",
    RAIN = "🌧️",
    SNOW = "❄️",
    FOG = "🌫️",
    THUNDER = "⛈️",
    CLOUDS = "☁️"
}

local icon = weatherIcons[currentWeather] or "🌤️"
print("Current weather: " .. icon .. " " .. currentWeather)
```

#### Weather-Based Camera Effects

```lua
-- Apply camera effects based on weather
local function applyWeatherEffects()
    local weather = exports['POS-TimeSync']:GetWeather()
    
    if weather == "FOG" or weather == "MISTY" then
        -- Reduce visibility
        SetWeatherTypeNow("FOG")
        AnimpostfxPlay("DeathFailMP", 0, false)
    elseif weather == "RAIN" or weather == "SHOWER" then
        -- Add rain effects
        SetWeatherTypeNow("RAIN")
        AnimpostfxPlay("MP_race_crash", 0, false)
    elseif weather == "SANDSTORM" then
        -- Add sandstorm effects
        AnimpostfxPlay("MP_corona_tournament_DOF", 0, false)
    else
        -- Clear effects
        AnimpostfxStop("DeathFailMP")
        AnimpostfxStop("MP_race_crash")
        AnimpostfxStop("MP_corona_tournament_DOF")
    end
end

-- Update effects when weather changes
Citizen.CreateThread(function()
    local lastWeather = nil
    while true do
        Citizen.Wait(5000)
        local currentWeather = exports['POS-TimeSync']:GetWeather()
        
        if lastWeather ~= currentWeather then
            applyWeatherEffects()
            lastWeather = currentWeather
        end
    end
end)
```

#### Weather-Based UI Updates

```lua
-- Update UI based on weather conditions
local function updateWeatherUI()
    local weather = exports['POS-TimeSync']:GetWeather()
    
    local weatherData = {
        type = weather,
        color = getWeatherColor(weather),
        description = getWeatherDescription(weather),
        severity = getWeatherSeverity(weather)
    }
    
    SendNUIMessage({
        action = "updateWeatherDisplay",
        data = weatherData
    })
end

local function getWeatherColor(weather)
    local colors = {
        SUNNY = "#FFD700",
        RAIN = "#4682B4",
        SNOW = "#E6E6FA",
        FOG = "#708090",
        THUNDER = "#2F4F4F",
        SANDSTORM = "#CD853F"
    }
    return colors[weather] or "#FFFFFF"
end

local function getWeatherDescription(weather)
    local descriptions = {
        SUNNY = "Clear skies with bright sunshine",
        RAIN = "Steady rainfall across the region",
        SNOW = "Snow falling, roads may be slippery",
        FOG = "Dense fog reducing visibility",
        THUNDER = "Thunderstorm with lightning",
        SANDSTORM = "Dangerous sandstorm conditions"
    }
    return descriptions[weather] or "Weather conditions are stable"
end

local function getWeatherSeverity(weather)
    local severities = {
        SUNNY = 1,
        CLOUDS = 1,
        MISTY = 2,
        FOG = 3,
        RAIN = 2,
        SHOWER = 3,
        THUNDER = 4,
        THUNDERSTORM = 5,
        HURRICANE = 5,
        SNOW = 2,
        SNOWLIGHT = 1,
        GROUNDBLIZZARD = 5,
        SANDSTORM = 5
    }
    return severities[weather] or 1
end
```

</details>

<details>

<summary><strong>⏰ GetTime Export</strong></summary>

The client-side export function for retrieving current time information from the POS-TimeSync system. This export provides the current game time in a structured format.

### Usage

```lua
local timeData = exports['POS-TimeSync']:GetTime()
```

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| None | - | - | This export takes no parameters |

### Return Value

| Type | Description |
|------|-------------|
| `table` | Table containing time information with `hour`, `minute`, and `second` keys |

### Return Table Structure

```lua
{
    hour = 14,    -- Hour (0-23)
    minute = 30,  -- Minute (0-59)
    second = 45   -- Second (0-59)
}
```

### Examples

#### Basic Time Display

```lua
-- Get current time for UI display
local timeData = exports['POS-TimeSync']:GetTime()
local timeString = string.format("%02d:%02d:%02d", timeData.hour, timeData.minute, timeData.second)

SendNUIMessage({
    action = "updateTime",
    time = timeString,
    hour = timeData.hour,
    minute = timeData.minute,
    second = timeData.second
})

print("Current time: " .. timeString)
```

#### 12-Hour Format Display

```lua
-- Convert to 12-hour format with AM/PM
local function formatTime12Hour()
    local timeData = exports['POS-TimeSync']:GetTime()
    local hour = timeData.hour
    local minute = timeData.minute
    local ampm = "AM"
    
    if hour == 0 then
        hour = 12
    elseif hour > 12 then
        hour = hour - 12
        ampm = "PM"
    elseif hour == 12 then
        ampm = "PM"
    end
    
    return string.format("%d:%02d %s", hour, minute, ampm)
end

-- Usage
local displayTime = formatTime12Hour()
print("Current time: " .. displayTime)
```

#### Time-Based UI Themes

```lua
-- Change UI theme based on time of day
local function updateTimeBasedTheme()
    local timeData = exports['POS-TimeSync']:GetTime()
    local hour = timeData.hour
    
    local theme = "day"
    
    if hour >= 6 and hour < 12 then
        theme = "morning"
    elseif hour >= 12 and hour < 18 then
        theme = "afternoon"
    elseif hour >= 18 and hour < 21 then
        theme = "evening"
    else
        theme = "night"
    end
    
    SendNUIMessage({
        action = "updateTheme",
        theme = theme,
        hour = hour
    })
end

-- Update theme every minute
Citizen.CreateThread(function()
    local lastMinute = -1
    while true do
        Citizen.Wait(1000)
        local timeData = exports['POS-TimeSync']:GetTime()
        
        if timeData.minute ~= lastMinute then
            updateTimeBasedTheme()
            lastMinute = timeData.minute
        end
    end
end)
```

#### Business Hours Check

```lua
-- Check if a business should be open based on time
local function isBusinessOpen(openHour, closeHour)
    local timeData = exports['POS-TimeSync']:GetTime()
    local currentHour = timeData.hour
    
    if openHour < closeHour then
        -- Normal hours (e.g., 9 AM to 5 PM)
        return currentHour >= openHour and currentHour < closeHour
    else
        -- Overnight hours (e.g., 10 PM to 6 AM)
        return currentHour >= openHour or currentHour < closeHour
    end
end

-- Usage examples
local isShopOpen = isBusinessOpen(8, 22)  -- 8 AM to 10 PM
local isBarOpen = isBusinessOpen(18, 2)   -- 6 PM to 2 AM
local is24HourOpen = isBusinessOpen(0, 24) -- 24/7

print("Shop open: " .. tostring(isShopOpen))
print("Bar open: " .. tostring(isBarOpen))
```

#### Time-Based Notifications

```lua
-- Show time-based notifications
local function checkTimeNotifications()
    local timeData = exports['POS-TimeSync']:GetTime()
    local hour = timeData.hour
    local minute = timeData.minute
    
    -- Check for hourly notifications
    if minute == 0 then
        if hour == 6 then
            TriggerEvent('POS-Core:notify', 'POS-TimeSync', 'Good morning! The sun is rising.', 'info', 5000)
        elseif hour == 12 then
            TriggerEvent('POS-Core:notify', 'POS-TimeSync', 'It\'s noon! Time for lunch.', 'info', 5000)
        elseif hour == 18 then
            TriggerEvent('POS-Core:notify', 'POS-TimeSync', 'Evening is approaching.', 'info', 5000)
        elseif hour == 22 then
            TriggerEvent('POS-Core:notify', 'POS-TimeSync', 'It\'s getting late. Consider resting.', 'info', 5000)
        end
    end
end

-- Check every minute
Citizen.CreateThread(function()
    local lastCheck = -1
    while true do
        Citizen.Wait(1000)
        local timeData = exports['POS-TimeSync']:GetTime()
        
        if timeData.minute ~= lastCheck then
            checkTimeNotifications()
            lastCheck = timeData.minute
        end
    end
end)
```

#### Real-Time Clock Widget

```lua
-- Create a real-time updating clock widget
local function createClockWidget()
    local function updateClock()
        local timeData = exports['POS-TimeSync']:GetTime()
        local weather = exports['POS-TimeSync']:GetWeather()
        
        local clockData = {
            time = string.format("%02d:%02d:%02d", timeData.hour, timeData.minute, timeData.second),
            time12 = formatTime12Hour(),
            weather = weather,
            hour = timeData.hour,
            minute = timeData.minute,
            second = timeData.second
        }
        
        SendNUIMessage({
            action = "updateClock",
            data = clockData
        })
    end
    
    -- Update every second
    Citizen.CreateThread(function()
        while true do
            Citizen.Wait(1000)
            updateClock()
        end
    end)
end

-- Initialize clock widget
createClockWidget()
```

#### Time-Based Lighting

```lua
-- Adjust lighting based on time of day
local function updateTimeLighting()
    local timeData = exports['POS-TimeSync']:GetTime()
    local hour = timeData.hour
    
    if hour >= 6 and hour < 8 then
        -- Sunrise
        SetArtificialLightsState(false)
        SetStreetlights(false)
    elseif hour >= 8 and hour < 19 then
        -- Daytime
        SetArtificialLightsState(false)
        SetStreetlights(false)
    elseif hour >= 19 and hour < 21 then
        -- Sunset
        SetArtificialLightsState(true)
        SetStreetlights(true)
    else
        -- Night
        SetArtificialLightsState(true)
        SetStreetlights(true)
    end
end

-- Update lighting every game minute
Citizen.CreateThread(function()
    local lastHour = -1
    while true do
        Citizen.Wait(5000)
        local timeData = exports['POS-TimeSync']:GetTime()
        
        if timeData.hour ~= lastHour then
            updateTimeLighting()
            lastHour = timeData.hour
        end
    end
end)
```

#### Combined Weather and Time Display

```lua
-- Create a comprehensive weather and time display
local function createWeatherTimeDisplay()
    local timeData = exports['POS-TimeSync']:GetTime()
    local weather = exports['POS-TimeSync']:GetWeather()
    
    local displayData = {
        time = {
            hour = timeData.hour,
            minute = timeData.minute,
            second = timeData.second,
            formatted = string.format("%02d:%02d", timeData.hour, timeData.minute),
            formatted12 = formatTime12Hour()
        },
        weather = {
            type = weather,
            display = weather:lower():gsub("^%l", string.upper),
            icon = getWeatherIcon(weather),
            color = getWeatherColor(weather)
        },
        period = getTimePeriod(timeData.hour)
    }
    
    SendNUIMessage({
        action = "updateWeatherTime",
        data = displayData
    })
end

local function getTimePeriod(hour)
    if hour >= 5 and hour < 12 then
        return "Morning"
    elseif hour >= 12 and hour < 17 then
        return "Afternoon"
    elseif hour >= 17 and hour < 21 then
        return "Evening"
    else
        return "Night"
    end
end

local function getWeatherIcon(weather)
    local icons = {
        SUNNY = "☀️",
        CLOUDS = "☁️",
        RAIN = "🌧️",
        SHOWER = "🌦️",
        THUNDER = "⛈️",
        THUNDERSTORM = "⛈️",
        SNOW = "❄️",
        SNOWLIGHT = "🌨️",
        FOG = "🌫️",
        MISTY = "🌫️",
        SANDSTORM = "🌪️",
        HURRICANE = "🌀"
    }
    return icons[weather] or "🌤️"
end

-- Update display every 5 seconds
Citizen.CreateThread(function()
    while true do
        Citizen.Wait(5000)
        createWeatherTimeDisplay()
    end
end)
```

</details>

***

## Integration

These client exports integrate seamlessly with your UI systems, gameplay mechanics, and visual effects. They provide real-time access to synchronized weather and time data, perfect for:

- **HUD Elements**: Real-time clocks and weather displays
- **Visual Effects**: Time and weather-based lighting and atmosphere
- **Gameplay Mechanics**: Time-sensitive activities and weather-dependent features
- **Business Logic**: Operating hours and weather-based restrictions
- **Immersion Features**: Dynamic themes and atmospheric changes

### Best Practices

1. **Cache results** when calling frequently to avoid performance issues
2. **Use appropriate update intervals** - not every frame is necessary
3. **Handle UI updates efficiently** with NUI messaging
4. **Consider performance impact** of visual effects
5. **Test across different times and weather** conditions

### Notes

- Both exports return current client-side values
- Data is automatically synchronized from the server
- Exports return `nil` if the respective systems are disabled
- Time format is 24-hour by default but can be converted to 12-hour format
- Weather types match server-side weather system exactly