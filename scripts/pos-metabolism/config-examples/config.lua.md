# config.lua

```lua
Config = {}

Config.MaxHealth = 600

Config.ClothesTemperature = {
    ["hat"] = 1,            -- Provides minimal warmth
    ["shirt"] = 2,          -- Slightly more warmth than a hat
    ["pants"] = 2,          -- Regular pants provide basic warmth
    ["boots"] = 2,          -- Boots are slightly warmer than shoes
    ["coat"] = 4,           -- Closed coat for heavy warmth
    ["opencoat"] = 3,       -- Open coats are slightly less effective than closed ones
    ["gloves"] = 1,         -- Gloves provide minimal warmth
    ["vest"] = 2,           -- Vests provide some insulation
    ["poncho"] = 3,         -- Ponchos offer decent protection from the cold
    ["skirts"] = 1,         -- Minimal warmth, similar to pants
    ["chaps"] = 2,          -- Adds moderate warmth to legs
    ["mask"] = 1,
}

Config.VoiceChat = 'pma' -- pma, salty or custom and you can edit it in Config.Functions

Config.VoiceModes = {1,2,3} -- 1 = Whisper, 2 = Normal, 3 = Shout, add more if you want

Config.DataUpdateDuration = 60000
Config.DistanceToClean = 2.0 

Config.HideCores = true -- Hide default cores

Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.OptOut = false -- Opt out when toggling a hud setting. 

Config.Webhooks = {
    DefaultWebhook = '', -- Default webhook for all deposits

    useItem = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

}

Config.DynamicHide = {
    RadarHidden = false,
    PauseMenu = false,
    SpectatorMode = false,
    HudHidden = false,
    NuiFocused = false
}

Config.Commands = {
    [1] = {
        Command = 'updateHud', -- or false to disable it
        Description = 'Update hud positions',
        Parameters = {},
        Groups = {}
    },
    [2] = {
        Command = 'resetHud', -- or false to disable it
        Description = 'Reset hud positions',
        Parameters = {},
        Groups = {}
    },
    [3] = {
        Command = 'showscenario', -- or false to disable it
        Description = 'Show the current active scenario',
        Parameters = {},
        Groups = {}
    },
    [4] = {
        Command = 'heal', -- or false to disable it
        Description = 'Heal yourself',
        Parameters = {
            { name="id", help="Player ID to heal or no id to heal yourself" },
        },
        Groups = {'admin', 'superadmin'}
    },
    [5] = {
        Command = 'toggleUi',
        Description = 'Toggle the UI on or off',
        Parameters = {},
        Groups = {}
    }
}

Config.DurationToDecreaseFoodAndWater = 2000
Config.ChecksForNotificationFoodWater = 5 -- How many checks to do before notifying the player
Config.ActionCommand = "me" -- Command to display the actions. Example: /me Needs to shower. Default: /me

Config.DefaultHudData = '{}'
Config.DefaultData = {
    food = 100,
    water = 100,
    piss = 0,
    poop = 0,
    shower = 0,
    health = 600,
    poopedHimself = false,
    peedHimself = false,
    alcohol = 0,
    deadeye = 100,
    stress = 0,
}

Config.HudSettings = {
    health = {
        enabled = true,
    },

    stamina = {
        enabled = true,
    },

    onesync = {
        enabled = true,
    },

    microphone = {
        enabled = true,
    },

    deadeye = {
        enabled = true,
    },
    
    food = {
        enabled = true,
        hotValue = 35,
        decrease = 0.02,
        decreaseWhileRunning = 0.06,
        hotDecrease = 0.12, -- Will be added to decrease/decreaseWhileRunning
        damage = 20,
        time = 5000
    },
    water = {
        enabled = true,
        hotValue = 35,
        decrease = 0.03,
        decreaseWhileRunning = 0.08,
        hotDecrease = 0.12, -- Will be added to decrease/decreaseWhileRunning
        damage = 20,
        time = 5000
    },
    temperature = {
        enabled = true,
        time = 10000,
        damage = 15,
        coldValue = -10,
        hotValue = 40,
        coldWarningValue = -5,
        hotWarningValue = 35,
        waterValue = -10,
        notificationChecks = 5, -- How many checks to do before notifying the player
    },
    shower = {
        enabled = true,
        hotValue = 35,
        increase = 0.02,
        increaseWhileRunning = 0.3,
        hotIncrease = 0.06, -- Will be added to increase/increaseWhileRunning/waterIncrease
        waterIncrease = 0.02, -- Will be added to increase/increaseWhileRunning/hotIncrease
        time = 3000,
        showerValue = 95, -- Values to start showing notification to shower
        notificationChecks = 5, -- How many checks to do before notifying the player
        flies = {
            value = 95, -- Value to start showing flies around the character
            scale = 2, -- Intensity of the flies.
        }
    },
    poop = {
        enabled = true,
        poopCommand = "poop",
        poopValue = 60,
        time = 5000,
        damage = 20,
        notificationChecks = 5, -- Checks before a normal poop warning
        poopHimselfChecks = 10, -- Checks before player poops himself
        poopHimselfNotificationChecks = 7 -- Checks before sending "pooped himself" warning
    },

    piss = {
        enabled = true,
        pissCommand = "piss",
        pissValue = 60,
        time = 5000,
        damage = 20,
        notificationChecks = 5, -- Checks before a normal pee warning
        peeHimselfChecks = 10, -- Checks before player pees himself
        peeHimselfNotificationChecks = 7 -- Checks before sending "peed himself" warning
    },

    alcohol = {
        enabled = true,
        levels = {
            {
                value = 20,
                disableRun = false,
                disableJump = false,
                fall = false,
                drunk = false,
                effect = 'MP_Region',
            },
            {
                value = 50,
                disableRun = true,
                disableJump = true,
                fall = false,
                drunk = true,
                effect = 'PlayerHealthPoor',
            },
            {
                value = 80,
                disableRun = true,
                disableJump = true,
                fall = {
                    chance = 25,
                    getUpChance = 0,
                    actionInterval = {20000, 30000},
                    sleepChance = 40, 
                    sleepDuration = {10000, 20000},

                    interval = {10000, 20000},
                },
                drunk = true,
                effect = 'PlayerDrunk01',
            },
        },

        time = 5000,
        decrease = 0.2,
    },
    stress = {
        enabled = true,
        time = 0, -- Time in ms to update and check for stress actions
        increaseWhileInCombat = 0.01,
        increaseWhileShooting = 1,
        increaseWhileRunning = 0.01,
        increaseWhileFalling = 0.01,
        increaseWhileJumping = 0.01,
        timeToAction = 10000,
        damage = 0, -- Damage to health when stress is 100
        decrease = 0, -- Decrease value

        timeCheck = 5000, -- Time in ms to check for stress actions
        decreaseScenarios = {
            254049387,  
        },
        decreaseWhileUsingScenario = 3,
        decreaseWhileCrouching = 2,

        locations = {
            distance = 100,
            coords = {
                vector3(2802.5420, -1092.6741, 45.9559)
            },
            removeStress = 2,
            checkTime = 5000,
        },

        levels = {
            {
                value = 20,
                effect = 'MP_PedKill',
            },

            {
                value = 50,
                effect = 'SpectatorCam01',
            },
            {
                value = 80,
                effect = 'GunSlingerFill',
            },
        }
    },

}




Config.Controls = {
    GetUp = 0x760A9C6F,
    Clean = 0x760A9C6F, -- Default: E
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['hungry'] = 'You are hungry!',
        ['thirsty'] = 'You are thirsty!',
        ['hot_warning'] = 'You are hot, cool down or you will start to dehydrate!',
        ['hot'] = 'You are very hot, you are dehydrating!',
        ['cold_warning'] = 'You are cold, go to warmth or you will start to suffer from hypothermia!',
        ['cold'] = 'You are freezing, you are starting to suffer from hypothermia!',
        ['no_space'] = 'You don\'t have enough space to claim the items!',
        ['not_allowed'] = 'You are not allowed to do that!',
        
        ['error_occurred'] = 'An error occurred during the process!',
        ['item_used'] = 'You have used an item!',
        ['pooped_himself'] = 'It smells like poop!',
        ['poop_himself'] = 'You feel like you can\'t anymore and had to poop yourself!',
        ['piss_himself'] = 'You feel like you can\'t anymore and had to pee yourself!',
        ['peed_himself'] = 'It smells like urine!',
        ['poop_warning'] = 'Your stomach hurts! Go to the toilet!',
        ['piss_warning'] = 'You feel like you need to pee! Go to the toilet!',
        ['cannot_poop'] = 'You don\'t need to poop!',
        ['cannot_piss'] = 'You don\'t need to pee!',
        ['shower_warning'] = 'You emit a strong odor of sweat!',
        
        ['item_name'] = 'Item Name',
        ['food'] = 'Food',
        ['water'] = 'Water',
        ['health'] = 'Health',
        ['piss'] = 'Urine',
        ['poop'] = 'Poop',
        ['webhook_user_information'] = 'Player Info',
        ['webhook_useItem'] = 'The item has been used!',
        ['webhook_useItem_info'] = '%s used the item %s, updating statistics.',
        ['getup_prompt'] = 'Get up!',
        ['failed_to_get_up'] = 'You failed to get up!',
        ['missing_required_item'] = 'Missing x%s %s to use this item!',
        ['poisoned'] = 'You feel poisoned and weak!',
        ['cured'] = 'You feel much better now!',
        ['settings_updated'] = 'Settings updated successfully!',
        ['hud_reset'] = 'The hud has been reset!',
        ['reset_success'] = 'The HUD has been successfully reset!',
        ['clean_prompt'] = 'Clean',
        ['cleaned_poop'] = 'You cleaned up the poop successfully!',
        ['ui_shown'] =  'The UI is now shown!',
        ['ui_hidden'] = 'The UI is now hidden!',
    }

}

Config.PoopItems = {
    receiveAll = true, -- If false, it will pick 1 item at random if true it will give every item.
    items = {
        ['sticla_apa'] = { -- item name
            count = 1, -- How many items to receive
            chance = 100, -- Chance to receive the item (0-100)
        }
    }
}

Config.ProgressBars = {
    ['clean_poop'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Cleaning..',
        canStop = true,
        time = 15000,

        animation = {
            type = 'scenario',
            scenario = 'WORLD_HUMAN_FARMER_RAKE',
            anim = "idle_c",
        }
        
        
    },
}

Config.Items = {
    
    ["alcool"] = {
        prop = nil,

        playerStats = {
            water = 20,
            food = 0,
            stamina = 0, 
            health = 50,
            deadeye = 10,
            
            outerCoreGoldDeadeye = 0,
            innerCoreGoldDeadeye = 0,

            outerCoreGoldHealth = 0,
            innerCoreGoldHealth = 0,
            outerCoreGoldStamina = 600,
            innerCoreGoldStamina = 600,
            poop = 0,
            piss = 0, 
            alcohol = 10,
            stress = -20,

            temperature = {
                value = 100,
                duration = 10000, -- time in ms (5000 = 5 seconds) or false for permanent
            },
            -- false or table
        },

        poison = { -- false or table
            chance = 50, -- chance to get poisoned
            duration = 10000, -- time in ms (5000 = 5 seconds)
            durationAction = 1000, -- time in ms (5000 = 5 seconds). Every how many seconds to do damage 
            damage = 10,
            actions = {
                disableJump = true,

                disableRun = true,

                fall = {
                    chance = 50,
                    getUpChance = 0,
                    actionInterval = {20000, 30000},
                    sleepChance = 40, 
                    sleepDuration = {10000, 20000},
                    interval = {10000, 20000},
                },
                drunk = true,
            },
            
            effect = 'MP_Region',
        },

        horseStats = {
            stamina = 0,
            health = 0,
            outerCoreGoldHealth = 0,
            innerCoreGoldHealth = 0,
            outerCoreGoldStamina = 0,
            innerCoreGoldStamina = 0,
        },

        itemUse = {
            removeItem = true,
            durability = 1,
            returnOnRemove = true, -- return items only if the item is removed
            returnItems = {
                ["sticla_goala"] = {
                    metadata = {},
                    count = 1
                },
            },
            requireAdditionalItems = false,
        },

        animation = "drink",
    },

}

Config.CureItems = {
    ["morphina"] = {
        prop = "mp007_p_mp_syringe01x_1",
        animation = "inject",

        itemUse = {
            removeItem = true,
            durability = 1,
            returnOnRemove = true, -- return items only if the item is removed
            returnItems = {
                ["sticla_goala"] = {
                    metadata = {},
                    count = 1
                },
            },
            requireAdditionalItems = false,
        },
    },
}

local function playAnimationWithProp(ped, dict, anim, propname, boneName, animtime, attachOffset, animFlags)
    RequestAnimDict(dict)
    while not HasAnimDictLoaded(dict) do
        Citizen.Wait(100)
    end

    local coords = GetEntityCoords(ped)
    local prop = CreateObject(propname, coords.x, coords.y, coords.z + 0.2, true, true, false, false, true)
    local boneIndex = GetEntityBoneIndexByName(ped, boneName)
    AttachEntityToEntity(prop, ped, boneIndex, table.unpack(attachOffset))
    TaskPlayAnim(ped, dict, anim, 8.0, -8.0, animtime, animFlags, 0, true, 0, false, 0, false)
    Citizen.Wait(animtime)
    DeleteEntity(prop)
    ClearPedSecondaryTask(ped)
end

Config.Functions = {
    ["wake_drunk"] = function()
        exports['POS-Metabolism']:UpdateMultipleStatus({
            ["water"] = -30,
            ["food"] = -30,
            ["alcohol"] = -100,
        })
    end,
    ["custom_voice"] = function()
        return 100 -- should return the voice range, in percentages.
    end,

    ["poop"] = function()
        exports['POS-Metabolism']:UpdateMultipleStatus({
            ["shower"] = 10,
        })
    end
}

Config.Animations = {
    ["bandage"] = function(propname)
        local dict = "mini_games@story@mob4@heal_jules@bandage@arthur"
        local anim = "tourniquet_slow"
        local animtime = 5000
        local ped = PlayerPedId()
        local attachOffset = { 0.11, 0.06, 0.05, 89.0, 0.0, 0.0 }
        
        playAnimationWithProp(ped, dict, anim, propname, "skel_l_hand", animtime, attachOffset, 31)
        Citizen.InvokeNative(0x4102732DF6B4005F, "RespawnPulseMP01", 0, true)
        SetTimeout(2000, AnimpostfxStopAll)
        return true
    end,

    ["pipe"] = function(propname)
        SmokePipe()
    end,

    ["cigarette"] = function(propname)
        SmokeCigarette()
    end,

    ["cigar"] = function(propname)
        SmokeCigar()
    end,

    ["smoke"] = function (name)
        local data = {
            execute = nil, -- Function name to be called in POS-Interactions
            type = 'cigar', -- cigar, cigarette, pipe
        }

        Smoke(data)

    end,

    ["mushroom"] = function()
        MushroomEvent()
    end,

    ["pomade"] = function()
        PomadeEvent()
    end,

    ["pocket_watch"] = function (propname)
        local watches = {
            ["pocket_watch_1"] = {prop = "p_si_pocketwatch01x", type = math.random(1, 2)},
            ["pocket_watch_2"] = {prop = "s_inv_pocketwatch01x", type = math.random(1, 2)},
            ["pocket_watch_3"] = {prop = "s_inv_pocketwatch02x", type = math.random(1, 2)},
            ["pocket_watch_4"] = {prop = "s_inv_pocketwatch03x", type = math.random(1, 2)},
            ["pocket_watch_5"] = {prop = "s_inv_pocketwatch04x", type = math.random(1, 2)},
            ["pocket_watch_6"] = {prop = "s_inv_pocketwatch06x", type = math.random(1, 2)},
            ["pocket_watch_7"] = {prop = "s_inv_pocketwatch07x", type = math.random(1, 2)},
            ["pocket_watch_8"] = {prop = "s_oldpocketwatch01x", type = math.random(1, 2)},
            ["pocket_watch_9"] = {prop = "s_pocketwatch_reutlinge", type = math.random(1, 2)}
        }

        local watch = watches[propname]

        WatchEvent(watch)
    end,
    
    ["morphina"] = function(propname)
        local dict = "mech_inventory@item@stimulants@inject@quick"
        local anim = "quick_stimulant_inject_lhand"
        local animtime = 5000
        local ped = PlayerPedId()
        local attachOffset = { 0.11, 0.06, 0.05, 89.0, 0.0, 0.0 }
        
        playAnimationWithProp(ped, dict, anim, propname, "skel_l_hand", animtime, attachOffset, 1)
        Citizen.InvokeNative(0x4102732DF6B4005F, "RespawnPulseMP01", 0, true)
        SetTimeout(2000, AnimpostfxStopAll)
        return true
    end,
    
    ["eat"] = function(propname)
        local ped = PlayerPedId()
        local act = GetHashKey("EAT_CANNED_FOOD_CYLINDER@D8-2_H10-5_QUICK_LEFT")
        local prop = propname or "s_canrigcorn01x"
        local obj = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, true, false, false, true)
        
        Citizen.InvokeNative(0x72F52AA2D2B172CC, ped, 1242464081, obj, 2120637577, act, 1, 0, -1.0)
        return true
    end,
    
    ["stew"] = function(propname)
        local ped = PlayerPedId()
        local coords = GetEntityCoords(ped)
        local bowl = CreateObject("p_bowl04x_stew", coords, true, true, true)
        local spoon = CreateObject("p_spoon01x", coords, true, true, true)
        
        Citizen.InvokeNative(0x669655FFB29EF1A9, bowl, 0, "Stew_Fill", 1.0)
        Citizen.InvokeNative(0xCAAF2BCCFEF37F77, bowl, 20)
        Citizen.InvokeNative(0xCAAF2BCCFEF37F77, spoon, 82)
        
        TaskItemInteraction_2(ped, 599184882, bowl, GetHashKey("p_bowl04x_stew_ph_l_hand"), -583731576, 3, 0, -1.0)
        TaskItemInteraction_2(ped, 599184882, spoon, GetHashKey("p_spoon01x_ph_r_hand"), -583731576, 3, 0, -1.0)
        Citizen.InvokeNative(0xB35370D5353995CB, ped, -583731576, 1.0)
        
        Citizen.Wait(20000)
        DeleteEntity(bowl)
        DeleteEntity(spoon)
        return true
    end,
    
    ["sandwich"] = function(propname)
        local ped = PlayerPedId()
        local coords = GetEntityCoords(ped)
        local prop = CreateObject(propname, coords.x, coords.y, coords.z + 0.2, true, true, false, false, true)
        local animation = {
            dict = "mech_inventory@eating@multi_bite@sphere_d8-2_sandwich",
            name = "quick_left_hand", 
            flag = 24,
            bone = "SKEL_L_Finger12",
        }
        local boneIndex = GetEntityBoneIndexByName(ped, animation.bone)
        local attachOffset = { 0.02, 0.028, 0.001, 15.0, 175.0, 0.0 }
        
        RequestAnimDict(animation.dict)
        while not HasAnimDictLoaded(animation.dict) do
            Citizen.Wait(100)
        end
        
        Citizen.InvokeNative(0xFCCC886EDE3C63EC, 2, 1)
        TaskPlayAnim(ped, animation.dict, animation.name, 8.0, -8.0, -1, animation.flag, 0, true, 0, false, 0, false)
        AttachEntityToEntity(prop, ped, boneIndex, table.unpack(attachOffset))
        
        Citizen.Wait(1000)
        DeleteEntity(prop)
        ClearPedSecondaryTask(ped)
        return true
    end,
    
    ["water"] = function(propname)
        local ped = PlayerPedId()
        local act = GetHashKey("DRINK_Bottle_Oval_L5-5W9-5H10_Neck_A6_B2-5_QUICK_RIGHT_HAND")
        local prop = propname or "p_water01x"
        local obj = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, true, false, false, true)
        
        Citizen.InvokeNative(0x72F52AA2D2B172CC, ped, 1242464081, obj, 2120637577, act, 1, 0, -1.0)
        return true
    end,

    -- Additional animations
    ["drink"] = function(propname)
        local ped = PlayerPedId()
        local act = GetHashKey("DRINK_Bottle_Oval_L5-5W9-5H10_Neck_A6_B2-5_QUICK_RIGHT_HAND")
        local prop = propname or "p_bottlemedicine09x"
        local obj = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, true, false, false, true)
        
        Citizen.InvokeNative(0x72F52AA2D2B172CC, ped, 1242464081, obj, 2120637577, act, 1, 0, -1.0)
        return true
    end,
    
    ["coffe"] = function(propname)
        local ped = PlayerPedId()
        local prop = propname or "p_mugCoffee01x"
        local propEntity = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, true, false, false, true)
        TaskItemInteraction_2(ped, -1199896558, propEntity, GetHashKey("p_mugCoffee01x_ph_r_hand"), GetHashKey("DRINK_COFFEE_HOLD"), 1, 0, -1.0)
        return true
    end,
    
    ["beer"] = function(propname)
        local ped = PlayerPedId()
        local prop = propname or "p_bottleJD01x"
        local prop2 = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, false, 1, 1, 0)
        TaskItemInteraction_2(ped, 1737033966, prop2, GetHashKey("p_bottleJD01x_ph_r_hand"), GetHashKey("DRINK_BOTTLE@Bottle_Cylinder_D1-3_H30-5_Neck_A13_B2-5_UNCORK"), true, 0, 0)
        return true
    end,
    
    ["whisky"] = function(propname)
        local ped = PlayerPedId()
        local prop = propname or "p_bottleJD01x"
        Citizen.InvokeNative(0x524B54361229154F, ped, GetHashKey("WORLD_HUMAN_DRINK_FLASK"), 5000, true, false, false, false)
        Wait(5000)
        ClearPedSecondaryTask(ped)
        ClearPedTasks(ped)
        return true
    end,

    ["horse"] = function(propname)
        local food = {
            "s_horsnack_carrot01x",
            "s_horsnack_sugarcube01x",
            "s_horsnack_beet01x",
            "s_horsnack_peppermint01x",
            "s_horsnack_haycube01x",
            "s_horsnack_celery01x",
        }
        local random = math.random(1, #food)
        local prop = GetHashKey(food[random])
        local ped = PlayerPedId()
        local mount = GetMount(ped)
        Citizen.InvokeNative(0xCD181A959CFDD7F4, ped, mount, GetHashKey("Interaction_Food"), prop, 1)
        return true
    end,

    ["inject"] = function(propname)
        local ped = PlayerPedId()
        local prop = propname or "mp007_p_mp_syringe01x_1"
        local prop2 = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, false, 1, 1, 0)
        TaskItemInteraction_2(ped, 1737033966, prop2, GetHashKey("PrimaryItem"), GetHashKey("USE_STIMULANT_INJECTION_QUICK_LEFT_HAND"), true, 0, 0)
        SetTimeout(3000, function()
            DeleteObject(prop2)
        end)
    end,

    ["horseinject"] = function(propname)
        local ped = PlayerPedId()
        local mount = GetMount(ped)
        local prop = propname or "p_cs_syringe01x"
        Citizen.InvokeNative(0xCD181A959CFDD7F4, ped, mount, GetHashKey("Interaction_Injection_Quick"), GetHashKey(prop), 1)
    end,
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
