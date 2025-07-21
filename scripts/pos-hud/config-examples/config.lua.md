# config.lua

```lua
Config = {}

Config.DefaultEnabled = true
Config.HudCommand = 'hud' -- Command to toggle the HUD or false to disable it
Config.ShowDuration = false -- Duration in milliseconds to show the HUD after the command is executed or false to show it permanently
Config.HudVersion = 1

Config.DynamicHide = {
    RadarHidden = false,
    PauseMenu = false,
    SpectatorMode = false,
    HudHidden = false,
    NuiFocused = false
}

Config.HudSettings = { -- Special Values: hour, date, players (players online) | You can use functions to get the value of the normal values (example: function(source) return exports['POS-Core']:GetMoney(source) end)
    [1] = {
        TopValues = {
            {
                name = "Hour",
                icon = {
                    icon = "fa-solid fa-clock",
                    color = "white" 
                },
                value = "game_hour" -- or game_hour for the game hour
            },
            
            {
                name = "Date",
                icon = {
                    icon = "fa-solid fa-calendar",
                    color = "white"
                },
                value = "date"
            },

            {
                name = "Players",
                icon = {
                    icon = "fa-solid fa-users",
                    color = "white" 
                },
                value = "players"
            }            
        },

        NormalValues = {
            {
                name = "Money",
                icon = {
                    icon = "fa-solid fa-sack-dollar",
                    color = "#28A745"
                },
                value = function(source)
                    return '$' .. exports['POS-Core']:GetMoney(source)
                end
            },

            {
                name = "ID",
                icon = {
                    icon = "fa-solid fa-sack-dollar",
                    color = "#28A745"
                },
                value = function(source)
                    return source
                end
            },
                   
        }
    },

    [2] = {
        TopValues = {
            {
                name = "Hour",
                icon = {
                    icon = "fa-solid fa-clock",
                    color = "white"
                },
                value = "hour"
            },

            {
                name = "Date",
                icon = {
                    icon = "fa-solid fa-calendar",
                    color = "white"
                },
                value = "date"
            },

            {
                name = "Players",
                icon = {
                    icon = "fa-solid fa-users",
                    color = "white"
                },
                value = "players"
            },
        },

        NormalValues = {
            {
                name = "ID",
                icon = {
                    icon = "fa-solid fa-fingerprint",
                    color = "#7289DA" 
                },
                value = function (source)
                    return source
                end,
            },
            
            {
                name = "Money",
                icon = {
                    icon = "fa-solid fa-sack-dollar",
                    color = "#28A745"
                },
                value = function (source)
                    return '$' .. exports['POS-Core']:GetMoney(source)
                end,
            }
        },
            
    }
}

Config.Settings = {
    UpdateInterval = 1000, -- Update interval in milliseconds
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['hud_description'] = 
        [[
            <div class="webside">
        
              <div class="webbox">
                <span class="websiteLink">website link</span>
                <i class="fa-solid fa-arrow-pointer"></i>
              </div>
        
              <div class="webbox">
                <span class="discordLink">discord.gg/</span>
                <i class="fa-brands fa-discord"></i>
              </div>
        
        
            </div> 
        ]],
    },
}
```
