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
                [1] = { item = "p_bed05x", prop = "p_bed05x", itemType = "normal", price = 150 },
                [2] = { item = "p_bed17x", prop = "p_bed17x", itemType = "normal", price = 150 },
                [3] = { item = "p_bedking02x", prop = "p_bedking02x", itemType = "normal", price = 200 },
                [4] = { item = "p_bed22x", prop = "p_bed22x", itemType = "normal", price = 200 },
                [5] = { item = "p_bed21x", prop = "p_bed21x", itemType = "normal", price = 200 },
                [6] = { item = "p_bed20madex", prop = "p_bed20madex", itemType = "normal", price = 200 },
                [7] = { item = "p_bed12x", prop = "p_bed12x", itemType = "normal", price = 200 },
                [8] = { item = "nativebed", prop = "p_bedindian01x", itemType = "normal", price = 300 },
                [9] = { item = "chest1", prop = "s_lootablebedchest", itemType = "normal", price = 175 },
                [10] = { item = "p_tablebedside02x", prop = "p_tablebedside02x", itemType = "normal", price = 170 },
            }
        },
        
        [2] = {
            name = "SEATING",
            furniture = {
                [1] = { item = "loungechair", prop = "p_settee01x", itemType = "normal", price = 180 },
                [2] = { item = "loungechair2", prop = "p_settee_05x", itemType = "normal", price = 190 },
                [3] = { item = "p_couch11x", prop = "p_couch11x", itemType = "normal", price = 180 },
                [4] = { item = "p_couch10x", prop = "p_couch10x", itemType = "normal", price = 180 },
                [5] = { item = "p_couch01x", prop = "p_couch01x", itemType = "normal", price = 180 },
                [6] = { item = "p_couch02x", prop = "p_couch02x", itemType = "normal", price = 180 },
                [7] = { item = "p_couch05x", prop = "p_couch05x", itemType = "normal", price = 180 },
                [8] = { item = "p_couch06x", prop = "p_couch06x", itemType = "normal", price = 180 },
                [9] = { item = "p_couch08x", prop = "p_couch08x", itemType = "normal", price = 180 },
                [10] = { item = "p_couch09x", prop = "p_couch09x", itemType = "normal", price = 180 },
                [11] = { item = "p_chaircomfy12x", prop = "p_chaircomfy12x", itemType = "normal", price = 100 },
                [12] = { item = "p_chaircomfy11x", prop = "p_chaircomfy11x", itemType = "normal", price = 110 },
                [13] = { item = "p_chaircomfy22x", prop = "p_chaircomfy22x", itemType = "normal", price = 130 },
                [14] = { item = "p_chaircomfy18x", prop = "p_chaircomfy18x", itemType = "normal", price = 90 },
                [15] = { item = "p_chaircomfy06x", prop = "p_chaircomfy06x", itemType = "normal", price = 140 },
                [16] = { item = "p_chaircomfy01x", prop = "p_chaircomfy07x", itemType = "normal", price = 150 },
                [17] = { item = "p_chaircomfy08x", prop = "p_chaircomfy08x", itemType = "normal", price = 120 },
                [18] = { item = "p_chaircomfy02", prop = "p_chaircomfy02", itemType = "normal", price = 110 },
                [19] = { item = "p_chairdesk01x", prop = "p_chairdesk01x", itemType = "normal", price = 160 },
                [20] = { item = "p_chairdining03x", prop = "p_chairdining03x", itemType = "normal", price = 170 },
                [21] = { item = "p_chairdining02x", prop = "p_chairdining02x", itemType = "normal", price = 190 },
                [22] = { item = "p_chaircomfy04x", prop = "p_chaircomfy04x", itemType = "normal", price = 200 },
                [23] = { item = "p_chair14x", prop = "p_chair14x", itemType = "normal", price = 120 },
                [24] = { item = "p_chair27x", prop = "p_chair27x", itemType = "normal", price = 160 },
                [25] = { item = "p_chair30x", prop = "p_chair30x", itemType = "normal", price = 180 },
                [26] = { item = "p_chair31x", prop = "p_chair31x", itemType = "normal", price = 140 },
                [27] = { item = "p_chair26x", prop = "p_chair26x", itemType = "normal", price = 190 },
                [28] = { item = "p_chair20x", prop = "p_chair20x", itemType = "normal", price = 170 },
                [29] = { item = "p_chair37x", prop = "p_chair37x", itemType = "normal", price = 160 },
                [30] = { item = "p_chair19x", prop = "p_chair19x", itemType = "normal", price = 150 },
                [31] = { item = "p_chair06x", prop = "p_chair06x", itemType = "normal", price = 110 },
                [32] = { item = "p_bistrochair01x", prop = "p_bistrochair01x", itemType = "normal", price = 130 },
                [33] = { item = "p_chair18x", prop = "p_chair18x", itemType = "normal", price = 140 },
                [34] = { item = "p_chair17x", prop = "p_chair17x", itemType = "normal", price = 120 },
                [35] = { item = "p_chair16x", prop = "p_chair16x", itemType = "normal", price = 110 },
                [36] = { item = "p_chair15x", prop = "p_chair15x", itemType = "normal", price = 130 },
                [37] = { item = "p_chair13x", prop = "p_chair13x", itemType = "normal", price = 140 },
                [38] = { item = "p_chair12x", prop = "p_chair12x", itemType = "normal", price = 160 },
                [39] = { item = "p_chair12bx", prop = "p_chair12bx", itemType = "normal", price = 150 },
                [40] = { item = "p_chair_10x", prop = "p_chair_10x", itemType = "normal", price = 120 },
                [41] = { item = "p_chair11x", prop = "p_chair11x", itemType = "normal", price = 130 },
                [42] = { item = "p_chaircomfy03x", prop = "p_chaircomfy03x", itemType = "normal", price = 160 },
                [43] = { item = "p_woodendeskchair01x", prop = "p_woodendeskchair01x", itemType = "normal", price = 100 },
            }
        },
        
        [3] = {
            name = "TABLES",
            furniture = {
                [1] = { item = "kitchencounter", prop = "p_kitchenhutch01x", itemType = "normal", price = 350 },
                [2] = { item = "p_table02x", prop = "p_table02x", itemType = "normal", price = 210 },
                [3] = { item = "p_table11x", prop = "p_table11x", itemType = "normal", price = 180 },
                [4] = { item = "p_table39x", prop = "p_table39x", itemType = "normal", price = 230 },
                [5] = { item = "p_table40x", prop = "p_table40x", itemType = "normal", price = 250 },
                [6] = { item = "p_table55x", prop = "p_table55x", itemType = "normal", price = 190 },
                [7] = { item = "p_tableannsaloon01x", prop = "p_tableannsaloon01x", itemType = "normal", price = 220 },
                [8] = { item = "p_tableconsole01x", prop = "p_tableconsole01x", itemType = "normal", price = 210 },
                [9] = { item = "p_tableconsole03x", prop = "p_tableconsole03x", itemType = "normal", price = 250 },
                [10] = { item = "p_tableconsole05bx", prop = "p_tableconsole05bx", itemType = "normal", price = 200 },
                [11] = { item = "p_tablework02x", prop = "p_tablework02x", itemType = "normal", price = 180 },
                [12] = { item = "pokerset", prop = "pg_mg_poker", itemType = "normal", price = 210 },
                [13] = { item = "trayoffood", prop = "p_group_man01x_longtable", itemType = "normal", price = 200 },
            }
        },
        
        [4] = {
            name = "DESKS",
            furniture = {
                [1] = { item = "p_desk03x", prop = "p_desk03x", itemType = "normal", price = 150 },
                [2] = { item = "p_desk09x", prop = "p_desk09x", itemType = "normal", price = 150 },
                [3] = { item = "p_desk13x", prop = "p_desk13x", itemType = "normal", price = 150 },
                [4] = { item = "p_desk14x", prop = "p_desk14x", itemType = "normal", price = 150 },
                [5] = { item = "p_desk17x", prop = "p_desk17x", itemType = "normal", price = 150 },
                [6] = { item = "p_desk09bx", prop = "p_desk09bx", itemType = "normal", price = 150 },
                [7] = { item = "p_desk07x", prop = "p_desk07x", itemType = "normal", price = 150 },
                [8] = { item = "p_desk04x", prop = "p_desk04x", itemType = "normal", price = 150 },
                [9] = { item = "p_desk01x", prop = "p_desk01x", itemType = "normal", price = 150 },
                [10] = { item = "p_workbenchdesk01x", prop = "p_workbenchdesk01x", itemType = "normal", price = 200 },
                [11] = { item = "p_bw_desk01x", prop = "p_bw_desk01x", itemType = "normal", price = 200 },
                [12] = { item = "p_benchwork01x", prop = "p_benchwork01x", itemType = "crafting", price = 150 },
            }
        },
        
        [5] = {
            name = "STORAGE",
            furniture = {
                [1] = { item = "bookcase", prop = "p_cabinetdoctor01x", itemType = "stash", price = 200 },
                [2] = { item = "p_nbmbookshelves01x", prop = "p_nbmbookshelves01x", itemType = "stash", price = 250 },
                [3] = { item = "p_kitchenhutch01x", prop = "p_kitchenhutch01x", itemType = "stash", price = 200 },
                [4] = { item = "chest2", prop = "s_lootablemiscchest_wagon", itemType = "stash", price = 185 },
                [5] = { item = "chest3", prop = "s_lootablebigbluechest03x", itemType = "stash", price = 190 },
                [6] = { item = "beerbox", prop = "P_bottlecrate02X", itemType = "stash", price = 90 },
                [7] = { item = "s_lootablemiscchest", prop = "s_lootablemiscchest", itemType = "stash", price = 350 },
                [8] = { item = "p_chestmedhunt01x", prop = "p_chestmedhunt01x", itemType = "stash", price = 280 },
                [9] = { item = "mp009_p_mp_chestornate01x", prop = "mp009_p_mp_chestornate01x", itemType = "stash", price = 500 },
                [10] = { item = "p_weddingchest01x", prop = "p_weddingchest01x", itemType = "stash", price = 400 },
                [11] = { item = "mp006_s_lootablechest03x", prop = "mp006_s_lootablechest03x", itemType = "stash", price = 420 },
            }
        },
        
        [6] = {
            name = "DRESSERS",
            furniture = {
                [1] = { item = "changer", prop = "p_doc_coatstandrack01x", itemType = "normal", price = 150 },
                [2] = { item = "p_dresser01x", prop = "p_dresser01x", itemType = "normal", price = 150 },
                [3] = { item = "p_dresser03x", prop = "p_dresser03x", itemType = "normal", price = 150 },
                [4] = { item = "p_dresser04x", prop = "p_dresser04x", itemType = "normal", price = 150 },
                [5] = { item = "p_dresser05x", prop = "p_dresser05x", itemType = "normal", price = 150 },
                [6] = { item = "p_dresser06x", prop = "p_dresser06x", itemType = "normal", price = 150 },
                [7] = { item = "p_dresser07x", prop = "p_dresser07x", itemType = "normal", price = 150 },
                [8] = { item = "p_dresser08x", prop = "p_dresser08x", itemType = "normal", price = 150 },
                [9] = { item = "p_dresser09x", prop = "p_dresser09x", itemType = "normal", price = 150 },
                [10] = { item = "p_vanitydresserdesk01x", prop = "p_vanitydresserdesk01x", itemType = "outfit", price = 200 },
                [11] = { item = "p_dresser11x", prop = "p_dresser11x", itemType = "outfit", price = 180 },
                [12] = { item = "p_dresser10x", prop = "p_dresser10x", itemType = "outfit", price = 170 },
                [13] = { item = "p_dresser09x", prop = "p_dresser09x", itemType = "outfit", price = 150 },
                [14] = { item = "p_dresser06x", prop = "p_dresser06x", itemType = "outfit", price = 160 },
                [15] = { item = "p_dresser08x", prop = "p_dresser08x", itemType = "outfit", price = 180 },
                [16] = { item = "p_dresser05x", prop = "p_dresser05x", itemType = "outfit", price = 140 },
                [17] = { item = "p_dresser04x", prop = "p_dresser04x", itemType = "outfit", price = 190 },
                [18] = { item = "p_dresser03x", prop = "p_dresser03x", itemType = "outfit", price = 150 },
                [19] = { item = "p_dresser01x", prop = "p_dresser01x", itemType = "outfit", price = 210 },
                [20] = { item = "p_cabinet03x", prop = "p_cabinet03x", itemType = "outfit", price = 220 },
                [21] = { item = "p_washbasinregal01x", prop = "p_washbasinregal01x", itemType = "normal", price = 100 },
            }
        },
        
        [7] = {
            name = "LIGHTING",
            furniture = {
                [1] = { item = "standingtorch", prop = "p_torchpostalwayson01x", itemType = "normal", price = 120 },
                [2] = { item = "p_lampstanding09x", prop = "p_lampstanding09x", itemType = "normal", price = 120 },
                [3] = { item = "p_lampstanding06x", prop = "p_lampstanding06x", itemType = "normal", price = 150 },
                [4] = { item = "p_lampstanding04x", prop = "p_lampstanding04x", itemType = "normal", price = 140 },
                [5] = { item = "p_lampstanding01x", prop = "p_lampstanding01x", itemType = "normal", price = 160 },
                [6] = { item = "p_lampstanding02x", prop = "p_lampstanding02x", itemType = "normal", price = 130 },
                [7] = { item = "p_lampstanding03x", prop = "p_lampstanding03x", itemType = "normal", price = 170 },
                [8] = { item = "lamppost1", prop = "pg_ambient_camp_add_gamepole01", itemType = "normal", price = 100 },
                [9] = { item = "lamppost2", prop = "pg_ambient_camp_add_lamppost01", itemType = "normal", price = 105 },
            }
        },
        
        [8] = {
            name = "NATIVE",
            furniture = {
                [1] = { item = "nativemask", prop = "mp005_p_mp_predhunt_skull08x", itemType = "normal", price = 120 },
                [2] = { item = "nativearms", prop = "p_spookynative05x", itemType = "normal", price = 180 },
                [3] = { item = "tipi", prop = "s_wap_rainsfalls", itemType = "normal", price = 400 },
                [4] = { item = "dreamcatcher", prop = "p_indiandream01x", itemType = "normal", price = 90 },
                [5] = { item = "nativeskull", prop = "p_spookynative02x", itemType = "normal", price = 130 },
                [6] = { item = "nativepot", prop = "p_potteryindian02x", itemType = "normal", price = 95 },
                [7] = { item = "nativebasket1", prop = "p_basketindian02x", itemType = "normal", price = 85 },
                [8] = { item = "nativebasket2", prop = "p_basketindian03x", itemType = "normal", price = 90 },
                [9] = { item = "skullpost", prop = "p_skullpost02x", itemType = "normal", price = 140 },
                [10] = { item = "nativedecor", prop = "pg_ambient_camp_add_native01", itemType = "normal", price = 130 },
            }
        },
        
        [9] = {
            name = "OUTDOOR",
            furniture = {
                [1] = { item = "cage", prop = "mp005_p_wildanimalcage01", itemType = "normal", price = 250 },
                [2] = { item = "tent2", prop = "mp005_s_posse_tent_trader07x", itemType = "normal", price = 350 },
                [3] = { item = "tent3", prop = "mp005_s_posse_tent_bountyhunter04x", itemType = "normal", price = 370 },
                [4] = { item = "tent4", prop = "p_mptenttanner01x", itemType = "normal", price = 360 },
                [5] = { item = "woodfence", prop = "p_fence02ax", itemType = "normal", price = 110 },
                [6] = { item = "decortent1", prop = "pg_mp_possecamp_tent_bounty07x", itemType = "normal", price = 390 },
                [7] = { item = "decortent2", prop = "pg_mp_possecamp_tent_trader07x", itemType = "normal", price = 395 },
                [8] = { item = "decortent3", prop = "pg_mp_possecamp_tent_collector07x", itemType = "normal", price = 400 },
                [9] = { item = "horsehitches", prop = "PG_COMPANIONACTIVITY_RUSTLING", itemType = "normal", price = 250 },
                [10] = { item = "robberyplanning", prop = "PG_COMPANIONACTIVITY_ROBBERY", itemType = "normal", price = 275 },
                [11] = { item = "naturalwagon", prop = "pg_mp007_naturalist_camp01x", itemType = "normal", price = 500 },
                [12] = { item = "mountainmen", prop = "pg_re_mountainmen01x", itemType = "normal", price = 300 },
                [13] = { item = "undertaker1", prop = "s_loansharkundertaker01x", itemType = "normal", price = 280 },
                [14] = { item = "undertaker2", prop = "mp004_s_mp_coffindecor01x", itemType = "normal", price = 290 },
                [15] = { item = "shootingtarget", prop = "s_confedtarget", itemType = "normal", price = 150 },
                [16] = { item = "hitchingpost", prop = "p_hitchingpost01x", itemType = "normal", price = 160 },
                [17] = { item = "gypsywagon", prop = "PG_MP005_COLLECTORWAGONCAMP01", itemType = "normal", price = 450 },
                [18] = { item = "p_watertower_lrg_05", prop = "p_watertower_lrg_05", itemType = "normal", price = 180 },
                [19] = { item = "p_watertower_med_02", prop = "p_watertower_med_02", itemType = "normal", price = 190 },
                [20] = { item = "p_watertower_med_03", prop = "p_watertower_med_03", itemType = "normal", price = 170 },
                [21] = { item = "p_watertower_med_04", prop = "p_watertower_med_04", itemType = "normal", price = 210 },
                [22] = { item = "p_watertower_med_05", prop = "p_watertower_med_05", itemType = "normal", price = 200 },
                [23] = { item = "p_watertower_med_06", prop = "p_watertower_med_06", itemType = "normal", price = 180 },
                [24] = { item = "p_watertower_med_07", prop = "p_watertower_med_07", itemType = "normal", price = 190 },
                [25] = { item = "p_windmill01x", prop = "p_windmill01x", itemType = "normal", price = 220 },
            }
        },
        
        [10] = {
            name = "DECORATIVE",
            furniture = {
                [1] = { item = "p_nbmpiano01x", prop = "p_nbmpiano01x", itemType = "normal", price = 300 },
                [2] = { item = "mp006_p_mshn_painting01x", prop = "mp006_p_mshn_painting01x", itemType = "normal", price = 100 },
                [3] = { item = "mp006_p_mshn_painting02x", prop = "mp006_p_mshn_painting02x", itemType = "normal", price = 100 },
                [4] = { item = "mp006_p_mshn_painting03x", prop = "mp006_p_mshn_painting03x", itemType = "normal", price = 100 },
                [5] = { item = "mp006_p_mshn_painting04x", prop = "mp006_p_mshn_painting04x", itemType = "normal", price = 100 },
                [6] = { item = "mp006_p_mshn_painting05x", prop = "mp006_p_mshn_painting05x", itemType = "normal", price = 100 },
                [7] = { item = "mp006_p_mshn_painting06x", prop = "mp006_p_mshn_painting06x", itemType = "normal", price = 100 },
                [8] = { item = "mp006_p_mshn_painting07x", prop = "mp006_p_mshn_painting07x", itemType = "normal", price = 100 },
                [9] = { item = "mp006_p_mshn_painting08x", prop = "mp006_p_mshn_painting08x", itemType = "normal", price = 100 },
                [10] = { item = "mp006_p_mshn_painting09x", prop = "mp006_p_mshn_painting09x", itemType = "normal", price = 100 },
                [11] = { item = "mp006_p_mshn_painting10x", prop = "mp006_p_mshn_painting10x", itemType = "normal", price = 100 },
                [12] = { item = "mp006_p_mshn_painting11x", prop = "mp006_p_mshn_painting11x", itemType = "normal", price = 100 },
                [13] = { item = "mp006_p_mshn_painting12x", prop = "mp006_p_mshn_painting12x", itemType = "normal", price = 100 },
                [14] = { item = "p_phoneantique01x", prop = "p_phoneantique01x", itemType = "phone", price = 350 },
            }
        }
    },
}
```
