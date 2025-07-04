# config.lua

```lua
Config = {}

Config.Controls = {
    StopSmoke = 0x760A9C6F,
    Smoke = 0xB2F377E8,
    ChangePosition = 0x26E9DC00,
}

Config.Items = {
    ['ciuperca_halucinogena'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'mushrooms',
        args = {
            animation = 'mushroom' -- This is the animation name used in Config.Animations mushroom or cigar
        },
    },

    ['pomade'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'pomade',
        args = {},
    },

    ['ceas1'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'watch',
        args = { 
            watch = "pocket_watch_1"
        },
    },

    ['pipa'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'pipe',
        args = {},
    },

    ['tigara'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'cigarette',
        args = {},
    },

    ['trabuc'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'cigar',
        args = {},
    },

    ['joint'] = {
        removeItem = false,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'smoke',
        args = { 
            type = 'cigar', -- cigar, cigarette, pipe
            execute = nil -- Function in Config.Functions to be executed after use.
        }, 
    }
}

Config.ActionTypes = {
    ['mushrooms'] = function(source, data)
        MushroomEvent(source, data.animation)
    end,

    ['pomade'] = function(source)
        PomadeEvent(source)
    end,

    ['watch'] = function(source, data)

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

        local watch = watches[data.watch]


        WatchEvent(source, watch)
    end,

    ['pipe'] = function(source)
        SmokePipe(source)
    end,

    ['cigarette'] = function(source)
        SmokeCigarette(source)
    end,

    ['cigar'] = function(source)
        SmokeCigar(source)
    end,

    ['smoke'] = function(source, data)
        Smoke(source, data)
    end

}

Config.PipePositions = {
    ['male'] = {
        { 
            idle = {
                dict = "amb_rest@world_human_smoking@male_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_b@idle_a",
                anim = "idle_a",
                time = 10000,
            }

        },

        { 
            idle = {
                dict = "amb_rest@world_human_smoking@pipe@proper@male_d@wip_base", 
                anim = "wip_base" 
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_b@idle_a",
                anim = "idle_a",
                time = 10000,
            }

        },
    },
    ['female'] = {
        { 
            idle = {
                dict = "amb_rest@world_human_smoking@male_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_b@idle_a",
                anim = "idle_a",
                time = 10000,
            }

        },

        { 
            idle = {
                dict = "amb_rest@world_human_smoking@pipe@proper@male_d@wip_base", 
                anim = "wip_base" 
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_b@idle_a",
                anim = "idle_a",
                time = 10000,
            }

        },
    }
}

Config.CigarettePositions = {
    ['male'] = {
        { 
            idle = {
                dict = "amb_rest@world_human_smoking@male_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_c@idle_a",
                anim = "idle_b",
                time = 10000,
            }

        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@nervous_stressed@male_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@nervous_stressed@male_b@idle_c",
                anim = "idle_g",
                time = 13433,
            }
        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@male_d@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_d@idle_a",
                anim = "idle_b",
                time = 7366,
            }
        },

        {
            idle = {
                dict = "amb_wander@code_human_smoking_wander@male_a@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@male_a@idle_a",
                anim = "idle_b",
                time = 12533,
            } 
        }
    },
    ['female'] = {
        {
            idle = {
                dict = "amb_rest@world_human_smoking@female_c@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@female_c@idle_a",
                anim = "idle_a",
                time = 9566,
            } 
        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@female_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@female_b@idle_b",
                anim = "idle_f",
                time = 8033,
            }
        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@female_a@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@female_a@idle_b",
                anim = "idle_d",
                time = 14566,
            }
        }
    
    }
}

Config.CigarPositions = {
    ['male'] = {
        { 
            idle = {
                dict = "amb_rest@world_human_smoking@male_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoke_cigar@male_a@idle_b",
                anim = "idle_d",
                time = 12533,
            } 

        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@nervous_stressed@male_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoke_cigar@male_a@idle_b",
                anim = "idle_d",
                time = 12533,
            } 
        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@male_d@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoke_cigar@male_a@idle_b",
                anim = "idle_d",
                time = 12533,
            } 
        },

        {
            idle = {
                dict = "amb_wander@code_human_smoking_wander@male_a@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoke_cigar@male_a@idle_b",
                anim = "idle_d",
                time = 12533,
            } 
        }
    }, 

    ['female'] = {
        {
            idle = {
                dict = "amb_rest@world_human_smoking@female_c@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@female_c@idle_a",
                anim = "idle_a",
                time = 9566,
            } 
        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@female_b@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@female_b@idle_b",
                anim = "idle_f",
                time = 8033,
            }
        },

        {
            idle = {
                dict = "amb_rest@world_human_smoking@female_a@base", 
                anim = "base"
            },
            smoke = {
                dict = "amb_rest@world_human_smoking@female_a@idle_b",
                anim = "idle_d",
                time = 14566,
            }
        }
    }
}

Config.Functions = {
    ['pipe_smoke'] = function()

    end,

    ['cigarette_smoke'] = function()

    end,

    ['cigar_smoke'] = function()

    end,

    ['mushrooms'] = function ()
        
    end,

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

Config.Animations = {
    ["mushroom"] = function(propname)

        local dict = "mech_inventory@eating@multi_bite@wedge_a4-2_b0-75_w8_h9-4_eat_cheese"
        local anim = "quick_right_hand"
        local animtime = 5000
        local attachOffset = {0.005, -0.045, 0.0, -170.0, 10.0, -15.0}
        
        playAnimationWithProp(PlayerPedId(), dict, anim, "s_amedmush", "SKEL_R_Finger13", animtime, attachOffset, 30)
    end,

    ["pomade"] = function ()
        local ped = PlayerPedId()

        if Citizen.InvokeNative(0xFB4891BD7578CDC1, ped, tonumber(0x9925C067)) then -- Native name doesn't exist in the natives list
            TaskItemInteraction(ped, 0, GetHashKey("APPLY_POMADE_WITH_HAT"), 1, 0, -1082130432)
        else
            TaskItemInteraction(ped, 0, GetHashKey("APPLY_POMADE_WITH_NO_HAT"), 1, 0, -1082130432)
        end
    end,

    ['cigar'] = function()
        Smoke({
            type = 'cigar',
        })
    end
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['smoke_prompt'] = 'Smoke',
        ['change_position_prompt'] = 'Change Position',
        ['stop_smoke_prompt'] = 'Stop Smoke',
        ['smoke_group'] = 'Smoking',
        ['missing_required_item'] = 'Missing x%s %s to use this item!',
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
