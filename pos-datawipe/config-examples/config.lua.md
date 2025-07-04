# config.lua

```lua
Config = {}

Config.CheckTime = 3600 * 1000 -- 1 hour in milliseconds
Config.WipeTime = 3600 * 1000 * 24 * 30 -- 30 days in milliseconds

Config.Tables = {
    ["pos_clans_players"] = { -- table name
        identifier = "identifier", -- row name for identifier, or nil
        characterid = "characterid", -- row name for characterid, or nil
    }
}

Config.Webhook = '' -- Discord webhook link or false

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS

Config.Text = {
    EN = {
        ['webhook_delete_player'] = 'A player has been deleted due to inactivity:',
        ['days'] = 'days',
        
        ['webhook_delete_logs'] = "\n\n Player: \n" ..
            "Identifier: %s\n" ..
            "Character IDS: %s\n" ..
            "Was found and deleted %s times from the database\n" ..
            "Last connection: %s (%s)\n",
    }
}

```
