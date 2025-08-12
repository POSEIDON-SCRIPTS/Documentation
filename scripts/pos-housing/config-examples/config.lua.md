# config.lua

```lua
Config = {}

Config.Distances = {
    OpenMenu = 4, -- Distance to open the house menu
    BuyHouse = 4, -- Distance to buy a house
    FurnitureInteract = 3, -- Distance to interact with furniture
    OpenStash = 3, -- Distance to open the stash
    ChangeLock = 4,
}

Config.Offset = {
    minZ = 0.0,
    maxZ = 0.0,
}


Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = 'https://discord.com/api/webhooks/1320745401455742997/aHN-uBCSyV6fgUvBrfgbE9yG_6N3QQhT8eeZAhGmx4HrhfNic6_x68MbHYIoMZwb39Oy', -- Default webhook for all deposits

    buyHouseMoney = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    buyHouseKey = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    createHouse = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    ownerUpdateWebhook = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    ownerUpdateName = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    ownerAddAccess = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    ownerRemoveAccess = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    ownerTransferHouse = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    ownerSellHouse = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    changeHouseLocks = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHousePrice = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseLocations = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseMain = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseType = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseName = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseTransfer = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseSell = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseAddAccess = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseRemoveAccess = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseLockId = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    updateHouseWebhook = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    deleteHouse = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },

    buyFurniture = {
        sensitive = true, -- True or a specific webhook
        nonSensitive = '',
    },
}



Config.Controls = {
    BuyMoney = 0x760A9C6F,
    OpenMenu = 0x760A9C6F,
    UseFurniture = 0x760A9C6F,
    AddLocation = 0x8AAA0AD4,
    RemoveLocation = 0x4AF4D473,
    Confirm = 0x760A9C6F,
    ChangeLock = 0x760A9C6F,


    up = 0x07CE1E61,
    down = 0xF84FA74F,
    left = 0xA65EBAB4,
    right = 0xDEB34313,
    forward = 0x6319DB71,
    backward = 0x05CA7C52,
    
    rotateLeft = 0xE6F612E4,
    rotateRight = 0x1CE6D9EB,
}


Config.KeysBuying = {
    enabled = true, -- If true, the player will be able to buy the keys for the house. If false, the player will not be able to buy the keys.
    amount = {
        stash = 1,
        house = 1,
        door = 1,
    }
} 

Config.Locksmith = {
    enableNpc = true, -- If true, the player will be able to interact with the locksmith NPC to change locks. If false, the player will be able to buy only keys.
    Jobs = {
        'police', -- List of jobs that can change locks.
    },
    
    Items = {
        stash = 'cheie_cufar',
        house = 'cheie_casa',
        door = 'cheie_usa',
        locksmith = 'mdt',
    },

    BlipModel = "blip_mp_playlist_freeforall",
    Ped = "CS_mradler",  -- Use string for Ped model
    Positions = {
        vector4(2715.8452, -1194.2130, 50.6709, 104.6428)
    },
    Prices = {
        [1] = {
            house = 1,
            stash = 1,
            door = 1,
            change = 1,
        }, 
        [2] = {
            house = 2,
            stash = 2,
            door = 2,
            change = 2,
        },
        [3] = {
            house = 3,
            stash = 3,
            door = 3,
            change = 3,
        },
        [4] = {
            house = 4,
            stash = 4,
            door = 4,
            change = 4,
        },
        [5] = {
            house = 5,
            stash = 5,
            door = 5,
            change = 5,
        },
    }
}


Config.HouseTypes = {
    [1] = {
        stash = 500, 
        furniture = {
            outfit = false,
            stash = true,
            phone = false,
            crafting = false,
        },
        farming = false,
    },
    [2] = {
        stash = 1000,
        furniture = {
            outfit = false,
            stash = true,
            phone = false,
            crafting = false,
        },
        farming = false,
    },
    [3] = {
        stash = 1500,
        furniture = {
            outfit = false,
            stash = true,
            phone = false,
            crafting = false,
        },
        farming = false,
    },
    [4] = {
        stash = 2000,
        furniture = {
            outfit = false,
            stash = true,
            phone = false,
            crafting = false,
        },
        farming = false,
    },
    [5] = {
        stash = 2500,
        furniture = {
            outfit = true,
            stash = true,
            phone = true,
            crafting = true,
        },
        farming = true,
    },
}


Config.Movement = {
    Offsets = {
        x = 0.2,                -- Left and right movement speed multiplier
        y = 0.2,                -- Forward and backward movement speed multiplier
        z = 0.1,                -- Upward and downward movement speed multiplier
        rx = 3,               -- Rotation speed multiplier
    },
}

Config.HouseAccess = { -- Who can see/acces all the stash houses.
    { job = 'police', grades = nil }, -- grades = nil or table 
}


Config.Blips = {
    ['owned'] = {
        blip = "blip_proc_home",
        modifier = "BLIP_MODIFIER_MP_COLOR_20",
    },

    ['personal'] = {
        blip = "blip_proc_home",
        modifier = "BLIP_MODIFIER_MP_COLOR_20",
    },
    
    ['sale'] = {
        blip = "blip_robbery_home",
        modifier = nil,
    },

    ['private'] = { -- only jobs can see it
        blip = "blip_proc_home_locked",
        modifier = "BLIP_MODIFIER_MP_COLOR_13",
    },

    ['locksmith'] = {
        scale = 1.0,
        model = 'blip_ambient_posse_deputy',
        modifier = 'BLIP_MODIFIER_DEBUG_GREEN',
    }
}


Config.MenuAlign = 'top-left' -- top-right, top-left, bottom-right, bottom-left

Config.Commands = {
    [1] = {
        Command = 'createhouse', -- or false to disable it
        Description = 'Create a house with the specified parameters.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [2] = {
        Command = 'edithouse', -- or false to disable it
        Description = 'Edit a house with the specified parameters.',
        Parameters = {
            { name="id", help="Specify the house id to edit." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [3] = {
        Command = 'deletehouse', -- or false to disable it
        Description = 'Delete a house with the specified parameters.',
        Parameters = {
            { name="id", help="Specify the house id to delete." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'}
    },
    [4] = {
        Command = 'cancellocksmith', -- or false to disable it
        Description = 'Cancel the locksmith action.',
        Parameters = {},
        Groups = {}
    },
    [5] = {
        Command = 'togglehousesign', -- or false to disable it
        Description = 'Toggle the house sign on or off.',
        Parameters = {},
        Groups = {}
    }
}

Config.PriceInput = {
    title = "House Price",
    form = {
        {
            label = "Money",
            id = "money",
            type = "string",
            required = false
        },

        {
            label = "Coin duration (or nothing for permanent)",
            id = "coin_duration",
            type = "string",
            required = false
        },

        {
            label = "Coins",
            id = "coins",
            type = "string",
            required = false
        },

    }
}

Config.SellConfirmationInput = {
    title = "Sell Confirmation",
    form = {
        {
            label = "Are you sure you want to sell this house? Type 'SELL' to confirm.",
            id = "confirm",
            type = "string",
            required = true
        },
    }
}

Config.HouseTypeInput = {
    title = "House Type",
    form = {
        {
            label = "Type",
            id = "house_type",
            type = "string",
            required = true
        },
    }
}

Config.NameInput = {
    title = "House Name",
    form = {
        {
            label = "Name",
            id = "name",
            type = "string",
            required = true
        },
    }
}

Config.WebhookInput = {
    title = "Webhook",
    form = {
        {
            label = "Webhook",
            id = "webhook",
            type = "string",
            required = true
        },
    }
}

Config.Resources = {
    ['POS-IdentityCard'] = true,
}

Config.Taxes = {
    maxTaxes = 1000, -- amount of taxes someone needs to have for the house to be removed or not be able to buy. 
    houseTax = 10, -- percentage of house price in cash
    taxDays = 30, -- what interval to apply the taxes
    checkDuration = 3600 * 1000, -- how often to check for taxes in milliseconds
}

Config.ProgressBars = {
    ['change_lock'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Changing lock...',
        time = 10000,
        animation = {
            anim = "idle_c",
            flags = 1,
            animDict = "amb_camp@world_camp_jack_plant@idle_a"
        }
    }
}

Config.HouseLimitIncrease = {
    ['groups'] = {
        ['admin'] = {
            normal = 1, -- How many houses can a player own
            vip = 1, -- How many VIP houses can a player own
            access = 1, -- How many houses can a player have access to besides owned ones
            tenants = 1, -- How many players can a player add to his house
        }
    },
    ['character_groups'] = {
        ['vip'] = {
            normal = 1, -- How many houses can a player own
            vip = 1, -- How many VIP houses can a player own
            access = 1, -- How many houses can a player have access to besides owned ones
            tenants = 1, -- How many players can a player add to his house
        }
    },
    ['jobs'] = {
        ['police'] = {
            normal = 1, -- How many houses can a player own
            vip = 1, -- How many VIP houses can a player own
            access = 1, -- How many houses can a player have access to besides owned ones
            tenants = 1, -- How many players can a player add to his house
        }
    }
}

Config.HouseLimit = {
    ['normal'] = {
        limit = 1,
    },

    ['vip'] = {
        limit = 2,
    },

    ['access'] = { -- How many houses can a player have access to besides owned ones
        limit = 1,
    },

    ['tenants'] = { -- How many players can a player add to his house
        limit = 1,
    },

}

Config.Settings = {
    stashFromKey = true, -- if true, you will be able to place the stash from the key menu, if false, you will need to place the stash as a furniture
}

Config.SellReward = {
    ['normal'] = 99, -- 99% of the house price
    ['vip'] = 99, -- 99% of the house price

}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do this.',
        ['create_house'] = 'Create a house!',
        ['set_price'] = 'Set Price.',
        ['set_price_desc'] = 'Set the price of the house with the specified parameters.',
        ['set_house_type'] = 'Set Type.',
        ['set_house_type_desc'] = 'House types are found and taken from the config',
        ['set_main_menu'] = 'Set Main Menu.',
        ['set_main_menu_desc'] = 'Set the main menu location.',
        ['set_locations'] = 'Set Locations.',
        ['set_locations_desc'] = 'Set the locations of the house with the specified parameters.',
        ['set_name'] = 'Set Name.',
        ['set_name_desc'] = 'Set the name of the house with the specified parameters.',
        ['confirm_house'] = 'Confirm.',
        ['confirm_house_desc'] = 'Confirm the house with the specified parameters.',
        ['access'] = 'Access.',
        ['access_desc'] = 'Access the house with the specified parameters.',
        ['set_webhook'] = 'Set Webhook.',
        ['set_webhook_desc'] = 'Set the webhook of the house with the specified parameters.',
        ['sell'] = 'Sell House.',
        ['sell_desc'] = 'Sell the house with the specified parameters.',
        ['transfer'] = 'Transfer House.',
        ['transfer_desc'] = 'Transfer the house with the specified parameters.',
        ['owner_menu'] = 'House Owner Menu',
        ['add_access'] = 'Add Access', 
        ['add_access_desc'] = 'Add access to the house for another player.',
        ['remove_access_desc'] = 'Remove access to the house for another player.',

        ['sell_input'] = 'SELL', -- Message for the prompt

        ['confirm'] = 'Confirm',
        ['finish'] = 'Finish',
        ['cancel'] = 'Cancel',
        ['add_location'] = 'Add location',
        ['remove_location'] = 'Remove location',
        ['add_locations'] = 'Add locations. (#%s)',

        ['wrong_arguments'] = 'You have entered wrong arguments.',
        ['price_set'] = 'Price set successfully!',
        ['type_set'] = 'Type set successfully!',
        ['name_set'] = 'Name set successfully!',
        ['main_set'] = 'Main set successfully!',
        ['locations_set'] = 'Locations set successfully!',
        ['house_created'] = 'House created successfully!',
        ['webhook_set'] = 'Webhook set successfully!',
        ['house_sold'] = 'House sold successfully!',
        ['house_transferred'] = 'House transferred successfully!',
        ['access_added'] = 'Access added successfully!',
        ['access_removed'] = 'Access removed successfully!',

        ['house_not_found'] = 'You do not have access to this house or you are not in the range of a house.',

        ['private_property'] = 'Private Property',
        ['personal_property'] = 'Personal Property',
        ['property_for_sale'] = 'Property for Sale',
        ['owned_property'] = 'Owned Property',
        ['house_deleted'] = 'House deleted successfully!',
        ['edit_house'] = 'Edit house',

        ['house_title'] = '%s (%s)', -- house name (id) 
        ['buy_money_prompt'] = 'Buy with money',
        ['buy_house_info'] = '%s. Money: %s',
        ['house_bought'] =  'Congratulations! You have successfully bought the house.',
        ['property_owned'] = 'This property is already owned by someone else.',
        ['not_enough_money'] = 'You do not have enough money to do this.',
        ['house_limit'] = 'You have reached the house limit for your account.',
        ['cannot_do_self'] = 'You cannot perform this action on yourself.',

        ['furniture_limit'] = 'You have reached the furniture limit for this house.',

        
        ['open_menu'] = 'Open Menu',
        ['menu_house'] = '%s (%s)',
        ['buy_stash_key_desc'] = 'Buy stash key for: $%s',
        ['buy_stash_key'] = 'Stash key',
        ['buy_house_key'] = 'Buy house key',
        ['buy_house_key_desc'] = 'Buy a key for the house: $%s',
        ['buy_door_key'] = 'Buy door key',
        ['buy_door_key_desc'] = 'Buy a key for the door: $%s',
        ['confirm_deletion'] = 'Confirm deletion.',
        ['furniture_price'] = 'Price to buy this furniture: $%s',
        ['furniture_placement'] = 'Furniture Placement | Move from arrows.',
        ['up_down'] = 'Up/Down',
        ['rotate'] = 'Rotate Left/Right',
        ['locksmith_title'] = 'Locksmith',
        ['house_key'] = 'House Key: %s (%s)',
        ['key_bought'] = 'You have successfully bought the key.',
        ['not_inside'] = 'You are not inside a house.',

        ['house_menu'] = 'House Menu',
        ['house_menu_desc'] = 'Access your house settings and manage your property.',
        ['change_locks'] = 'Change Locks.',
        ['change_locks_desc'] = 'Change the locks of your house to secure it: $%s',
        ['furniture_menu'] = 'Furniture Menu',
        ['furniture_menu_desc'] = 'Access and manage furniture for your house.',
        ['add_furniture'] = 'Add Furniture',
        ['add_furniture_desc'] = 'Add new furniture to your house.',
        ['remove_furniture'] = 'Remove Furniture',
        ['remove_furniture_desc'] = 'Remove existing furniture from your house.',
        ['object_added'] = 'Furniture added successfully!',
        ['object_removed'] = 'Furniture removed successfully!',
        ['locksmith_next_location'] = 'Proceed to the next location to continue the locksmith process.',
        ['locksmith_go_begining'] = 'Go to the beginning of the locksmith process to end.',
        ['already_locksmith'] = 'You are already interacting with the locksmith.',
        ['locksmith_started'] = 'You have started the process of locksmithing. Go to your house to continue.',
        ['locksmith_cancelled'] = 'You have cancelled the locksmith process.',
        ['locksmith_ended'] = 'You have successfully completed the locksmith process.',
        ['lockid_set'] = 'The lock ID has been set successfully!',
        ['change_lockid'] = 'Change lock id.',
        ['change_lockid_desc'] = 'The lock ID is the ID of the database lock. Changing this will render current keys useless.',
        ['use_furniture'] = 'Use Furniture.',

        ['edit_doors'] = 'Edit Doors.',
        ['edit_doors_desc'] = 'Edit the doors of the house with the specified parameters.',
        ['add_door'] = 'Add Door',
        ['remove_door'] = 'Remove Door',
        ['add_door_desc'] = 'Add a new door to the house with the specified parameters.',
        ['remove_door_desc'] = 'Remove an existing door from the house with the specified parameters.',
        ['normal_door'] = 'Normal Door',
        ['double_door'] = 'Double Door',
        ['house_name'] = 'House Name',
        ['set_stash_location'] = 'Set Stash Location.',
        ['set_stash_location_desc'] = 'Set the location of the stash within the house.',

        -- Webhooks
        ['webhook_user_information'] = 'User Information',
        ['webhook_target_information'] = 'Target Information',

        ['webhook_buyHouseMoney'] = 'House Purchased with Money',
        ['webhook_buyHouseMoney_info'] = '%s has purchased house ID %s for %s using money.',
        
        ['webhook_payment_method'] = 'Payment Method',
        ['webhook_payment_money'] = 'Cash Payment',
        ['webhook_house_id'] = 'House ID',
        ['webhook_house_price'] = 'House Price',

        ['webhook_buyHouseKey'] = 'House Key Purchased',
        ['webhook_buyHouseKey_info'] = '%s has purchased a house key for house ID %s of type %s for %s using money.',
        
        ['webhook_house_key_type'] = 'Key Type',
        ['webhook_house_key_price'] = 'Key Price',

        ['webhook_createHouse'] = 'A new house was created!',
        
        ['webhook_house_name'] = 'House Name',
        ['webhook_house_type'] = 'House Type',
        ['webhook_house_coin_price'] = 'Coin Price',
        ['webhook_house_coin_duration'] = 'Coin Duration',
        ['webhook_house_lockid'] = 'Lock ID',
        ['webhook_house_position'] = 'Main Position',

        ['no_tenants'] = 'No Tenants',
        ['not_active'] = 'Not Active',
        ['locked'] = 'Locked',
        ['unlocked'] = 'Unlocked',

        ['house_id'] = 'House ID',
        ['house_owner'] = 'House Owner',
        ['house_tenants'] = 'House Tenants',
        ['house_access'] = 'House Access',
        ['house_type'] = 'House Type',
        ['house_price'] = 'House Price',
        ['house_coins'] = 'House Coins',
        ['house_lockid'] = 'House Lock ID',
        ['house_doors'] = 'House Doors',
        ['no_doors'] = 'No Doors',
        ['house_main'] = 'House Main Menu',
        ['house_locations'] = 'House Locations',
        ['set'] = 'Set',
         

        ['webhook_house_n_a'] = 'N/A',
        ['days'] = 'days',

        ['webhook_createHouse_info'] = '%s has created a new house with ID %s',

        ['webhook_ownerUpdateWebhook'] = 'Owner Updated Webhook',
        ['webhook_new_webhook'] = 'New Webhook URL',
        ['webhook_new_name'] = 'New Name',
        ['webhook_ownerUpdateWebhook_info'] = '%s has updated the webhook for house ID %s to %s.',

        ['webhook_ownerUpdateName'] = 'Owner Updated Name',
        ['webhook_ownerUpdateName_info'] = '%s has updated the name for house ID %s to %s.',

        ['webhook_new_access'] = 'New Access',
        ['webhook_ownerAddAccess'] = 'Owner Added Access',
        ['webhook_ownerAddAccess_info'] = '%s has added %s to the access list for house ID %s.',

        ['webhook_removed_access'] = 'Removed Access',
        ['webhook_ownerRemoveAccess'] = 'Owner Removed Access',
        ['webhook_ownerRemoveAccess_info'] = '%s has removed %s from the access list for house ID %s.',

        ['webhook_house_sold'] = 'House Sold',
        ['webhook_house_sold_info'] = '%s has sold house ID %s for %s.',
        ['webhook_removed_access_id'] = 'Removed Access ID',

        ['webhook_ownerTransferHouse'] = 'Owner Transferred House',
        ['webhook_ownerTransferHouse_info'] = '%s has transferred house ID %s to %s.',
        ['webhook_new_owner'] = 'New Owner',

        ['webhook_ownerSellHouse'] = 'Owner Sold House',
        ['webhook_ownerSellHouse_info'] = '%s has sold house ID %s.',
        ['webhook_house_reward'] = 'House Reward',
        ['coins'] = 'Coins',
        ['identity_required'] = 'You need an identity card in order to do this.',
 
        ['webhook_price'] = 'Price',
        ['webhook_new_lockid'] = 'New Lock ID',
        ['select_category_desc'] = 'Select a category to view available options.',
        ['select_furniture_category'] = 'Select furniture category',

        ['webhook_changeHouseLocks'] = 'Change House Locks',
        ['webhook_changeHouseLocks_info'] = '%s has changed the locks for house ID %s. New lock id: %s',

        ['webhook_updateHousePrice'] = 'Update House Price',
        ['webhook_updateHousePrice_info'] = '%s has updated the price for house ID %s.',

        ['webhook_house_zone'] = 'House Zone',
        ['webhook_updateHouseLocations'] = 'Update House Locations',
        ['webhook_updateHouseLocations_info'] = '%s has updated the locations for house ID %s.',

        ['webhook_updateHouseMain'] = 'Update House Main Menu',
        ['webhook_updateHouseMain_info'] = '%s has updated the main menu location for house ID %s.',
        ['webhook_house_main'] = 'House Main Menu',
        ['webhook_updateHouseType'] = 'Update House Type',
        ['webhook_updateHouseType_info'] = '%s has updated the type for house ID %s to %s.',

        ['webhook_updateHouseName'] = 'Update House Name',
        ['webhook_updateHouseName_info'] = '%s has updated the name for house ID %s to %s.',

        ['webhook_updateHouseTransfer'] = 'Update House Transfer',
        ['webhook_updateHouseTransfer_info'] = '%s has transferred house ID %s to %s.',

        ['webhook_updateHouseSell'] = 'Update House Sell',
        ['webhook_updateHouseSell_info'] = '%s has sold the house ID %s.',

        ['webhook_updateHouseAddAccess'] = 'Update House Add Access',
        ['webhook_updateHouseAddAccess_info'] = '%s has added %s to the access list for house ID %s.',

        ['webhook_updateHouseRemoveAccess'] = 'Update House Remove Access',
        ['webhook_updateHouseRemoveAccess_info'] = '%s has removed %s from the access list for house ID %s.',

        ['webhook_updateHouseLockId'] = 'Update House Lock ID',
        ['webhook_updateHouseLockId_info'] = '%s has updated the lock ID for house ID %s to %s.',

        ['webhook_updateHouseWebhook'] = 'Update House Webhook',
        ['webhook_updateHouseWebhook_info'] = '%s has updated the webhook for house ID %s to %s.',
    
        ['webhook_deleteHouse'] = 'Delete House',
        ['webhook_deleteHouse_info'] = '%s has deleted house ID %s.',

        ['house_menu_enabled'] = 'The house menu has been enabled successfully.',
        ['house_menu_disabled'] = 'The house menu has been disabled successfully.',
        ['buy_furniture_group'] = 'Buy Furniture',
        ['buy_furniture'] = 'Price: $%s',
        ['not_enough_space'] = 'You do not have enough space to perform this action.',
        ['furniture_bought'] = 'You have successfully bought %s.',


        ["webhook_furniture_category"] = "Category",
        ["webhook_furniture_id"] = "Furniture ID",
        ["webhook_furniture_name"] = "Furniture Name",
        ["webhook_furniture_price"] = "Price",

        ['webhook_buyFurniture'] = 'Furniture Purchased',
        ['webhook_buyFurniture_info'] = '%s has purchased furniture "%s" for $%s.',
        ['stash_location_set'] = 'Stash location set successfully!',
        ['open_stash'] = 'Open Stash',
        ['open_stash_info'] = 'Stash %s',
        ['not_a_locksmith'] = 'You are not a locksmith and cannot perform this action.',
        ['not_in_house_zone'] = 'You are not in a house zone.',
        ['no_player_selected'] = 'No player selected. Please select a player to proceed.',
        ['player_not_allowed'] = 'The player does not have access to this house.',
        ['locksmith_location'] = 'Locksmith location',
        ['change_locks_group'] = '%s (ID: %s)',
        ['change_locks_prompt'] = 'Change Lock',
        ['house_tax_title'] = 'House tax for "%s"',
        ['house_tax_description'] = 'You have unpaid house tax for house %s (%s).',
        ['too_many_taxes'] = 'You have too many unpaid taxes.. You cannot do that!',
        ['player_too_many_taxes'] = 'The player has too many unpaid taxes. You cannot do that!',
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
