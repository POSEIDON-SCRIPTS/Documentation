# POS-River Installation Guide

## POS-River Water Interaction System

## Framework Independent

Welcome to the complete installation guide for POS-River. This advanced water interaction system provides comprehensive water-based activities for your RedM server and works seamlessly with the POS ecosystem.

***

## Prerequisites
<details>

<summary><strong>📋 Prerequisites</strong></summary>

Before beginning the installation process, ensure you have:

* **POS-Core** properly installed and running (required)
* **Server access** with file modification permissions
* **Keymaster** access for script downloads
* **Recent server backup** (highly recommended)

{% hint style="danger" %}
**Critical Requirement**: POS-Core must be installed before POS-River. POS-River depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-River, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-River.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-River</strong></summary>

Download and install the POS-River script:

1. Access your **Keymaster** account
2. Download the **POS-River** script
3. Extract the downloaded files
4. Place the `POS-River` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-River/          ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-River` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-River         ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-River loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-River</strong></summary>

Configure POS-River to your liking:

1. Navigate to `resources/[POS]/POS-River/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Water Locations**: Configure different water sources
   * **Interaction Settings**: Set up drink/shower/wash options
   * **Canteen Items**: Configure water containers
   * **Cure Items**: Set up medical items
   * **Controls**: Key bindings for water interactions
4. **Save** your changes

```lua
Config.WaterLocations = {
    [1] = {
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
        }
    },
}
```

5. **Configure Canteen Items**:

```lua
Config.CanteenItems = {
    ["pleosca"] = {
        uses = 5,   -- How many uses the canteen has
        fillDuration = 10000, -- How long it takes to fill
        boilDuration = 10000, -- How long it takes to boil water
        model = "p_cs_canteen_hercule",
    }
}
```

6. **Configure Water Objects**:

```lua
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
            }
        }
    }
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes water sources, interaction options, and survival mechanics.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-River
   * Water interaction system working correctly
   * Canteen filling/usage functioning
   * Poison/cure system operational

#### Common Success Indicators

* ✅ No console errors related to POS-River
* ✅ POS-Core integration messages appear in console
* ✅ Water locations respond to interactions
* ✅ Drink/shower/wash functions work correctly
* ✅ Canteen system functional
* ✅ Poison and cure mechanics working
* ✅ Server starts without POS-River related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-River is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-River
* Verify POS-Core configuration is correct

**Water Interactions Not Working**

* Check water location configurations
* Verify water hash codes are correct
* Test with different water sources

**Canteen System Issues**

* Check canteen item configurations
* Verify canteen models exist
* Test filling and usage mechanics

**Poison/Cure System Problems**

* Check poison chance settings
* Verify cure item configurations
* Test poison and cure mechanics

**Animation Issues**

* Check animation configurations
* Verify animation dictionaries load
* Test with different animation types

#### Getting Support

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Check POS-Core**: Ensure POS-Core is working properly
4. **Test Configuration**: Verify all config settings are correct
5. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Final Notes 

<details>

<summary><strong>📝 Final Notes & Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-River water interaction system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-River depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure water locations for your server's map
* Set up canteen items and water containers
* Configure poison/cure mechanics for survival gameplay
* Test water interaction systems thoroughly
* Train your staff on the new water system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive water interaction system that integrates seamlessly with the POS ecosystem!

</details>