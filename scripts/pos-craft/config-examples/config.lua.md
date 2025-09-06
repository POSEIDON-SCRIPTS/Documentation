# config.lua

```lua
Config = {}

Config.GlobalCraftItems = false -- If crafted items will show in every menu/book etc, if not it will show only in the one crafted.

Config.OpenMenuKey = 0x760A9C6F -- G

Config.DistanceToOpenMenu = 2


Config.xpLevels = {
    [1] = {
        level = 1,
        xp = 0,
        maxXp = 50,
    },
    [2] = {
        level = 2,
        xp = 50,
        maxXp = 300,
    },
    [3] = {
        level = 3,
        xp = 300,
        maxXp = 400,
    },
}

Config.Functions = {
    progressbar = function(time, title, item, percentage)
        local status = exports['POS-ProgressBar']:StartProgress({
            time = time,
            title = title,
            item = item,
            canStop = true,
            percentage = percentage,
        })

        return status
    end,

    addXp = function(source, id, xp) -- return true if xp added
        return nil
    end,

    getXp = function(source, id) -- return xp if exists
        return nil
    end,
}

Config.CraftMenus = {
    [1] = {
        title = 'Carte de Bucate',
        description = '',
        blurIfNoRequirements = false,

        positions = {
            -- vector3(2742.8213, -1393.6442, 46.1831)
        },

        jobs = { -- or false
            {job = 'politie', grade = 1}, -- Or grade = nil
        },

        characterids = {
            1,
            2
        },

        props = {
            "p_campfire01x",
            "p_campfire_win2_smolder01x",
            "p_campfire03x",
            "p_campfire05x",
            "s_campfirecombined01x",
            "s_cookfire01x",
            "s_cul_cookfire01x",
            "s_hobo_cookfire01x",
            "s_mil_cookfire01x",
            "s_sav_cookfire01x",
            "s_sur_cookfire01x",
            "p_campfirecombined02x",
            "p_campfirecombined01x_off",
            "p_campfire_coloursmoke01x",
        },

        
        items = false,
        clan = false, -- Clan required to open menu ? You can specify a clan id or just true 
        


        categories = {

            ['Mancaruri'] = {
                image = 'assets/img/consumable_meal.png',


                items = {
                    
                    "mic_dejun",
                    "consumable_meat_herptile_cooked",
                    "consumable_meat_mutton_cooked",
                    "consumable_meat_venison_jerky",
                                
                        },
            },


            ['Peste'] = {
                image = 'assets/img/consumable_bluegil.png',


                items = {
                    
                    "peste_gatit",
                    "peste_gatit1",
                    "peste_gatit2",
                    "peste_gatit3",
                    "peste_gatit4",
                    "peste_gatit5",
                    "peste_gatit6",
                    "peste_gatit7",
                    "peste_gatit8",
                    "peste_gatit9",
                    "peste_gatit10",
                    "peste_gatit11",
                    "peste_gatit12",
                    "peste_gatit13",
                    "peste_gatit14",
                    "peste_gatit15",
                    "peste_gatit16",
                    "peste_gatit17",
                    "peste_gatit18",
                    "peste_gatit19",
                    "peste_gatit20",
                    "peste_gatit21",
                    "peste_gatit22",
                    "peste_gatit23",
                    "peste_gatit24",


                                
                        },
            },

            ['Porc'] = {
                image = 'assets/img/consumable_meat_tender_pork_cooked.png',


                items = {
                    
                    "consumable_meat_tender_pork_cooked",
                    "bacon",
                    "bacon_sandwich",
                                
                        },
            },

            ['Vita'] = {
                image = 'assets/img/consumable_steak_veg.png',


                items = {
                    
                    "consumable_steak_veg",
                                
                        },
            },

            ['Pasare'] = {
                image = 'assets/img/consumable_meat_plump_bird_cooked.png',


                items = {
                    
                    "consumable_meat_plump_bird_cooked",
                    "consumable_meat_exotic_bird_cooked",
                    "consumable_meat_gamey_bird_cooked",
                                
                        },
            },

        },

    },
    
    [2] = {
        title = 'Unelte',
        description = '',
        blurIfNoRequirements = false,
        props = false,
        items = {"carte_craftare"},
        clan = false, -- Clan required to open menu ? You can specify a clan id or just true 
        
        jobs = { -- or false
            {job = 'politie', grade = 1}, -- Or grade = nil
        },

        characterids = {
            1,
            2
        },

        categories = {

            ['Unelte'] = {
                image = 'assets/img/unelte.png',


                items = {
                    
                    "p_goldcradlestand01x",
                    "cazan_tuica",
                    "ceaun",
                    "gratar",
                    "cocaina_plic",
                    "lockpick",
                    "lockpickmold",
                    "cazan_galeata",

                                
                },
            },


            ['Arme'] = {
                image = 'assets/img/arc.png',


                items = {
                    
                    "WEAPON_MELEE_KNIFE",
                    "WEAPON_MELEE_KNIFE_RUSTIC",
                    "WEAPON_MELEE_KNIFE_HORROR",
                    "WEAPON_BOW",
                    "ammoarrownormal",
                    -- "ammoarrowfire",
                    "WEAPON_LASSO",
                    
        
                        },
            },

            ['Utilitare'] = {
                image = 'assets/img/anvil.png',


                items = {
                    
                    "scoci",

                    
        
                        },
            },


        },

    },
    [3] = {
        title = 'Topitorie',
        description = '',
        blurIfNoRequirements = false,
        positions = {
            vector3(495.7758, 533.0596, 109.8139),
            vector3(499.3564, 532.6664, 109.8120)
        },
        props = false,
        items = false,
        clan = false, -- Clan required to open menu ? You can specify a clan id or just true 
        
        jobs = { -- or false
            {job = 'politie', grade = 1}, -- Or grade = nil
        },

        characterids = {
            1,
            2
        },

        categories = {

            ['Lingouri'] = {
                image = 'assets/img/lingouri_aur.png',


                items = {
                    
                    "lingou_cupru",
                    "lingou_otel",
                    --"lingou_aur",
                    --"lingou_fier",
                    --"pepite_aur",
                                
                        },
            },


            ['Sulf'] = {
                image = 'assets/img/praf_pusca.png',


                items = {
                    
                    "praf_pusca",
                    "sulf",
        
                        },
            },
        


        },

    },
    [4] = {
        title = 'Fierarie',
        description = '',
        blurIfNoRequirements = false,
        props = {},
        positions = {
            vector3(499.8197, 538.4257, 109.8121),
            vector3(496.2105, 538.7542, 109.8121)
        },
        items = {},
        clan = false, -- Clan required to open menu ? You can specify a clan id or just true 
        
        jobs = { -- or false
            {job = 'politie', grade = 1}, -- Or grade = nil
        },

        characterids = {
            1,
            2
        },

        categories = {

            ['Fierar'] = {
                image = 'assets/img/anvil.png',


                items = {
                    
                    "arc",
                    "suruburi",
                    "cazan_furtun",
                    "cuie",
                    "cazan_depozit",

                                
                        },
            },



        },

    },

}



Config.Recipes = {
    ['scoci'] = {
        item = 'scoci',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 60,
        requiredItems = {
            ['panza'] = { count = 1 },
            ['seva'] = { count = 2 },
        },

        xp = {
            required = false,
            add = 100,
        },

        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
            flag = 1,

            prop = {
                model = 'w_melee_knife06',
                coords = {
                    x = -0.01,
                    y = -0.02,
                    z = 0.02,
                    xr = 190.0,
                    yr = 0.0,
                    zr = 0.0
                },
                bone = 'SKEL_R_Finger13',
                subprop = {
                    bone = 'SKEL_R_Finger13',
                    model = 'p_redefleshymeat01xa',
                    coords = {
                        x = 0.00,
                        y = 0.02,
                        z = -0.20,
                        xr = 0.0,
                        yr = 0.0,
                        zr = 0.0
                    }
                }
            }
        },

        returnAllAditionalItems = false,
        additionalItems = {},
        requiresUnlock = { -- If you want to unlock the recipe after using an item
            "scoci"
        },
    },

    ['machiaj1'] = {
        item = 'machiaj1',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 45,
        requiredItems = {
            ['consumable_herb_harrietum'] = { count = 2 },
            ['consumable_herb_oregano'] = { count = 3 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  


    ['morphina'] = {
        item = 'morphina',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 150,
        requiredItems = {
            ['provision_wldflwr_blood_flower'] = { count = 1 },
            ['provision_wldflwr_creek_plum'] = { count = 1 },
            ['provision_wldflwr_wild_rhubarb'] = { count = 1 },
            ['provision_wldflwr_bitterweed'] = { count = 1 },
            ['provision_wldflwr_agarita'] = { count = 1 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  

    ['vesta'] = {
        item = 'vesta_antiglont',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 180,
        requiredItems = {
            ['provizie_corn_antilopa'] = { count = 2 },
            ['provision_rabbit_pelt'] = { count = 1 },
            ['generic_grasime_animal'] = { count = 2 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  
    
    ['machiaj2'] = {
        item = 'machiaj2',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 45,
        requiredItems = {
            ['consumable_herb_parasol_mushroom'] = { count = 2 },
            ['consumable_herb_burdock_root'] = { count = 3 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  

    ['machiaj3'] = {
        item = 'machiaj3',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 45,
        requiredItems = {
            ['consumable_herb_milkweed'] = { count = 2 },
            ['provision_wldflwr_chocolate_daisy'] = { count = 3 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  

    ['machiaj4'] = {
        item = 'machiaj4',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 45,
        requiredItems = {
            ['consumable_herb_evergreen_huckleberry'] = { count = 2 },
            ['consumable_herb_indian_tobacco'] = { count = 3 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  

    ['machiaj5'] = {
        item = 'machiaj5',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 45,
        requiredItems = {
            ['consumable_herb_rams_head'] = { count = 2 },
            ['consumable_herb_english_mace'] = { count = 3 },
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },  

    ['potiune_resuscitare'] = {
        item = 'potiune_resuscitare',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 180,
        requiredItems = {
            ['consumable_herb_golden_currant'] = { count = 3 },
            ['consumable_herb_chanterelles'] = { count = 4 },
            ['consumable_herb_bay_bolete'] = { count = 2 },
            ['consumable_herb_alaskan_ginseng'] = { count = 5 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },

    ['accesoriiindiancal'] = {
        item = 'accesoriiindiancal',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 150,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 15 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },

    ['accesoriuindiancap1'] = {
        item = 'accesoriuindiancap1',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap2'] = {
        item = 'accesoriuindiancap2',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap3'] = {
        item = 'accesoriuindiancap3',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap4'] = {
        item = 'accesoriuindiancap4',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap5'] = {
        item = 'accesoriuindiancap5',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap6'] = {
        item = 'accesoriuindiancap6',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap7'] = {
        item = 'accesoriuindiancap7',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap8'] = {
        item = 'accesoriuindiancap8',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap9'] = {
        item = 'accesoriuindiancap9',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap10'] = {
        item = 'accesoriuindiancap10',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap11'] = {
        item = 'accesoriuindiancap11',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancap12'] = {
        item = 'accesoriuindiancap12',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },

    ['accesoriuindiancorp1'] = {
        item = 'accesoriuindiancorp1',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    
    ['accesoriuindiancorp2'] = {
        item = 'accesoriuindiancorp2',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancorp3'] = {
        item = 'accesoriuindiancorp3',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancorp4'] = {
        item = 'accesoriuindiancorp4',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancorp5'] = {
        item = 'accesoriuindiancorp5',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancorp6'] = {
        item = 'accesoriuindiancorp6',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancorp7'] = {
        item = 'accesoriuindiancorp7',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },
    ['accesoriuindiancorp8'] = {
        item = 'accesoriuindiancorp8',
        count = 1,
        chanceToCraft = 100,
        timeToCraft = 90,
        requiredItems = {
            ['provizie_pene_pasare_zbor'] = { count = 5 },
            ['sfoara'] = { count = 1 }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false,
        additionalItems = {},
    },

    ['stimulent_cai'] = { --Recipe name
        item = 'stimulent_cai', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['consumable_herb_violet_snowdrop'] = { -- Item Name
                count = 1, -- Count
            },
            ['consumable_herb_desert_sage'] = { -- Item Name
                count = 1, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['WEAPON_BOW_IMPROVED'] = { --Recipe name
        item = 'WEAPON_BOW_IMPROVED', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 180, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['lemn'] = { -- Item Name
                count = 1, -- Count
            },
            ['sfoara'] = { -- Item Name
                count = 2, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['WEAPON_LASSO_REINFORCED'] = { --Recipe name
        item = 'WEAPON_LASSO_REINFORCED', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 90, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            -- ['lemn'] = { -- Item Name
            --     count = 1, -- Count
            -- },
            ['sfoara'] = { -- Item Name
                count = 2, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },


    ['WEAPON_THROWN_TOMAHAWK'] = { --Recipe name
        item = 'WEAPON_THROWN_TOMAHAWK', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 150, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['lemn'] = { -- Item Name
                count = 1, -- Count
            },
            ['lingou_fier'] = { -- Item Name
                count = 2, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },
    
    

    ['ammotomahawk'] = { --Recipe name
        item = 'ammotomahawk', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 90, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['lingou_fier'] = { -- Item Name
                count = 2, -- Count
            }
            -- ['lingou_fier'] = { -- Item Name
            --     count = 1, -- Count
            -- }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    

    ['WEAPON_MELEE_KNIFE_JAWBONE'] = { --Recipe name
        item = 'WEAPON_MELEE_KNIFE_JAWBONE', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 150, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['lemn'] = { -- Item Name
                count = 1, -- Count
            },
            ['lingou_fier'] = { -- Item Name
                count = 2, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['WEAPON_MELEE_TORCH'] = { --Recipe name
        item = 'WEAPON_MELEE_TORCH', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['lemn'] = { -- Item Name
                count = 1, -- Count
            },
            ['generic_grasime_animal'] = { -- Item Name
                count = 2, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['WEAPON_MELEE_LANTERN_HALLOWEEN'] = { --Recipe name
        item = 'WEAPON_MELEE_LANTERN_HALLOWEEN', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 150, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['lingou_fier'] = { -- Item Name
                count = 2, -- Count
            },
            ['generic_grasime_animal'] = { -- Item Name
                count = 5, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },
    

    ['mic_dejun'] = { --Recipe name
        item = 'mic_dejun', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give
        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item
        requiredItems = { -- Required Items
            ['bacon'] = { -- Item Name
                count = 1, -- Count
            },
            ['ou'] = { -- Item Name
                count = 1, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },
        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['consumable_meat_herptile_cooked'] = { --Recipe name
        item = 'consumable_meat_herptile_cooked', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['provizie_carne_reptila'] = { -- Item Name
                count = 1, -- Count
            }
        },
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },


    ['consumable_meat_mutton_cooked'] = { --Recipe name
        item = 'consumable_meat_mutton_cooked', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['provizie_carne_miel'] = { -- Item Name
                count = 1, -- Count
            }
        },
        
        animation = {
            dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
            anim = "loop",
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['consumable_meat_venison_jerky'] = { --Recipe name
        item = 'consumable_meat_venison_jerky', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 120, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['provizie_carne_matura_caprioara'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['peste_gatit'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishbluegil_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
    },

    ['peste_gatit1'] = { --Recipe name
    item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
    count = 1, -- amount to give



    chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
    timeToCraft = 45, -- Time in seconds to craft the item

    requiredItems = { -- Required Items
        ['a_c_fishbluegil_01_ms'] = { -- Item Name
            count = 1, -- Count
        }
    },

    returnAllAditionalItems = false, --Return every item, or just one at random
    additionalItems = { -- items to return
        -- ['praf_pusca'] = { -- Item Name
        --     count = 1, -- Item Count
        --     chance = 100, -- Chance to return the item
        -- }
    },
},

        ['peste_gatit2'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishbluegil_01_sm'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit3'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishbullheadcat_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit4'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishbullheadcat_01_sm'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit5'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishchainpickerel_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit6'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishchainpickerel_01_sm'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit7'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishchannelcatfish_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit8'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishchannelcatfish_01_xl'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit9'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishlakesturgeon_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit10'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishlargemouthbass_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit11'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishlargemouthbass_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit12'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishlongnosegar_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit13'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishperch_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit14'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishperch_01_sm'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit15'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishrainbowtrout_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit16'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishrainbowtrout_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit17'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishredfinpickerel_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },


        ['peste_gatit18'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishredfinpickerel_01_sm'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit19'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishrockbass_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit20'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 30, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishrockbass_01_sm'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit21'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 60, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishsalmonsockeye_01_lg'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },


        ['peste_gatit22'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 50, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishsalmonsockeye_01_ml'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },

        ['peste_gatit23'] = { --Recipe name
        item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
        count = 1, -- amount to give



        chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
        timeToCraft = 45, -- Time in seconds to craft the item

        requiredItems = { -- Required Items
            ['a_c_fishsalmonsockeye_01_ms'] = { -- Item Name
                count = 1, -- Count
            }
        },

        returnAllAditionalItems = false, --Return every item, or just one at random
        additionalItems = { -- items to return
            -- ['praf_pusca'] = { -- Item Name
            --     count = 1, -- Item Count
            --     chance = 100, -- Chance to return the item
            -- }
        },
        },


        ['peste_gatit24'] = { --Recipe name
            item = 'peste_gatit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['a_c_fishsmallmouthbass_01_lg'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['consumable_meat_tender_pork_cooked'] = { --Recipe name
            item = 'consumable_meat_tender_pork_cooked', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 45, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['provizie_carne_porc_frageda'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['bacon'] = { --Recipe name
            item = 'bacon', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 30, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['provizie_carne_porc_frageda'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['bacon_sandwich'] = { --Recipe name
            item = 'bacon_sandwich', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['provizie_carne_porc_frageda'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['consumable_steak_veg'] = { --Recipe name
            item = 'consumable_steak_veg', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['provizie_carne_vita_calitate_superioara'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['consumable_meat_plump_bird_cooked'] = { --Recipe name
            item = 'consumable_meat_plump_bird_cooked', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 45, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['provizie_carne_pasare'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        
        ['consumable_meat_gamey_bird_cooked'] = { --Recipe name
            item = 'consumable_meat_gamey_bird_cooked', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 45, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['provizie_carne_pasare_grasa'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['p_goldcradlestand01x'] = { --Recipe name
            item = 'p_goldcradlestand01x', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['scanduri'] = { -- Item Name
                    count = 5, -- Count
                },
                ['lemn'] = { -- Item Name
                    count = 5, -- Count
                },
                ['cuie'] = { -- Item Name
                    count = 20, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['cazan_tuica'] = { --Recipe name
            item = 'cazan_tuica', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 240, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['cazan_galeata'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cazan_furtun'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cazan_depozit'] = { -- Item Name
                    count = 1, -- Count
                },
                ['scoci'] = { -- Item Name
                    count = 2, -- Count
                },
                ['cuie'] = { -- Item Name
                    count = 20, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ceaun'] = { --Recipe name
            item = 'ceaun', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_cupru'] = { -- Item Name
                    count = 1, -- Count
                },
                ['scanduri'] = { -- Item Name
                    count = 2, -- Count
                },
                ['piatra'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['gratar'] = { --Recipe name
            item = 'gratar', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['scanduri'] = { -- Item Name
                    count = 5, -- Count
                },
                ['piatra'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        
        ['lockpick'] = { --Recipe name
            item = 'lockpick', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 45, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lockpickmold'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },

        },
        ['lockpickmold'] = { --Recipe name
            item = 'lockpickmold', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },

        },
        ['cazan_galeata'] = { --Recipe name
            item = 'cazan_galeata', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['scanduri'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lemn'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cuie'] = { -- Item Name
                    count = 10, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },

        },
        ['dinamita'] = { --Recipe name
            item = 'dinamita', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['praf_pusca'] = { -- Item Name
                    count = 1000, -- Count
                },

            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },

        },
        ['dinamita_mare'] = { --Recipe name
            item = 'dinamita_mare', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 240, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['praf_pusca'] = { -- Item Name
                    count = 1500, -- Count
                },

            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },

        },

        ['WEAPON_MELEE_KNIFE'] = { --Recipe name
            item = 'WEAPON_MELEE_KNIFE', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lemn'] = { -- Item Name
                    count = 2, -- Count
                },
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_MELEE_KNIFE_RUSTIC'] = { --Recipe name
            item = 'WEAPON_MELEE_KNIFE_RUSTIC', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lemn'] = { -- Item Name
                    count = 2, -- Count
                },
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_MELEE_KNIFE_HORROR'] = { --Recipe name
            item = 'WEAPON_MELEE_KNIFE_HORROR', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lemn'] = { -- Item Name
                    count = 2, -- Count
                },
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_BOW'] = { --Recipe name
            item = 'WEAPON_BOW', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lemn'] = { -- Item Name
                    count = 1, -- Count
                },
                ['sfoara'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ammoarrownormal'] = { --Recipe name
            item = 'ammoarrownormal', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lemn'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ammoarrowfire'] = { --Recipe name
            item = 'ammoarrowfire', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 150, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lemn'] = { -- Item Name
                    count = 2, -- Count
                },
                ['generic_grasime_animal'] = { -- Item Name
                    count = 2, -- Count
                },
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        
        ['WEAPON_LASSO'] = { --Recipe name
            item = 'WEAPON_LASSO', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['sfoara'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['lingou_cupru'] = { --Recipe name
            item = 'lingou_cupru', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give

            requiresUnlock = {"test"},

            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 150, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['minereu_cupru'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['lingou_otel'] = { --Recipe name
            item = 'lingou_otel', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give
            requiresUnlock = {"test2"},


            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_fier'] = { -- Item Name
                    count = 3, -- Count
                },
                ['carbune'] = { -- Item Name
                    count = 3, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['lingou_aur'] = { --Recipe name
            item = 'lingou_aur', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['pepite_aur'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['lingou_fier'] = { --Recipe name
            item = 'lingou_fier', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 150, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['minereu_fier'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },


            ['pepite_aur'] = { --Recipe name
            item = 'pepite_aur', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 5, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['minereu_aur'] = { -- Item Name
                    count = 10, -- Count
                }
            },    

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['sulf'] = { --Recipe name
            item = 'sulf', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['minereu_sulf'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['praf_pusca'] = { --Recipe name
            item = 'praf_pusca', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 10, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['sulf'] = { -- Item Name
                    count = 1, -- Count
                },
                ['carbune'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['arc'] = { --Recipe name (Metalic arc)
            item = 'arc', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 2, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_fier'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            animation = {
                dict = "script_mp@emotes@lets_craft@male@unarmed@upper",
                anim = "loop",
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['suruburi'] = { --Recipe name
            item = 'suruburi', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 20, -- amount to give


            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_fier'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['cuie'] = { --Recipe name
            item = 'cuie', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 10, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_fier'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['cazan_furtun'] = { --Recipe name
            item = 'cazan_furtun', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_cupru'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['cazan_depozit'] = { --Recipe name
            item = 'cazan_depozit', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 150, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_cupru'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['teava_pistol'] = { --Recipe name
            item = 'teava_pistol', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['matrita_pistol'] = { --Recipe name
            item = 'matrita_pistol', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['corp_pistol'] = { --Recipe name
            item = 'corp_pistol', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['maner_pistol'] = { --Recipe name
            item = 'maner_pistol', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                },
                ['scanduri'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['teava_revolver'] = { --Recipe name
            item = 'teava_revolver', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['cilindru_revolver'] = { --Recipe name
            item = 'cilindru_revolver', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['matrita_revolver'] = { --Recipe name
            item = 'matrita_revolver', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 150, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['maner_revolver'] = { --Recipe name
            item = 'maner_revolver', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 60, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                },
                ['scanduri'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['teava_repeater'] = { --Recipe name
            item = 'teava_repeater', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['corp_repeater'] = { --Recipe name
            item = 'corp_repeater', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['matrita_repeater'] = { --Recipe name
            item = 'matrita_repeater', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['maner_repeater'] = { --Recipe name
            item = 'maner_repeater', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                },
                ['scanduri'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['teava_pusca'] = { --Recipe name
            item = 'teava_pusca', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 210, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['corp_pusca'] = { --Recipe name
            item = 'corp_pusca', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 210, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['matrita_pusca'] = { --Recipe name
            item = 'matrita_pusca', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 210, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['maner_pusca'] = { --Recipe name
            item = 'maner_pusca', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 90, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_otel'] = { -- Item Name
                    count = 1, -- Count
                },
                ['scanduri'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['cartus_pistol'] = { --Recipe name
            item = 'cartus_pistol', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 50, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 120, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_cupru'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['cartus_pusca'] = { --Recipe name
            item = 'cartus_pusca', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 50, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 150, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['lingou_cupru'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ammopistolnormal'] = { --Recipe name
            item = 'ammopistolnormal', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['praf_pusca'] = { -- Item Name
                    count = 100, -- Count
                },
                ['cartus_pistol'] = { -- Item Name
                    count = 100, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ammoriflenormal'] = { --Recipe name
            item = 'ammoriflenormal', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 240, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['praf_pusca'] = { -- Item Name
                    count = 100, -- Count
                },
                ['cartus_pusca'] = { -- Item Name
                    count = 100, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ammorevolvernormal'] = { --Recipe name
            item = 'ammorevolvernormal', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 180, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['praf_pusca'] = { -- Item Name
                    count = 100, -- Count
                },
                ['cartus_pistol'] = { -- Item Name
                    count = 100, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['ammorepeaternormal'] = { --Recipe name
            item = 'ammorepeaternormal', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 240, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['praf_pusca'] = { -- Item Name
                    count = 100, -- Count
                },
                ['cartus_pusca'] = { -- Item Name
                    count = 100, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

        ['WEAPON_PISTOL_SEMIAUTO'] = { --Recipe name
            item = 'WEAPON_PISTOL_SEMIAUTO', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 300, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_PISTOL_MAUSER'] = { --Recipe name
            item = 'WEAPON_PISTOL_MAUSER', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 300, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_PISTOL_VOLCANIC'] = { --Recipe name
            item = 'WEAPON_PISTOL_VOLCANIC', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 240, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 10, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_PISTOL_M1899'] = { --Recipe name
            item = 'WEAPON_PISTOL_M1899', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 240, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pistol'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 10, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REVOLVER_SCHOFIELD'] = { --Recipe name
            item = 'WEAPON_REVOLVER_SCHOFIELD', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 330, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cilindru_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REVOLVER_NAVY'] = { --Recipe name
            item = 'WEAPON_REVOLVER_NAVY', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 270, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cilindru_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 10, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REVOLVER_NAVY_CROSSOVER'] = { --Recipe name
            item = 'WEAPON_REVOLVER_NAVY_CROSSOVER', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft =100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 270, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cilindru_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 10, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REVOLVER_LEMAT'] = { --Recipe name
            item = 'WEAPON_REVOLVER_LEMAT', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 330, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cilindru_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 2, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REVOLVER_DOUBLEACTION'] = { --Recipe name
            item = 'WEAPON_REVOLVER_DOUBLEACTION', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 270, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cilindru_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 10, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REVOLVER_CATTLEMAN_MEXICAN'] = { --Recipe name
            item = 'WEAPON_REVOLVER_CATTLEMAN_MEXICAN', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 270, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['cilindru_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_revolver'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 10, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REPEATER_WINCHESTER'] = { --Recipe name
            item = 'WEAPON_REPEATER_WINCHESTER', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 360, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REPEATER_HENRY'] = { --Recipe name
            item = 'WEAPON_REPEATER_HENRY', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 360, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REPEATER_EVANS'] = { --Recipe name
            item = 'WEAPON_REPEATER_EVANS', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 420, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_REPEATER_CARBINE'] = { --Recipe name
            item = 'WEAPON_REPEATER_CARBINE', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 420, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_repeater'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_RIFLE_BOLTACTION'] = { --Recipe name
            item = 'WEAPON_RIFLE_BOLTACTION', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 390, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_SNIPERRIFLE_CARCANO'] = { --Recipe name
            item = 'WEAPON_SNIPERRIFLE_CARCANO', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 480, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 30, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_RIFLE_SPRINGFIELD'] = { --Recipe name
            item = 'WEAPON_RIFLE_SPRINGFIELD', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 390, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 20, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },
        ['WEAPON_SNIPERRIFLE_ROLLINGBLOCK'] = { --Recipe name
            item = 'WEAPON_SNIPERRIFLE_ROLLINGBLOCK', -- ITEM TO RECEIVE, LABEL IS TAKEN FROM DATABASE
            count = 1, -- amount to give



            chanceToCraft = 100, -- The chance from 1 to 100 to craft the item
            timeToCraft = 420, -- Time in seconds to craft the item

            requiredItems = { -- Required Items
                ['teava_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['corp_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['matrita_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['maner_pusca'] = { -- Item Name
                    count = 1, -- Count
                },
                ['suruburi'] = { -- Item Name
                    count = 30, -- Count
                },
                ['arc'] = { -- Item Name
                    count = 1, -- Count
                },
                ['lingou_aur'] = { -- Item Name
                    count = 5, -- Count
                }
            },

            returnAllAditionalItems = false, --Return every item, or just one at random
            additionalItems = { -- items to return
                -- ['praf_pusca'] = { -- Item Name
                --     count = 1, -- Item Count
                --     chance = 100, -- Chance to return the item
                -- }
            },
        },

}

Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = 'https://discord.com/api/webhooks/1320745401455742997/aHN-uBCSyV6fgUvBrfgbE9yG_6N3QQhT8eeZAhGmx4HrhfNic6_x68MbHYIoMZwb39Oy', -- Default webhook for all deposits

    openMenu = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    craftItem = {
        sensitive = true,
        nonSensitive = '',
    },

    claimItem = {
        sensitive = true,
        nonSensitive = '',
    },

}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['ready'] = 'Ready.',
        ['crafted_item'] = 'The item was crafted successfully!',
        ['openmenu_prompt'] = 'Open Menu',
        ['craft_started'] = 'The selected item has started crafting and will be ready in %s.',
        ['not_enough_items'] = 'You do not have enough materials to start this craft !',
        ['item_collected'] = 'You have collected the item !', 
        ['no_space'] = 'You do not have enough space to claim the items !',
        ['not_allowed'] = 'You are not allowed to do that !', 
        ['recipe_unlocked'] = 'You have unlocked a new recipe!',
        ['recipe_already_unlocked'] = 'You have already unlocked this recipe!',
        
        ['error_occurred'] = 'An error has occurred while doing this !',
        
        ['webhook_user_information'] = 'Player Info',
        ['webhook_openMenu'] = 'A menu was opened!',
        ['webhook_openMenu_info'] = '%s has opened the menu %s.',
        
        ['webhook_item_crafted_item'] = "Item",
        ['webhook_item_crafted_label'] = "Label",
        ['webhook_item_crafted_recipe'] = "Recipe",
        ['webhook_item_crafted_time'] = "Time to Craft",
        ['webhook_item_crafted_character'] = "Character ID",

        ['webhook_craftItem'] = "Item Crafting",
        ['webhook_craftItem_info'] = "%s started crafting %s.",

        ['webhook_claimed_item'] = "Claimed Item",
        ['webhook_claimed_recipe'] = "Recipe",
        ['webhook_claimed_count'] = "Count",
        ['webhook_item_crafted_amount'] = "Amount",
        ['crafting_resumed'] = 'Crafting resumed! Percentage Completed: %s',
        ['crafting_failed'] = 'Crafting failed! Percentage Completed: %s',

        ['webhook_claimItem'] = "Item Claimed",
        ['webhook_claimItem_info'] = "%s claimed the item %s.",

        ['webhook_menu_title'] = "Menu Title",
        ['webhook_character_id'] = "Character ID",
        ['webhook_player'] = "Player",
        ['unknown_menu'] = "Unknown Menu",
        ['crafting_item'] = "Crafting: %s x %s.",
        ['invalid_amount'] = 'The amount entered is invalid!',
        ['script_loading'] = 'The script is starting, please wait before oppening the menu!',
        ['not_enough_level_xp'] = 'You do not have enough XP to craft this item!',
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
