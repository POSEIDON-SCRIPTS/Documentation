# config.lua

```lua
Config = {}

Config.Debug = true -- if you want to show the id in the name of the blips from database

Config.Blips = {
    {
        name = 'Test blip',
        position = vector3(2728.4309, -1414.4446, 46.1770),
        data = {
            model = 'blip_hire_camp_follower',
            scale = 25.0,
            modifier = 'BLIP_MODIFIER_DEBUG_GREEN',
            zone = true, -- True if you want to create a zone
        },
    }
    
}



Config.BlipInput = {
    title = "Blip",
    form = {
        {
            label = "Blip model",
            id = "model",
            type = "string",
        },
        {
            label = "Blip modifier",
            id = "modifier",
            type = "string",
            required = false
        },
        {
            label = "Blip scale",
            id = "scale",
            type = "float",
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


Config.BlipNameInput = {
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


Config.BlipSearchInput = {
    title = "Search Blip",
    form = {
        {
            label = "Blip Name",
            id = "name",
            type = "string",
            required = false
        },
    }
}

Config.MenuAlign = 'right' -- top-right, top-left, bottom-right, bottom-left

Config.Commands = {
    [1] = {
        Command = 'create_blip', -- or false to disable it
        Description = 'Create a blip with the specified parameters.',
        Parameters = {},
        Groups = {'owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [2] = {
        Command = 'edit_blip', -- or false to disable it
        Description = 'Edit a blip with the specified parameters.',
        Parameters = {
            { name="id", help="Specify the blip id to edit." },
        },
        Groups = {'Owner', 'Administrator', 'Fondator', 'admin'} 
    },
    [3] = {
        Command = 'toggle_debug_blips', -- or false to disable it
        Description = 'Toggle debug blips on or off.',
        Parameters = {},
        Groups = {'owner', 'Administrator', 'Fondator', 'admin'}
    },
    [4] = {
        Command = 'edit_blips', -- or false to disable it
        Description = 'Edit blips with the specified parameters.',
        Parameters = {},
        Groups = {'owner', 'Administrator', 'Fondator', 'admin'}
    }
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['debug_name'] = "%s (%s)",

        ['not_set'] = "Not set",
        ['set'] = "Set",
        ['enabled'] = "Enabled",
        ['disabled'] = "Disabled",

        -- Zone descriptors
        ['zone_main_location'] = "Main location",
        ['zone_zone'] = "Zone enabled",
        ['zone_name'] = "Name",
        ['zone_blip'] = "Blip sprite",
        ['zone_blip_modifier'] = "Blip modifier",
        ['zone_scale'] = "Scale",

        -- Menu items
        ['set_main_location'] = "Set main location",
        ['set_main_location_desc'] = "Set the position of the blip",
        ['set_main_location_success'] = "Main location set successfully",

        ['set_name'] = "Set blip name",
        ['set_name_desc'] = "Set the display name of the blip",
        ['set_name_success'] = "Blip name set successfully",

        ['set_blip'] = "Set blip details",
        ['set_blip_desc'] = "Set the sprite, modifier, and scale of the blip",
        ['set_blip_success'] = "Blip details set successfully",

        ['toggle_zone'] = "Toggle zone",
        ['toggle_zone_desc'] = "Enable or disable zone area for this blip",
        ['zone_enabled'] = "Zone enabled",
        ['zone_disabled'] = "Zone disabled",

        ['create_blip'] = "Create blip",
        ['create_blip_desc'] = "Finish and create the blip",
        ['wrong_arguments'] = "You must set location, name, model and scale",

        ['delete_blip'] = "Delete blip",
        ['delete_blip_desc'] = "Delete this blip",
        ['delete_blip_fail'] = "Blip not deleted",
        ['delete_blip_success'] = "Blip deleted successfully",
        ['input_yes'] = "YES",

        ['edit_blip'] = "Save changes",
        ['edit_blip_desc'] = "Save and update the current blip",
        ['edit_blip_success'] = "Blip updated successfully",

        ['not_allowed'] = "You are not allowed to use this command",
        ['blip_not_found'] = "Blip not found with this ID",
        ['debug_enabled'] = "Debug mode enabled",
        ['debug_disabled'] = "Debug mode disabled",
        ['blip_list'] = 'Blip List',
        ['blip_desc'] = 'Press to edit the following blip:',
        ['search_results'] = "Search Results",
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
