# config.lua

```lua
Config = {}


Config.DistanceToInteract = 3.0 -- distance to interact with the backpack, you can change it to your liking
Config.DistanceToShow = 100.0 -- distance to show the backpack, you can change it to your liking

Config.Settings = {
    requireEmptyBackpack = true, -- if true, the player must have an empty backpack to put be able to remove it 
    dropBackpackOnDeath = true, -- if true, the backpack will be dropped on death
}

Config.Backpacks = {
    [1] = { -- backpack id, you can put a string to better name it 
        item = 'backpack',
        jobs = { -- jobs that can open this backpack, or you can put false to allow all jobs
            'police',
        },
        name = 'Backpack', -- backpack name, it will be used in the inventory menu
        prop = {
            prop = 'p_bag01x',
            bone = 'SKEL_L_HAND',
            position = {
                position = vector3(0.45, 0.0, 0.0),
                rotation = vector3(0.0, -90.0, -65.0)
            }
        }, 
        acceptWeapons = true, -- if true, the backpack will accept weapons
        storage = 500, -- storage capacity in kg
    },

    [2] = {
        item = 'backpack2',
        jobs = false,
        name = 'Backpack 2', 
        prop = {
            prop = 'p_ambpack01x',
            bone = 'CP_Back',
            position = {
                position = vector3(-0.5, 0.0, 0.08),
                rotation = vector3(-80.0, 0.0, -90.0),
            }
        },
        storage = 300, -- storage capacity in kg
        acceptWeapons = true, -- if true, the backpack will accept weapons
    },

    [3] = {
        item = 'backpack3',
        jobs = false,
        name = 'Backpack 3',
        storage = 400, -- storage capacity in kg
        prop = {
            prop = 'p_ambpack02x',
            bone = 'CP_Back',
            position = {
                position = vector3(-0.35, 0.0, 0.12),
                rotation = vector3(-70.0, 0.0, -90.0),
            }
        }
    },
    
    [4] = {
        item = 'backpack4',
        jobs = false,
        name = 'Backpack 4',
        storage = 350, -- storage capacity in kg
        prop = {
            prop = 'p_ambpack04x',
            bone = 'CP_Back',
            position = {
                position = vector3(-0.2, -0.1, 0.06),
                rotation = vector3(20.0, 0.0, -90.0),
            }
        }
    },
    
    [5] = {
        item = 'backpack5',
        jobs = false,
        name = 'Backpack 5',
        storage = 450, -- storage capacity in kg
        prop = {
            prop = 's_knapsack01x',
            bone = 'CP_Back',
            position = {
                position = vector3(-0.13, 0.0, 0.01),
                rotation = vector3(0.0, -100.0, 0.0),
            }
        }
    },
}

Config.Controls = {
    OpenBackpack = 0x760A9C6F,
    PutAway = 0x26E9DC00,
    DropBackpack = 0xE30CD707,
    PickUp = 0x26E9DC00,
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['open_backpack'] = 'Open ',
        ['put_away_backpack'] = 'Put away',
        ['drop_backpack'] = 'Drop',
        ['pick_up_backpack'] = 'Pick up',
        ['backpack_already_equipped'] = 'You already have a backpack equipped!',
        ['backpack_not_allowed'] = 'You do not have the required permission to use this backpack!',
        ['backpack_not_empty'] = 'You must empty your backpack before removing it!',
        ['backpack_not_opened'] = 'You need to open first the backpack before doing this!',
        ['backpack_put_away'] = 'You have put away the backpack!',
        ['backpack_not_found'] = 'The target backpack was not found, please try again!',
        ['dropped_backpack'] = 'You have dropped the backpack!',
        ['picked_up_backpack'] = 'You have picked up the backpack!',
        ['backpack_too_far'] = 'The backpack is too far to do this, do not try to cheat!',
        ['not_enough_space'] = 'You do not have enough space in your inventory to store this item!'
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
