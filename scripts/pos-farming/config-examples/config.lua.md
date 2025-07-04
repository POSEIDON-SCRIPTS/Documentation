# config.lua

```lua
Config = {}

Config.Functions = {
    ['rainCheck'] = function()
        local rainWeathers = {
            ["rain"] = true,
            ["shower"] = true,
            ["thunder"] = true,
            ["thunderstorm"] = true,
            ["drizzle"] = true,
            ["sleet"] = true
        }

        local type = exports.weathersync:getWeather():lower()

        return rainWeathers[type] or false
    end,
    ['harvest_plant'] = function (source) -- in case you want to implement a system, like give xp etc.
        
    end
}



Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = '', -- Default webhook for all deposits

    farmingwaterplant = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    farmingfertilizer = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },

    farmingdestroy = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },

    farmingharvest = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },

    farmingplant = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
}


Config.MenuAlign = 'right' -- top-right, top-left, bottom-right, bottom-left

Config.Commands = {
    [1] = {
        Command = 'createzone', -- or false to disable it
        Description = 'Create a house with the specified parameters.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [2] = {
        Command = 'editzone', -- or false to disable it
        Description = 'Edit a house with the specified parameters.',
        Parameters = {
            { name="id", help="Specify the house id to edit." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
}


Config.Duration = {
    updateTime = 30000, -- 30 seconds
    increaseIfRain = 10, -- value to increase water if it rains
    decreaseTime = 30000, -- 30 seconds
    decreaseWater = 0.1, -- value to decrease water
    decreaseFertilizer = 0.1, -- value to decrease fertilizer
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

Config.PlantInput = {
    title = "Plant",
    form = {
        {
            label = "Plant",
            id = "plant",
            type = "string",
            required = true
        },
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

Config.BucketItems = {
    ['galeata_goala'] = {
        value = 50, -- water to increase
        uses = 3, -- how many times can you water a plant before it is empty
    }
}

Config.FertilizerItems = {
    ['fertilizant'] = {
        value = 50, -- fertilizer to increase
    }
}

Config.BlacklistedCities = {
    'Valentine',
    'Saint Denis', -- location name from POS-Core Config.Text
}

Config.Settings = {
    harvestPercentage = 50, -- percentage to harvest the plant
    harvestMultiply = 2,     -- amount to multiply the harvest if percentage is 100
    harvestOnlyOwned = true, -- if true, you can only harvest your own plants
    limit = 5, -- limit of plants per person or false
    destroyOnlyOwned = true, -- if true, you can only destroy your own plants
    plantOnlyInZone = true, -- if true, if a plant is in a zone but you are not in the zone, you cannot plant it
    itemRequiredForPlanting = true,
    itemRequiredForHarvesting = true, -- if true, you need an item to harvest the plant
    harvestDefaultPlants = true, -- if true, you can harvest the default in game plants
    minimumWater = 0, -- minimum water for the plant to grow, if the water is below this value, the plant will not grow
    durationPlantDieZeroWater = 1800, -- 30 minutes, time for the plant to die if it has no water or false to disable it
}

Config.Distances = {
    plantDistance = 7, -- distance between plants to be able to plant another one
    fertilizerDistance = 2,
    destroyDistance = 2, -- distance to destroy the plant
    spawnDistance = 150,
    showDistance = 1.5, -- distance to show the prompts
}


Config.PlantingItems = {
    ['mini_lopata'] = {
        time = 15000, -- time to plant the plant
    }
}

Config.HarvestingItems = {
    ['galeata_goala'] = {
        bonus = {
            max = 3, -- maximum amount of items to receive
            min = 1, -- minimum amount of items to receive
        }, -- bonus items to receive when harvesting the plant with this item in the inventory or false to disable it
        multiply = 2, -- amount to multiply the harvest or false to disable it
    },
}

Config.HarvestableProps = {
    [1] = {
        item = 'sticla_apa',
        props = {
            'crp_cornstalks_ab_sim',
        },
        amount = {
            min = 1,
            max = 3
        },
        description = 'A robust corn plant that grows fresh and crisp corn.',
        time = 60, -- 1 minute
    },
}

Config.BlipSettings = {
    blip = "blip_proc_home_locked",
    modifier = "BLIP_MODIFIER_MP_COLOR_13",
}


Config.WaterSettings = {
    {
        percentage = 0,
        durationMultiplier = 0.5 -- the time reduction will be x times faster
    }, 
    {
        percentage = 50,
        durationMultiplier = 1 -- the time reduction will be x times faster
    }, 
    {
        percentage = 100,
        durationMultiplier = 1.5 -- the time reduction will be x times faster
    }
}


Config.FertilizerSettings = {
    {
        percentage = 0, 
        durationMultiplier = 0.5 -- the time reduction will be x times faster 
    }, 
    {
        percentage = 50, 
        durationMultiplier = 1 -- the time reduction will be x times faster 
    }, 
    {
        percentage = 100, 
        durationMultiplier = 1.5 -- the time reduction will be x times faster 
    }
}

Config.Plants = {
    ['mdt'] = {
        item = 'sticla_apa',
        amount = {
            min = 2,
            max = 5
        },
        required = {
            water = true,
            fertilizer = false,
        },
        removeAfterHarvest = true, 
        
        time = 900, -- 15 minutes
        type = 'tobacco',
        description = 'Premium tobacco plants that produce high-quality leaves for processing.',
        seedChance = 35,
        temp = {
            min = 15,
            max = 35,
        }
    },

    ['cannabis_buds'] = {
        item = 'cannabis_bud',
        amount = {
            min = 3,
            max = 8
        },
        required = {
            water = true,
            fertilizer = true,
        },
        removeAfterHarvest = true, 
        
        time = 1200, -- 20 minutes
        type = 'cannabis',
        description = 'Carefully cultivated cannabis plants that yield potent buds.',
        seedChance = 40,
        temp = {
            min = 18,
            max = 28,
        }
    },

    ['fresh_tomatoes'] = {
        item = 'tomato',
        amount = {
            min = 4,
            max = 12
        },
        required = {
            water = true,
            fertilizer = true,
        },
        removeAfterHarvest = false, 
        
        time = 720, -- 12 minutes
        type = 'wild_carrot',
        description = 'Juicy red tomatoes perfect for cooking and eating fresh.',
        seedChance = 60,
        temp = {
            min = 10,
            max = 30,
        }
    },

    ['corn_harvest'] = {
        item = 'corn_cob',
        amount = {
            min = 2,
            max = 6
        },
        required = {
            water = true,
            fertilizer = true,
        },
        removeAfterHarvest = true, 
        
        time = 1800, -- 30 minutes
        type = 'corn',
        description = 'Golden corn stalks that produce sweet and nutritious corn cobs.',
        seedChance = 45,
        temp = {
            min = 12,
            max = 32,
        }
    },

    ['medicinal_herbs'] = {
        item = 'herb_mix',
        amount = {
            min = 1,
            max = 4
        },
        required = {
            water = true,
            fertilizer = false,
        },
        removeAfterHarvest = true, 
        
        time = 480, -- 8 minutes
        type = 'thyme',
        description = 'Aromatic medicinal herbs with healing properties and culinary uses.',
        seedChance = 70,
        temp = {
            min = 5,
            max = 25,
        }
    },
}

Config.PlantTypes = {
    ["tobacco"] = {
        { percentage = 0, prop = "crp_tobaccoplant_aa_sim", offset = -1.0 },
        { percentage = 50, prop = "crp_tobaccoplant_ab_sim", offset = -1.0 },
        { percentage = 100, prop = "crp_tobaccoplant_ac_sim", offset = -1.0 }
    },
    ["cannabis"] = {
        { percentage = 0, prop = "bkr_prop_weed_01_small_01b", offset = -1.65 },
        { percentage = 50, prop = "bkr_prop_weed_med_01b", offset = -4.2 },
        { percentage = 100, prop = "bkr_prop_weed_lrg_01b", offset = -4.0 }
    },
    ["cannabis_bud"] = {
        { percentage = 0, prop = "bkr_prop_weed_bud_pruned_01a", offset = -1.05 },
        { percentage = 50, prop = "bkr_prop_weed_bud_02b", offset = -1.05 },
        { percentage = 100, prop = "bkr_prop_weed_bud_02a", offset = -1.05 }
    },
    ["ginseng"] = {
        { percentage = 0, prop = "ginseng_p", offset = -1.25 },
        { percentage = 50, prop = "s_ginseng01x", offset = -1.25 },
        { percentage = 100, prop = "s_ginseng01x", offset = -1.25 }
    },
    ["milkweed"] = {
        { percentage = 0, prop = "s_inv_milkweed01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_milkweed01dx", offset = -1.05 },
        { percentage = 100, prop = "s_milkweed01x", offset = -1.05 }
    },
    ["blackcurrant"] = {
        { percentage = 0, prop = "s_inv_blackcurrant01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_blackcurrant01x", offset = -1.05 },
        { percentage = 100, prop = "blackcurrant_p", offset = -1.05 }
    },
    ["bloodflower"] = {
        { percentage = 0, prop = "s_inv_bloodflower01x", offset = -1.05 },
        { percentage = 50, prop = "mp005_bloodflower_p", offset = -1.05 },
        { percentage = 100, prop = "s_inv_bloodflower_bunch01x", offset = -1.05 }
    },
    ["chocolate_daisy"] = {
        { percentage = 0, prop = "mp005_s_inv_chocdaisy01x", offset = -1.05 },
        { percentage = 50, prop = "mp005_s_inv_chocdaisy01dx", offset = -1.05 },
        { percentage = 100, prop = "mp005_chocdaisy_p", offset = -1.05 }
    },
    ["maple_tree"] = {
        { percentage = 0, prop = "p_sap_maple_ba_sim", offset = -1.05 },
        { percentage = 50, prop = "p_sap_maple_ac_sim", offset = -1.05 },
        { percentage = 100, prop = "p_sap_maple_ab_sim", offset = -2.05 }
    },
    ["thyme"] = {
        { percentage = 0, prop = "s_inv_thyme01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_thyme01cx", offset = -1.05 },
        { percentage = 100, prop = "thyme_p", offset = -1.05 }
    },
    ["crows_garlic"] = {
        { percentage = 0, prop = "s_inv_crowsgarlic01x", offset = -1.05 },
        { percentage = 50, prop = "crowsgarlic_p", offset = -1.05 },
        { percentage = 100, prop = "crowsgarlic_p", offset = -1.05 }
    },
    ["english_mace"] = {
        { percentage = 0, prop = "s_inv_engmace01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_engmace01dx", offset = -1.05 },
        { percentage = 100, prop = "engmace_p", offset = -1.05 }
    },
    ["indian_tobacco"] = {
        { percentage = 0, prop = "s_inv_indtobacco01x", offset = -1.05 },
        { percentage = 50, prop = "s_indiantobacco01x", offset = -1.05 },
        { percentage = 100, prop = "s_indiantobaccopicked01x", offset = -1.05 }
    },
    ["parasol_mushroom"] = {
        { percentage = 0, prop = "s_inv_parasol", offset = -0.90 },
        { percentage = 50, prop = "s_inv_parasol", offset = -0.90 },
        { percentage = 100, prop = "s_inv_parasol01bx", offset = -0.95 }
    },
    ["raspberry"] = {
        { percentage = 0, prop = "s_inv_raspberry01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_raspberry01x", offset = -1.05 },
        { percentage = 100, prop = "s_inv_raspberry01x", offset = -1.05 }
    },
    ["red_sage"] = {
        { percentage = 0, prop = "s_inv_redsage01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_redsage01dx", offset = -1.05 },
        { percentage = 100, prop = "redsage_p", offset = -1.05 }
    },
    ["wild_carrot"] = {
        { percentage = 0, prop = "s_inv_wildcarrot01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_wildcarrot01x", offset = -1.05 },
        { percentage = 100, prop = "wildcarrot_p", offset = -1.05 }
    },
    ["wild_mint"] = {
        { percentage = 0, prop = "s_inv_wildmint01x", offset = -1.05 },
        { percentage = 50, prop = "s_inv_wildmint01cx", offset = -1.05 },
        { percentage = 100, prop = "wildmint_p", offset = -1.05 }
    },
    ["wintergreen"] = {
        { percentage = 0, prop = "s_inv_wintergreen01bx", offset = -1.05 },
        { percentage = 50, prop = "s_inv_wintergreen01bx", offset = -1.05 },
        { percentage = 100, prop = "s_inv_wintergreen01bx", offset = -1.05 }
    },
    ["yarrow"] = {
        { percentage = 0, prop = "s_inv_yarrow02bx", offset = -1.05 },
        { percentage = 50, prop = "yarrow02_p", offset = -1.05 },
        { percentage = 100, prop = "yarrow04_p", offset = -1.05 }
    },
    ["corn"] = {
        { percentage = 0, prop = "crp_cornstalks_bb_sim", offset = -1.05 },
        { percentage = 50, prop = "crp_cornstalks_bd_sim", offset = -1.05 },
        { percentage = 100, prop = "crp_cornstalks_bc_sim", offset = -1.05 }
    },
    ["orange_tree"] = {
        { percentage = 0, prop = "p_tree_orange_01", offset = -1.40 },
        { percentage = 50, prop = "p_tree_orange_01", offset = -1.40 },
        { percentage = 100, prop = "p_tree_orange_01", offset = -1.40 }
    },
    ["sugarcane"] = {
        { percentage = 0, prop = "crp_sugarcane_ab_sim", offset = -1.05 },
        { percentage = 50, prop = "crp_sugarcane_ac_sim", offset = -1.05 },
        { percentage = 100, prop = "crp_sugarcane_ad_sim", offset = -1.05 }
    },
    ["potato"] = {
        { percentage = 0, prop = "crp_potato_sap_aa_sim", offset = -1.05 },
        { percentage = 50, prop = "crp_potato_aa_sim", offset = -1.05 },
        { percentage = 100, prop = "crp_potato_aa_sim", offset = -1.05 }
    },
    ["hemp"] = {
        { percentage = 0, prop = "prop_weed_02", offset = -1.70 },
        { percentage = 50, prop = "prop_weed_02", offset = -1.15 },
        { percentage = 100, prop = "prop_weed_01", offset = -1.05 }
    },
    ["aloe"] = {
        { percentage = 0, prop = "rdr_bush_aloe_aa_sim", offset = -1.05 },
        { percentage = 50, prop = "rdr_bush_aloe_aa_sim", offset = -1.05 },
        { percentage = 100, prop = "rdr_bush_aloe_aa_sim", offset = -1.05 }
    },
}

Config.WaterWagons = {
    [1] = {
        model = "cart05",
        limit = 100, -- limit of water in the wagon
    }
}

Config.DestroyItems = {
    "matches",
}


Config.Controls = {
    DropBucket = 0x760A9C6F,
    WaterPlant = 0xF3830D8E,
    FillBucket = 0xCEFD9220,
    HarvestPlant = 0x760A9C6F,
    FillWagon = 0x26E9DC00,
    FullyFillWagon = 0xE30CD707,
}



Config.ProgressBars = {
    ['fill_bucket'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling bucket..',
        time = 10000,
        animation = {
            time = -1,
            scenario = -2053511979,
            type = 'scenario',
        }
    },

    ['fill_bucket_wagon'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling bucket..',
        time = 10000,
        animation = {
            anim = "idle_a",
            flags = 1,
            animDict = "amb_work@prop_human_pump_water@female_b@idle_a"
        }
    },

    ['fill_wagon'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling bucket..',
        time = 10000,
        animation = {
            time = -1,
            scenario = -2053511979,
            type = 'scenario',
        }
    },

    ['fully_fill_wagon'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling bucket..',
        time = 30000,
        animation = {
            time = -1,
            scenario = -2053511979,
            type = 'scenario',
        }
    },

    ['fill_bucket_pump'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling bucket..',
        time = 10000,
        animation =  false,
    },
    ['water_plant'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Watering',
        time = 10000,
        animation = {
            time = -1,
            scenario = -634535025,
            type = 'scenario',
            
        }
    },
    ['plant'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Planting',
        canStop = true,
        time = 15000,
        prop = {
            bone = "CH_R_Hand",
            rotation = {
                x = -90.0,
                y = 10.0,
                z = -50.0
            },
            model = "p_gardenscoop01x",
            coords = {
                x = 0.0,
                y = 0.0,
                z = -0.05
            }
        },

        animation = {
            anim = "idle_c",
            flags = 1,
            animDict = "amb_camp@world_camp_jack_plant@idle_a"
        }
        
        
    },

    ['fertilizer'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Fertilizing..',
        time = 10000,
        animation = {
            time = -1,
            scenario = "WORLD_HUMAN_FEED_CHICKEN",
            type = 'scenario',
            
        }
    },

    ['harvest_plant'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Harvesting',
        time = 10000,
        animation = {
            anim = "base",
            flags = 1,
            animDict = "mech_pickup@plant@berries"
        }
    },

    ['destroy_plant'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Destroying',
        time = 10000,
        animation = {
            anim = "idle_c",
            flags = 1,
            animDict = "amb_camp@world_camp_jack_plant@idle_a"
        }
    }


    
}

Config.Resources = {
    ['POS-Housing'] = true,
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do this.',
        ['plant_planted'] = 'You have planted a %s.',
        ['plant_limit_reached'] = 'You have reached the plant limit.',
        ['plant_too_close'] = 'You cannot plant here, another plant is too close.',
        ['fertilizer_used'] = '%s was used and increased this plant\'s fertilizer by %s.',
        ['temperature_not_right'] = 'The temperature is not suitable for this plant.',
        ['plant_title'] = '%s (%s)',
        ['zone_title'] = '%s (%s)',
        ['wrong_arguments'] = 'You have provided the wrong or incomplete arguments.',
        ['plant_not_found'] = 'There was no plant found to do this.',
        ['plant_not_yours'] = 'This plant does not belong to you.',
        ['not_enough_space'] = 'You do not have enough space to do this.',
        ['plant_harvested'] = 'You harvested a %s and received %s x %s',
        ['harvest_plant_prompt'] = 'Harvest plant.',
        ['drop_bucket_prompt'] = 'Drop bucket',
        ['fill_bucket_prompt'] = 'Fill bucket',
        ['water_plant_prompt'] = 'Water plant',
        ['filled_bucket'] = 'You have filled the bucket with water.',
        ['watered_plant'] = 'You have watered the plant.',
        ['cannot_plant_here'] = 'You cannot plant here!',
        ['plant_destroyed'] = 'You have destroyed a %s.',
        ['invalid_plant'] = 'The following plant was not found in the config: %s',
        ['fully_fill_wagon_prompt'] = 'Fully fill wagon',
        

        ['set_locations'] = 'Set locations',
        ['set_locations_desc'] = 'Set the locations for the zone.',
        ['set_main_location'] = 'Set main location',
        ['set_main_location_desc'] = 'Set the main location for the zone.',
        ['manage_plants'] = 'Manage plants',
        ['manage_plants_desc'] = 'Manage the plants in the zone.',

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
        ['added_plant'] = 'You have added the %s to the zone.',
        ['removed_plant'] = 'You have removed the %s from the zone.',

        ['zone_main_location'] = 'Main Location',
        ['zone_locations'] = 'Zone Locations',
        ['zone_name'] = 'Zone Name',
        ['zone_blip'] = 'Zone Blip',
        ['zone_blip_modifier'] = 'Blip Modifier',
        ['set'] = 'Set',
        ['not_set'] = 'Not Set',
        ['no_plants'] = 'No plants in this zone.',
        ['add_plant'] = 'Add plant',
        ['add_plant_desc'] = 'Add a plant to the zone.',
        ['remove_plant_desc'] = 'Remove a plant from the zone.',
        ['zone_plants'] = 'Zone Plants',
        ['zone_not_found'] = 'Zone not found.',
        ['edit_zone'] = 'Edit zone',
        ['edit_zone_desc'] = 'Edit the zone.',
        ['delete_zone'] = 'Delete zone',
        ['delete_zone_desc'] = 'Delete the zone.',
        ['zone_deleted'] = 'Zone deleted successfully.',
        ['zone_updated'] = 'Zone updated successfully.',
        ['zone_created'] = 'Zone created successfully.',
        ["webhook_title"] = "🌱 Farming Webhook",


        ["webhook_farming"] = "🌱 Farming Webhook",
        ["input_yes"] = "YES",

        ["webhook_plant_id"] = "🌱 Plant ID",
        ["webhook_watering_type"] = "💧 Watering Type",
        ["webhook_watering_item"] = "🧺 Item Used",
        ["webhook_water_amount"] = "📦 Water Amount",
        ["webhook_farmingwaterplant"] = "🌾 Plant Watered",
        ["webhook_farmingwaterplant_info"] = "A plant was watered.",
        ["webhook_user_information"] = "User Information",
        ["webhook_target_information"] = "Target Information",
        ["webhook_total_water"] = "💧 Total Water Level",

        ["webhook_fertilizer_item"] = "🧪 Fertilizer Item",
        ["webhook_fertilizer_amount"] = "📦 Fertilizer Amount",
        ["webhook_total_fertilizer"] = "🧬 Total Fertilizer Level",
        ["webhook_farmingfertilizer"] = "🌿 Fertilizer Used",
        ["webhook_farmingfertilizer_info"] = "A plant was fertilized.",

        ["webhook_destroy_item"] = "🧨 Destroy Item",
        ["webhook_farmingdestroy"] = "🔥 Plant Destroyed",
        ["webhook_farmingdestroy_info"] = "A plant was destroyed.",
        ['player_busy'] = 'You are already doing an action, wait for it to finish before starting another action.',

        ["webhook_harvest_item"] = "🌾 Harvested",
        ["webhook_water_level"] = "💧 Water Level",
        ["webhook_fertilizer_level"] = "🌿 Fertilizer Level",
        ["webhook_growth_level"] = "📊 Growth Level",
        ["webhook_seed_received"] = "🌰 Got Seed?",
        ["webhook_farmingharvest"] = "🌿 Plant Harvested",
        ["webhook_farmingharvest_info"] = "A plant was harvested.",
        ["yes"] = "✅ Yes",
        ["no"] = "❌ No",

        ["webhook_plant_type"] = "🌿 Plant Type",
        ["webhook_plant_temp"] = "🌡️ Temperature Check",
        ["webhook_plant_owner"] = "👤 Plant Owner",
        ["webhook_plant_coords"] = "📍 Coordinates",
        ["webhook_farmingplant"] = "🌿 New Plant Planted",
        ["webhook_farmingplant_info"] = "A new plant has been planted.",
        ["water_wagon_prompt"] = "Water: %s / %s | Uses %s / %s.",
        ['fill_wagon_prompt'] = 'Fill wagon',
        ["water_wagon_not_found"] = "Water wagon not found.",
        ["water_wagon_full"] = "The water wagon is already full.",
        ["water_wagon_filled"] = "%s poured into the wagon. Current: %s.",
        ["water_wagon_not_enough_water"] = "Not enough water in the wagon.",
        ["water_bucket_filled"] = "You filled your bucket with %s.",
        ['item_required_to_plant'] = 'You need a specific item to plant this.',
        ['item_required_to_harvest'] = 'You need a specific item to harvest this.',
        ['plant_already_fertilized'] = 'This plant has already been fertilized to the maximum.',
        ['water_bucket_prompt'] = 'Water bucket. (Uses: %s/%s)',
        ['water_wagon_fully_filled'] = 'The wagon was fully filled and now it has %s water.',
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
