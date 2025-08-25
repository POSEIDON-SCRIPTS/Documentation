# config.lua

```lua
Config = {}

Config.WaterLocations = {
    [1] = {
        name = "Sea of Coronado",
        waterhash = -247856387,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [2] = {
        name = "San Luis River",
        waterhash = -1504425495,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [3] = {
        name = "Lake Don Julio",
        waterhash = -1369817450,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [4] = {
        name = "Flat Iron Lake",
        waterhash = -1356490953,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [5] = {
        name = "Upper Montana River",
        waterhash = -1781130443,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [6] = {
        name = "Owanjila",
        waterhash = -1300497193,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [7] = {
        name = "Hawks Eye Creek",
        waterhash = -1276586360,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [8] = {
        name = "Little Creek River",
        waterhash = -1410384421,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [9] = {
        name = "Dakota River",
        waterhash = 370072007,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [10] = {
        name = "Beartooth Beck",
        waterhash = 650214731,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [11] = {
        name = "Lake Isabella",
        waterhash = 592454541,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [12] = {
        name = "Cattail Pond",
        waterhash = -804804953,
        watertype = "pond",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [13] = {
        name = "Deadboot Creek",
        waterhash = 1245451421,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [14] = {
        name = "Spider Gorge",
        waterhash = -218679770,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [15] = {
        name = "O'Creagh's Run",
        waterhash = -1817904483,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [16] = {
        name = "Moonstone Pond",
        waterhash = -811730579,
        watertype = "pond",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [17] = {
        name = "Kamassa River",
        waterhash = -1229593481,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [18] = {
        name = "Elysian Pool",
        waterhash = -105598602,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [19] = {
        name = "Heartland Overflow",
        waterhash = 1755369577,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [20] = {
        name = "Bayou NWA",
        waterhash = -557290573,
        watertype = "swamp",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [21] = {
        name = "Lannahechee River",
        waterhash = -2040708515,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [22] = {
        name = "Calmut Ravine",
        waterhash = 231313522,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [23] = {
        name = "Ringneck Creek",
        waterhash = 2005774838,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [24] = {
        name = "Stillwater Creek",
        waterhash = -1287619521,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [25] = {
        name = "Lower Montana River",
        waterhash = -1308233316,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [26] = {
        name = "Aurora Basin",
        waterhash = -196675805,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [27] = {
        name = "Arroyo De La Vibora",
        waterhash = -49694339,
        watertype = "river",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [28] = {
        name = "Whinyard Strait",
        waterhash = -261541730,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [29] = {
        name = "Hot Springs",
        waterhash = 1175365009,
        watertype = "pond",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [30] = {
        name = "Barrow Lagoon",
        waterhash = 795414694,
        watertype = "lake",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [31] = {
        name = "Dewberry Creek",
        waterhash = 469159176,
        watertype = "creek",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [32] = {
        name = "Cairn Lake",
        waterhash = -1073312073,
        watertype = "pond",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [33] = {
        name = "Mattlock Pond",
        waterhash = 301094150,
        watertype = "pond",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [34] = {
        name = "Southfield Flats",
        waterhash = -823661292,
        watertype = "pond",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    },
    [35] = {
        name = "Bahia De La Paz",
        waterhash = -1168459546,
        watertype = "ocean",
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    }

}

Config.ObejectTypes = {
    ["p_barrel_wash01x"] = {
        locationConfig = {
            Active = true,
            Options = {
                drink = true,
                shower = true,
                items = true,
            },
            WaterSettings = {
                increase = 25,
                duration = 10000,
                damage = {
                    enabled = true,
                    chance = 50,
                    value = 50,
                },
                poison = {
                    enabled = true,
                    chance = 50,
                    value = 5,
                    interval = {15000, 60000},
                }
            },
            ShowerSettings = {
                duration = 10000,
            }
        }
    }
}

Config.Controls = {
    Wash = 0xB2F377E8,
    Drink = 0x760A9C6F,
    Vomit = 0xB2F377E8,
    BoilWater = 0xE30CD707,
    FillCanteen = 0xF3830D8E,
    FillBucket = 0x9959A6F0,
}

Config.CrouchRequired = true

Config.Functions = {
    ["wash"] = function()
        exports['POS-Metabolism']:ShowerEvent()
    end,

    ["drink"] = function(value)
        exports['POS-Metabolism']:UpdateMultipleStatus({
            ["water"] = value,
            ["piss"] = value*(2/3)
        })
    end,

    ["poison"] = function ()
        exports['POS-Metabolism']:UpdateMultipleStatus({
            ["poop"] = 30,
        })
    end,

    ["vomit"] = function()
        exports['POS-Metabolism']:UpdateStatus("food", -15)
    end
}

Config.CureItems = {
    ["morphina"] = {
        prop = "mp007_p_mp_syringe01x_1",
        animation = "inject",

        returnItems = {
            {
                name = "sticla_goala",
                count = 1
            },
        },
    },
}

Config.CanteenItems = {
    ["pleosca"] = {
        uses = 5,   -- How many uses the canteen has
        fillDuration = 10000, -- How long it takes to fill the canteen
        boilDuration = 10000, -- How long it takes to boil the water
        model = "p_cs_canteen_hercule",
    }

}

Config.BucketItems = {
    ['galeata_goala'] = {
        item = 'galeata',
        fillDuration = 10000, -- How long it takes to fill the bucket
    }
}

Config.ProgressBars = {
    ['fill_bucket'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling bucket..',
        canStop = true,
        animation = {
            time = -1,
            scenario = -2053511979,
            type = 'scenario',
        }
    },

    ['boil_water'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Boiling water..',
        canStop = true,
        animation = {
            anim = "base",
            flags = 3,
            animDict = "mech_dynamic@world_player_dynamic_kneel_ground@cook@knife@searing@base"
        },
        prop = {
            bone = "SKEL_R_HAND",
            rotation = {
                x = 306.0,
                y = 18.0,
                z = 0.0
            },
            model = nil, -- will be set dynamically
            coords = {
                x = 0.12,
                y = 0.09,
                z = -0.05
            }
        },
    },

    ['fill_canteen'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Filling canteen..',
        canStop = true,
        prop = {
            bone = "SKEL_R_HAND",
            rotation = {
                x = 306.0,
                y = 18.0,
                z = 0.0
            },
            model = "p_cs_canteen_hercule",
            coords = {
                x = 0.12,
                y = 0.09,
                z = -0.05
            }
        },

        animation = {
            anim = "idle_a",
            flags = 3,
            animDict = "amb_work@world_human_crouch_inspect@male_c@idle_a"
        },
    },

    ['wash'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Washing yourself..',
        canStop = true,
        animation = {
            anim = "idle_l",
            flags = 17,
            animDict = "amb_misc@world_human_wash_face_bucket@table@male_a@idle_d"
        },
    },

    ['drink_canteen'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Drinking water..',
        canStop = true,
        animation = {
            anim = "idle_a",
            flags = 31,
            animDict = "amb_rest_drunk@world_human_drinking@male_a@idle_a"
        },
        prop = {
            bone = "SKEL_R_Finger12",
            rotation = {
                x = 15.0,
                y = 175.0,
                z = 0.0
            },
            model = nil, -- will be set dynamically
            coords = {
                x = 0.02,
                y = 0.028,
                z = 0.001
            }
        }        
    },

    ['drink_normal'] = {
        item = 'galeata_goala', -- Item to be used in the database as image
        title = 'Drinking water..',
        canStop = true,
        animation = {
            anim = "idle_h",
            flags = 31,
            animDict = "amb_rest_drunk@world_human_bucket_drink@ground@male_a@idle_c"
        },
    }
}

Config.WashSettings = {
    enabled = false, -- if you want to enable the soap requirement
    requireAllItems = true, -- if true all items need to be in the inventory
    WashWithoutClothes = true, -- if you want to wash without clothes

    items = {
        ["sticla_apa"] = {
            durability = 100, -- How much durability the soap has.
        }
    }
}

Config.Animations = {
    ["inject"] = function(propname)
        local ped = PlayerPedId()
        local prop = "mp007_p_mp_syringe01x_1"
        if propname then
            prop = propname
        end
        local prop2 = CreateObject(GetHashKey(prop), GetEntityCoords(ped), false, false, 1, 1, 0)
        TaskItemInteraction_2(ped, 1737033966, prop2, GetHashKey("PrimaryItem"), GetHashKey("USE_STIMULANT_INJECTION_QUICK_LEFT_HAND"), true, 0, 0)
        SetTimeout(3000,function()
            DeleteObject(prop2)
        end)
    end,
}

Config.CampfireObjects = {
    ['p_campfire01x'] = true,
}

Config.Lang = 'EN' -- YOU NEED TO MODIFY IT TOO IN THE FILE CONFIG.JS FOR THE MENU TRANSLATION, THE FOLLOWING MESSAGES ARE JUST FOR NOTIFICATIONS



Config.Text = {
    EN = {
        ['wash_character'] = 'Wash Yourself',
        ['drink_water'] = 'Drink',
        ['fill_canteen'] = 'Fill Canteen',
        ['cannot_wash_clothes'] = 'You cannot wash with your clothes on!',
        ['cannot_drink_mask'] = 'You cannot drink water with a mask on!',
        ['water_damage_received'] = 'You drank dirty water and got hurt!',
        ['water_poison_received'] = 'You drank dirty water and got poisoned! You must vomit to heal!',
        ['vomit'] = 'Vomit',
        ['poison_cured'] = 'You have been cured! Next time, boil your water before drinking!',
        ['not_poisoned'] = 'You don’t need this remedy! You are not poisoned!',
        ['canteen_empty'] = 'This item is empty! Go to a lake and collect water!',
        ['no_canteen'] = 'You don’t have a container to fill!',
        ['canteen_filled'] = 'You filled an item with water! New uses: %s',
        ['canteen_use'] = 'You used this item! Remaining uses: %s.',
        ['cannot_do_poisoned'] = 'You cannot do this while poisoned!',
        ['already_drinking'] = 'You are already doing this! Wait until you finish before trying again.',
        ['fill_bucket'] = 'Fill bucket',
        ['bucket_filled'] = 'You filled the bucket with water!',
        ['no_bucket'] = 'You don’t have a bucket to fill!',
        ['fill_canteen_cancelled'] = 'You have cancelled the filling of the canteen',
        ['fill_bucket_cancelled'] = 'You have cancelled the filling of the bucket',
        ['canteen_description'] = [[
            <div style="font-family: 'Verdana', sans-serif; padding: 15px; border-radius: 8px; background: linear-gradient(to bottom, #2a3440, #1c252e); color: #fff; box-shadow: 0 3px 10px rgba(0,0,0,0.3); max-width: 300px;">
            <div style="display: flex; align-items: center; margin-bottom: 12px;">
                <div style="font-size: 22px; margin-right: 10px;">🧴</div>
                <div style="font-size: 18px; font-weight: bold; text-transform: uppercase; letter-spacing: 1px;">Canteen</div>
            </div>
            
            <div style="display: flex; justify-content: space-between; margin-bottom: 8px;">
                <div style="color: #aaa;">Uses Remaining:</div>
                <div style="font-size: 20px; font-weight: bold; color: #3498db;">%s</div>
            </div>
            
            <div style="display: flex; justify-content: space-between; margin-bottom: 12px;">
                <div style="color: #aaa;">Status:</div>
                <div style="font-weight: bold; color: %s;">%s</div>
            </div>
            
            <div style="background-color: rgba(255,255,255,0.1); border-left: 4px solid #f39c12; padding: 8px; border-radius: 4px; margin-top: 5px;">
                <div style="font-size: 13px; color: #f39c12; margin-bottom: 3px; font-weight: bold;">TIP</div>
                <div style="font-size: 13px;">Always boil your water for safety!</div>
            </div>
            </div>
        ]],
        ['boil_water'] = 'Boil Water',
        ['no_boil'] = 'You have nothing to boil!',
        ['water_boiled'] = 'You successfully boiled the water!',
        ['boiled'] = 'Boiled',
        ['unboiled'] = 'Unboiled',
        ['no_soap'] = 'You have no soap to wash with!',
        ['boil_cancelled'] = 'You have cancelled the boiling of the water',
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
