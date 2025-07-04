# config.lua

```lua
Config = {}

Config.DistanceToOpenMenu = 5.0 -- Distance to open the menu

Config.Settings = {
    model = "stagecoach001x", 
    driver = "cs_bivcoachdriver", 
    speed = 6.0,
    driveStyle = 786603, --  https://vespura.com/fivem/drivingstyle/
    camera = true, 
    distanceToEnd = 10.0, 
    guard = {
        model = "cs_bivcoachdriver",
        amount = 2,
        weapon = "WEAPON_RIFLE_BOLTACTION",
    },
    dynamicPrice = true, -- if true, the price will be calculated based on the distance between the two locations in km
    -- guard = false
}


Config.BlipSettings = {
    blip = "blip_ambient_warp",
    modifier = false
}

Config.PropSettings = {
    prop = "p_sca_sign",
}

Config.MenuAlign = 'right'

Config.Commands = {
    [1] = {
        Command = 'cancelcaravan', -- or false to disable it
        Description = 'Cancel the current ride.',
        Parameters = {},
        Groups = {}
    },

}

Config.Locations = {
    [1] = {
        name = "Saint Denis",
        position = vector4(2691.623046875, -1436.6051025390625, 45.01542663574219, 114.67), -- Menu position
        wagon = vector4(2681.19189453125, -1440.2666015625, 46.06610488891601, -66.23), -- Position for wagon
        price = 1  -- Price in km to go from this location to another one
    },
    [2] = {
        name = "Blackwater",
        position = vector4(-886.2470703125, -1242.76611328125, 42.36553192138672, -2.557), 
        wagon = vector4(-870.7986450195312, -1241.309326171875, 43.33686065673828, -2.557),
        price = 1
    },
    [3] = {
        name = "Valentine",	
        position = vector4(-187.3721, 645.0938, 112.4660, 137.7453),
        wagon = vector4(-197.3860, 650.5486, 112.8155, 141.7542),
        price = 1
    },
    [4] = {
        name = "Rhodes",
        position = vector4(1245.669921875, -1290.7127685546875, 74.82366943359375, 47.218),
        wagon = vector4(1236.9051513671875, -1267.71484375, 75.16978454589844, -35.216),
        price = 1
    },
    [5] = {
        name = "Strawberry",
        position = vector4(-1752.435302734375, -405.5144348144531, 154.42361450195312, -30.108),
        wagon = vector4(-1750.9742431640625, -401.6171569824219, 155.50173950195312, -120.316),
        price = 1
    },
    [6] = {
        name = "Annesburg",
        position = vector4(2923.36669921875, 1283.4749755859375, 43.42635345458984, 162.351),
        wagon = vector4(2927.951416015625, 1295.222412109375, 44.4082145690918, 161.64),
        price = 1
    },
    [7] = {
        name = "Armadillo",
        position = vector4(-3724.4211, -2616.4856, -14.4559, 176.9862),
        wagon = vector4(-3715.7007, -2617.8833, -13.5703, 358.7037),
        price = 1
    }
}

Config.Controls = {
    OpenMenu = 0x760A9C6F,
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['caravan_start'] = 'The ride has been started, please get in the wagon and enjoy your ride!',
        ['caravan_end'] = 'You have reached your destination and the caravan has ended..',
        ['caravan_stop'] = 'Get back in the caravan to continue your ride.',
        ['caravan_resumed'] = 'The caravan ride has been resumed, enjoy the ride!',
        ['caravan_cancel'] = 'The caravan ride has been cancelled.',
        ['caravan_menu'] = 'Caravan Menu',
        ['caravan_start_desc'] = 'Start the caravan ride',
        ['confirm_caravan'] = 'Confirm the caravan ride',
        ['caravan_price'] = 'Price: %s$',
        ['not_enough_money'] = 'You do not have enough money to start this ride.',
        ['open_menu'] = 'Open Menu',
        ['caravan_not_active'] = 'You have not started a caravan ride.',
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
