# config.lua

```lua
Config = {}

Config.Resources = {
    ['POS-Housing'] = true,
}

Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = '', -- Default webhook for all deposits

    identity_card_register_real = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },
    identity_card_register_fake = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
    identity_card_update_real = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
    identity_card_update_fake = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
    identity_card_delete_fake = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
    identity_card_offence = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
    identity_card_offence_fine_paid = {
        sensitive = true, -- True or a specific webook
        nonSensitive = '',
    },
}

Config.Controls = {
    OpenMenu = 0x760A9C6F,
}

Config.AgeSettings ={
    min = 18, -- Minimum age to get a card
    max = 99, -- Maximum age to get a card
}

Config.Prices = {
    normal = {
        register = 100,
        update = 50,
        buy = 50,
    },
    fake = {
        register = 100,
        update = 50,
        delete = 50,
        buy = 50,
    }
} 

Config.Settings = {
    distanceToOpen = 5.0, -- Distance to open the menu
}

Config.Locations = {
    [1] = {
        name = 'Saint Denis Station',
        position = vector4(2748.0706, -1396.3884, 45.1831, 30.7514),
        blip = {
            blip = 'blip_special_series_1', -- false to disable
            modifier = false,
        },
        fake = false, -- true to make it so it is only for fake cards, false for real cards
        ped = {
            model = 'CS_mradler' -- false to disable
        }
    },
    [2] = {
        name = 'Rhodes Station',
        position = vector4(1230.2098, -1298.4854, 75.9044, 226.5511),
        blip = {
            blip = 'blip_special_series_1', 
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler' 
        }
    },
    [3] = {
        name = 'Blackwater Station',
        position = vector4(-875.3148, -1330.8729, 42.9579, 253.3495),
        blip = {
            blip = 'blip_special_series_1', 
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler'
        }
    },
    [4] = {
        name = 'Annesburg Station',
        position = vector4(2933.0435, 1282.3058, 43.6529, 66.7525),
        blip = {
            blip = 'blip_special_series_1', 
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler' 
        }
    },
    
    [5] = {
        name = 'Valentine Station',
        position = vector4(-175.3082, 632.0118, 113.0896, 322.7331),
        blip = {
            blip = 'blip_special_series_1', 
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler' 
        }
    },
    [6] = {
        name = 'Strawberry Station',
        position = vector4(-1766.1459, -380.4287, 156.7310, 146.6386),
        blip = {
            blip = 'blip_special_series_1', 
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler' 
        }
    },
    [7] = {
        name = "Armadillo Station",
        position = vector4(-3729.1543, -2601.3101, -13.9377, 179.0721),
        blip = {
            blip = 'blip_special_series_1', 
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler' 
        }
    },
    [8] = {
        name = 'Fake Identity Card',
        position = vector4(2330.9260, -1514.5966, 42.1026, 263.5819), 
        blip = false, 
        fake = true, -- This location is only for fake cards
        ped = {
            model = 'CS_mradler'
        }
    },
    [9] = {
        name = 'Fake Identity Card',
        position = vector4(-5394.3311, -3666.1975, -24.9672, 130.4849), 
        blip = false,
        fake = true,
        ped = {
            model = 'CS_mradler' 
        }
    },
}

Config.MenuAlign = 'right' -- top-right, top-left, bottom-right, bottom-left


Config.Items = {
    identity_card = 'buletin',
    fake_card = 'buletin_fals',
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do this.',
        ['open_menu_prompt'] = 'Open Menu',
        ['national_office_title'] = 'National Office',
        ['identity_card_service'] = 'Identity Card Service',
        ['fake_card_service'] = 'Fake Card Service',
        ['identity_card_service_desc'] = 'Get your identity card here.',
        ['fake_card_service_desc'] = 'Get your fake card here.',

        ['register_identity_card'] = 'Register Identity Card: %s$',
        ['register_fake_card'] = 'Register Fake Card: %s$',
        ['register_identity_card_desc'] = 'Register your identity card here for %s$.',
        ['register_fake_card_desc'] = 'Register your fake card here for %s$.',

        ['update_identity_card'] = 'Update Identity Card: %s$',
        ['update_identity_card_desc'] = 'Update your identity card here for %s$.',
        ['update_fake_card'] = 'Update Fake Card: %s$',
        ['update_fake_card_desc'] = 'Update your fake card here for %s$.',

        ['buy_identity_card'] = 'Buy Identity Card: %s$',
        ['buy_fake_card'] = 'Buy Fake Card: %s$',
        ['buy_identity_card_desc'] = 'Buy your identity card here for %s$.',
        ['buy_fake_card_desc'] = 'Buy your fake card here for %s$.',

        ['identity_card_does_not_exist'] = 'Identity card does not exist.',
        ['identity_card_already_exists'] = 'Identity card already exists.',
        ['identity_card_bought'] = 'Identity card bought.',
        ['identity_card_deleted'] = 'Identity card deleted.',
        ['identity_card_updated'] = 'Identity card updated.',
        ['identity_card_registered'] = 'Identity card registered.',

        ['delete_fake_card'] = 'Delete Fake Card: %s$',
        ['delete_fake_card_desc'] = 'Delete your fake card here for %s$.',

        ['not_enough_money'] = 'You do not have enough money.',
        ['not_enough_space'] = 'You do not have enough space in your inventory.',
        ['unknown'] = 'Unknown',
        ['default_city'] = 'Government',
        ['default_officer'] = 'Government',
        ['offences_service_desc'] = 'View your offences and penalties here.',
        ['offences_service'] = 'Offences Service',
        ['offence_title'] = 'Offence #%s',
        ['yes'] = 'YES',
        ['no'] = 'NO',
        ['penal_color'] = '#ff6666',
        ['no_penal_color'] = '#999999',
        ['fine_amount'] = '%s$',
        ['fine_paid'] = 'You have paid the fine.',
        ['fine_already_paid'] = 'The fine has already been paid.',
        ['no_offences'] = 'You have no offences.',
        ['no_offences_desc'] = 'You have no offences registered in the system.',
        ['house_string'] = '%s',
        ['offence_template'] = [[
            <div style="font-family: 'Segoe UI', Arial, sans-serif; background-color: #1a1a1a; border-radius: 8px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.5); margin: 10px; max-width: 400px;">
                <!-- Header with Service Name -->
                <div style=" color: white; padding: 12px 16px; display: flex; align-items: center; border-bottom: 2px solid #3a3a3a;">
                    <div style="flex-grow: 1; font-weight: bold;">%s</div>
                </div>

                <!-- Main Content Area -->
                <div style="background-color: #2a2a2a; padding: 16px;">
                    <!-- Offence Code as Menu-Style Header -->
                    <div style="background-color: #1a1a1a; padding: 10px 16px; margin-bottom: 16px; border-radius: 4px; text-align: center; font-weight: bold; color: #ffffff;">
                        %s
                    </div>

                    <!-- Details Section -->
                    <div style="background-color: #1a1a1a; border-radius: 4px; padding: 16px; margin-bottom: 16px;">
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 12px;">
                            <div>
                                <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">DATE</div>
                                <div style="color: #ffffff; font-weight: 500;">%s</div>
                            </div>
                            <div>
                                <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">CITY</div>
                                <div style="color: #ffffff; font-weight: 500;">%s</div>
                            </div>
                            <div>
                                <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">OFFICER</div>
                                <div style="color: #ffffff; font-weight: 500;">%s</div>
                            </div>
                            <div>
                                <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">PENALTY</div>
                                <div style="color:%s; font-weight: 500;">%s</div>
                            </div>
                        </div>
                    </div>

                    <!-- Fine Amount in Menu-Style Button -->
                    <div style="background-color: #1a1a1a; border-radius: 4px; padding: 12px; margin-bottom: 16px; text-align: center;">
                        <div style="color: #8a8aab; font-size: 12px; margin-bottom: 4px;">FINE AMOUNT</div>
                        <div style="color: #ff4444; font-weight: bold; font-size: 18px;">%s</div>
                    </div>

                </div>

            </div>
        ]],
        ['webhook_idnr'] = 'ID Number',
        ['webhook_identity_card_register_real'] = '🪪 Identity Card Registration (Real)',
        ['webhook_identity_card_register_fake'] = '🪪 Identity Card Registration (Fake)',

        ['webhook_identity_card_register_real_info'] = '📝 A **real** identity card was registered: %s',
        ['webhook_identity_card_register_fake_info'] = '📝 A **fake** identity card was registered: %s',
        ['webhook_first_name'] = 'First Name',
        ['webhook_last_name'] = 'Last Name',
        ['webhook_dob'] = 'Date of Birth',
        ['webhook_city'] = 'City',
        ['webhook_job'] = 'Job',
        ['webhook_height'] = 'Height',
        ['webhook_weight'] = 'Weight',
        ['webhook_sex'] = 'Sex',
        ['webhook_houses'] = 'Houses',
        ['webhook_user_information'] = 'User Information',
        ['webhook_register_date'] = 'Register Date',
        ['webhook_identity_card_update_real'] = '📝 Identity Card Updated (Real)',
        ['webhook_identity_card_update_fake'] = '📝 Identity Card Updated (Fake)',

        ['webhook_identity_card_update_real_info'] = '✏️ A **real** identity card was updated: %s',
        ['webhook_identity_card_update_fake_info'] = '✏️ A **fake** identity card was updated: %s',
        ['webhook_identity_card_delete_fake'] = '🗑️ Fake Identity Card Deleted',
        ['webhook_identity_card_delete_fake_info'] = '🗑️ A fake identity card was permanently deleted: %s',
        ['webhook_identity_card_offence'] = '⚖️ New Criminal Offence',
        ['webhook_identity_card_offence_info'] = '📋 A new offence was registered: %s',
        
        -- Field Names
        ['webhook_offence_title'] = 'Title',
        ['webhook_offence_description'] = 'Description',
        ['webhook_officer'] = 'Officer',
        ['webhook_fine'] = 'Fine',
        ['webhook_jail_time'] = 'Jail Time',
        ['webhook_offence_id'] = 'Offence Id',
        ['webhook_offence_penal'] = 'Penal',

        ['webhook_identity_card_offence_fine_paid'] = '💰 Offence Fine Paid',
        ['webhook_identity_card_offence_fine_paid_info'] = '💸 A fine was paid for offence: %s',
        ['webhook_payment_status'] = 'Status',
        ['webhook_paid'] = 'Paid',
        ['webhook_offence_character_id'] = 'Character ID',
        ['webhook_offence_date'] = 'Offence Date',
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
