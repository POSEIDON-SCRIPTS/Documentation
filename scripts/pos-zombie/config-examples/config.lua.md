# config.lua

```lua
Config = {}

Config.SafeZone = {
    show = true,
    disableWeapon = true,
    invincible = true,
    disableMelee = true,
}

Config.Functions = {
    damage = function ()
        
    end -- Function to handle damage (add a infection or something), you can implement your own logic here
}

Config.ZombieSettings = {
    sound = 'https://www.youtube.com/watch?v=z7NJYzvDIVE',
    distance = 25.0,
    distanceCooldown = 5000, -- time to reset the sound so zombies will not forget instantly
    spawnEverywhere = true, -- If true, zombies can spawn anywhere in the world, if false, they will only spawn in specific locations
    spawnSettings = { -- spawnEverywhere = false
        distance = 250,
        maxPerLocation = 80, -- Maximum number of zombies that can spawn in a radius
        spawnCooldown = 1000, -- cooldown between spawns in milliseconds, per player
        locations = {
            vector3(-2917.3730, -2284.0583, 77.8632)
        }
    },
    damage = 20, -- damage dealt
    zombieSounds = {
        {
            name = "ZombieAmbient_1",
            index = 1,
            playing = false,
            delay = 0, -- in milliseconds
            lastStart = 0
        },
        {
            name = "ZombieAmbient_2",
            index = 10,
            playing = false,
            delay = 2000, -- delayed by 2 seconds
            lastStart = 0
        }
    },
    walks = {
        {"default", "very_drunk"},
        {"murfree", "very_drunk"},
        {"default", "dehydrated_unarmed"},
    }
}

Config.Distance = {
    default = 100, -- default distance for a zombie to see the player
    shotDistance = 20, -- distance that is added when the player shoots
    vehicleDistance = 20, -- distance that is added when the player is in a vehicle
    crouchDistance = -40, -- distance that is added when the player is crouched
    mountDistance = 20, -- distance that is added when the player is mounted
    runningDistance = 20, -- distance that is added when the player is running
    meleeDistance = 20, -- distance that is added when the player is in melee combat
    coverDistance = -40, -- distance that is added when the player is in cover
}

Config.LootSettings = {
    deleteAfterLoot = true, -- Delete the zombie or airdrop after looting
    lootDistance = 2.0, -- Distance to loot the zombie or airdrop
}


Config.ProgressBars = {
    ['loot_zombie'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Looting zombie...',
        canStop = true,
        time = 10000,
        animation = {
            anim = "action_skinner02",
            flags = 1,
            animDict = "script_proc@bounty@skinner_search"
        }
    },
    ['loot_airdrop'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Looting Airdrop...',
        canStop = true,
        time = 10000,
        animation = {
            anim = "base_idle_skinner02",
            flags = 1,
            animDict = "script_proc@bounty@skinner_search"
        }
    },
    

}

Config.Controls = {
    LootZombie = 0x760A9C6F,
    LootAirdrop = 0x760A9C6F,
}


Config.MenuAlign = 'right' -- top-right, top-left, bottom-right, bottom-left

Config.Commands = {
    [1] = {
        Command = 'createsafezone', -- or false to disable it
        Description = 'Create a house with the specified parameters.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [2] = {
        Command = 'editsafezone', -- or false to disable it
        Description = 'Edit a house with the specified parameters.',
        Parameters = {
            { name="id", help="Specify the house id to edit." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [3] = {
        Command = 'spawn_airdrop', -- or false to disable it
        Description = 'Spawn an airdrop on the map.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [4] = {
        Command = "spawn_zombies", -- or false to disable it
        Description = "Spawn zombies at the player's location.",
        Parameters = {
            { name="amount", help="Number of zombies to spawn." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'}
    }
}

Config.BlipInput = {
    title = "Blip",
    form = {
        {
            label = "Blip model",
            id = "model",
            type = "string",
            required = false
        },
        {
            label = "Blip modifier",
            id = "modifier",
            type = "string",
            required = false
        }
    }
}

Config.DeleteInput = {
    title = "Delete",
    form = {
        {
            label = "Type YES to delete",
            id = "delete",
            type = "string",
            required = true
        },
    }
}


Config.ZoneNameInput = {
    title = "Set zone name",
    form = {
        {
            label = "Name",
            id = "name",
            type = "string",
            required = false
        },
    }
}

Config.Looting = {
    enabled = true,
    deleteAfterLoot = true,
    distance = 2.0, -- Distance to loot the zombie 
    chances = {
        money = 30,
        item = 50,
        receiveBoth = 20,
    },
    
    moneyAmounts = {
        min = 1,
        max = 100
    },

    itemList = {
        { name = "WEAPON_PISTOL_MAUSER", amount = 1, chance = 2 }, 
        { name = "empty_bucket", amount = 1, chance = 20 }, 
        { name = "apple_seeds", amount = 1, chance = 78 }, 
    }
}

Config.WhitelistedWeapons = { -- Weapons that will not attract zombies when fired
    "WEAPON_BOW", 
}

Config.AirDrops = {
    enabled = true, -- Enable or disable airdrops
    velocity = -0.5, -- Velocity of the airdrop
    cooldown = { 60000, 120000 }, -- Cooldown between airdrops in milliseconds
    deleteAfterLoot = true, -- Delete the airdrop after looting
    notification = true, -- Notification when airdrop is spawned
    locations = {
        [1] = {
            prop = {
                model = 'p_toolshed02x',
                offset = -6.5
            },

            blip = {
                model = 'blip_mission_area_bounty',
                size = 25.0,
                modifier = 'BLIP_MODIFIER_AREA'
            },

            multipleDrops = false, -- If true, it will spawn the airdrops in multiple locations at the same time, if not it will spawn only one
            coords = {
                vector4(2395.3281, -1369.6479, 44.7530, 55.6714)
            },

            chances = {
                money = 30,
                item = 50,
                receiveBoth = 20,
            },
            
            moneyAmounts = {
                min = 1,
                max = 100
            },
        
            itemList = {
                { name = "WEAPON_PISTOL_MAUSER", amount = 1, chance = 2 }, 
            }
            

        }
    },
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do this.',

        ['set_locations'] = 'Set locations',
        ['set_locations_desc'] = 'Set the locations for the zone.',
        ['set_main_location'] = 'Set main location',
        ['set_main_location_desc'] = 'Set the main location for the zone.',

        ['set_name'] = 'Set name',
        ['set_name_desc'] = 'Set the name for the zone.',
        ['set_blip'] = 'Set blip',
        ['set_blip_desc'] = 'Set the blip for the zone.',
        ['create_zone'] = 'Create zone',
        ['create_zone_desc'] = 'Create a new zone.',
        ['set_main_location_success'] = 'Main location set successfully.',
        ['set_locations_success'] = 'Locations set successfully.',
        ['set_name_success'] = 'Name set successfully.',
        ['set_blip_success'] = 'Blip set successfully.',

        ['zone_main_location'] = 'Main Location',
        ['zone_locations'] = 'Zone Locations',
        ['zone_name'] = 'Zone Name',
        ['zone_blip'] = 'Zone Blip',
        ['zone_blip_modifier'] = 'Blip Modifier',
        ['set'] = 'Set',
        ['not_set'] = 'Not Set',
        ['zone_plants'] = 'Zone Plants',
        ['zone_not_found'] = 'Zone not found.',
        ['edit_zone'] = 'Edit zone',
        ['edit_zone_desc'] = 'Edit the zone.',
        ['delete_zone'] = 'Delete zone',
        ['delete_zone_desc'] = 'Delete the zone.',
        ['zone_deleted'] = 'Zone deleted successfully.',
        ['zone_updated'] = 'Zone updated successfully.',
        ['zone_created'] = 'Zone created successfully.',
        ["input_yes"] = "YES",
        ['zone_title'] = '%s (%s)',
        ['entered_safezone'] = 'You have entered a safezone!',
        ['exited_safezone'] = 'You have exited a safezone!',
        ['zombie_prompt'] = 'Zombie',
        ['loot_zombie'] = 'Loot Zombie',
        ['already_looted'] = 'This has already been looted.',
        ['nothing_found'] = 'Nothing was found.',
        ['received_money'] = 'You have received $%s',
        ['received_item'] = 'You have received %sx %s',
        ['received_weapon'] = 'You have received %sx %s',
        ['inventory_full'] = 'You cannot carry the following item: %s',
        ['loot_airdrop'] = 'Loot Airdrop',
        ['airdrop_prompt'] = 'Airdrop',
        ['airdrop_not_exist'] = 'The airdrop does not exist.',
        ['airdrop_title'] = 'Supply Airdrop',
        ['airdrop_notification'] = 'An airdrop has been spotted. Check your map for its location!',
        ['invalid_amount'] = 'The amount you entered was invalid!',
        ['no_zombies_spawned'] = 'There was a problem spawning the zombies, try again later!',
        ['spawned_zombies'] = '%s zombies were spawned at your location'
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
