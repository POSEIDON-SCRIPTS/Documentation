# config.lua

```lua
Config = {
    Debug = false,
    -- Time synchronization settings
    UseTime = true,  -- Whether to use the in-game time synchronization system (default: true)
    RealTime = false,  -- Whether to use real-world time (false means using a custom day/night cycle)
    DayDuration = 4 * 3600,  -- Duration of the in-game day (in seconds). For example, 4 hours of in-game daytime.
    NightDuration = 2 * 3600,  -- Duration of the in-game night (in seconds). For example, 2 hours of in-game nighttime.
    
    DefaultTransition = 5,  -- Default transition time (in seconds) for weather and time changes

    -- Weather synchronization settings
    UseWeather = true,  -- Whether to use the in-game weather synchronization system (default: true)
    CityRealWeather = 'Bucharest',  -- City name to fetch real-time weather data (leave as false if you don't want to use real-world weather data)
    RealWeatherCache = 180,  -- Time (in seconds) to cache the real-world weather data. Set to 0 or false to disable weather fetching from real-world sources.

    -- Default weather pattern settings
    WeatherPattern = false,  -- Default weather pattern when CityRealWeather is off (e.g., "Apocalypse", "Thunderstorm")

    -- Snow-related settings
    SnowInWeatherSnow = true,  -- If true, snow will cover the ground when the weather is snowy (if weather snow is enabled).

    -- Daytime configuration (used to define the range of daytime hours)
    DayTime = {6, 18}  -- Defines the in-game daytime hours. This example means it is considered daytime from 6 AM to 6 PM in the game.
}

Config.Commands = {
    [1] = {
        Command = 'settime', -- or false to disable it
        Description = 'Set the in-game time to a specified hour, minute, and second.',
        Parameters = {
            { name="hour", help="Specify the hour to set the time to (0-23)." },
            { name="minute", help="Specify the minute to set the time to (0-59)." },
            { name="second", help="Specify the second to set the time to (0-59)." },
            { name="transition", help="Specify the transition time in milliseconds." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [2] = {
        Command = 'setweather', -- or false to disable it
        Description = 'Set the in-game weather to a specified type.',
        Parameters = {
            { name="weather", help="Specify the weather type to set (e.g., sunny, cloudy, rainy)." },
            { name="transition", help="Specify the transition time in milliseconds." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [3] = {
        Command = 'localTime', -- or false to disable it
        Description = 'Set the in-game time to your preferred time.',
        Parameters = {
            { name="hour", help="Specify the hour to set the time to (0-23)." },
            { name="minute", help="Specify the minute to set the time to (0-59)." },
            { name="second", help="Specify the second to set the time to (0-59)." },
            { name="transition", help="Specify the transition time in milliseconds." },
        },
        Groups = {}
    }
}

Config.Pattern = {
    Cycle = 60000,  -- Time to cycle weather patterns (in ms)

    Patterns = {
        -- Christmas Weather Pattern 
        Christmas = {
            weather = {
                'sunny', 'sunny', 'snow', 'overcast', 'sunny', 'misty', 'snow', 'fog', 
                'overcast', 'overcast', 'misty', 'overcast', 'overcast', 'sunny', 
                'snow', 'snow', 'blizzard', 'overcast', 'groundblizzard'
            },
            transition = 15,  -- 15 seconds transition
            snow = true,  -- Snow will be on the ground
        },

        Christmas2 = {
            weather = {
                ['BayouNwa'] = {
                    'sunny', 'sunny', 'snow', 'overcast', 'sunny', 'misty', 'snow', 'fog',
                    'overcast', 'overcast', 'misty', 'overcast', 'overcast', 'sunny',
                    'snow', 'snow', 'blizzard', 'overcast', 'groundblizzard'
                },
                ['Heartlands'] = {
                    'snow'
                },
                ['Unknown'] = {
                    'sunny', 'sunny', 'snow', 'overcast', 'sunny', 'misty', 'snow', 'fog',
                    'overcast', 'overcast', 'misty', 'overcast', 'overcast', 'sunny',
                    'snow', 'snow', 'blizzard', 'overcast', 'groundblizzard'
                }

            },
            transition = 15,  -- 15 seconds transition
            snow = true,  -- Snow will be on the ground
        },


        -- Summer Weather Pattern
        Summer = {
            weather = {'sunny', 'sunny', 'sunny', 'sunny', 'sunny', 'sunny', 'clouds', 'clouds', 'thunderstorm'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Halloween Weather Pattern
        Halloween = {
            weather = {'hurricane', 'thunderstorm', 'hurricane', 'hurricane', 'hurricane'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Apocalypse Weather Pattern
        Apocalypse = {
            weather = {'hurricane', 'thunderstorm', 'sandstorm', 'groundblizzard', 'blizzard'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Spring Weather Pattern 
        Spring = {
            weather = {'sunny', 'clouds', 'drizzle', 'fog', 'overcast', 'rain', 'thunderstorm', 'sunny', 'clouds'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Autumn Weather Pattern 
        Autumn = {
            weather = {'overcast', 'clouds', 'rain', 'drizzle', 'fog', 'snowlight', 'sunny', 'misty', 'overcast', 'groundblizzard'},
            transition = 15,  -- 15 seconds transition
            snow = true,  -- Snow on the ground can occur
        },

        -- Stormy Night 
        StormyNight = {
            weather = {'thunderstorm', 'thunderstorm', 'rain', 'thunder', 'hail', 'hail', 'rain', 'thunderstorm'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Tropical Rainstorm 
        TropicalRainstorm = {
            weather = {'rain', 'rain', 'rain', 'drizzle', 'drizzle', 'rain', 'thunderstorm', 'clouds'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Cold Front 
        ColdFront = {
            weather = {'snow', 'snow', 'snow', 'snow', 'blizzard', 'groundblizzard', 'snowlight', 'snow'},
            transition = 15,  -- 15 seconds transition
            snow = true,  -- Snow on the ground
        },

        -- Sandstorm 
        Sandstorm = {
            weather = {'sandstorm', 'sandstorm', 'sandstorm', 'HURRICANE', 'HURRICANE', 'HURRICANE', 'sandstorm'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },

        -- Calm Weather 
        CalmWeather = {
            weather = {'sunny', 'clouds', 'clear', 'sunny', 'clouds'},
            transition = 15,  -- 15 seconds transition
            snow = false,  -- No snow
        },
    }
}

-- Available weather regions, which can be put above in every weather pattern
-- BayouNwa
-- bigvalley
-- BluewaterMarsh
-- ChollaSprings
-- Cumberland
-- DiezCoronas
-- GaptoothRidge
-- greatPlains
-- GrizzliesEast
-- GrizzliesWest
-- GuarmaD
-- Heartlands
-- HennigansStead
-- Perdido
-- PuntaOrgullo
-- RioBravo
-- roanoke
-- scarlettMeadows
-- TallTrees
-- Unknown


weatherTypes = {
    [0] = "SUNNY",
    [1] = "SUNNY", -- Clear sky
    [2] = "CLOUDS", -- Partly cloudy
    [3] = "OVERCAST", -- Overcast
    [45] = "FOG", -- Fog
    [48] = "FOG", -- Depositing rime fog
    [51] = "DRIZZLE", -- Light drizzle
    [53] = "DRIZZLE", -- Moderate drizzle
    [55] = "DRIZZLE", -- Dense drizzle
    [56] = "SLEET", -- Freezing drizzle (light)
    [57] = "SLEET", -- Freezing drizzle (dense)
    [61] = "RAIN", -- Slight rain
    [63] = "RAIN", -- Moderate rain
    [65] = "SHOWER", -- Heavy rain
    [66] = "HAIL", -- Freezing rain (light)
    [67] = "HAIL", -- Freezing rain (heavy)
    [71] = "SNOW", -- Light snow
    [73] = "SNOW", -- Moderate snow
    [75] = "SNOW", -- Heavy snow
    [77] = "WHITEOUT", -- Snow grains
    [80] = "SHOWER", -- Rain shower (light)
    [81] = "SHOWER", -- Rain shower (moderate)
    [82] = "THUNDERSTORM", -- Rain shower (violent)
    [85] = "SNOWLIGHT", -- Snow shower (light)
    [86] = "SNOW", -- Snow shower (heavy)
    [95] = "THUNDER", -- Thunderstorm (slight/moderate)
    [96] = "THUNDERSTORM", -- Thunderstorm with slight hail
    [99] = "THUNDERSTORM", -- Thunderstorm with heavy hail
}

-- Available weathers:
--"SUNNY", "CLOUDS", "MISTY", "FOG", "OVERCASTDARK", "OVERCAST", "THUNDER", "THUNDERSTORM", "DRIZZLE", "RAIN", "SHOWER", "HURRICANE", "SNOWLIGHT", "SNOW", "GROUNDBLIZZARD", "SANDSTORM"
Config.WeatherTypes = {
    'SUNNY', 'CLOUDS', 'MISTY', 'FOG', 'OVERCASTDARK', 'OVERCAST', 'THUNDER', 
    'THUNDERSTORM', 'DRIZZLE', 'RAIN', 'SHOWER', 'HURRICANE', 
    'SNOWLIGHT', 'SNOW', 'GROUNDBLIZZARD', 'SANDSTORM'
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['cannot_use_real_time'] = 'You cannot use this command while having real time enabled!', 
        ['time_set'] = 'You set the time to %s:%s:%s. And it will be set in %s ms',
        ['not_allowed'] = 'You are not allowed to do that!',
        ['weather_set'] = 'You have set the weather to: %s with a transition of %s s',
        ['weather_set_region'] = 'You have set the weather to %s in this region with a transition of %s s',
        ['weather_disabled'] = 'Weather control is currently disabled!',
        ['cannot_use_real_weather'] = 'You cannot use this command while real weather is enabled!',
        ['invalid_weather_type'] = 'You must specify a valid weather type!',
        ['invalid_weather_type_list'] = 'Invalid weather type! Allowed types are: %s',
        ['time_set_override'] = 'You have set your time to %s %s %s, and will be set in %s ms',
        ['time_reset_override'] = 'You have reset your time override, and now it will be synced with the server',
    
    },
}





local isServer = IsDuplicityVersion()
function Notify(source, text, type) --You can replace with your own notification system. Type can be fail, success, info.
    if isServer then
        TriggerClientEvent("POS-Core:notify", source, 'USI', text, type, 5000) 
    else 
        TriggerEvent("POS-Core:notify", 'USI', text, type, 5000)
    end
end


```
