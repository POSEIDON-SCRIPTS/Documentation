# config.lua

```lua
Config = {}

Config.ServerName = "POSEIDON PD" -- Server Name or false
Config.BadgeItem = 'insigna' -- Item name for the badge
Config.UIStyles = {
    DefaultName = {
        top = '130px',
        type = 'circle',
        circle = { type = 'normal', angle = 115 },
        fontSize = '30px',
        left = '78%',
        rotate = '79deg',
        color = "#161928"
    },
    DefaultServer = {
        top = '137px',
        left = '21%',
        fontSize = '30px',
        type = 'circle',
        rotate = '98deg',
        circle = { type = 'reverse', angle = 115 },
        color = "#161928"
    },
    SilverName = {
        top = '115px',
        left = "50%",
        type = 'circle',
        circle = { type = 'normal', angle = 115 },
        color = "#654a29"
    },
    SilverServer = {
        top = '262px',
        left = '40%',
        type = 'normal',
        circle = { type = 'normal', angle = 115 },
        color = "#654a29"
    },
    SheriffName = {
        top = '94px',
        type = 'circle',
        circle = { type = 'normal', angle = 115 },
        color = "#654a29"
    },
    SheriffServer = {
        top = '240px',
        left = '35%',
        type = 'normal',
        fontSize = '26px',
        circle = { type = 'normal', angle = 115 },
        color = "wheat"
    }
}

-- Badge definitions per job/grade
Config.Badges = {
    police = {
        [1] = {
            prop = 's_badgepolice01x',
            image = 'marshal',
            showName = true,
            ui = {
                name = Config.UIStyles.DefaultName,
                server = Config.UIStyles.DefaultServer
            }
        },
        [2] = {
            prop = 's_badgepinkerton01x',
            image = 'silverbadge',
            showName = true,
            ui = {
                name = Config.UIStyles.SilverName,
                server = Config.UIStyles.SilverServer
            }
        },
        [3] = {
            prop = 's_badgeusmarshal01x',
            image = 'sheriff',
            showName = true,
            ui = {
                name = Config.UIStyles.SheriffName,
                server = Config.UIStyles.SheriffServer
            }
        },
    }
}

Config.MenuAlign = 'left' 

Config.Offsets = {
    x = 0.005,
    y = 0.005,
    z = 0.005,
    xRot = 2,
    yRot = 2,
    zRot = 2,
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do this.',
        ['go_up'] = 'Go Up',
        ['go_down'] = 'Go Down',
        ['go_forward'] = 'Go Forward',
        ['go_back'] = 'Go Back',
        ['rotate_left'] = 'Rotate Left',
        ['rotate_right'] = 'Rotate Right',
        ['modify_positions'] = 'Modify Positions',
        ['toggle_badge'] = 'Toggle Badge',
        ['toggle_badge_desc'] = 'Toggle the badge visibility.',
        ['modify_positions_desc'] = 'Modify the position of the badge.',
        ['go_up_desc'] = 'Move the badge up.',
        ['go_down_desc'] = 'Move the badge down.',
        ['go_forward_desc'] = 'Move the badge forward.',
        ['go_back_desc'] = 'Move the badge back.',
        ['rotate_left_desc'] = 'Rotate the badge to the left.',
        ['rotate_right_desc'] = 'Rotate the badge to the right.',
        ['go_left'] = 'Go Left',
        ['go_right'] = 'Go Right',
        ['go_left_desc'] = 'Move the badge to the left.',
        ['go_right_desc'] = 'Move the badge to the right.',
        ['badge_menu'] = 'Badge Menu',
        ['rotate_up'] = 'Rotate Up',
        ['rotate_down'] = 'Rotate Down',
        ['rotate_up_desc'] = 'Rotate the badge up.',
        ['rotate_down_desc'] = 'Rotate the badge down.',
        ['wrong_arguments'] = 'Wrong arguments provided.',
        ['badge_not_found'] = 'The badge for your job was not found.',
        ['create_badge'] = 'Create Badge',
        ['create_badge_desc'] = 'Create a badge for your job.',
        ['show_badge'] = 'Show Badge',
        ['show_badge_desc'] = 'Show the badge of the nearest player.',
        ['badge_not_created'] = 'The badge has not been created yet.',
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
