# config.lua

```lua
Config = {

StartAfter = 15000, 

ServerYear = 1800, -- YEAR OF THE SERVER

Debug = true,

Controls = {
    AddLocation = 0x8AAA0AD4,
    RemoveLocation = 0x4AF4D473,
    Confirm = 0x760A9C6F,
},

Offset = {
    minZ = 0.0,
    maxZ = 0.0,
},

PlayerSelect = {
    useNames = true, -- Use player names in the player selector
},

AdminSystem = {
    useDefault = true, -- Use the default admin system
    useIdentifierGroup = false, -- Use the admin group system
    useAce = false, -- Use the ace group system
},

IdentifierGroups = {
    ['owner'] = {
        "discord:495601526493020180" -- identifier
    },

},

AceGroups = {
    ['owner'] = {
        'poscore.owner',
    },
    ['admin'] = {
        'poscore.admin',
    }
},



CustomWaypoint = {
    isEnabled = true, 
    defaultStatus = false, -- false = disabled, true = enabled

    defaultBlip = {
        icon = "blip_deadeye_cross", 
        colorRGB = {232, 16, 5}  
    },

    displaySettings = {  
        size = {0.02, 0.035}, 
        text = {
            scale = 0.25,
            colorRGBA = {255, 255, 255, 255}, 
            font = 4,
            offset = 0.025
        },
        visibility = {
            minDistance = 2.0,
            heightOffset = 0.0
        }
    },

    commands = {
        toggleWaypoint = "togglewaypoint"  
    }
},


AdminAce = 'poscore.admin',

WebhookAvatar = '',

CancelCommand = 'cancelRoute',

--Vorp WEAPONS
Weapons = {
    -- Unarmed & Utility
    {item = "WEAPON_UNARMED", label = "Unarmed"},
    {item = "WEAPON_KIT_CAMERA", label = "Camera"},
    {item = "WEAPON_KIT_CAMERA_ADVANCED", label = "Advanced Camera"},
    {item = "WEAPON_KIT_BINOCULARS", label = "Binoculars"},
    {item = "WEAPON_KIT_BINOCULARS_IMPROVED", label = "Improved Binoculars"},
    {item = "WEAPON_KIT_METAL_DETECTOR", label = "Metal Detector"},
    {item = "WEAPON_FISHINGROD", label = "Fishing Rod"},

    -- Lassos & Bolas
    {item = "WEAPON_LASSO", label = "Lasso"},
    {item = "WEAPON_LASSO_REINFORCED", label = "Reinforced Lasso"},
    {item = "WEAPON_THROWN_BOLAS", label = "Bolas"},
    {item = "WEAPON_THROWN_BOLAS_HAWKMOTH", label = "Bolas Hawkmoth"},
    {item = "WEAPON_THROWN_BOLAS_IRONSPIKED", label = "Bolas Ironspiked"},
    {item = "WEAPON_THROWN_BOLAS_INTERTWINED", label = "Bolas Intertwined"},

    -- Knives & Melee
    {item = "WEAPON_MELEE_KNIFE", label = "Knife"},
    {item = "WEAPON_MELEE_KNIFE_RUSTIC", label = "Rustic Knife"},
    {item = "WEAPON_MELEE_KNIFE_HORROR", label = "Horror Knife"},
    {item = "WEAPON_MELEE_KNIFE_CIVIL_WAR", label = "Civil War Knife"},
    {item = "WEAPON_MELEE_KNIFE_JAWBONE", label = "Jawbone Knife"},
    {item = "WEAPON_MELEE_KNIFE_MINER", label = "Miner's Knife"},
    {item = "WEAPON_MELEE_KNIFE_VAMPIRE", label = "Vampire Knife"},
    {item = "WEAPON_MELEE_KNIFE_TRADER", label = "Trader Knife"},
    {item = "WEAPON_MELEE_CLEAVER", label = "Cleaver"},
    {item = "WEAPON_MELEE_HAMMER", label = "Hammer"},
    {item = "WEAPON_MELEE_MACHETE", label = "Machete"},
    {item = "WEAPON_MELEE_MACHETE_COLLECTOR", label = "Collector Machete"},
    {item = "WEAPON_MACHETE_HORROR", label = "Horror Machete"},
    {item = "WEAPON_MELEE_TORCH", label = "Torch"},

    -- Hatchets
    {item = "WEAPON_MELEE_HATCHET", label = "Hatchet"},
    {item = "WEAPON_MELEE_HATCHET_DOUBLE_BIT", label = "Double Bit Hatchet"},
    {item = "WEAPON_MELEE_HATCHET_HEWING", label = "Hewing Hatchet"},
    {item = "WEAPON_MELEE_HATCHET_HUNTER", label = "Hunter Hatchet"},
    {item = "WEAPON_MELEE_HATCHET_VIKING", label = "Viking Hatchet"},

    -- Throwables
    {item = "WEAPON_THROWN_TOMAHAWK", label = "Tomahawk"},
    {item = "WEAPON_THROWN_TOMAHAWK_ANCIENT", label = "Ancient Tomahawk"},
    {item = "WEAPON_THROWN_THROWING_KNIVES", label = "Throwing Knives"},
    {item = "WEAPON_THROWN_DYNAMITE", label = "Dynamite"},
    {item = "WEAPON_THROWN_MOLOTOV", label = "Molotov"},
    {item = "WEAPON_THROWN_POISONBOTTLE", label = "Poison Bottle"},
    {item = "WEAPON_MOONSHINEJUG_MP", label = "Moonshine Jug"},

    -- Bows
    {item = "WEAPON_BOW", label = "Bow"},
    {item = "WEAPON_BOW_IMPROVED", label = "Improved Bow"},

    -- Pistols
    {item = "WEAPON_PISTOL_VOLCANIC", label = "Volcanic Pistol"},
    {item = "WEAPON_PISTOL_MAUSER", label = "Mauser Pistol"},
    {item = "WEAPON_PISTOL_SEMIAUTO", label = "Semi-Auto Pistol"},
    {item = "WEAPON_PISTOL_M1899", label = "M1899 Pistol"},

    -- Revolvers
    {item = "WEAPON_REVOLVER_CATTLEMAN", label = "Cattleman Revolver"},
    {item = "WEAPON_REVOLVER_CATTLEMAN_MEXICAN", label = "Mexican Cattleman Revolver"},
    {item = "WEAPON_REVOLVER_DOUBLEACTION", label = "Double Action Revolver"},
    {item = "WEAPON_REVOLVER_SCHOFIELD", label = "Schofield Revolver"},
    {item = "WEAPON_REVOLVER_LEMAT", label = "LeMat Revolver"},
    {item = "WEAPON_REVOLVER_NAVY", label = "Navy Revolver"},
    {item = "WEAPON_REVOLVER_NAVY_CROSSOVER", label = "Navy Crossover Revolver"},

    -- Repeaters
    {item = "WEAPON_REPEATER_CARBINE", label = "Carbine Repeater"},
    {item = "WEAPON_REPEATER_HENRY", label = "Henry Repeater"},
    {item = "WEAPON_REPEATER_EVANS", label = "Evans Repeater"},
    {item = "WEAPON_REPEATER_WINCHESTER", label = "Winchester Repeater"},

    -- Rifles
    {item = "WEAPON_RIFLE_VARMINT", label = "Varmint Rifle"},
    {item = "WEAPON_RIFLE_SPRINGFIELD", label = "Springfield Rifle"},
    {item = "WEAPON_RIFLE_BOLTACTION", label = "Bolt Action Rifle"},
    {item = "WEAPON_RIFLE_ELEPHANT", label = "Elephant Rifle"},

    -- Snipers
    {item = "WEAPON_SNIPERRIFLE_ROLLINGBLOCK", label = "Rolling Block Rifle"},
    {item = "WEAPON_SNIPERRIFLE_CARCANO", label = "Carcano Rifle"},

    -- Shotguns
    {item = "WEAPON_SHOTGUN_DOUBLEBARREL", label = "Double Barrel Shotgun"},
    {item = "WEAPON_SHOTGUN_DOUBLEBARREL_EXOTIC", label = "Exotic Double Barrel Shotgun"},
    {item = "WEAPON_SHOTGUN_SAWEDOFF", label = "Sawed-Off Shotgun"},
    {item = "WEAPON_SHOTGUN_SEMIAUTO", label = "Semi-Auto Shotgun"},
    {item = "WEAPON_SHOTGUN_REPEATING", label = "Repeating Shotgun"},
    {item = "WEAPON_SHOTGUN_PUMP", label = "Pump Shotgun"},

    -- Lanterns
    {item = "WEAPON_MELEE_LANTERN", label = "Lantern"},
    {item = "WEAPON_MELEE_DAVY_LANTERN", label = "Davy Lantern"},
    {item = "WEAPON_MELEE_LANTERN_HALLOWEEN", label = "Halloween Lantern"},
    {item = "WEAPON_MELEE_LANTERN_HALOWEEN", label = "Halloween Lantern (Alt)"},
    {item = "WEAPON_MELEE_LANTERN_ELECTRIC", label = "Electric Lantern"}
},

Wagons = {
    {model = "cart01", label = "Cart 1"},
    {model = "cart02", label = "Cart 2"},
    {model = "cart03", label = "Cart 3"},
    {model = "cart04", label = "Cart 4"},
    {model = "cart05", label = "Cart 5"},
    {model = "cart06", label = "Cart 6"},
    {model = "cart07", label = "Cart 7"},
    {model = "cart08", label = "Cart 8"},
    {model = "buggy01", label = "Buggy 1"},
    {model = "buggy02", label = "Buggy 2"},
    {model = "buggy03", label = "Buggy 3"},
    {model = "handcart", label = "Handcart"},

    -- Wagons
    {model = "armysupplywagon", label = "Army Supply Wagon"},
    {model = "coal_wagon", label = "Coal Wagon"},
    {model = "logwagon", label = "Log Wagon"},
    {model = "supplywagon", label = "Supply Wagon 1"},
    {model = "supplywagon2", label = "Supply Wagon 2"},
    {model = "utilliwag", label = "Utility Wagon"},
    {model = "wagon02x", label = "Wagon 2"},
    {model = "wagon03x", label = "Wagon 3"},
    {model = "wagon04x", label = "Wagon 4"},
    {model = "wagon05x", label = "Wagon 5"},
    {model = "wagon06x", label = "Wagon 6"},
    {model = "wagonprison01x", label = "Prison Wagon"},
    {model = "wagondairy01x", label = "Dairy Wagon"},
    {model = "wagonwork01x", label = "Work Wagon"},
    {model = "wagontraveller01x", label = "Traveller Wagon"},
    {model = "wagoncircus01x", label = "Circus Wagon 1"},
    {model = "wagoncircus02x", label = "Circus Wagon 2"},

    -- Coaches
    {model = "coach2", label = "Coach 2"},
    {model = "coach3", label = "Coach 3"},
    {model = "coach4", label = "Coach 4"},
    {model = "coach5", label = "Coach 5"},
    {model = "coach6", label = "Coach 6"},
    {model = "chuckwagon000x", label = "Chuck Wagon 1"},
    {model = "chuckwagon002x", label = "Chuck Wagon 2"},
    {model = "stagecoach001x", label = "Stagecoach 1"},
    {model = "stagecoach002x", label = "Stagecoach 2"},
    {model = "stagecoach003x", label = "Stagecoach 3"},
    {model = "stagecoach004x", label = "Stagecoach 4"},
    {model = "stagecoach005x", label = "Stagecoach 5"},
    {model = "stagecoach006x", label = "Stagecoach 6"},

    -- Police & Specialty
    {model = "policewagon01x", label = "Police Wagon"},
    {model = "oilwagon01x", label = "Oil Wagon 1"},
    {model = "oilwagon02x", label = "Oil Wagon 2"},
    {model = "gatchuck", label = "Gat Chuck"},
    {model = "gatchuck_2", label = "Gat Chuck 2"},

    -- Boats & Watercraft
    {model = "canoe", label = "Canoe"},
    {model = "canoetreetrunk", label = "Tree Trunk Canoe"},
    {model = "pirogue", label = "Pirogue"},
    {model = "rcboat", label = "RC Boat"},
    {model = "rowboat", label = "Rowboat"},
    {model = "rowboatswamp", label = "Swamp Rowboat"},
    {model = "skiff", label = "Skiff"},
    {model = "keelboat", label = "Keelboat"},
    {model = "ship_guama02", label = "Guama Ship"},
    {model = "ship_nbdguama", label = "NBD Guama Ship"},
    {model = "horseboat", label = "Horse Boat"},
    {model = "turbineboat", label = "Turbine Boat"},

    -- Trains & Railcars (Private/North)
    {model = "caboose01x", label = "Caboose"},
    {model = "northpassenger01x", label = "North Passenger"},
    {model = "northpassenger03x", label = "North Passenger 3"},
    {model = "northsteamer01x", label = "North Steamer"},
    {model = "northcoalcar01x", label = "North Coal Car"},
    {model = "northflatcar01x", label = "North Flat Car"},
    {model = "privatecoalcar01x", label = "Private Coal Car"},
    {model = "privatedining01x", label = "Private Dining Car"},
    {model = "privateflatcar01x", label = "Private Flat Car"},
    {model = "privateboxcar01x", label = "Private Box Car 1"},
    {model = "privateboxcar02x", label = "Private Box Car 2"},
    {model = "privateboxcar04x", label = "Private Box Car 4"},
    {model = "privatebaggage01x", label = "Private Baggage Car"},
    {model = "privatepassenger01x", label = "Private Passenger Car"},
    {model = "privateobservationcar", label = "Private Observation Car"},
    {model = "privatearmoured", label = "Private Armoured Car"},
    {model = "privateopensleeper02x", label = "Private Open Sleeper"},
    {model = "privatesteamer01x", label = "Private Steamer"},
    {model = "armoredcar03x", label = "Armored Car"},
    {model = "wintersteamer", label = "Winter Steamer"},
    {model = "wintercoalcar", label = "Winter Coal Car"},

    -- Cannons & Heavy Weapons
    {model = "breach_cannon", label = "Breach Cannon"},
    {model = "hotchkiss_cannon", label = "Hotchkiss Cannon"},
    {model = "gatling_gun", label = "Gatling Gun"},
    {model = "gatlingmaxim02", label = "Gatling Maxim"},

    -- Other
    {model = "hotaairballoon01", label = "Hot Air Balloon"},
    {model = "smuggler02", label = "Smuggler"}
}






}




Config.SkinCategory = {
    vorp = {
      components = {
        Accessories = "accessories",
        armor = "armor",
        Badge = "badges",
        Beard = "beards_complete",
        Belt = "belts",
        Boots = "boots",
        bow = "hair_accessories",
        Bracelet = "jewelry_bracelets",
        Buckle = "belt_buckles",
        Chap = "chaps",
        Cloak = "cloaks",
        Coat = "coats",
        CoatClosed = "coats_closed",
        Dress = "dresses",
        EyeWear = "eyewear",
        Gauntlets = "gauntlets",
        Glove = "gloves",
        Gunbelt = "gunbelts",
        GunbeltAccs = "gunbelt_accs",
        Hair = "hair",
        Hat = "hats",
        Holster = "holsters_left",
        Loadouts = "loadouts",
        Mask = "masks",
        NeckTies = "neckties",
        NeckWear = "neckwear",
        Pant = "pants",
        Poncho = "ponchos",
        RingLh = "jewelry_rings_left",
        RingRh = "jewelry_rings_right",
        Satchels = "satchels",
        Shirt = "shirts_full",
        Skirt = "skirts",
        Spats = "spats",
        Spurs = "boot_accessories",
        Suspender = "suspenders",
        Teeth = "teeth",
        Vest = "vests",
      },
      overlays = {
        acne = "acne",
        ageing = "ageing",
        beardstabble = "beard",
        blush = "blush",
        complex = "complex",
        disc = "disc",
        eyebrows = "eyebrow",
        eyeliner = "eyeliner",
        eyeliners = "eyeliner",
        foundation_ = "foundation",
        freckles = "freckles",
        grime = "grime",
        hair = "hair",
        lipsticks = "lipstick",
        moles = "moles",
        paintedmasks = "masks",
        scars = "scar",
        shadows = "eyeshadow",
        spots = "spots",
      },
    },
  }




Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS


Config.Text = {
    EN = {
        ['confirm'] = 'Confirm',
        ['add_location'] = 'Add location',
        ['remove_location'] = 'Remove location',
        ['add_locations'] = 'Add locations. (#%s)',
        ['route_set'] = 'Route has been set!',
        ['route_removed'] = 'Route has been removed!',
        ['waypoint_disabled'] = 'Waypoint has been disabled!',
        ['waypoint_enabled'] = 'Waypoint has been enabled!',

        -- Town Names (all lowercase keys)
        ['aguasdulcesfarm'] = 'Aguasdulces Farm',
        ['aguasdulcesruins'] = 'Aguasdulces Ruins',
        ['aguasdulcesvilla'] = 'Aguasdulces Villa',
        ['annesburg'] = 'Annesburg',
        ['armadillo'] = 'Armadillo',
        ['beechershope'] = 'Beecher\'s Hope',
        ['blackwater'] = 'Blackwater',
        ['braithwaite'] = 'Braithwaite Manor',
        ['butcher'] = 'Butcher Creek',
        ['caliga'] = 'Caliga Hall',
        ['cornwall'] = 'Cornwall',
        ['emerald'] = 'Emerald Ranch',
        ['lagras'] = 'Lagras',
        ['manicato'] = 'Manicato',
        ['manzanita'] = 'Manzanita Post',
        ['rhodes'] = 'Rhodes',
        ['siska'] = 'Sisika Penitentiary',
        ['stdenis'] = 'Saint Denis',
        ['strawberry'] = 'Strawberry',
        ['tumbleweed'] = 'Tumbleweed',
        ['valentine'] = 'Valentine',
        ['vanhorn'] = 'Van Horn',
        ['wallace'] = 'Wallace Station',
        ['wapiti'] = 'Wapiti Indian Reservation',
        ['unknown'] = 'Unknown',
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


Config.WeaponLabels = {}
for _, weapon in ipairs(Config.Weapons) do
    local weaponHash = GetHashKey(weapon.item)
    Config.WeaponLabels[weaponHash] = weapon.label
end

Config.WagonLabels = {}
for _, vehicle in ipairs(Config.Wagons) do
    local vehicleHash = GetHashKey(vehicle.model)
    Config.WagonLabels[vehicleHash] = vehicle.label
end

```
