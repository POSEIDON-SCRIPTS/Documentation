# config.lua

```lua
Config = {}

Config.DistanceToUnlockDoor = 3

Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = '', -- Default webhook for all deposits

    toggleDoor = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    lockpickDoor = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    createDoor = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    editDoor = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },

    deleteDoor = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },
    
}

Config.Resources = {
    ['POS-Housing'] = true
}

Config.Settings = {
    showMarker = true, -- Show the marker for the door
    usePrompts = false, -- Use prompts for the door
}



Config.HouseUseKey = true -- If you want players to need a key to enter their house, or if you want them to be able to enter without a key (only house owners)

Config.RequireUseItem = false -- If true then the player will need to use an item to unlock the door. If false then the player will be able to unlock the door if the item is in the inventory.
Config.MenuAlign = 'top-left' -- top-right, top-left, bottom-right, bottom-left


Config.HouseIdInput = {
    title = "House ID",
    form = {
        {
            label = "House id",
            id = "house",
            type = "string",
            required = true
        },
    }
}

Config.JobInput = {
    title = "Job",
    form = {
        {
            label = "Job",
            id = "job",
            type = "string",
            required = true
        },
    }
}

Config.ItemInput = {
    title = "Item",
    form = {
        {
            label = "Item",
            id = "item",
            type = "string",
            required = true
        },
    }
}


Config.Controls = {
    ToggleDoor = 0x760A9C6F,

    up = 0x07CE1E61,    
    down = 0xF84FA74F,   
    left = 0xA65EBAB4, 
    right = 0xDEB34313,
    forward = 0x8AAA0AD4, 
    backward = 0x05CA7C52,
    Cancel = 0x4AF4D473,
    Confirm = 0x760A9C6F
}

Config.Lockpicks = {

    ["lockpick"] = {
        durability = 100,
        returnOnRemove = true, -- return items only if the item is removed
        returnItems = false,
        requireAdditionalItems = false,
    },

}


Config.Commands = {
    [1] = {
        Command = 'createdoor', -- or false to disable it
        Description = 'Create a door with the specified parameters.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [2] = {
        Command = 'editdoor', -- or false to disable it
        Description = 'Edit a door with the specified parameters.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    
    [3] = {
        Command = 'deletedoor', -- or false to disable it
        Description = 'Delete a door.',
        Parameters = {},
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS


Config.Text = {
    EN = {
        ["toggle_door_status_prompt"] = "Press to lock/unlock", 
        ["not_allowed"] = "You are not allowed to do this !",
        ["no_door_found_item"] = "No door was found nearby to unlock with this item !",
        ["no_acces_to_open"] = "You don't have acces to open this door !",
        ["wrong_arguments"] = "The arguments are not right for this command !",
        ["admin_door_deleted"] = "The door was deleted succesfully!",
        ["admin_door_created"] = "The door was created succesfully!",
        ["admin_door_edited"] = 'The door was edited succesfully!',
        ["select_door_prompt"] = 'Select door.',
        ["cancel_select_prompt"] = 'Cancel selection',
        ["operation_canceled"] = 'The operation was aborted!',
        ["edit_door_title"] = 'Edit door',
        ["delete_door_title"] = 'Delete door',
        ["create_door_title"] = 'Create door (%s/%s)',
        ['confirm_door_prompt'] = 'Confirm',
        ['go_up_down_prompt'] = 'Up/Down',
        ['go_left_right_prompt'] = 'Left/Right',
        ['lockpick_failed'] = 'The lockpick failed!',
        ['missing_required_item'] = 'You are missing %s %s',
        ['go_forward_backward_prompt'] = 'Forward/Backward',

        ['webhook_user_information'] = 'Player Info',
        ['door_unlocked'] = 'Unlocked',
        ['door_locked'] = 'Locked',

        ['toggle_double_door'] = 'Toggle Double Door',
        ['toggle_double_door_desc'] = 'Toggles the amount of doors that will be set.',
        ['toggle_lockpick'] = 'Toggle Lockpick',
        ['toggle_lockpick_desc'] = 'Toggles if the door can be lockpicked.',
        ['set_house'] = 'Set House',
        ['set_house_desc'] = 'Set the house for the door.',
        ['manage_jobs'] = 'Manage Jobs',
        ['manage_jobs_desc'] = 'Manage the jobs that can access the door.',
        ['manage_items'] = 'Manage Items',
        ['manage_items_desc'] = 'Manage the items that can access the door.',
        ['create_door'] = 'Create door',
        ['create_door_desc'] = 'Create a door with the specified parameters.',
        ['edit_door'] = 'Edit door',
        ['edit_door_desc'] = 'Edit a door with the specified parameters.',

        ['number_doors'] = 'Number of doors',
        ['can_lockpick'] = 'Can lockpick',
        ['yes'] = 'Yes',
        ['no'] = 'No',
        ['house_id'] = 'House ID',
        ['jobs'] = 'Jobs that can open',
        ['items'] = 'Items that can open',
        ['add_job'] = 'Add job',
        ['add_item'] = 'Add item',
        ['remove_jobs_desc'] = 'Press enter to remove this job',
        ['remove_items_desc'] = 'Press enter to remove this item',

        ['job_added'] = 'Job %s was added to the door',
        ['job_removed'] = 'Job %s was removed from the door',
        ['item_added'] = 'Item %s was added to the door',
        ['item_removed'] = 'Item %s was removed from the door',

        
        ['webhook_door_id'] = 'Door ID',
        ['webhook_door_state'] = 'Door State',
        ['webhook_door_jobs'] = 'Jobs',
        ['webhook_door_items'] = 'Items',
        ['webhook_door_created'] = 'Created',
        ['webhook_door_edited'] = 'Edited',
        ['webhook_door_deleted'] = 'Deleted',
        ['webhook_door_coords'] = 'Coords',
        ['webhook_door_lockpick'] = 'Lockpick',
        ['webhook_door_numberDoors'] = 'Number of doors',
        ['webhook_door_clans'] = 'Clans:',
        ['webhook_door_house'] = 'House:',
        

        ['webhook_toggleDoor'] = 'A door was toggled!',
        ['webhook_toggleDoor_info'] = '%s has toggled the door %s. Status: %s',


        ['webhook_lockpickDoor'] = 'A door was lockpicked!',
        ['webhook_lockpickDoor_info'] = '%s has lockpicked the door %s. Status: %s',
        ['webhook_createDoor'] = 'A door was created!',
        ['webhook_createDoor_info'] = '%s has created a door with the following id: %s',
        ['webhook_editDoor'] = 'A door was edited!',
        ['webhook_editDoor_info'] = '%s has edited the door %s',
        ['webhook_deleteDoor'] = 'A door was deleted!',
        ['webhook_deleteDoor_info'] = '%s has deleted the door %s',
    },


}

Config.Movement = {
    Offsets = {
        x = 0.2,                -- Left and right movement speed multiplier
        y = 0.2,                -- Forward and backward movement speed multiplier
        z = 0.1,                -- Upward and downward movement speed multiplier
    },
}

Config.Lockpick = function()
    local MiniGame = exports['bcc-minigames'].initiate()

    local cfg = {
        focus = true, -- Should minigame take nui focus
        cursor = true, -- Should minigame have cursor  (required for lockpick)
        maxattempts = 3, -- How many fail attempts are allowed before game over
        threshold = 10, -- +- threshold to the stage degree (bigger number means easier)
        hintdelay = 500, --milliseconds delay on when the circle will shake to show lockpick is in the right position.
        stages = {
            {
                deg = 25 -- 0-360 degrees
            },
            {
                deg = 0 -- 0-360 degrees
            },
            {
                deg = 300 -- 0-360 degrees
            }
        }
        
    }


    local p = promise.new()
    MiniGame.Start('lockpick', cfg, function(result)
        p:resolve(result.unlocked)
    end)

    return Citizen.Await(p)
end


local isServer = IsDuplicityVersion()
function Notify(source, text, type) --You can replace with your own notification system. Type can be fail, success, info.
    if isServer then
        TriggerClientEvent("POS-Core:notify", source, 'USI', text, type, 5000) 
    else 
        TriggerEvent("POS-Core:notify", 'USI', text, type, 5000)
    end
end

```
