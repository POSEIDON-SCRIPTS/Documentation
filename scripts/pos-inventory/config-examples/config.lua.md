# config.lua

```lua
Config = {}

Config.DisableInventoryWhileDead = true
Config.OpenKey = 0xC1989F95
Config.DefaultWeight = 50
Config.MaxGroundWeight = 1000
Config.DroppedItemsDistance = 8.0
Config.InventoryUpdateRange = 20.0

Config.RemoveDroppedItemsAfter = false

Config.RemoveItemsZeroPercent = false

Config.Debug = false
Config.EnableAmmoItems = true -- NEW
Config.UseRawKeys = false -- if you want to use the new raw keys system (only if you know what you are doing)

Config.RSG = false
Config.RSGStores = false

Config.ImportInventoryVORP = false -- command '' or false. Make sure to disable it.
Config.UseMaxWeightVORP = true -- If you want to use max weight from config, set this to true. If you want to use max weight from database, set this to false.
Config.ItemsInDatabaseVORP = true -- If you want to use items in database, set this to true. If you want to use items in config, set this to false.
Config.UseLoadoutTableVORP = true -- If you want to use loadout table, set this to true. (This will make sure weapon scripts are working properly)


Config.HotBarSettings = {
    giveAmmoOnRemove = true, -- Give ammo back when removing a weapon from hotbar
}

Config.MoneyItem = 'bani' -- Item name for money (used in the main inventory)

Config.Commands = {
    [1] = {
        Command = 'giveItem', -- or false to disable it
        Description = 'Gives an item to a player.',
        Parameters = {
            { name="id", help="Specify the id of the player to give the item." },
            { name="item", help="Specify the item to give." },
            { name="amount", help="Specify the amount of the item to give." }
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
}

Config.Functions = {
    ['GetXp'] = function (source)
        
        return 0 -- return the XP of the player, 0 (xp necessary for weapon usage) by default
    end
}

Config.StashSize = {
    maxweight = 50000, -- default weight for stash
}

Config.NewPlayers = {
    ['sticla_apa'] = 10,
    ['WEAPON_LASSO'] = 1
}

Config.Recipes = {
    ["applejuice"] = {
        input = {
            [1] = { item = "porumb", amount = 1 },
            [4] = { item = "cheie_cufar", amount = 1 },
            [3] = nil,
            [2] = nil,
            [5] = nil,
            [6] = nil,
            [7] = nil,
            [8] = nil,
            [9] = nil,
        },
        output = {
            item = "sticla_apa",
            amount = 1,
        }

    }
}



Config.Respawn = {

    Money = { 
        JobWhitelist = {},
        Enable = true,
        RemoveAll = false,
        PartMoney = 0.5 -- 50%
    }, 
    
    Ammo = {
        Enable = true,
        JobWhitelist = {},
        RemoveAll = false,
        PartAmmo = 0.5 -- 50% -- 50% of ammo will be removed
    },
    
    Items = { -- Includes weapons
        Enable = true,
        RemoveType = "drop", --Drop or Delete
        JobWhitelist = {},
        RemoveAll = true,
        WhitelistItems = {},
        DeleteItems = {}
    }
}

Config.UseItemCooldown = 3000

Config.ItemCooldowns = {
    ['WEAPON_PISTOL_MAUSER'] = 5000
}

Config.Clothes = {
    boot_accessories = { hash = 0x18729F39, label = "Boot Accessories" },
    pants = { hash = 0x1D4C528A, label = "Pants" },
    cloaks = { hash = 0x3C1A74CD, label = "Cloaks" },
    hats = { hash = 0x9925C067, label = "Hats" },
    vests = { hash = 0x485EE834, label = "Vests" },
    chaps = { hash = 0x3107499B, label = "Chaps" },
    shirts_full = { hash = 0x2026C46D, label = "Shirts (Full)" },
    badges = { hash = 0x3F7F3587, label = "Badges" },
    masks = { hash = 0x7505EF42, label = "Masks" },
    spats = { hash = 0x514ADCEA, label = "Spats" },
    neckwear = { hash = 0x5FC29285, label = "Neckwear" },
    boots = { hash = 0x777EC6EF, label = "Boots" },
    accessories = { hash = 0x79D7DF96, label = "Accessories" },
    jewelry_rings_right = { hash = 0x7A6BBD0B, label = "Jewelry (Right Rings)" },
    jewelry_rings_left = { hash = 0xF16A1D23, label = "Jewelry (Left Rings)" },
    jewelry_bracelets = { hash = 0x7BC10759, label = "Jewelry (Bracelets)" },
    gauntlets = { hash = 0x91CE9B20, label = "Gauntlets" },
    neckties = { hash = 0x7A96FACA, label = "Neckties" },
    loadouts = { hash = 0x83887E88, label = "Loadouts" },
    suspenders = { hash = 0x877A2CF7, label = "Suspenders" },
    satchels = { hash = 0x94504D26, label = "Satchels" },
    gunbelts = { hash = 0x9B2C8B89, label = "Gunbelts" },
    belts = { hash = 0xA6D134C6, label = "Belts" },
    belt_buckles = { hash = 0xFAE9107F, label = "Belt Buckles" },
    holsters_left = { hash = 0xB6B6122D, label = "Holsters (Left)" },
    holsters_right = { hash = 0xB9E2FA01, label = "Holsters (Right)" },
    coats = { hash = 0xE06D30CE, label = "Coats" },
    coats_closed = { hash = 0x662AC34, label = "Coats (Closed)" },
    ponchos = { hash = 0xAF14310B, label = "Ponchos" },
    armor = { hash = 0x72E6EF74, label = "Armor" },
    eyewear = { hash = 0x5E47CA6, label = "Eyewear" },
    gloves = { hash = 0xEABE0032, label = "Gloves" },
    hair_accessories = { hash = 0x8E84A2AA, label = "Hair Accessories" },
    dresses = { hash = 0xA2926F9B, label = "Dresses" },
    skirts = { hash = 0xA0E3AB7F, label = "Skirts" }
}

Config.ClothingAnimation = {
    gunbelts = {
        dict = "script_respawn@one_shot@fullbody@generic@unarmed@stand_adjust_belt@a",
        flag = 24,
        anim = "respawn_action",
        timer = 1000,
    },
    gloves = {
        dict = "mech_loco_m@character@arthur@fidgets@item_selection@gloves",
        flag = 24,
        anim = "gloves_b",
        timer = 500,
    },
    hats = {
        dict = "mech_respawn@nap_grnd",
        anim = "getup_v1_player",
        offset = 0.6,
        timer = 900,
        flag = 24,
        equip = {
            timer = 800
        }
    },
    boots = {
        dict = "script_respawn@one_shot@fullbody@generic@unarmed@stand_boot_clean@a",
        anim = "respawn_action",
        timer = 500,
    },
    neckwear = {
        dict = "mech_inventory@clothing@bandana",
        flag = 24,
        equip = {
            anim = "neck_2_satchel",
            timer = 1000
        },
        unequip = {
            anim = "satchel_2_neck",
            timer = 2000
        }
    },
    masks = {
        dict = "mech_inventory@clothing@mask",
        flag = 24,
        equip = {
            anim = "face_2_satchel",
            timer = 1000,
        },
        unequip = {
            anim = "satchel_2_face",
            timer = 2000,
        }
    },
    eyewear = {
        dict = "amb_wander@code_human_wander@male@generic",
        flag = 24,
        anim = "wipe_eyes_02",
        timer = 1000,
    }
}

Config.GroundItems = {
    default = { model = "P_COTTONBOX01X", roll = 0.0, pitch = 0.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = 0.0 }, -- DON'T TOUCH

    WEAPON_LASSO = { model = "w_melee_lasso01", roll = 0.0, pitch = 90.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = -0.32 },
    WEAPON_LASSO_REINFORCED = { model = "w_melee_lasso01", roll = 0.0, pitch = 90.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = -0.32 },

    WEAPON_PISTOL_SEMIAUTO = { model = "p_pistol_semiauto_cs01x", roll = 90.0, pitch = 0.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = 0.0 },
    WEAPON_PISTOL_MAUSER = { model = "w_pistol_mauser02", roll = 0.0, pitch = 90.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = -0.1 },

    tarnacop = { model = "p_pickaxe01x", roll = 90.0, pitch = 0.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = -0.05 },
	sticla_apa = { model = "p_bottletequilafull02x", roll = 0.0, pitch = 0.0, yaw = 0.0, offsetX = 0.0, offsetY = 0.0, offsetZ = 0.0 },
}

Config.NonSerialNumber = {
    "WEAPON_MELEE_CLEAVER",
    "WEAPON_MELEE_HATCHET",
    "WEAPON_MELEE_HATCHET_HUNTER",
    "WEAPON_MELEE_KNIFE",
    "WEAPON_KIT_BINOCULARS_IMPROVED",
    "WEAPON_KIT_BINOCULARS",
    "WEAPON_FISHINGROD",
    "WEAPON_KIT_CAMERA",
    "WEAPON_kIT_CAMERA_ADVANCED",
    "WEAPON_MELEE_LANTERN",
    "WEAPON_MELEE_DAVY_LANTERN",
    "WEAPON_MELEE_LANTERN_HALLOWEEN",
    "WEAPON_KIT_METAL_DETECTOR",
    "WEAPON_MELEE_HAMMER",
    "WEAPON_BOW",
    "WEAPON_BOW_IMPROVED",
    "WEAPON_LASSO",
    "WEAPON_LASSO_REINFORCED",
}


Config.Ammo = {
    ["AMMO_PISTOL"] = "ammopistolnormal",
    ["AMMO_PISTOL_EXPRESS"] = "ammopistolexpress",
    ["AMMO_PISTOL_EXPRESS_EXPLOSIVE"] = "ammopistolexplosive",
    ["AMMO_PISTOL_HIGH_VELOCITY"] = "ammopistolvelocity",
    ["AMMO_PISTOL_SPLIT_POINT"] = "ammopistolsplitpoint",
    
    ["AMMO_REPEATER"] = "ammorepeaternormal",
    ["AMMO_REPEATER_EXPRESS"] = "ammorepeaterexpress",
    ["AMMO_REPEATER_EXPRESS_EXPLOSIVE"] = "ammorepeaterexplosive",
    ["AMMO_REPEATER_HIGH_VELOCITY"] = "ammorepeatervelocity",
    ["AMMO_REPEATER_SPLIT_POINT"] = "ammorepeatersplitpoint",
    
    ["AMMO_REVOLVER"] = "ammorevolvernormal",
    ["AMMO_REVOLVER_EXPRESS"] = "ammorevolverexpress",
    ["AMMO_REVOLVER_EXPRESS_EXPLOSIVE"] = "ammorevolverexplosive",
    ["AMMO_REVOLVER_HIGH_VELOCITY"] = "ammorevolvervelocity",
    ["AMMO_REVOLVER_SPLIT_POINT"] = "ammorevolversplitpoint",
    
    ["AMMO_SHOTGUN"] = "ammoshotgunnormal",
    ["AMMO_SHOTGUN_BUCKSHOT_INCENDIARY"] = "ammoshotgunincendiary",
    ["AMMO_SHOTGUN_SLUG_EXPLOSIVE"] = "ammoshotgunexplosive",
    ["AMMO_SHOTGUN_SLUG"] = "ammoshotgunslug",
    
    ["AMMO_RIFLE"] = "ammoriflenormal",
    ["AMMO_RIFLE_ELEPHANT"] = "ammorifleelephant",
    ["AMMO_RIFLE_EXPRESS"] = "ammorifleexpress",
    ["AMMO_RIFLE_EXPRESS_EXPLOSIVE"] = "ammorifleexplosive",
    ["AMMO_RIFLE_HIGH_VELOCITY"] = "ammoriflevelocity",
    ["AMMO_RIFLE_SPLIT_POINT"] = "ammoriflesplitpoint",
    
    ["AMMO_22"] = "ammo22normal",
    ["AMMO_22_TRANQUILIZER"] = "ammo22tranquilizer",
    
    ["AMMO_ARROW"] = "ammoarrownormal",
    ["AMMO_ARROW_DYNAMITE"] = "ammoarrowdynamite",
    ["AMMO_ARROW_FIRE"] = "ammoarrowfire",
    ["AMMO_ARROW_IMPROVED"] = "ammoarrowimproved",
    ["AMMO_ARROW_SMALL_GAME"] = "ammoarrowsmallgame",
    ["AMMO_ARROW_POISON"] = "ammoarrowpoison",
    
    ["AMMO_THROWING_KNIVES"] = "ammothrowingknife",
    ["AMMO_TOMAHAWK"] = "ammotomahawk",
    ["AMMO_POISONBOTTLE"] = "ammopoisonbottle",
    
    ["AMMO_BOLAS"] = "ammobolas",
    ["AMMO_BOLAS_HAWKMOTH"] = "ammobolashawkmoth",
    ["AMMO_BOLAS_INTERTWINED"] = "ammobolasintertwined",
    ["AMMO_BOLAS_IRONSPIKED"] = "ammobolasironspiked",
    
    ["AMMO_DYNAMITE"] = "ammodynamite",
    ["AMMO_DYNAMITE_VOLATILE"] = "ammodynamitevolatile",
    ["AMMO_MOLOTOV"] = "ammomolotov",
    ["AMMO_MOLOTOV_VOLATILE"] = "ammomolotovvolatile",
    
    ["AMMO_HATCHET_CLEAVER"] = "ammohatchethcleaver",
    ["AMMO_HATCHET_HUNTER"] = "ammohatchethunter",
    ["AMMO_HATCHET_DOUBLE_BIT"] = "ammohatchetdoublebit",
    ["AMMO_HATCHET_HEWING"] = "ammohatchethewing",
    ["AMMO_HATCHET_VIKING"] = "ammohatchetviking",
    ["AMMO_HATCHET"] = "ammohatchet"
}

Config.MaxAmmo = {
    AMMO_PISTOL = 100,
    AMMO_PISTOL_EXPRESS = 100,
    AMMO_PISTOL_EXPRESS_EXPLOSIVE = 100,
    AMMO_PISTOL_HIGH_VELOCITY = 100,
    AMMO_PISTOL_SPLIT_POINT = 100,
    AMMO_REPEATER = 100,
    AMMO_REPEATER_EXPRESS = 100,
    AMMO_REPEATER_EXPRESS_EXPLOSIVE = 100,
    AMMO_REPEATER_HIGH_VELOCITY = 100,
    AMMO_REPEATER_SPLIT_POINT = 100,
    AMMO_REVOLVER = 100,
    AMMO_REVOLVER_EXPRESS = 100,
    AMMO_REVOLVER_EXPRESS_EXPLOSIVE = 100,
    AMMO_REVOLVER_HIGH_VELOCITY = 100,
    AMMO_REVOLVER_SPLIT_POINT = 100,
    AMMO_RIFLE = 100,
    AMMO_RIFLE_ELEPHANT = 100,
    AMMO_RIFLE_EXPRESS = 100,
    AMMO_RIFLE_EXPRESS_EXPLOSIVE = 100,
    AMMO_RIFLE_HIGH_VELOCITY = 100,
    AMMO_RIFLE_SPLIT_POINT = 100,
    AMMO_22 = 100,
    AMMO_22_TRANQUILIZER = 100,
    AMMO_SHOTGUN = 100,
    AMMO_SHOTGUN_BUCKSHOT_INCENDIARY = 100,
    AMMO_SHOTGUN_SLUG_EXPLOSIVE = 100,
    AMMO_SHOTGUN_SLUG = 100,
    AMMO_ARROW = 10,
    AMMO_ARROW_DYNAMITE = 10,
    AMMO_ARROW_FIRE = 10,
    AMMO_ARROW_IMPROVED = 10,
    AMMO_ARROW_SMALL_GAME = 10,
    AMMO_ARROW_POISON = 10,
    AMMO_THROWING_KNIVES = 10,
    AMMO_TOMAHAWK = 10,
    AMMO_POISONBOTTLE = 10,
    AMMO_BOLAS = 10,
    AMMO_BOLAS_HAWKMOTH = 10,
    AMMO_BOLAS_INTERTWINED = 10,
    AMMO_BOLAS_IRONSPIKED = 10,
    AMMO_DYNAMITE = 5,
    AMMO_DYNAMITE_VOLATILE = 5,
    AMMO_MOLOTOV = 5,
    AMMO_MOLOTOV_VOLATILE = 5,
    AMMO_HATCHET_CLEAVER = 10,
    AMMO_HATCHET_HUNTER = 10,
    AMMO_HATCHET_DOUBLE_BIT = 10,
    AMMO_HATCHET_HEWING = 10,
    AMMO_HATCHET_VIKING = 10,
    AMMO_HATCHET = 10,
}

Config.AmmoItems = {
    ["ammopistolnormal"] = {
        amount = 1,
        type = "AMMO_PISTOL",
        primary = true,
        weapons = {},
        natives = {
            0xDDC64F5E31EEDAB6, -- IsWeaponPistol
        },
    },
    ["ammopistolexpress"] = {
        amount = 1,
        type = "AMMO_PISTOL_EXPRESS",
        primary = true,
        weapons = {},
        natives = {
            0xDDC64F5E31EEDAB6, -- IsWeaponPistol
        },
    },
    ["ammopistolexplosive"] = {
        amount = 1,
        type = "AMMO_PISTOL_EXPRESS_EXPLOSIVE",
        primary = true,
        weapons = {},
        natives = {
            0xDDC64F5E31EEDAB6, -- IsWeaponPistol
        },
    },
    ["ammopistolvelocity"] = {
        amount = 1,
        type = "AMMO_PISTOL_HIGH_VELOCITY",
        primary = true,
        weapons = {},
        natives = {
            0xDDC64F5E31EEDAB6, -- IsWeaponPistol
        },
    },
    ["ammopistolsplitpoint"] = {
        amount = 1,
        type = "AMMO_PISTOL_SPLIT_POINT",
        primary = true,
        weapons = {},
        natives = {
            0xDDC64F5E31EEDAB6, -- IsWeaponPistol
        },
    },

    ["ammorepeaternormal"] = {
        amount = 1,
        type = "AMMO_REPEATER",
        primary = true,
        weapons = {},
        natives = {
            0xDDB2578E95EF7138, -- IsWeaponRepeater
        },
    },
    ["ammorepeaterexpress"] = {
        amount = 1,
        type = "AMMO_REPEATER_EXPRESS",
        primary = true,
        weapons = {},
        natives = {
            0xDDB2578E95EF7138, -- IsWeaponRepeater
        },
    },
    ["ammorepeaterexplosive"] = {
        amount = 1,
        type = "AMMO_REPEATER_EXPRESS_EXPLOSIVE",
        primary = true,
        weapons = {},
        natives = {
            0xDDB2578E95EF7138, -- IsWeaponRepeater
        },
    },
    ["ammorepeatervelocity"] = {
        amount = 1,
        type = "AMMO_REPEATER_HIGH_VELOCITY",
        primary = true,
        weapons = {},
        natives = {
            0xDDB2578E95EF7138, -- IsWeaponRepeater
        },
    },
    ["ammorepeatersplitpoint"] = {
        amount = 1,
        type = "AMMO_REPEATER_SPLIT_POINT",
        primary = true,
        weapons = {},
        natives = {
            0xDDB2578E95EF7138, -- IsWeaponRepeater
        },
    },

    ["ammorevolvernormal"] = {
        amount = 1,
        type = "AMMO_REVOLVER",
        primary = true,
        weapons = {},
        natives = {
            0xC212F1D05A8232BB, -- IsWeaponRevolver
        },
    },
    ["ammorevolverexpress"] = {
        amount = 1,
        type = "AMMO_REVOLVER_EXPRESS",
        primary = true,
        weapons = {},
        natives = {
            0xC212F1D05A8232BB, -- IsWeaponRevolver
        },
    },
    ["ammorevolverexplosive"] = {
        amount = 1,
        type = "AMMO_REVOLVER_EXPRESS_EXPLOSIVE",
        primary = true,
        weapons = {},
        natives = {
            0xC212F1D05A8232BB, -- IsWeaponRevolver
        },
    },
    ["ammorevolvervelocity"] = {
        amount = 1,
        type = "AMMO_REVOLVER_HIGH_VELOCITY",
        primary = true,
        weapons = {},
        natives = {
            0xC212F1D05A8232BB, -- IsWeaponRevolver
        },
    },
    ["ammorevolversplitpoint"] = {
        amount = 1,
        type = "AMMO_REVOLVER_SPLIT_POINT",
        primary = true,
        weapons = {},
        natives = {
            0xC212F1D05A8232BB, -- IsWeaponRevolver
        },
    },

    ["ammoshotgunnormal"] = {
        amount = 1,
        type = "AMMO_SHOTGUN",
        primary = true,
        weapons = {},
        natives = {
            0xC75386174ECE95D5, -- IsWeaponShotgun
        },
    },
    ["ammoshotgunincendiary"] = {
        amount = 1,
        type = "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY",
        primary = true,
        weapons = {},
        natives = {
            0xC75386174ECE95D5, -- IsWeaponShotgun
        },
    },
    ["ammoshotgunexplosive"] = {
        amount = 1,
        type = "AMMO_SHOTGUN_SLUG_EXPLOSIVE",
        primary = true,
        weapons = {},
        natives = {
            0xC75386174ECE95D5, -- IsWeaponShotgun
        },
    },
    ["ammoshotgunslug"] = {
        amount = 1,
        type = "AMMO_SHOTGUN_SLUG",
        primary = true,
        weapons = {},
        natives = {
            0xC75386174ECE95D5, -- IsWeaponShotgun
        },
    },


    ["ammoriflenormal"] = {
        amount = 1,
        type = "AMMO_RIFLE",
        primary = true,
        weapons = {},
        natives = {
            0x6AD66548840472E5, -- IsWeaponSniper
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },
    ["ammorifleelephant"] = {
        amount = 1,
        type = "AMMO_RIFLE_ELEPHANT",
        primary = true,
        weapons = {},
        natives = {
            0x6AD66548840472E5, -- IsWeaponSniper
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },
    ["ammorifleexpress"] = {
        amount = 1,
        type = "AMMO_RIFLE_EXPRESS",
        primary = true,
        weapons = {},
        natives = {
            0x6AD66548840472E5, -- IsWeaponSniper
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },
    ["ammorifleexplosive"] = {
        amount = 1,
        type = "AMMO_RIFLE_EXPRESS_EXPLOSIVE",
        primary = true,
        weapons = {},
        natives = {
            0x6AD66548840472E5, -- IsWeaponSniper
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },
    ["ammoriflevelocity"] = {
        amount = 1,
        type = "AMMO_RIFLE_HIGH_VELOCITY",
        primary = true,
        weapons = {},
        natives = {
            0x6AD66548840472E5, -- IsWeaponSniper
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },
    ["ammoriflesplitpoint"] = {
        amount = 1,
        type = "AMMO_RIFLE_SPLIT_POINT",
        primary = true,
        weapons = {},
        natives = {
            0x6AD66548840472E5, -- IsWeaponSniper
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },

    ["ammo22normal"] = {
        amount = 1,
        type = "AMMO_22",
        primary = true,
        weapons = {},
        natives = {
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },
    ["ammo22tranquilizer"] = {
        amount = 1,
        type = "AMMO_22_TRANQUILIZER",
        primary = true,
        weapons = {},
        natives = {
            0x0A82317B7EBFC420, -- IsWeaponRifle
        },
    },

    ["ammoarrownormal"] = {
        amount = 1,
        type = "AMMO_ARROW",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammoarrowdynamite"] = {
        amount = 1,
        type = "AMMO_ARROW_DYNAMITE",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammoarrowfire"] = {
        amount = 1,
        type = "AMMO_ARROW_FIRE",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammoarrowimproved"] = {
        amount = 1,
        type = "AMMO_ARROW_IMPROVED",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammoarrowsmallgame"] = {
        amount = 1,
        type = "AMMO_ARROW_SMALL_GAME",
        primary = true,
        weapons = {},
        natives = {},
    },

    ["ammoarrowpoison"] = {
        amount = 1,
        type = "AMMO_ARROW_POISON",
        primary = true,
        weapons = {},
        natives = {},
    },



    ["ammothrowingknife"] = {
        amount = 1,
        type = "AMMO_THROWING_KNIVES",
        primary = true,
        weapons = {"WEAPON_THROWN_THROWING_KNIVES"},
        natives = {},
    },

    ["ammotomahawk"] = {
        amount = 1,
        type = "AMMO_TOMAHAWK",
        primary = true,
        weapons = {"WEAPON_THROWN_TOMAHAWK"},
        natives = {},
    },

    ["ammopoisonbottle"] = {
        amount = 1,
        type = "AMMO_POISONBOTTLE",
        primary = true,
        weapons = {"WEAPON_THROWN_POISONBOTTLE"},
        natives = {},
    },

    ["ammohatchethcleaver"] = {
        amount = 1,
        type = "AMMO_HATCHET_CLEAVER",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammohatchethunter"] = {
        amount = 1,
        type = "AMMO_HATCHET_HUNTER",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammohatchetdoublebit"] = {
        amount = 1,
        type = "AMMO_HATCHET_DOUBLE_BIT",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammohatchethewing"] = {
        amount = 1,
        type = "AMMO_HATCHET_HEWING",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammohatchetviking"] = {
        amount = 1,
        type = "AMMO_HATCHET_VIKING",
        primary = true,
        weapons = {},
        natives = {},
    },

    ["ammohatchet"] = {
        amount = 1,
        type = "AMMO_HATCHET",
        primary = true,
        weapons = {},
        natives = {},
    },

    ["ammodynamite"] = {
        amount = 1,
        type = "AMMO_DYNAMITE",
        primary = true,
        weapons = {},
        natives = {},
    },
    
    ["ammodynamitevolatile"] = {
        amount = 1,
        type = "AMMO_DYNAMITE_VOLATILE",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammomolotov"] = {
        amount = 1,
        type = "AMMO_MOLOTOV",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammomolotovvolatile"] = {
        amount = 1,
        type = "AMMO_MOLOTOV_VOLATILE",
        primary = true,
        weapons = {},
        natives = {},
    },

    ["ammobolas"] = {
        amount = 1,
        type = "AMMO_BOLAS",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammobolashawkmoth"] = {
        amount = 1,
        type = "AMMO_BOLAS_HAWKMOTH",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammobolasintertwined"] = {
        amount = 1,
        type = "AMMO_BOLAS_INTERTWINED",
        primary = true,
        weapons = {},
        natives = {},
    },
    ["ammobolasironspiked"] = {
        amount = 1,
        type = "AMMO_BOLAS_IRONSPIKED",
        primary = true,
        weapons = {},
        natives = {},
    },
    
}

Config.WeaponAmmoGroups = {
    ['WEAPON_THROWN_TOMAHAWK'] = {"AMMO_TOMAHAWK"},
    ['WEAPON_THROWN_TOMAHAWK_ANCIENT'] = {"AMMO_TOMAHAWK"},
    ['WEAPON_THROWN_THROWING_KNIVES'] = {"AMMO_THROWING_KNIVES"},
    ['WEAPON_THROWN_POISONBOTTLE'] = {"AMMO_POISONBOTTLE"},
    ['WEAPON_THROWN_DYNAMITE'] = {"AMMO_DYNAMITE", "AMMO_DYNAMITE_VOLATILE"},
    ['WEAPON_THROWN_MOLOTOV'] = {"AMMO_MOLOTOV", "AMMO_MOLOTOV_VOLATILE"},
    ['WEAPON_THROWN_BOLAS'] = {"AMMO_BOLAS"},
    ['WEAPON_THROWN_BOLAS_HAWKMOTH'] = {"AMMO_BOLAS_HAWKMOTH"},
    ['WEAPON_THROWN_BOLAS_IRONSPIKED'] = {"AMMO_BOLAS_IRONSPIKED"},
    ['WEAPON_THROWN_BOLAS_INTERTWINED'] = {"AMMO_BOLAS_INTERTWINED"},
    ['WEAPON_MELEE_CLEAVER'] = {"AMMO_HATCHET_CLEAVER"},
    
    ['WEAPON_BOW'] = {"AMMO_ARROW", "AMMO_ARROW_DYNAMITE", "AMMO_ARROW_FIRE", "AMMO_ARROW_IMPROVED", "AMMO_ARROW_SMALL_GAME", "AMMO_ARROW_POISON"},
    ['WEAPON_BOW_IMPROVED'] = {"AMMO_ARROW", "AMMO_ARROW_DYNAMITE", "AMMO_ARROW_FIRE", "AMMO_ARROW_IMPROVED", "AMMO_ARROW_SMALL_GAME", "AMMO_ARROW_POISON"},
    
    ['WEAPON_PISTOL_SEMIAUTO'] = {"AMMO_PISTOL", "AMMO_PISTOL_EXPRESS", "AMMO_PISTOL_EXPRESS_EXPLOSIVE", "AMMO_PISTOL_HIGH_VELOCITY", "AMMO_PISTOL_SPLIT_POINT"},
    ['WEAPON_PISTOL_MAUSER'] = {"AMMO_PISTOL", "AMMO_PISTOL_EXPRESS", "AMMO_PISTOL_EXPRESS_EXPLOSIVE", "AMMO_PISTOL_HIGH_VELOCITY", "AMMO_PISTOL_SPLIT_POINT"},
    ['WEAPON_PISTOL_VOLCANIC'] = {"AMMO_PISTOL", "AMMO_PISTOL_EXPRESS", "AMMO_PISTOL_EXPRESS_EXPLOSIVE", "AMMO_PISTOL_HIGH_VELOCITY", "AMMO_PISTOL_SPLIT_POINT"},
    ['WEAPON_PISTOL_M1899'] = {"AMMO_PISTOL", "AMMO_PISTOL_EXPRESS", "AMMO_PISTOL_EXPRESS_EXPLOSIVE", "AMMO_PISTOL_HIGH_VELOCITY", "AMMO_PISTOL_SPLIT_POINT"},

    ['WEAPON_REVOLVER_SCHOFIELD'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_NAVY'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_NAVY_CROSSOVER'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_LEMAT'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_DOUBLEACTION'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_CATTLEMAN'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_CATTLEMAN_MEXICAN'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},
    ['WEAPON_REVOLVER_DOUBLEACTION_GAMBLER'] = {"AMMO_REVOLVER", "AMMO_REVOLVER_EXPRESS", "AMMO_REVOLVER_EXPRESS_EXPLOSIVE", "AMMO_REVOLVER_HIGH_VELOCITY", "AMMO_REVOLVER_SPLIT_POINT"},

    ['WEAPON_RIFLE_VARMINT'] = {"AMMO_22", "AMMO_22_TRANQUILIZER"},
    ['WEAPON_RIFLE_BOLTACTION'] = {"AMMO_RIFLE", "AMMO_RIFLE_EXPRESS", "AMMO_RIFLE_EXPRESS_EXPLOSIVE", "AMMO_RIFLE_HIGH_VELOCITY", "AMMO_RIFLE_SPLIT_POINT"},
    ['WEAPON_RIFLE_SPRINGFIELD'] = {"AMMO_RIFLE", "AMMO_RIFLE_EXPRESS", "AMMO_RIFLE_EXPRESS_EXPLOSIVE", "AMMO_RIFLE_HIGH_VELOCITY", "AMMO_RIFLE_SPLIT_POINT"},
    ['WEAPON_RIFLE_ELEPHANT'] = {"AMMO_RIFLE_ELEPHANT"},

    ['WEAPON_REPEATER_WINCHESTER'] = {"AMMO_REPEATER", "AMMO_REPEATER_EXPRESS", "AMMO_REPEATER_EXPRESS_EXPLOSIVE", "AMMO_REPEATER_HIGH_VELOCITY", "AMMO_REPEATER_SPLIT_POINT"},
    ['WEAPON_REPEATER_HENRY'] = {"AMMO_REPEATER", "AMMO_REPEATER_EXPRESS", "AMMO_REPEATER_EXPRESS_EXPLOSIVE", "AMMO_REPEATER_HIGH_VELOCITY", "AMMO_REPEATER_SPLIT_POINT"},
    ['WEAPON_REPEATER_EVANS'] = {"AMMO_REPEATER", "AMMO_REPEATER_EXPRESS", "AMMO_REPEATER_EXPRESS_EXPLOSIVE", "AMMO_REPEATER_HIGH_VELOCITY", "AMMO_REPEATER_SPLIT_POINT"},
    ['WEAPON_REPEATER_CARBINE'] = {"AMMO_REPEATER", "AMMO_REPEATER_EXPRESS", "AMMO_REPEATER_EXPRESS_EXPLOSIVE", "AMMO_REPEATER_HIGH_VELOCITY", "AMMO_REPEATER_SPLIT_POINT"},

    ['WEAPON_SNIPERRIFLE_ROLLINGBLOCK'] = {"AMMO_RIFLE", "AMMO_RIFLE_EXPRESS", "AMMO_RIFLE_EXPRESS_EXPLOSIVE", "AMMO_RIFLE_HIGH_VELOCITY", "AMMO_RIFLE_SPLIT_POINT"},
    ['WEAPON_SNIPERRIFLE_CARCANO'] = {"AMMO_RIFLE", "AMMO_RIFLE_EXPRESS", "AMMO_RIFLE_EXPRESS_EXPLOSIVE", "AMMO_RIFLE_HIGH_VELOCITY", "AMMO_RIFLE_SPLIT_POINT"},

    ['WEAPON_SHOTGUN_SEMIAUTO'] = {"AMMO_SHOTGUN ", "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY", "AMMO_SHOTGUN_SLUG_EXPLOSIVE", "AMMO_SHOTGUN_SLUG"},
    ['WEAPON_SHOTGUN_SAWEDOFF'] = {"AMMO_SHOTGUN ", "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY", "AMMO_SHOTGUN_SLUG_EXPLOSIVE", "AMMO_SHOTGUN_SLUG"},
    ['WEAPON_SHOTGUN_REPEATING'] = {"AMMO_SHOTGUN ", "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY", "AMMO_SHOTGUN_SLUG_EXPLOSIVE", "AMMO_SHOTGUN_SLUG"},
    ['WEAPON_SHOTGUN_DOUBLEBARREL_EXOTIC'] = {"AMMO_SHOTGUN ", "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY", "AMMO_SHOTGUN_SLUG_EXPLOSIVE", "AMMO_SHOTGUN_SLUG"},
    ['WEAPON_SHOTGUN_PUMP'] = {"AMMO_SHOTGUN ", "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY", "AMMO_SHOTGUN_SLUG_EXPLOSIVE", "AMMO_SHOTGUN_SLUG"},
    ['WEAPON_SHOTGUN_DOUBLEBARREL'] = {"AMMO_SHOTGUN ", "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY", "AMMO_SHOTGUN_SLUG_EXPLOSIVE", "AMMO_SHOTGUN_SLUG"},
}


Config.AmmoTypes = {
    [416676503] = {
        "AMMO_PISTOL",
        "AMMO_PISTOL_EXPRESS",
        "AMMO_PISTOL_EXPRESS_EXPLOSIVE",
        "AMMO_PISTOL_HIGH_VELOCITY",
        "AMMO_PISTOL_SPLIT_POINT"
    },
    [-594562071] = {
        "AMMO_REPEATER",
        "AMMO_REPEATER_EXPRESS",
        "AMMO_REPEATER_EXPRESS_EXPLOSIVE",
        "AMMO_REPEATER_HIGH_VELOCITY",
        "AMMO_REPEATER_SPLIT_POINT"
    },
    [-1101297303] = {
        "AMMO_REVOLVER",
        "AMMO_REVOLVER_EXPRESS",
        "AMMO_REVOLVER_EXPRESS_EXPLOSIVE",
        "AMMO_REVOLVER_HIGH_VELOCITY",
        "AMMO_REVOLVER_SPLIT_POINT",
        "AMMO_SHOTGUN",
        "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY",
        "AMMO_SHOTGUN_SLUG_EXPLOSIVE",
        "AMMO_SHOTGUN_SLUG"
    },
    [970310034] = { 
        "AMMO_RIFLE",
        "AMMO_RIFLE_ELEPHANT",
        "AMMO_RIFLE_EXPRESS",
        "AMMO_RIFLE_EXPRESS_EXPLOSIVE",
        "AMMO_RIFLE_HIGH_VELOCITY",
        "AMMO_RIFLE_SPLIT_POINT",
        "AMMO_22", 
        "AMMO_22_TRANQUILIZER"
    },
    [-1212426201] = { "AMMO_RIFLE",
        "AMMO_RIFLE_EXPRESS",
        "AMMO_RIFLE_EXPRESS_EXPLOSIVE",
        "AMMO_RIFLE_HIGH_VELOCITY",
        "AMMO_RIFLE_SPLIT_POINT"
    },
    [860033945] = { "AMMO_SHOTGUN",
        "AMMO_SHOTGUN_BUCKSHOT_INCENDIARY",
        "AMMO_SHOTGUN_SLUG_EXPLOSIVE",
        "AMMO_SHOTGUN_SLUG"
    },
    [-1241684019] = { 
        "AMMO_ARROW",
        "AMMO_ARROW_DYNAMITE",
        "AMMO_ARROW_FIRE",
        "AMMO_ARROW_IMPROVED",
        "AMMO_ARROW_SMALL_GAME",
        "AMMO_ARROW_POISON"
    },
    [1548507267] = {
        "AMMO_THROWING_KNIVES",
        "AMMO_TOMAHAWK",
        "AMMO_POISONBOTTLE",
        "AMMO_BOLAS",
        "AMMO_BOLAS_HAWKMOTH",
        "AMMO_BOLAS_INTERTWINED",
        "AMMO_BOLAS_IRONSPIKED",
        "AMMO_DYNAMITE",
        "AMMO_DYNAMITE_VOLATILE",
        "AMMO_MOLOTOV",
        "AMMO_MOLOTOV_VOLATILE"
    },
    [-1188697038] = {
        "AMMO_HATCHET_CLEAVER",

    },
    [446901936] = {
        "AMMO_HATCHET_HUNTER",
        "AMMO_HATCHET_DOUBLE_BIT",
        "AMMO_HATCHET_HEWING",
        "AMMO_HATCHET_VIKING",
        "AMMO_HATCHET",
    }
}


Config.AmountInput = {
    title = "Enter amount.",
    form = {
        {
            label = "Amount",
            id = "amount",
            type = "float",
        },

    }
}

Config.StorePriceInput = {
    title = "Item price.",
    form = {
        {
            label = "Price",
            id = "price",
            type = "number",
        },

    }
}

Config.UseAmmoInput = {
    title = "Cate gloante doresti sa despachetezi?",
    form = {
        {
            label = "Gloante",
            id = "ammo",
            type = "number",
            
        },

    }
}

Config.HotBar = {
    [0] = {
        key = 0xE6F612E4,
        allowItem = true,
        allowWeapon = true,
    },
    [1] = {
        key = 0x1CE6D9EB,
    },
    [2] = {
        key = 0x4F49CC4C,
    },
    [3] = {
        key = 0x8F9F9E58,
    },
    [4] = {
        key = 0xAB62E997,
    },
    [5] = {
        key = 0xA1FDE2A6,
    },
    [6] = {
        key = 0xB03A913B,
    },

}


Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = '', -- Default webhook for all deposits

    dropItem = {
        sensitive = '', -- True or a specific webbook
        nonSensitive = true,
    },

    pickupItem = {
        sensitive = '',
        nonSensitive = true,
    },

    giveMoney = {
        sensitive = '',
        nonSensitive = true,
    },

    giveGold = {
        sensitive = '',
        nonSensitive = true,
    },

    giveItem = {
        sensitive = '',
        nonSensitive = true,
    },

    moveCustomItem = {
        sensitive = '',
        nonSensitive = true,
    },

    takeCustomItem = {
        sensitive = '',
        nonSensitive = true,
    },

    searchPlayer = {
        sensitive = '',
        nonSensitive = true,
    },

    stealItem = {
        sensitive = '',
        nonSensitive = true,
    },

    
 
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['target_not_enough_space'] = 'The player does not have enough space to receive this item!',
        ['not_allowed'] = 'You are not allowed to do that!',
        ['not_valid_amount'] = 'You have entered an invalid amount! It cannot be below 0.',
        ['received_item'] = 'You received %s x%s',
        ['gave_item'] = 'You gave %s x%s',
        ['received_money'] = 'You received $%s',
        ['gave_money'] = 'You gave $%s',
        ['item_blacklisted'] = 'This item is blacklisted!',
        ['not_enough_money'] = 'You do not have enough money!',
        ['not_enough_items'] = 'You do not have enough items to do this!',
        ['cooldown_active'] = 'You must wait %s seconds to do this.',
        ['inventory_weapon_not_allowed'] = 'You cannot place weapons in this inventory!',
        ['inventory_not_enough_space'] = 'This inventory does not have enough space!',
        ['not_enough_space'] = 'You do not have enough space in your inventory to do this!',
        ['wrong_ammo'] = 'You do not have a weapon equipped that uses this type of ammo!',
        ['used_ammo'] = 'You unpacked x%s %s.',
        ['target_not_online'] = 'The player is not online!',
        ['inventory_already_used'] = 'This inventory is already in use!',
        ['stole_max_items'] = 'You cannot take more items from this player!',
        ['inventory_item_not_allowed'] = 'You cannot move this item!',
        ['ground_inventory'] = 'Ground',
        ['sell_for'] = 'You can sell for: $%s',
        ['not_enough_gold'] = 'You do not have enough gold!',
        ['received_gold'] = 'You received %s gold',
        ['gave_gold'] = 'You gave %s gold',
        

        -- Webhooks
        ['webhook_user_information'] = 'Player Info',
        ['webhook_target_information'] = 'Target Info',
        ['webhook_give_money_source'] = 'Sender',
        ['webhook_give_money_target'] = 'Receiver',
        ['webhook_give_money_amount'] = 'Amount',
        ['webhook_giveMoney'] = 'Money Transfer',
        ['webhook_giveMoney_info'] = '%s has transferred $%s to %s.',

        ['webhook_giveItem'] = 'Item Transfer',
        ['webhook_item_label'] = 'Item Label',
        ['webhook_item_item'] = 'Item Name',
        ['webhook_item_quantity'] = 'Quantity',
        ['webhook_item_last_id'] = 'Last Item ID',
        ['webhook_item_new_id'] = 'New Item ID',
        ['webhook_giveItem_info'] = '%s has given %s x%s to %s.',

        ['webhook_dropItem'] = 'Item Dropped',
        ['webhook_dropItem_info'] = '%s has dropped %s x%s.',

        ['webhook_giveGold'] = 'Gold Transfer',
        ['webhook_giveGold_info'] = '%s has transferred %s gold to %s.',
        ['webhook_gold_amount'] = 'Amount',
        ['webhook_gold_source'] = 'Sender',
        ['webhook_gold_target'] = 'Receiver',



        ['webhook_pickupItem'] = 'Item Picked Up',
        ['webhook_pickupItem_info'] = '%s has picked up %s x%s.',

        ['webhook_moveCustomItem'] = 'Custom Inventory Transfer',
        ['webhook_custom_inventory_id'] = 'Custom Inventory ID',
        ['webhook_moveCustomItem_info'] = '%s has moved %s x%s to custom inventory ID %s.',

        ['webhook_takeCustomItem'] = 'Custom Inventory Transfer',
        ['webhook_takeCustomItem_info'] = '%s has taken %s x%s from the custom inventory ID %s.',

        ['webhook_searching_player'] = "Searching Player",
        ['webhook_searched_target'] = "Searched Target",
        ['webhook_search_limit'] = "Search Limit",
        ['webhook_searchPlayer'] = "Searching Player",
        ['webhook_searchPlayer_info'] = "%s is searching %s.",


        ['webhook_stealItem'] = 'Item Theft',
        ['webhook_stealItem_info'] = '%s has stolen %s x%s from %s.',
        ['too_fast'] = 'You are doing this too fast! Slow down!',
        ['item_broken'] = 'This item is broken and cannot be used!',
        ['ammo_full'] = 'You already have the maximum amount of this ammo!',
        ['crafted_item'] = 'You have crafted %s x%s.',
        ['not_enough_ingredients'] = 'You do not have enough ingredients to craft this item!',
        ['not_usable'] = 'This item is not usable or you do not have the xp necessary!',
        ['item_not_removable'] = 'This item cannot be removed!',
        ['item_price'] = 'Price: <span style="color:green">%s</span>',
        ['not_enough_stock'] = 'There is not enough stock of this item!',
        ['bought_item'] = 'You bought: %s %s for $%s', 
        ['cannot_sell'] = 'You cannot sell this item to this store.',
        ['store_max_stock'] = 'This store has reached the maximum stock for this item!',
        ['sold_item'] = 'You sold: %s %s for $%s',
        ['not_allowed_in_slot'] = 'This type of item is not allowed in this slot.',
        ['wrong_arguments'] = 'You have entered incorrect arguments!',
        ['item_not_found'] = 'Item not found!',
        ['not_valid_quantity'] = 'You have entered an invalid quantity! It must be greater than 0.',
        ['loading_inventory'] = 'The inventory script is still loading, wait a few seconds before opening it!',
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
