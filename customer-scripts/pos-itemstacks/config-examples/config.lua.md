# config.lua

```lua
Config = {}


Config.Items = {
    ['sticla_apa'] = { -- Item name
        removeItems = {
            { item = 'sticla_apa', count = 1, chance = 100 }, -- Chance is the percentage chance of removing the item, 100 means it will always be removed
        },
        addItems = {
            { item = 'sfoara', count = 1, chance = 100 }, -- Chance is the percentage chance of adding the item, 100 means it will always be added, you can add weapons too as WEAPON_PISTOL_MAUSER
            { item = 'WEAPON_PISTOL_MAUSER', count = 1, chance = 50 }, -- This will add a Mauser pistol with a 50% chance
        },
        cash = {1, 5}, -- Cash is the range of cash that can be given, it will randomly choose a number between 1 and 5
    }
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do that!',
        ['not_enough_space'] = 'You do not have enough space in the inventory to carry the items!',
        ['not_enough_items'] = 'You are missing %s x %s to be able to do this!',
        ['success'] = 'You have successfully made the item!',

    }

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
