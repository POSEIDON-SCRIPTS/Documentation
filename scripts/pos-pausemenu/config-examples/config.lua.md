# config.lua

```lua
Config = {}

Config.GuideCommand = 'guide' -- Command to open the guide menu or false


Config.PauseMenu = {
    top = {
        [1] = {
            title = 'DISCONNECT',
            action = function() TOP1() end 
        },
        [2] = {
            title = 'SETTINGS',
            link = 'https://www.google.com/',
            action = function() TOP2() end
        },
        [3] = {
            title = 'MAP',
            action = function() TOP3() end
        },
    },
    left = {
        [1] = {
            title = 'TUTORIALS',
            action = function() LEFT1() end
        },
        [2] = {
            title = 'SERVER RULES',
            action = function() LEFT2() end
        },
        [3] = {
            title = 'COMMANDS',
            action = function() LEFT3() end
        },
    }
}

-- Define the functions
function TOP1()
    TriggerServerEvent('POS-PauseMenu:Server:Disconnect')
end

function TOP2()
    Citizen.InvokeNative(0xC1BCF31E975B3195, GetHashKey('settings_menu'), true, -1)
end

function TOP3()
    Citizen.InvokeNative(0xC1BCF31E975B3195, GetHashKey('map'), true, -1)
end

function LEFT1()
    TriggerEvent('POS-PauseMenu:Client:OpenGuide', 1)
end

function LEFT2()
    TriggerEvent('POS-PauseMenu:Client:OpenGuide', 2)
end
function LEFT3()
    TriggerEvent('POS-PauseMenu:Client:OpenGuide', 3)
end


Config.Guides = {
    [1] = {
        title = 'TUTORIALS',
        description = '<img src="https://i.ibb.co/zb5X4hq/server-logo.png" height=150px width=150px>',
        categories = {
            [1] = {
                title = 'COACHMAN',
                content = {
                    [1] = {
                        title = 'COACHMAN',
                        description = [[
            
                        Live the adventure of the Wild West as a coachman, transporting passengers and goods between picturesque settlements. Enjoy the freedom of endless roads, a flexible schedule, and the satisfaction of providing an indispensable service to the community. If you love life on the road, hop into your carriage and explore the world as a coachman in every town!
            
                        <br>
                        <br>
                        1 - You can get off the carriage if needed and defend yourself if attacked by NPCs.
                        <br>
                        2 - You can start the job from any town.
                        <br>
                        3 - You cannot be robbed while doing the coachman job.
                        <br>
                        4 - If you lose the goods in your inventory, you will be penalized at the end of the route.
                        <br>
                        5 - You can choose a normal route or a random route, keeping in mind that you will be attacked if you choose a random route, but you will earn more money per ride.
                        <br>
                        6 - You can cancel an ongoing ride using the command </span><span style="color: #ef6226;"><strong><span style="color: #ffffff;">/</span>cancelmission</strong></span>
                        ]]
                    },
            
                    [2] = {
                        title = 'How can I do this job?',
                        description = [[
            
                        You can start the job from any town.
                        <br>
                        <br>
                        
                        <img src="https://img001.prntscr.com/file/img001/D1BHSU8STXeKS-I_Sty9ag.png" width = 785px height = 420px alt="" />
                        ]]
                    },
                }
            },
            [2] = {
                title = 'DOCK WORKER',
                content = {
                    [1] = {
                        title = 'DOCK WORKER',
                        description = [[
            
                        Embark on an energetic career as a dock worker, helping to load and unload packages from ships. Enjoy an active, outdoor environment and the satisfaction of contributing to the smooth operation of maritime trade. If you like physical work and are ready to become an essential part of the port team, don’t hesitate to find your place among the dock workers in every dock!
                        ]]
                    },
                    [2] = {
                        title = 'How can I do this job?',
                        description = [[
            
                        You need to go to the port of Saint Denis and speak with Ahmed to start the job.
                        <br>
                        <br>
                        <img src="https://i.ibb.co/q71wGXk/salahor-final.png" width = 785px height = 420px alt="" />
                        ]]
                    },
            
                    [3] = {
                        title = 'What do I have to do?',
                        description = [[
            
                        After speaking with Ahmed, you must go to the workplace and start loading/unloading packages. Go to the checkpoints to collect the goods, then deliver them to the ship.
                        <br>
                        <br>
                        <img src="https://i.ibb.co/v4rRNNs/salahor2-final.png" alt="" />
                        ]]
                    },
                }
            },
            
            [3] = {
                title = 'CARPENTER',
                content = {
                    [1] = {
                        title = 'CARPENTER',
                        description = [[
            
                        Discover the craftsmanship of woodworking as a carpenter, transforming raw materials into furniture or quality constructions. Enjoy a flexible schedule and the satisfaction of creating durable and beautiful items with your own hands. If you are drawn to the art of carpentry and want to bring unique projects to life, join the team of master carpenters and help repair and maintain the city!
                        ]]
                    },
                    [2] = {
                        title = 'How can I do this job?',
                        description = [[
            
                        You need to go to Saint Denis and start the job.
                        <br>
                        <br>
                        <img src="https://i.ibb.co/gSqJqhk/tamplarie1.png" width = 785px height = 420px alt="" />
                        ]]
                    },
            
                    [3] = {
                        title = 'What do I have to do?',
                        description = [[
            
                        After starting the job, you must go to the four marked locations on the map in the following order:
                        <br>
                       
                        1 - Collect materials (Start Area)
                        <br>
                        2 - Go to repair (Repair Area)
                        <br>
                        3 - Go to recycle (Recycling Area)
                        <br>
                        4 - Sell the goods (Selling Area)
                        <br>
                        <br>
                        <img src="https://i.ibb.co/6XfJ89w/tamplarie2.png" width = 785px height = 420px alt="" />
                        ]]
                    },
                }
            },
            
            [4] = {
                title = 'FARMER',
                content = {
                    [1] = {
                        title = 'FARMER',
                        description = [[
            
                        Experience the authentic life of a farmer, handling the harvesting, processing, and delivery of fresh corn from the fields. Enjoy the fresh air of nature and the satisfaction of providing the community with quality products while working in a flexible and dynamic environment. If you love being close to the land and seeing the fruits of your labor, take your place among the hardworking farmers in every harvest season!
                        ]]
                    },
                    [2] = {
                        title = 'How can I do this job?',
                        description = [[
            
                        You need to go to the location on the map and start the job.
                        <br>
                        <br>
                        <img src="https://i.ibb.co/58J8zHn/fermier-final1.png" width = 785px height = 420px alt="" />
                        <br>
                        <br>
                        VERY IMPORTANT: Once you start the job, make sure the cart has spawned and move it. If not, you must stop/restart the job until the cart appears.
                        <br> 
                        <img src="https://i.ibb.co/PhTZF5p/tura.jpg" width = 785px height = 420px alt="" />
                        <br>
                        VERY IMPORTANT: You must move the cart before you start collecting corn. If another player also starts the job, carts will spawn on top of each other.
                        <br>
                        ]]
                    },
            
                    [3] = {
                        title = 'What do I have to do?',
                        description = [[
            
                        After starting the job, you must go to the four marked locations on the map in the following order:
                        <br>
                       
                        1 - Harvest Corn (Harvesting Area)
                        <br>
                        2 - Process Corn (Processing Area)
                        <br>
                        3 - Pack in Sacks (Packing Area)
                        <br>
                        4 - Deliver to Valentine (Delivery Area)
                        <br>
                        <br>
                        <img src="https://i.ibb.co/1X1smfD/fermier-final2.png" width = 785px height = 420px alt="" />
                        ]]
                    },
                }
            },
            
        },
    },
    [2] = {
        title = 'RULES',
        description = '<img src="https://i.ibb.co/zb5X4hq/server-logo.png" height=150px width=150px>',
        categories = {
            [1] = {
                title = 'Regulations (OOC)',
                content = {
                    [1] = {
                        title = '(1) 1. Interpretation of the Rules',
                        description = [[
            
                         - It is <span style="color: #FF0000;">strictly forbidden</span> to interpret any rule in the regulations to avoid sanctions or escape a situation. If the rules leave room for interpretation, the final decision on rule enforcement will be made by the staff handling the ticket or an administration member.
                        <br>
                        <br>
                        
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">PERMANENT BAN</span>
                        ]]
                    },
                    [2] = {
                        title = '(1) 2. PowerGaming (PG)',
                        description = [[
            
                         - Refers to <span style="color: #FF0000;">unrealistic</span> or impossible actions from a RolePlay perspective. These actions violate the principles of authentic and fair roleplay.
                        <br>
                        - It is considered <span style="color: #FF0000;">PowerGaming</span> when a player does not give others a fair chance in roleplay.
                        <br>
                        <br>
                        <span style="color: #FF0000;">Examples of PowerGaming:</span>
                        <br>
                            - A player sees a police officer on a plantation and uses the command /me is hidden so well that the officer does not see him.
                            <br>
                            - A player notices another player hiding in a bush after a /me indicates "SMELLS LIKE SWEAT" and heads straight towards them.
                            <br>
                            - A player falls from a great height without taking any damage and continues without any issues.
                            <br>
                            <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">WARNING/BAN 3 DAYS (Depending on severity and number of infractions)</span>
                        ]]
                    },
                    [3] = {
                        title = '(1) 3. Mixing (MX)',
                        description = [[
            
                        - Mixing <span style="color: #FF0000;">(MX)</span> refers to transmitting In-Character <span style="color: #FF0000;">(IC)</span> information on Out-Of-Character <span style="color: #FF0000;">(OOC)</span> channels. These types of information must remain strictly separate to maintain roleplay authenticity.
                        <br>
                        - Additionally, transmitting Out-Of-Character <span style="color: #FF0000;">(OOC)</span> information through <span style="color: #FF0000;">Voice Chat</span> is considered Mixing.
                        <br>
                        <br>
                        <span style="color: #FF0000;">Examples of Mixing:</span>
                        <br>
                            - You are in Annesburg without a horse or any transport and send a Discord message to your friend to come pick you up.
                            - You use OOC terms such as: TICKET, ADMIN, MIXING, METAGAMING, 'ANGEL', 'MEAL VOUCHER' in Voice Chat or any other IC communication (e.g., through /me commands).
                            <br>
                            <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">WARNING/BAN 7 DAYS (Depending on severity and number of infractions)</span>
                        ]]
                    },
                    
                    [4] = {
                        title = '(1) 4. MetaGaming (MG)',
                        description = [[
            
                        - MetaGaming <span style="color: #FF0000;">(MG)</span> involves using information obtained outside the character <span style="color: #FF0000;">(OOC)</span> in an In-Character <span style="color: #FF0000;">(IC)</span> situation. This is forbidden and harms the authenticity of roleplay.
                        <br>
                        <br>
                        <span style="color: #FF0000;">Examples of MetaGaming:</span>
                        <br>
                            - Talking to someone on Discord or other platforms (without being on "deafen") while participating in roleplay.
                            <br>
                            - Watching a livestream and using the information to locate that person on the map.
                            <br>
                            - Receiving a message from a friend on Discord asking to be picked up and acting accordingly in roleplay.
                            <br>
                            <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">WARNING/BAN 7 DAYS (Depending on severity and number of infractions)</span>
                            <br>
                            <br>
                        <span style="color: #FF0000;">Clarifications:</span>
                        <br>
                        <span style="color: #40E0D0;">Mixing</span>: Transmitting <span style="color: #FF0000;">IC</span> information on <span style="color: #FF0000;">OOC</span> chats.
                        <br>
                        <span style="color: #40E0D0;">Metagaming</span>: Using <span style="color: #FF0000;">OOC</span> information for <span style="color: #FF0000;">IC</span> purposes.
                        ]]
                    },
                    [5] = {
                        title = '(1) 5. Disconnecting during roleplay (Disconnect in RolePlay)',
                        description = [[
            
                        - Disconnecting during a roleplay refers to leaving the server before the roleplay action is considered completed. A roleplay is considered finished only when you are no longer participating in that action for a minimum of <span style="color: #FF0000;">10 minutes</span>.
                        <br>
                        <br>
                        <span style="color: #FF0000;">WARNING!</span>
                        <br>
                         If you know you are being pursued or someone is looking for you due to a roleplay event, you are not allowed to abuse the system and disconnect.
                        <br>
                        <br>
                        <span style="color: #FF0000;">Examples of Disconnecting in Roleplay:</span>
                        <br>
                            - Disconnecting during roleplay is when you rob a bank, the police chase you, you hide in a bush, and then log out.
                            <br>
                            - Disconnecting during roleplay is when you are on a plantation, the police arrive for a raid, and you log out to escape.
                            <br>
                            - Disconnecting during roleplay is when someone is robbing you, and you disconnect to avoid losing your items.
                            <br>
                            <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">BAN 10 DAYS</span>
                            <br>
                        ]]
                    },
                }
            },
            
            [2] = {
                title = 'Rules (IC)',
                content = {
                    [1] = {
                        title = '(2) 1. Hostage',
                        description = [[
                    
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to take someone hostage without a valid reason.
                        
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to hold a hostage for more than <span style="color: #FF0000;">30 minutes</span> from the moment a negotiator is found. If no negotiator is found, the hostage can be held until someone is available.
                        <br>
                        - If <span style="color: #FF0000;">negotiation requests</span> are <span style="color: #FF0000;">denied</span>, the hostage can be killed and will receive a Character Kill (<span style="color: #FF0000;">CK</span>) if they belong to an organization. If not, they will receive a Player Kill (<span style="color: #FF0000;">PK</span>).
                        <br>
                        - If no negotiator is found, you are allowed to make the hostage work for you for <span style="color: #FF0000;">30 minutes</span> (equivalent to negotiation time). During this time, you may take their items, but you are required to return them once the work is completed.
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to demand more than <span style="color: #FF0000;">$200</span> in cash or items of equivalent value in exchange for a hostage.
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to take a hostage during bank robberies.
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to make unreasonable demands during hostage negotiations.
                        <br>
                        <br>
                        <span style="color: #FF0000;">Examples of unacceptable demands:</span>
                        <br>
                        Making all police officers drop their weapons.
                        <br>
                        Requiring a gang leader and an entire organization to show up.
                        <br>
                        <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">7-DAY BAN</span>
                        ]]
                    },
                    [2] = {
                        title = '(2) 2. Corruption',
                        description = [[
                    
                        - A police officer <span style="color: #FF0000;">is not allowed</span> to steal items from police inventories.
                        
                        <br>
                        - A police officer <span style="color: #FF0000;">is not allowed</span> to sell or give away items from the police menu (weapons, MDT, ammo, etc.).
                        <br>
                        - A police officer <span style="color: #FF0000;">is not allowed</span> to keep confiscated items from a player and must store them in the police inventory.
                        <br>
                        - A police officer <span style="color: #FF0000;">can be corrupt</span> only in the context of accepting bribes to release detainees or handing over a prisoner in exchange for money. Additionally, a police officer is not allowed to take action against a civilian without a valid reason.
                    
                        <br>
                        <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">30-DAY BAN</span>
                        ]]
                    },
                    [3] = {
                        title = '(2) 3. Mugging Players',
                        description = [[
                    
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to rob if you have less than <span style="color: #FF0000;">50</span> hours <span style="color: #FF0000;">on your CHARACTER</span>. You are not allowed to participate in a robbery, even if you are just "watching," if you do not meet this requirement.
                        
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to rob anyone between 09:00 - 20:59. Robberies are <span style="color: #FF0000;">only allowed</span> between 21:00 - 08:59.
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to rob someone who is performing a legal job at that moment.
                        <br>
                        <span style="color: #FF0000;">Exceptions:</span>
                        <br>
                        Gold Prospector
                        <br>
                        Treasure Hunter
                        <br>
                        Hunter
                        <br>
                        Fisherman
                        <br>
                    
                        Miner (you are not allowed to rob someone in the mine to ensure fair roleplay)
                        <br>
                        Advanced Miner (you are not allowed to rob someone in the mine to ensure fair roleplay)
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to rob in a green-marked area on the map (e.g., Saint Denis, Valentine, etc.).
                        <br>
                        <span style="color: #FF0000;">ATTENTION!</span>
                        <br>
                        In these areas, players can only be robbed when engaging in illegal delivery jobs (i.e., when the delivery animation has started).
                        <br>
                        - It is <span style="color: #FF0000;">ALLOWED</span> to rob someone in their house only if they have given you permission to enter.
                        <br>
                        <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">30-DAY BAN</span>
                        ]]
                    },
                    



                    
                }
            },
            [3] = {
                title = 'General Regulations',
                content = {
                    [1] = {
                        title = '(3) 1. Tied with Rope / Lasso:',
                        description = [[
                        <br>
                        - When you are tied with a lasso, <span style="color: #FF0000;">you are not allowed</span> to use the Give Up option, as this is considered Character Kill (<span style="color: #FF0000;">CK</span>).
                        
                        <br>
            
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to use the lasso in fights.
                        <br>
                        - It is <span style="color: #008000;">allowed</span> to attempt to untie yourself only when no one is watching you. However, if you are part of an active roleplay involving being tied up, you are not allowed to untie yourself. This rule applies if an admin has been called to clarify the situation.
                        <br>
                        <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">BAN 5 DAYS</span>
                        ]]
                    },
                    [2] = {
                        title = '(3) 2. VIP/Police Properties',
                        description = [[
                        <br>
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to sell horses, wagons, or boats acquired through VIP packages or purchased with BTC.
                        
                        <br>
            
                        - It is <span style="color: #FF0000;">strictly forbidden</span> to sell horses received from the police.
                        <br>
                        
                        <br>
                        <span style="color: #FF0000;">PENALTY</span>: <span style="color: #40E0D0;">PERMANENT BAN</span>
                        ]]
                    },
                    
                }
            },
            
        },
    },
    [3] = {
        title = 'COMMANDS',
        description = 'This is the list of all useful commands.',
        categories = {
            [1] = {
                title = 'USEFUL COMMANDS',
                content = {
                    [1] = {
                        title = 'USEFUL COMMANDS ON THE SERVER',
                        description = [[
    
    
                                                 
                        <span style="color: #FF0000;">/hud</span>: Opens the server HUD.
                        <br>
                         <span style="color: #FF0000;">/stats</span>: Opens your statistics.
                        <br>
                        <span style="color: #FF0000;">/rc</span>: Reloads your character.
                        <br>
                        <span style="color: #FF0000;">/cancelmission</span>: Cancels the Carriage Driver race.
                        <br>
                        <span style="color: #FF0000;">/clearroute</span>: Clears the route from the map.
                        <br>
                        <span style="color: #FF0000;">/vip</span>: Opens the VIP menu.
                        <br>
                        <span style="color: #FF0000;">/clear</span>: Clears the chat.
                        <br>
                        <span style="color: #FF0000;">/togglechat</span>: Show/Hide the chat.
                        <br>
                        <span style="color: #FF0000;">/anim</span>: Opens the animation menu.
                        <br>
                        <span style="color: #FF0000;">/love</span>: Opens the LOVE menu.
                        <br>
                        <span style="color: #FF0000;">/ticket</span>: Opens a ticket.
                        <br>
                        <span style="color: #FF0000;">/hudmenu</span>: Opens the HUD menu.
                        <br>
                        <span style="color: #FF0000;">/hudload</span>: Loads the HUD.
                        <br>
                        <span style="color: #FF0000;">/cancelcarriage</span>: Cancels the Carriage race (TAXI).
                        <br>
    
    
                        ]]
                    },
                }
            },
            [2] = {
                title = 'KEYBINDS',
                content = {
                    [1] = {
                        title = 'USEFUL KEYS ON THE SERVER',
                        description = [[
    
    
                                                 
                        <span style="color: #FF0000;">PAGE UP</span>: Voice chat volume 
                        <br>
                         <span style="color: #FF0000;">U</span>: Opens the Utility Menu
                        <br>
                        <span style="color: #FF0000;">R</span>: Interacts with objects, chairs, etc. (hold)
                        <br>
                        <span style="color: #FF0000;">L</span>: Interacts with your horse
                        <br>
                        <span style="color: #FF0000;">J</span>: Opens the Clothing menu
                        <br>
                        <span style="color: #FF0000;">G</span>: Sells drugs to NPCs (hold)
                        <br>
                        
    
    
                        ]]
                    },
                }
            },
            [3] = {
                title = 'CLOTHING COMMANDS',
                content = {
                    [1] = {
                        title = 'USEFUL CLOTHING COMMANDS ON THE SERVER',
                        description = [[
    
    
                                                 
                        <span style="color: #FF0000;">/mask</span>: Put on/Remove the mask.
                        <br>
                         <span style="color: #FF0000;">/gloves</span>: Put on/Remove gloves.
                        <br>
                        <span style="color: #FF0000;">/armor</span>: Put on/Remove armor.
                        <br>
                        <span style="color: #FF0000;">/tie</span>: Put on/Remove the tie.
                        <br>
                        <span style="color: #FF0000;">/vest</span>: Put on/Remove the vest.
                        <br>
                        <span style="color: #FF0000;">/coat</span>: Put on/Remove the coat.
                        <br>
                        <span style="color: #FF0000;">/poncho</span>: Put on/Remove the poncho.
                        <br>
                        <span style="color: #FF0000;">/hat</span>: Put on/Remove the hat.
                        <br>
                        <span style="color: #FF0000;">/pants</span>: Put on/Remove the pants.
                        <br>
                        <span style="color: #FF0000;">/shirt</span>: Put on/Remove the shirt.
                        <br>
                        <span style="color: #FF0000;">/belt</span>: Put on/Remove the belt.
                        <br>
                        <span style="color: #FF0000;">/boots</span>: Put on/Remove footwear.
                        <br>
                        <span style="color: #FF0000;">/leggings</span>: Put on/Remove leggings.
                        <br>
                        <span style="color: #FF0000;">/spats</span>: Put on/Remove spats.
                        <br>
    
    
                        ]]
                    },
                }
            },
        },
    },
    
}



```
