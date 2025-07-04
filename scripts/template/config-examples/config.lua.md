# config.lua

```lua
Config = {}

Config.OpenDepositKey = 0x760A9C6F -- G
Config.UpgradeDepositKey = 0xE30CD707 -- U
Config.BuySlotsKey = 0x7F8D09B8 -- F

Config.DistanceToOpenDeposit = 4

Config.BuySlotInput = {
    title = "Buy deposit slots",
    form = {
        {
            label = "Number of slots (Price: %s$/slot)",
            id = "slots",
            type = "number",
            
        },
    }
}

Config.DiscordWebhooks = true -- ENABLE or DISABLE **ALL** discord webhooks. (True or false)

Config.Webhooks = {
    DefaultWebhook = '', -- Default webhook for all deposits

    openDeposit = {
        sensitive = true, -- True or a specific webbook
        nonSensitive = '',
    },
    openSpecialDeposit = {
        sensitive = true,
        nonSensitive = '',
    },

    upgradeDeposit = {
        sensitive = true,
        nonSensitive = '',
    },

    buySlots = {
        sensitive = true,
        nonSensitive = '',
    },
}


Config.Deposits = {
        ['DepositSaintDenis'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Saint Denis',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 150,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(2582.0322, -1498.3979, 45.9692),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to
            },

            ['DepositValentine'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Valentine',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(-262.0936, 761.4332, 118.2005),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositRhodes'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Rhodes',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(1403.3330, -1372.7451, 81.3357),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositVanHorn'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Van Horn',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(3009.2632, 562.3879, 44.6934),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositAnnesburg'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Annesburg',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(2979.6494, 1439.0237, 44.8803),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositBlackwatter'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Blackwater',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(-956.0276, -1324.8584, 52.3371),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositArmadillo'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Armadillo',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(-3712.7532, -2570.9019, -13.6408),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositTumbleweed'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Tumbleweed',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil}, -- Jobs: {job = 'jobname', grade = 1, reduction = 0.05} or Jobs: {job = 'jobname', grade = nil, reduction = 0.05}
                Positions = {
                    vector3(-5499.1260, -2932.0562, -0.3655),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },

            ['DepositGuarma'] = { -- id of the inventory, it should not be duplicated. IF IT IS DUPLICATED IT WILL SHARE THE ITEMS WITH OTHER DEPOSITS
                showTitle = true,
                title = 'Depozit Guarma',
                description = 'Price per access: 0.15$',
                Weight = 250, -- how many items there should be in the deposit
                SlotPrice = 1, -- how much should the player pay for each slot, only after reaching the upgrade limit.
                Upgrades = {
                    [1] = {
                        Weight = 250, -- Weight increment
                        Price = 75,
                    },
                    [2] = {
                        Weight = 750,
                        Price = 160,
                    },
                    [3] = {
                        Weight = 1750,
                        Price = 300,
                    },
                },
                DepositTax = 0.15, -- the amount of money that should be reducted from the user account when oppening the deposit.
                TaxReductions = {jobs = nil},
                Positions = {
                    vector3(1335.9822, -7037.4341, 53.0871),
                },
                BlipModel = "blip_chest", -- or BlipModel = false to disable it
                Webhook = '', -- Discord webhook to send the logs to

            },
}

Config.SpecialDeposits = { -- Free of charge, only for specific jobs and vips. No upgrades available for these deposits.
    ['DepositPolitie'] = {
        showTitle = true,
        title = 'Depozit Politie',
        description = 'Free of charge, only for police officers.', -- or nil
        Weight = 250,
        shared = true,

        Access = { 
            jobs = {
                {job = 'politie', grade = 1}, -- Or grade = nil
            },
            characterGroups = {
                'police',
            },
            userGroups = {
                'police',
            },
        },

        Positions = {
            vector3(2572.1389, -1500.7891, 45.9699),
        },
        BlipModel = "blip_chest",
        Webhook = '',
    }
}


Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['not_allowed'] = 'You are not allowed to do this!',
        ['opendeposit_prompt'] = 'Open deposit',
        ['not_enough_money'] = 'You do not have enough money to access this deposit!',
        ['not_enough_money_deposit'] = 'You do not have enough money to upgrade this deposit!',
        ['deposit_upgraded_succesfully'] = 'The limit of this deposit has been successfully increased. New limit: %s.',
        ['money_saved'] = 'You saved $%s due to your status!',
        ['no_upgrades_available'] = 'You have reached the maximum level for this deposit!',
        ['upgradedeposit_prompt'] = 'Upgrade level',
        ['group_title'] = '%s (Level: %s / %s. Limit: %s (%s$))',
        ['buyslots_prompt'] = 'Buy slots',
        ['not_enough_money_slots'] = 'You do not have enough money to buy this amount of slots!',
        ['slots_bought_succesfully'] = 'You have successfully bought %s slots for %s$!',
        ['invalid_slot_input'] = 'Enter a valid value for slots!',

        -- Webhook and Deposit-related translations
        ['webhook_user_information'] = 'Player Info',
        ['webhook_openDeposit'] = 'A deposit was opened!',
        ['webhook_openDeposit_info'] = '%s has opened the deposit %s.',
        ['webhook_openSpecialDeposit'] = 'A special deposit was opened!',
        ['webhook_openSpecialDeposit_info'] = '%s has opened the special deposit %s.',
        ['webhook_upgradeDeposit'] = 'A deposit was upgraded!',
        ['webhook_upgradeDeposit_info'] = '%s has upgraded the deposit %s to level %s.',
        ['webhook_buySlots'] = 'Slots were bought!',
        ['webhook_buySlots_info'] = '%s has bought %s slots for %s$ in the deposit %s.',

        -- Deposit Fields for Webhook
        ['deposit_name'] = 'Deposit Name',
        ['original_deposit_cost'] = 'Original Deposit Cost',
        ['total_reductions'] = 'Total Reductions',
        ['final_deposit_cost'] = 'Final Deposit Cost',
        ['amount_saved'] = 'Amount Saved',
        ['paid_amount'] = 'Paid Amount',
        ['player_job'] = 'Player Job',
        ['player_vip_status'] = 'Player VIP Status',
        ['saved_for'] = 'Saved For',
        ['new_weight'] = 'New Weight',
        ['current_weight'] = 'Current Weight',
        ['slots_bought'] = 'Slots Bought',

    },

    RO = {
        ['not_allowed'] = 'Nu ai voie să faci asta!',
        ['opendeposit_prompt'] = 'Deschide depozit',
        ['not_enough_money'] = 'Nu ai suficienți bani pentru a accesa acest depozit!',
        ['not_enough_money_deposit'] = 'Nu ai suficienți bani pentru a upgrada acest depozit!',
        ['deposit_upgraded_succesfully'] = 'Limita acestui depozit a fost mărită cu succes. Noua limită: %s.',
        ['money_saved'] = 'Ai economisit $%s datorită statutului tău!',
        ['no_upgrades_available'] = 'Ai atins nivelul maxim pentru acest depozit!',
        ['upgradedeposit_prompt'] = 'Upgrade nivel',
        ['group_title'] = '%s (Nivel: %s / %s. Limită: %s (%s$))',
        ['buyslots_prompt'] = 'Cumpără sloturi',
        ['not_enough_money_slots'] = 'Nu ai suficienți bani pentru a cumpăra această cantitate de sloturi!',
        ['slots_bought_succesfully'] = 'Ai cumpărat cu succes %s sloturi pentru %s$!',
        ['invalid_slot_input'] = 'Introdu o valoare validă pentru sloturi!',

        -- Webhook și traduceri legate de depozit
        ['webhook_user_information'] = 'Informații jucător',
        ['webhook_openDeposit'] = 'Un depozit a fost deschis!',
        ['webhook_openDeposit_info'] = '%s a deschis depozitul %s.',
        ['webhook_openSpecialDeposit'] = 'Un depozit special a fost deschis!',
        ['webhook_openSpecialDeposit_info'] = '%s a deschis depozitul special %s.',
        ['webhook_upgradeDeposit'] = 'Un depozit a fost upgradat!',
        ['webhook_upgradeDeposit_info'] = '%s a upgradat depozitul %s la nivelul %s.',
        ['webhook_buySlots'] = 'Sloturi cumpărate!',
        ['webhook_buySlots_info'] = '%s a cumpărat %s sloturi pentru %s$ în depozitul %s.',

        -- Câmpuri pentru Webhook legate de depozit
        ['deposit_name'] = 'Nume depozit',
        ['original_deposit_cost'] = 'Cost original depozit',
        ['total_reductions'] = 'Reduceri totale',
        ['final_deposit_cost'] = 'Cost final depozit',
        ['amount_saved'] = 'Sumă economisită',
        ['paid_amount'] = 'Sumă plătită',
        ['player_job'] = 'Job jucător',
        ['player_vip_status'] = 'Statut VIP jucător',
        ['saved_for'] = 'Economisit pentru',
        ['new_weight'] = 'Greutate nouă',
        ['current_weight'] = 'Greutate curentă',
        ['slots_bought'] = 'Sloturi cumpărate',

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
