# Items.lua

```lua
Config.Items = {
    ['accesoriiindiancal'] = {
        label = "Accesorii Cal ",
        weight = 0.25,
        metadata = {}, -- Default item metadata or nil or empty table
        canRemove = true,
        canUse = true,
        image = 'test.png'
    },
    
}


Config.Weapons = {
    ['WEAPON_LASSO'] = {
        label = 'Lasso',
        weight = 0.50,
        canRemove = false,
        canUse = false,
        requiredXp = 0,
    },
    ['WEAPON_LASSO_REINFORCED'] = {
        label = 'Reinforced Lasso',
        weight = 0.55,
    },
    ['WEAPON_MELEE_KNIFE'] = {
        label = 'Knife',
        weight = 0.33,
    },
    ['WEAPON_MELEE_KNIFE_RUSTIC'] = {
        label = 'Knife Rustic',
        weight = 0.40,
    },
    ['WEAPON_MELEE_KNIFE_HORROR'] = {
        label = 'Knife Horror',
        weight = 0.40,
    },
    ['WEAPON_MELEE_KNIFE_CIVIL_WAR'] = {
        label = 'Knife Civil War',
        weight = 0.45,
    },
    ['WEAPON_MELEE_KNIFE_JAWBONE'] = {
        label = 'Knife Jawbone',
        weight = 0.37,
    },
    ['WEAPON_MELEE_KNIFE_MINER'] = {
        label = 'Knife Miner',
        weight = 0.40,
    },
    ['WEAPON_MELEE_KNIFE_VAMPIRE'] = {
        label = 'Knife Vampire',
        weight = 0.39,
    },
    ['WEAPON_MELEE_CLEAVER'] = {
        label = 'Cleaver',
        weight = 0.73,
    },
    ['WEAPON_MELEE_HATCHET'] = {
        label = 'Hachet',
        weight = 1.05,
    },
    ['WEAPON_MELEE_HATCHET_DOUBLE_BIT'] = {
        label = 'Hachet Double Bit',
        weight = 1.15,
    },
    ['WEAPON_MELEE_HATCHET_HEWING'] = {
        label = 'Hachet Hewing',
        weight = 1.10,
    },
    ['WEAPON_MELEE_HATCHET_HUNTER'] = {
        label = 'Hachet Hunter',
        weight = 1.15,
    },
    ['WEAPON_MELEE_HATCHET_VIKING'] = {
        label = 'Hachet Viking',
        weight = 1.20,
    },
    ['WEAPON_THROWN_TOMAHAWK'] = {
        label = 'Tomahawk',
        weight = 1.30,
    },
    ['WEAPON_THROWN_TOMAHAWK_ANCIENT'] = {
        label = 'Tomahawk Ancient',
        weight = 1.50,
    },
    ['WEAPON_THROWN_THROWING_KNIVES'] = {
        label = 'Throwing Knifes',
        weight = 1.05,
    },
    ['WEAPON_MELEE_MACHETE'] = {
        label = 'Machete',
        weight = 1.30,
    },
    ['WEAPON_BOW'] = {
        label = 'Bow',
        weight = 0.85,
    },
    ['WEAPON_PISTOL_SEMIAUTO'] = {
        label = 'Pistol Semi-Auto',
        weight = 1.18,
    },
    ['WEAPON_PISTOL_MAUSER'] = {
        label = 'Pistol Mauser',
        weight = 1.13,
    },
    ['WEAPON_PISTOL_VOLCANIC'] = {
        label = 'Pistol Volcanic',
        weight = 1.10,
    },
    ['WEAPON_PISTOL_M1899'] = {
        label = 'Pistol M1899',
        weight = 1.15,
    },
    ['WEAPON_REVOLVER_SCHOFIELD'] = {
        label = 'Revolver Schofield',
        weight = 1.30,
    },
    ['WEAPON_REVOLVER_NAVY'] = {
        label = 'Revolver Navy',
        weight = 1.20,
    },
    ['WEAPON_REVOLVER_NAVY_CROSSOVER'] = {
        label = 'Revolver Navy Crossover',
        weight = 1.25,
    },
    ['WEAPON_REVOLVER_LEMAT'] = {
        label = 'Revolver Lemat',
        weight = 1.86,
    },
    ['WEAPON_REVOLVER_DOUBLEACTION'] = {
        label = 'Revolver Double Action',
        weight = 0.94,
    },
    ['WEAPON_REVOLVER_CATTLEMAN'] = {
        label = 'Revolver Cattleman',
        weight = 1.04,
    },
    ['WEAPON_REVOLVER_CATTLEMAN_MEXICAN'] = {
        label = 'Revolver Cattleman Mexican',
        weight = 1.04,
    },
    ['WEAPON_RIFLE_VARMINT'] = {
        label = 'Varmint Rifle',
        weight = 2.80,
    },
    ['WEAPON_REPEATER_WINCHESTER'] = {
        label = 'Winchester Repeater',
        weight = 2.30,
    },
    ['WEAPON_REPEATER_HENRY'] = {
        label = 'Henry Reapeater',
        weight = 2.20,
    },
    ['WEAPON_REPEATER_EVANS'] = {
        label = 'Evans Repeater',
        weight = 2.45,
    },
    ['WEAPON_REPEATER_CARBINE'] = {
        label = 'Carabine Reapeater',
        weight = 2.10,
    },
    ['WEAPON_SNIPERRIFLE_ROLLINGBLOCK'] = {
        label = 'Rolling Block Rifle',
        weight = 2.20,
    },
    ['WEAPON_SNIPERRIFLE_CARCANO'] = {
        label = 'Carcano Rifle',
        weight = 2.62,
    },
    ['WEAPON_RIFLE_SPRINGFIELD'] = {
        label = 'Springfield Rifle',
        weight = 1.90,
    },
    ['WEAPON_RIFLE_ELEPHANT'] = {
        label = 'Elephant Rifle',
        weight = 3.50,
    },
    ['WEAPON_RIFLE_BOLTACTION'] = {
        label = 'BoltAction Rifle',
        weight = 2.08,
    },
    ['WEAPON_SHOTGUN_SEMIAUTO'] = {
        label = 'Semi-Auto Shotgun',
        weight = 2.53,
    },
    ['WEAPON_SHOTGUN_SAWEDOFF'] = {
        label = 'Sawedoff Shotgun',
        weight = 1.90,
    },
    ['WEAPON_SHOTGUN_REPEATING'] = {
        label = 'Repeating Shotgun',
        weight = 2.60,
    },
    ['WEAPON_SHOTGUN_DOUBLEBARREL_EXOTIC'] = {
        label = 'Double Barrel Exotic Shotgun',
        weight = 2.71,
    },
    ['WEAPON_SHOTGUN_PUMP'] = {
        label = 'Pump Shotgun',
        weight = 2.60,
    },
    ['WEAPON_SHOTGUN_DOUBLEBARREL'] = {
        label = 'Double Barrel Shotgun',
        weight = 2.65,
    },
    ['WEAPON_KIT_CAMERA'] = {
        label = 'Camera',
        weight = 0.47,
    },
    ['WEAPON_KIT_BINOCULARS_IMPROVED'] = {
        label = 'Improved Binoculars',
        weight = 1.50,
    },
    ['WEAPON_MELEE_KNIFE_TRADER'] = {
        label = 'Knife Trader',
        weight = 0.45,
    },
    ['WEAPON_KIT_BINOCULARS'] = {
        label = 'Binoculars',
        weight = 1.45,
    },
    ['WEAPON_KIT_CAMERA_ADVANCED'] = {
        label = 'Advanced Camera',
        weight = 0.55,
    },
    ['WEAPON_MELEE_LANTERN'] = {
        label = 'Lantern',
        weight = 0.56,
    },
    ['WEAPON_MELEE_DAVY_LANTERN'] = {
        label = 'Davy Lantern',
        weight = 0.65,
    },
    ['WEAPON_MELEE_LANTERN_HALLOWEEN'] = {
        label = 'Halloween Lantern',
        weight = 1.20,
    },
    ['WEAPON_THROWN_POISONBOTTLE'] = {
        label = 'Poison Bottle',
        weight = 0.35,
    },
    ['WEAPON_KIT_METAL_DETECTOR'] = {
        label = 'Metal Detector',
        weight = 0.45,
    },
    ['WEAPON_THROWN_DYNAMITE'] = {
        label = 'Dynamite',
        weight = 0.19,
    },
    ['WEAPON_THROWN_MOLOTOV'] = {
        label = 'Molotov',
        weight = 0.45,
    },
    ['WEAPON_BOW_IMPROVED'] = {
        label = 'Improved Bow',
        weight = 1.10,
    },
    ['WEAPON_MELEE_MACHETE_COLLECTOR'] = {
        label = 'Machete Collector',
        weight = 1.40,
    },
    ['WEAPON_MELEE_LANTERN_ELECTRIC'] = {
        label = 'Electric Lantern',
        weight = 0.95,
    },
    ['WEAPON_MELEE_TORCH'] = {
        label = 'Torch',
        weight = 1.50,
    },
    ['WEAPON_MOONSHINEJUG_MP'] = {
        label = 'Moonshine Jug',
        weight = 2.00,
    },
    ['WEAPON_THROWN_BOLAS'] = {
        label = 'Bolas',
        weight = 0.55,
    },
    ['WEAPON_THROWN_BOLAS_HAWKMOTH'] = {
        label = 'Bolas Hawkmoth',
        weight = 0.65,
    },
    ['WEAPON_THROWN_BOLAS_IRONSPIKED'] = {
        label = 'Bolas Ironspiked',
        weight = 0.75,
    },
    ['WEAPON_THROWN_BOLAS_INTERTWINED'] = {
        label = 'Bolas Intertwined',
        weight = 0.60,
    },
    ['WEAPON_FISHINGROD'] = {
        label = 'Fishing Rod',
        weight = 1.10,
    },
    ['WEAPON_MACHETE_HORROR'] = {
        label = 'Machete Horror',
        weight = 1.40,
    },
    ['WEAPON_MELEE_LANTERN_HALOWEEN'] = {
        label = 'Lantern Haloween',
        weight = 0.95,
    },
    ['WEAPON_MELEE_HAMMER'] = {
        label = 'Hammer',
        weight = 1.25,
    },
    ['WEAPON_REVOLVER_DOUBLEACTION_GAMBLER'] = {
        label = 'High Roller Double-Action Revolver',
        weight = 1.05,
    },
}

```
