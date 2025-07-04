# config.lua

````lua
Config = {}

Config.Debug = true -- if you want to show the id in the name of the blips from database

Config.Settings = {
    blipUpdateInterval = 5000, -- how often to update the blips in ms
    alertInterval = 300000, -- how often to show default alerts in ms
    restartTimer = true, -- if you want to show the on screen timer when the server is restarting
    restartAlerts = 1800, -- if you want to show the alerts when the server is restarting (time in seconds, 1800/900/450) -- this will start the restart timer too
    restartAlertInterval = 300000, -- how often to show the restart alerts in ms
    restartTimerUpdate = 30000,
    alertsOnlyOnDuty = true, -- if you want to be able to create an alert only if someone is on duty
}


Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = '', 
    
    alert_created = {
        sensitive = true, -- Shows full user info
        nonSensitive = true -- Shows limited user info
    },
    
    alert_claimed = {
        sensitive = true,
        nonSensitive = true
    },
    
    alert_deleted = {
        sensitive = true,
        nonSensitive = true
    },
    
    alert_cancelled = {
        sensitive = true,
        nonSensitive = true
    },
    
    alert_responder_cleared = {
        sensitive = true,
        nonSensitive = true
    }
}

Config.JobAlerts = {
 
    [1] = { -- id of the alert, can be id or name 
        name = 'Police job alerts',
        jobs = {
            ['police'] = {
                allowAll = true, -- if true, allow all grades
                grades = {
                    1, 2, 3, 4 
                }
            },
            ['policemanager'] = {
                allowAll = true, -- if true, allow all grades
                grades = {
                    1, 2, 3, 4 
                }
            },
        },

        dutyCheck = function (source, job, grade) -- function to check if the player is on duty, if false, alert will not send
            return true
        end,

        alertCommand = 'police_alert', -- command to trigger the alert, if false, no command will be registered
        cancelCommand = 'cancel_police_alert', -- command to cancel the alert, if false, no command will be registered

        texts = {
            ['alert_sent'] = 'The alert was sent to the police, a officer will be shortly on his way.',
            ['new_alert'] = 'Someone has called the police, open the menu and check the alert!',

            ['alert_claimed'] = 'The alert has been claimed, please wait for the officer to arrive.',
        },

        alertBlip = {  -- blip data
            name = 'Police alert',
            scale = 60.0,
            model = 'blip_mp_playstyle_offensive',
            modifier = 'BLIP_MODIFIER_MP_COLOR_20',
            zone = true,
        },

        responderBlip = {
            name = 'Police responder',
            scale = 60.0,
            model = 's_m_y_cop_01',
            modifier = 'BLIP_MODIFIER_MP_COLOR_20',
            zone = false,
        }
    },
    
    [2] = { -- id of the alert, can be id or name 
        name = 'Sisika job alerts',
        jobs = {
            ['sisika'] = {
                allowAll = true, -- if true, allow all grades
                grades = {
                    1, 2, 3, 4 
                }
            },
            ['policemanager'] = {
                allowAll = true, -- if true, allow all grades
                grades = {
                    1, 2, 3, 4 
                }
            }
        },

        dutyCheck = function (source, job, grade) -- function to check if the player is on duty, if false, alert will not send
            return true
        end,

        dutyCommand = { -- or false to disable it
            command = 'sisika_duty', -- command to see how many players are on duty, if false, no command will be registered
            text = 'There are currently %s players on duty in Sisika.',
        },

        alertCommand = 'sisika_alert', -- command to trigger the alert, if false, no command will be registered
        cancelCommand = 'cancel_sisika_alert', -- command to cancel the alert, if false, no command will be registered

        texts = {
            ['alert_sent'] = 'The alert was sent to the police, a officer will be shortly on his way.',
            ['new_alert'] = 'Someone has called the police, open the menu and check the alert!',

            ['alert_claimed'] = 'The alert has been claimed, please wait for the officer to arrive.',
        },

        alertBlip = {  -- blip data
            name = 'Police alert',
            scale = 60.0,
            model = 'blip_ambient_bounty_hunter',
            modifier = 'BLIP_MODIFIER_MP_COLOR_20',
            zone = true,
        },

        responderBlip = {
            name = 'Police responder',
            scale = 60.0,
            model = 'blip_ambient_chore',
            modifier = 'BLIP_MODIFIER_MP_COLOR_20',
            zone = false,
        }
    },
    
}

Config.Alerts = {
    "Remember to always stay in character — immersive roleplay makes the world come alive.",
    "Respect every player’s story. Roleplay is a shared experience, not a solo act.",
    "Use /me and /do commands to enhance your interactions and add depth to your character.",
    "Metagaming and powergaming are strictly prohibited. Keep the roleplay fair and realistic.",
    "Take your time with scenes — slow, meaningful roleplay is the most rewarding.",
    "If you're new, don’t be afraid to ask for help in-character. Locals might surprise you.",
    "Always think from your character's perspective — act and speak as they would.",
    "AFK or idle? Find a seat or use an emote to maintain immersion for others.",
    "Server rules exist to protect the RP environment — make sure you're familiar with them.",
    "Have fun and contribute to the story. Your character helps shape the world for everyone."
}

Config.RestartAlerts = {
    "The server is restarting in {time} minutes. Please wrap up your roleplay.",
    "Attention: Server restart in {time} minutes. Ensure your character is safe.",
    "Heads up! The server will restart in {time} minutes. Finish your current scene.",
    "Reminder: Server restart in {time} minutes. Don't forget to save your progress.",
    "Final call! The server will be down for maintenance in {time} minutes."
}

Config.MenuAlign = 'left' -- top-right, top-left, bottom-right, bottom-left

Config.Commands = {
    [1] = {
        Command = 'jobAlerts', -- or false to disable it
        Description = 'Show all the job menus that you have access to.',
        Parameters = {},
        Groups = {} 
    },
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['alert_accepted'] = 'The alert has been accepted, follow the marker to the location of the alert.',
        ['alert_removed'] =  'The alert has been removed.',
        ['alert_cleared'] = 'You have removed the alert from the map.',
        ['responder_removed'] = 'A responder has been removed from the alert.',
        ['select_job_menu'] = 'Select Job Menu',

        ['unknown'] = 'Unknown',
        ['not_allowed'] = 'You are not allowed or you are not on duty in order to perform this action.',
        ['clear_alert'] = 'Clear Alert',
        ['clear_alert_desc'] = 'Remove the current alert from your map and stop responding.',
        ['no_alerts'] = 'No Alerts Available',
        ['no_alerts_desc'] = 'There are currently no active alerts for your job.',
        ['responders_count'] = '%d responders',
        ['no_responders'] = 'No responders',
        ['select_alert'] = 'Click to view alert options',
        ['accept_alert'] = 'Accept Alert',
        ['accept_alert_desc'] = 'Accept this alert and set waypoint to location.',
        ['preview_location'] = 'Preview Location',
        ['preview_location_desc'] = 'Set a temporary waypoint to preview the alert location.',
        ['delete_alert'] = 'Delete Alert',
        ['delete_alert_desc'] = 'Permanently remove this alert from the system.',
        ['waypoint_set'] = 'Waypoint has been set to preview location.',
        ['alert_deleted'] = 'Alert has been successfully deleted.',
        ['no_allowed_menus'] = 'You do not have access to any alert menus.',
        ['already_claimed'] = 'You have already claimed this alert.',
        ['no_alert_found'] = 'No alert found or alert has already been removed.',
            
        ['webhook_user_information'] = 'User Information',
        ['webhook_target_information'] = 'Target Information',
        ['webhook_alert_id'] = 'Alert ID',
        ['webhook_alert_index'] = 'Alert Index',
        ['webhook_alert_name'] = 'Alert Name',
        ['webhook_alert_reporter'] = 'Reporter',
        ['webhook_alert_location'] = 'Location',
        ['webhook_responder_count'] = 'Responders',
        ['webhook_total_responders'] = 'Total Responders',
        ['webhook_remaining_responders'] = 'Remaining Responders',
        ['webhook_eligible_responders'] = 'Eligible Responders',
        
        -- Webhook Titles
        ['webhook_alert_created'] = '🚨 New Alert Created',
        ['webhook_alert_claimed'] = '✅ Alert Claimed',
        ['webhook_alert_deleted'] = '🗑️ Alert Deleted',
        ['webhook_alert_cancelled'] = '❌ Alert Cancelled',
        ['webhook_alert_responder_cleared'] = '👤 Responder Cleared',
        ['alert_has_been_deleted'] = 'Your alert has been deleted by a responding representative!',
        
        -- Webhook Messages
        ['webhook_alert_created_info'] = 'A new %s alert (#%s) has been created by %s',
        ['webhook_alert_claimed_info'] = 'Alert #%s (%s) has been claimed by a responder',
        ['webhook_alert_deleted_info'] = 'Alert #%s (%s) has been deleted by an authorized user',
        ['webhook_alert_cancelled_info'] = 'Alert #%s (%s) has been cancelled by the reporter',
        ['webhook_alert_responder_cleared_info'] = 'A responder has cleared from alert #%s',

        ['restart_skipped'] = 'The server restart has been skipped. No restart will occur at this time.',
        
        ['alert_description'] = [[ 
            <div style="font-family: 'Segoe UI', Arial, sans-serif; background-color: #1a1a1a; border-radius: 8px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.5); margin: 10px; max-width: 400px;"> 
                <!-- Header --> 
                <div style="color: white; padding: 12px 16px; display: flex; align-items: center; border-bottom: 2px solid #3a3a3a;"> 
                    <div style="flex-grow: 1; font-weight: bold;">Alert #%s</div> 
                </div> 
        
                <!-- Main Content --> 
                <div style="background-color: #2a2a2a; padding: 16px;"> 
                    <!-- Reporter and City Info --> 
                    <div style="background-color: #1a1a1a; padding: 10px 16px; margin-bottom: 16px; border-radius: 4px;"> 
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 12px; text-align: center;"> 
                            <div> 
                                <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">Reporter</div> 
                                <div style="color: #ffffff; font-weight: bold; font-size: 16px;">%s</div> 
                            </div> 
                            <div> 
                                <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">City</div> 
                                <div style="color: #ffffff; font-weight: bold; font-size: 16px;">%s</div> 
                            </div> 
                        </div> 
                    </div> 
        
                    <!-- Responders Info --> 
                    <div style="background-color: #1a1a1a; border-radius: 4px; padding: 12px; margin-bottom: 16px;"> 
                        <div style="text-align: center;"> 
                            <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">Responders</div> 
                            <div style="color: #ffffff; font-weight: bold; font-size: 16px;">%s</div> 
                        </div> 
                    </div> 
        
                    <!-- Alert Description Box --> 
                    <div style="background-color: #111111; border-left: 4px solid #00bcd4; padding: 12px 16px; border-radius: 4px;"> 
                        <div style="color: #ffffff; font-size: 14px; font-weight: 500;">%s</div> 
                    </div> 
                </div> 
            </div> 
        ]],
        ['no_responders_available'] = 'No responders are currently available for this alert. Please try again later.'        
    }
}




local isServer = IsDuplicityVersion()
function Notify(source, text, type) --You can replace with your own notification system. Type can be fail, success, info, announcement.
    local time = 5000 
    if type == 'announcement' then
        time = 15000 -- longer time for announcements
    end

    if isServer then
        TriggerClientEvent("POS-Core:notify", source, 'USI', text, type, time) 
    else 
        TriggerEvent("POS-Core:notify", 'USI', text, type, time)
    end
end




--- `CreateAlert` function for external use.
--- 
--- This function allows other resources to create alerts based on the provided data.
--- It validates the input data and ensures the alert ID exists in the configuration.
--- If valid, it creates an alert and returns `true`. Otherwise, it logs an error and returns `false`.
---
--- ### Parameters:
--- - `data` (table): A table containing the alert data.
---   - `data.id` (string): The unique identifier for the alert. Must exist in `Config.JobAlerts`.
---   - `data.source` (number, optional): The source player ID creating the alert.
---   - `data.coords` (vector3, optional): The coordinates of the alert. Defaults to the player's current position.
---   - `data.name` (string, optional): The name of the alert reporter. Defaults to the player's name.
---
--- ### Returns:
--- - `boolean`: `true` if the alert was successfully created, `false` otherwise.
---
--- ### Example Usage:
--- ```lua
--- local success = exports['POS-Alerts']:CreateAlert({
---     id = "police_alert",
---     source = 1, -- do not use source and coords together, use one of them
---     coords = vector3(123.45, 678.90, 21.0), -- or use source to get the player's position and name
---     name = "John Doe"
--- })
---
--- if success then
---     print("Alert created successfully!")
--- else
---     print("Failed to create alert.")
--- end
--- ```
````
