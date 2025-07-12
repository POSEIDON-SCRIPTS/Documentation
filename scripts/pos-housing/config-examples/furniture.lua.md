# furniture.lua

```lua
Config.Furniture = {
    distance = 400,
    max = 50,
    
    returnToPlayer = true, -- return money to player when selling furniture or item 
    returnMoneyPercentage = 0.5, -- 0.5 = 50%
    furnitureType = 3, -- 1 = items, 2 = menu, 3 = both

    Actions = {
        crafting = function()

        end,
        
        outfit = function()

        end,
    },

    stores = {
        [1] = {
            mainCoords = vector4(2626.0398, -1442.5376, 45.4752, 278.9376),
            propCoords = vector3(2633.689208984375, -1439.704345703125, 46.08770904541015),
            camCoords = vector4(2629.08, -1441.60, 47.88, -51.67),
            name = "Furniture Store",
            blip = {
                scale = 60.0,
                model = 'blip_shop_tailor',
                modifier = 'BLIP_MODIFIER_MP_COLOR_20',
                zone = false,
            },
            ped = {
                model = 'CS_mradler' -- false to disable
            }
        }
    },

    list = {
        [1] = {
            name = "BEDROOM",
            furniture = {
                [1] = { item = "p_bed05x", prop = "p_bed05x", itemType = "normal", price = 150, label = "Simple Bed" },
                [2] = { item = "p_bed17x", prop = "p_bed17x", itemType = "normal", price = 150, label = "Rustic Bed" },
                [3] = { item = "p_bedking02x", prop = "p_bedking02x", itemType = "normal", price = 200, label = "King Bed" },
                [4] = { item = "p_bed22x", prop = "p_bed22x", itemType = "normal", price = 200, label = "Modern Bed" },
                [5] = { item = "p_bed21x", prop = "p_bed21x", itemType = "normal", price = 200, label = "Classic Bed" },
                [6] = { item = "p_bed20madex", prop = "p_bed20madex", itemType = "normal", price = 200, label = "Handmade Bed" },
                [7] = { item = "p_bed12x", prop = "p_bed12x", itemType = "normal", price = 200, label = "Vintage Bed" },
                [8] = { item = "nativebed", prop = "p_bedindian01x", itemType = "normal", price = 300, label = "Native Bed" },
                [9] = { item = "chest1", prop = "s_lootablebedchest", itemType = "normal", price = 175, label = "Bedside Chest" },
                [10] = { item = "p_tablebedside02x", prop = "p_tablebedside02x", itemType = "normal", price = 170, label = "Bedside Table" },
            }
        },
        
        [2] = {
            name = "SEATING",
            furniture = {
                [1] = { item = "loungechair", prop = "p_settee01x", itemType = "normal", price = 180, label = "Lounge Chair" },
                [2] = { item = "loungechair2", prop = "p_settee_05x", itemType = "normal", price = 190, label = "Lounge Chair 2" },
                [3] = { item = "p_couch11x", prop = "p_couch11x", itemType = "normal", price = 180, label = "Couch 11" },
                [4] = { item = "p_couch10x", prop = "p_couch10x", itemType = "normal", price = 180, label = "Couch 10" },
                [5] = { item = "p_couch01x", prop = "p_couch01x", itemType = "normal", price = 180, label = "Couch 01" },
                [6] = { item = "p_couch02x", prop = "p_couch02x", itemType = "normal", price = 180, label = "Couch 02" },
                [7] = { item = "p_couch05x", prop = "p_couch05x", itemType = "normal", price = 180, label = "Couch 05" },
                [8] = { item = "p_couch06x", prop = "p_couch06x", itemType = "normal", price = 180, label = "Couch 06" },
                [9] = { item = "p_couch08x", prop = "p_couch08x", itemType = "normal", price = 180, label = "Couch 08" },
                [10] = { item = "p_couch09x", prop = "p_couch09x", itemType = "normal", price = 180, label = "Couch 09" },
                [11] = { item = "p_chaircomfy12x", prop = "p_chaircomfy12x", itemType = "normal", price = 100, label = "Comfy Chair 12" },
                [12] = { item = "p_chaircomfy11x", prop = "p_chaircomfy11x", itemType = "normal", price = 110, label = "Comfy Chair 11" },
                [13] = { item = "p_chaircomfy22x", prop = "p_chaircomfy22x", itemType = "normal", price = 130, label = "Comfy Chair 22" },
                [14] = { item = "p_chaircomfy18x", prop = "p_chaircomfy18x", itemType = "normal", price = 90, label = "Comfy Chair 18" },
                [15] = { item = "p_chaircomfy06x", prop = "p_chaircomfy06x", itemType = "normal", price = 140, label = "Comfy Chair 06" },
                [16] = { item = "p_chaircomfy01x", prop = "p_chaircomfy07x", itemType = "normal", price = 150, label = "Comfy Chair 01" },
                [17] = { item = "p_chaircomfy08x", prop = "p_chaircomfy08x", itemType = "normal", price = 120, label = "Comfy Chair 08" },
                [18] = { item = "p_chaircomfy02", prop = "p_chaircomfy02", itemType = "normal", price = 110, label = "Comfy Chair 02" },
                [19] = { item = "p_chairdesk01x", prop = "p_chairdesk01x", itemType = "normal", price = 160, label = "Desk Chair" },
                [20] = { item = "p_chairdining03x", prop = "p_chairdining03x", itemType = "normal", price = 170, label = "Dining Chair 03" },
                [21] = { item = "p_chairdining02x", prop = "p_chairdining02x", itemType = "normal", price = 190, label = "Dining Chair 02" },
                [22] = { item = "p_chaircomfy04x", prop = "p_chaircomfy04x", itemType = "normal", price = 200, label = "Comfy Chair 04" },
                [23] = { item = "p_chair14x", prop = "p_chair14x", itemType = "normal", price = 120, label = "Chair 14" },
                [24] = { item = "p_chair27x", prop = "p_chair27x", itemType = "normal", price = 160, label = "Chair 27" },
                [25] = { item = "p_chair30x", prop = "p_chair30x", itemType = "normal", price = 180, label = "Chair 30" },
                [26] = { item = "p_chair31x", prop = "p_chair31x", itemType = "normal", price = 140, label = "Chair 31" },
                [27] = { item = "p_chair26x", prop = "p_chair26x", itemType = "normal", price = 190, label = "Chair 26" },
                [28] = { item = "p_chair20x", prop = "p_chair20x", itemType = "normal", price = 170, label = "Chair 20" },
                [29] = { item = "p_chair37x", prop = "p_chair37x", itemType = "normal", price = 160, label = "Chair 37" },
                [30] = { item = "p_chair19x", prop = "p_chair19x", itemType = "normal", price = 150, label = "Chair 19" },
                [31] = { item = "p_chair06x", prop = "p_chair06x", itemType = "normal", price = 110, label = "Chair 06" },
                [32] = { item = "p_bistrochair01x", prop = "p_bistrochair01x", itemType = "normal", price = 130, label = "Bistro Chair" },
                [33] = { item = "p_chair18x", prop = "p_chair18x", itemType = "normal", price = 140, label = "Chair 18" },
                [34] = { item = "p_chair17x", prop = "p_chair17x", itemType = "normal", price = 120, label = "Chair 17" },
                [35] = { item = "p_chair16x", prop = "p_chair16x", itemType = "normal", price = 110, label = "Chair 16" },
                [36] = { item = "p_chair15x", prop = "p_chair15x", itemType = "normal", price = 130, label = "Chair 15" },
                [37] = { item = "p_chair13x", prop = "p_chair13x", itemType = "normal", price = 140, label = "Chair 13" },
                [38] = { item = "p_chair12x", prop = "p_chair12x", itemType = "normal", price = 160, label = "Chair 12" },
                [39] = { item = "p_chair12bx", prop = "p_chair12bx", itemType = "normal", price = 150, label = "Chair 12B" },
                [40] = { item = "p_chair_10x", prop = "p_chair_10x", itemType = "normal", price = 120, label = "Chair 10" },
                [41] = { item = "p_chair11x", prop = "p_chair11x", itemType = "normal", price = 130, label = "Chair 11" },
                [42] = { item = "p_chaircomfy03x", prop = "p_chaircomfy03x", itemType = "normal", price = 160, label = "Comfy Chair 03" },
                [43] = { item = "p_woodendeskchair01x", prop = "p_woodendeskchair01x", itemType = "normal", price = 100, label = "Wooden Desk Chair" },
            }
        },
        
        [3] = {
            name = "TABLES",
            furniture = {
                [1] = { item = "kitchencounter", prop = "p_kitchenhutch01x", itemType = "normal", price = 350, label = "Kitchen Counter" },
                [2] = { item = "p_table02x", prop = "p_table02x", itemType = "normal", price = 210, label = "Simple Table" },
                [3] = { item = "p_table11x", prop = "p_table11x", itemType = "normal", price = 180, label = "Rustic Table" },
                [4] = { item = "p_table39x", prop = "p_table39x", itemType = "normal", price = 230, label = "Modern Table" },
                [5] = { item = "p_table40x", prop = "p_table40x", itemType = "normal", price = 250, label = "Classic Table" },
                [6] = { item = "p_table55x", prop = "p_table55x", itemType = "normal", price = 190, label = "Vintage Table" },
                [7] = { item = "p_tableannsaloon01x", prop = "p_tableannsaloon01x", itemType = "normal", price = 220, label = "Saloon Table" },
                [8] = { item = "p_tableconsole01x", prop = "p_tableconsole01x", itemType = "normal", price = 210, label = "Console Table" },
                [9] = { item = "p_tableconsole03x", prop = "p_tableconsole03x", itemType = "normal", price = 250, label = "Elegant Console Table" },
                [10] = { item = "p_tableconsole05bx", prop = "p_tableconsole05bx", itemType = "normal", price = 200, label = "Wooden Console Table" },
                [11] = { item = "p_tablework02x", prop = "p_tablework02x", itemType = "normal", price = 180, label = "Work Table" },
                [12] = { item = "pokerset", prop = "pg_mg_poker", itemType = "normal", price = 210, label = "Poker Set Table" },
                [13] = { item = "trayoffood", prop = "p_group_man01x_longtable", itemType = "normal", price = 200, label = "Food Tray Table" },
            }
        },

        [4] = {
            name = "DESKS",
            furniture = {
                [1] = { item = "p_desk03x", prop = "p_desk03x", itemType = "normal", price = 150, label = "Simple Desk" },
                [2] = { item = "p_desk09x", prop = "p_desk09x", itemType = "normal", price = 150, label = "Rustic Desk" },
                [3] = { item = "p_desk13x", prop = "p_desk13x", itemType = "normal", price = 150, label = "Modern Desk" },
                [4] = { item = "p_desk14x", prop = "p_desk14x", itemType = "normal", price = 150, label = "Classic Desk" },
                [5] = { item = "p_desk17x", prop = "p_desk17x", itemType = "normal", price = 150, label = "Vintage Desk" },
                [6] = { item = "p_desk09bx", prop = "p_desk09bx", itemType = "normal", price = 150, label = "Wooden Desk" },
                [7] = { item = "p_desk07x", prop = "p_desk07x", itemType = "normal", price = 150, label = "Elegant Desk" },
                [8] = { item = "p_desk04x", prop = "p_desk04x", itemType = "normal", price = 150, label = "Work Desk" },
                [9] = { item = "p_desk01x", prop = "p_desk01x", itemType = "normal", price = 150, label = "Office Desk" },
                [10] = { item = "p_workbenchdesk01x", prop = "p_workbenchdesk01x", itemType = "normal", price = 200, label = "Workbench Desk" },
                [11] = { item = "p_bw_desk01x", prop = "p_bw_desk01x", itemType = "normal", price = 200, label = "Blackwood Desk" },
                [12] = { item = "p_benchwork01x", prop = "p_benchwork01x", itemType = "crafting", price = 150, label = "Crafting Bench" },
            }
        },

        [5] = {
            name = "STORAGE",
            furniture = {
                [1] = { item = "bookcase", prop = "p_cabinetdoctor01x", itemType = "stash", price = 200, label = "Bookcase" },
                [2] = { item = "p_nbmbookshelves01x", prop = "p_nbmbookshelves01x", itemType = "stash", price = 250, label = "Bookshelves" },
                [3] = { item = "p_kitchenhutch01x", prop = "p_kitchenhutch01x", itemType = "stash", price = 200, label = "Kitchen Hutch" },
                [4] = { item = "chest2", prop = "s_lootablemiscchest_wagon", itemType = "stash", price = 185, label = "Wagon Chest" },
                [5] = { item = "chest3", prop = "s_lootablebigbluechest03x", itemType = "stash", price = 190, label = "Blue Chest" },
                [6] = { item = "beerbox", prop = "P_bottlecrate02X", itemType = "stash", price = 90, label = "Beer Box" },
                [7] = { item = "s_lootablemiscchest", prop = "s_lootablemiscchest", itemType = "stash", price = 350, label = "Misc Chest" },
                [8] = { item = "p_chestmedhunt01x", prop = "p_chestmedhunt01x", itemType = "stash", price = 280, label = "Hunting Chest" },
                [9] = { item = "mp009_p_mp_chestornate01x", prop = "mp009_p_mp_chestornate01x", itemType = "stash", price = 500, label = "Ornate Chest" },
                [10] = { item = "p_weddingchest01x", prop = "p_weddingchest01x", itemType = "stash", price = 400, label = "Wedding Chest" },
                [11] = { item = "mp006_s_lootablechest03x", prop = "mp006_s_lootablechest03x", itemType = "stash", price = 420, label = "Lootable Chest" },
            }
        },

        [6] = {
            name = "DRESSERS",
            furniture = {
                [1] = { item = "changer", prop = "p_doc_coatstandrack01x", itemType = "outfit", price = 150, label = "Coat Stand Rack" },
                [2] = { item = "p_dresser01x", prop = "p_dresser01x", itemType = "outfit", price = 150, label = "Simple Dresser" },
                [3] = { item = "p_dresser03x", prop = "p_dresser03x", itemType = "outfit", price = 150, label = "Rustic Dresser" },
                [4] = { item = "p_dresser04x", prop = "p_dresser04x", itemType = "outfit", price = 150, label = "Modern Dresser" },
                [5] = { item = "p_dresser05x", prop = "p_dresser05x", itemType = "outfit", price = 150, label = "Classic Dresser" },
                [6] = { item = "p_dresser06x", prop = "p_dresser06x", itemType = "outfit", price = 150, label = "Vintage Dresser" },
                [7] = { item = "p_dresser07x", prop = "p_dresser07x", itemType = "outfit", price = 150, label = "Elegant Dresser" },
                [8] = { item = "p_dresser08x", prop = "p_dresser08x", itemType = "outfit", price = 150, label = "Wooden Dresser" },
                [9] = { item = "p_dresser09x", prop = "p_dresser09x", itemType = "outfit", price = 150, label = "Work Dresser" },
                [10] = { item = "p_vanitydresserdesk01x", prop = "p_vanitydresserdesk01x", itemType = "outfit", price = 200, label = "Vanity Dresser Desk" },
                [11] = { item = "p_dresser11x", prop = "p_dresser11x", itemType = "outfit", price = 180, label = "Regal Dresser" },
                [12] = { item = "p_dresser10x", prop = "p_dresser10x", itemType = "outfit", price = 170, label = "Antique Dresser" },
                [13] = { item = "p_dresser09x", prop = "p_dresser09x", itemType = "outfit", price = 150, label = "Compact Dresser" },
                [14] = { item = "p_dresser06x", prop = "p_dresser06x", itemType = "outfit", price = 160, label = "Vintage Outfit Dresser" },
                [15] = { item = "p_dresser08x", prop = "p_dresser08x", itemType = "outfit", price = 180, label = "Wooden Outfit Dresser" },
                [16] = { item = "p_dresser05x", prop = "p_dresser05x", itemType = "outfit", price = 140, label = "Classic Outfit Dresser" },
                [17] = { item = "p_dresser04x", prop = "p_dresser04x", itemType = "outfit", price = 190, label = "Modern Outfit Dresser" },
                [18] = { item = "p_dresser03x", prop = "p_dresser03x", itemType = "outfit", price = 150, label = "Rustic Outfit Dresser" },
                [19] = { item = "p_dresser01x", prop = "p_dresser01x", itemType = "outfit", price = 210, label = "Simple Outfit Dresser" },
                [20] = { item = "p_cabinet03x", prop = "p_cabinet03x", itemType = "outfit", price = 220, label = "Cabinet Dresser" },
                [21] = { item = "p_washbasinregal01x", prop = "p_washbasinregal01x", itemType = "outfit", price = 100, label = "Wash Basin" },
            }
        },
        
        [7] = {
            name = "LIGHTING",
            furniture = {
                [1] = { item = "standingtorch", label = "Standing Torch", prop = "p_torchpostalwayson01x", itemType = "normal", price = 120 },
                [2] = { item = "p_lampstanding09x", label = "Modern Standing Lamp", prop = "p_lampstanding09x", itemType = "normal", price = 120 },
                [3] = { item = "p_lampstanding06x", label = "Simple Standing Lamp", prop = "p_lampstanding06x", itemType = "normal", price = 150 },
                [4] = { item = "p_lampstanding04x", label = "Ornate Standing Lamp", prop = "p_lampstanding04x", itemType = "normal", price = 140 },
                [5] = { item = "p_lampstanding01x", label = "Classic Standing Lamp", prop = "p_lampstanding01x", itemType = "normal", price = 160 },
                [6] = { item = "p_lampstanding02x", label = "Old Standing Lamp", prop = "p_lampstanding02x", itemType = "normal", price = 130 },
                [7] = { item = "p_lampstanding03x", label = "Vintage Standing Lamp", prop = "p_lampstanding03x", itemType = "normal", price = 170 },
                [8] = { item = "lamppost1", label = "Wooden Gamepole Lamp", prop = "pg_ambient_camp_add_gamepole01", itemType = "normal", price = 100 },
                [9] = { item = "lamppost2", label = "Iron Lamppost", prop = "pg_ambient_camp_add_lamppost01", itemType = "normal", price = 105 },
            }
        },
        
        [8] = {
            name = "NATIVE",
            furniture = {
                [1] = { item = "nativemask", label = "Native Skull Mask", prop = "mp005_p_mp_predhunt_skull08x", itemType = "normal", price = 120 },
                [2] = { item = "nativearms", label = "Native Wooden Totem", prop = "p_spookynative05x", itemType = "normal", price = 180 },
                [3] = { item = "tipi", label = "Native Tipi Tent", prop = "s_wap_rainsfalls", itemType = "normal", price = 400 },
                [4] = { item = "dreamcatcher", label = "Dreamcatcher", prop = "p_indiandream01x", itemType = "normal", price = 90 },
                [5] = { item = "nativeskull", label = "Decorated Native Skull", prop = "p_spookynative02x", itemType = "normal", price = 130 },
                [6] = { item = "nativepot", label = "Tribal Clay Pot", prop = "p_potteryindian02x", itemType = "normal", price = 95 },
                [7] = { item = "nativebasket1", label = "Woven Basket 1", prop = "p_basketindian02x", itemType = "normal", price = 85 },
                [8] = { item = "nativebasket2", label = "Woven Basket 2", prop = "p_basketindian03x", itemType = "normal", price = 90 },
                [9] = { item = "skullpost", label = "Skull on Post", prop = "p_skullpost02x", itemType = "normal", price = 140 },
                [10] = { item = "nativedecor", label = "Native Camp Decor", prop = "pg_ambient_camp_add_native01", itemType = "normal", price = 130 },
            }
        },
        
        [9] = {
            name = "OUTDOOR",
            furniture = {
                [1] = { item = "cage", label = "Animal Cage", prop = "mp005_p_wildanimalcage01", itemType = "normal", price = 250 },
                [2] = { item = "tent2", label = "Trader Tent", prop = "mp005_s_posse_tent_trader07x", itemType = "normal", price = 350 },
                [3] = { item = "tent3", label = "Bounty Hunter Tent", prop = "mp005_s_posse_tent_bountyhunter04x", itemType = "normal", price = 370 },
                [4] = { item = "tent4", label = "Tanner's Tent", prop = "p_mptenttanner01x", itemType = "normal", price = 360 },
                [5] = { item = "woodfence", label = "Wooden Fence", prop = "p_fence02ax", itemType = "normal", price = 110 },
                [6] = { item = "decortent1", label = "Decorative Bounty Tent", prop = "pg_mp_possecamp_tent_bounty07x", itemType = "normal", price = 390 },
                [7] = { item = "decortent2", label = "Decorative Trader Tent", prop = "pg_mp_possecamp_tent_trader07x", itemType = "normal", price = 395 },
                [8] = { item = "decortent3", label = "Decorative Collector Tent", prop = "pg_mp_possecamp_tent_collector07x", itemType = "normal", price = 400 },
                [9] = { item = "horsehitches", label = "Horse Hitching Area", prop = "PG_COMPANIONACTIVITY_RUSTLING", itemType = "normal", price = 250 },
                [10] = { item = "robberyplanning", label = "Robbery Planning Setup", prop = "PG_COMPANIONACTIVITY_ROBBERY", itemType = "normal", price = 275 },
                [11] = { item = "naturalwagon", label = "Naturalist Wagon", prop = "pg_mp007_naturalist_camp01x", itemType = "normal", price = 500 },
                [12] = { item = "mountainmen", label = "Mountain Men Scene", prop = "pg_re_mountainmen01x", itemType = "normal", price = 300 },
                [13] = { item = "undertaker1", label = "Undertaker's Shack", prop = "s_loansharkundertaker01x", itemType = "normal", price = 280 },
                [14] = { item = "undertaker2", label = "Coffin Decor", prop = "mp004_s_mp_coffindecor01x", itemType = "normal", price = 290 },
                [15] = { item = "shootingtarget", label = "Shooting Target", prop = "s_confedtarget", itemType = "normal", price = 150 },
                [16] = { item = "hitchingpost", label = "Hitching Post", prop = "p_hitchingpost01x", itemType = "normal", price = 160 },
                [17] = { item = "gypsywagon", label = "Collector Wagon", prop = "PG_MP005_COLLECTORWAGONCAMP01", itemType = "normal", price = 450 },
                [18] = { item = "p_watertower_lrg_05", label = "Large Water Tower", prop = "p_watertower_lrg_05", itemType = "normal", price = 180 },
                [19] = { item = "p_watertower_med_02", label = "Medium Water Tower 02", prop = "p_watertower_med_02", itemType = "normal", price = 190 },
                [20] = { item = "p_watertower_med_03", label = "Medium Water Tower 03", prop = "p_watertower_med_03", itemType = "normal", price = 170 },
                [21] = { item = "p_watertower_med_04", label = "Medium Water Tower 04", prop = "p_watertower_med_04", itemType = "normal", price = 210 },
                [22] = { item = "p_watertower_med_05", label = "Medium Water Tower 05", prop = "p_watertower_med_05", itemType = "normal", price = 200 },
                [23] = { item = "p_watertower_med_06", label = "Medium Water Tower 06", prop = "p_watertower_med_06", itemType = "normal", price = 180 },
                [24] = { item = "p_watertower_med_07", label = "Medium Water Tower 07", prop = "p_watertower_med_07", itemType = "normal", price = 190 },
                [25] = { item = "p_windmill01x", label = "Windmill", prop = "p_windmill01x", itemType = "normal", price = 220 },
            }
        },
        
        
        [10] = {
            name = "DECORATIVE",
            furniture = {
                [1] = { item = "p_nbmpiano01x", label = "Classic Piano", prop = "p_nbmpiano01x", itemType = "normal", price = 300 },
                [2] = { item = "mp006_p_mshn_painting01x", label = "Painting 1", prop = "mp006_p_mshn_painting01x", itemType = "normal", price = 100 },
                [3] = { item = "mp006_p_mshn_painting02x", label = "Painting 2", prop = "mp006_p_mshn_painting02x", itemType = "normal", price = 100 },
                [4] = { item = "mp006_p_mshn_painting03x", label = "Painting 3", prop = "mp006_p_mshn_painting03x", itemType = "normal", price = 100 },
                [5] = { item = "mp006_p_mshn_painting04x", label = "Painting 4", prop = "mp006_p_mshn_painting04x", itemType = "normal", price = 100 },
                [6] = { item = "mp006_p_mshn_painting05x", label = "Painting 5", prop = "mp006_p_mshn_painting05x", itemType = "normal", price = 100 },
                [7] = { item = "mp006_p_mshn_painting06x", label = "Painting 6", prop = "mp006_p_mshn_painting06x", itemType = "normal", price = 100 },
                [8] = { item = "mp006_p_mshn_painting07x", label = "Painting 7", prop = "mp006_p_mshn_painting07x", itemType = "normal", price = 100 },
                [9] = { item = "mp006_p_mshn_painting08x", label = "Painting 8", prop = "mp006_p_mshn_painting08x", itemType = "normal", price = 100 },
                [10] = { item = "mp006_p_mshn_painting09x", label = "Painting 9", prop = "mp006_p_mshn_painting09x", itemType = "normal", price = 100 },
                [11] = { item = "mp006_p_mshn_painting10x", label = "Painting 10", prop = "mp006_p_mshn_painting10x", itemType = "normal", price = 100 },
                [12] = { item = "mp006_p_mshn_painting11x", label = "Painting 11", prop = "mp006_p_mshn_painting11x", itemType = "normal", price = 100 },
                [13] = { item = "mp006_p_mshn_painting12x", label = "Painting 12", prop = "mp006_p_mshn_painting12x", itemType = "normal", price = 100 },
                [14] = { item = "p_phoneantique01x", label = "Antique Telephone", prop = "p_phoneantique01x", itemType = "phone", price = 350 },
            }
        },        
    },
}
```
