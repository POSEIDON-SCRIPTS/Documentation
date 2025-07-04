# POS-Metabolism Installation Guide

## POS-Metabolism Survival System

## Framework Independent

Welcome to the complete installation guide for POS-Metabolism. This advanced survival system provides comprehensive metabolism mechanics including hunger, thirst, temperature, and hygiene for your RedM server and works seamlessly with the POS ecosystem.

***

## Prerequisites
<details>

<summary><strong>📋 Prerequisites</strong></summary>

Before beginning the installation process, ensure you have:

* **POS-Core** properly installed and running (required)
* **Server access** with file modification permissions
* **Keymaster** access for script downloads
* **Recent server backup** (highly recommended)
* **Database access** for table import

{% hint style="danger" %}
**Critical Requirement**: POS-Core must be installed before POS-Metabolism. POS-Metabolism depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Metabolism, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Metabolism.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Metabolism</strong></summary>

Download and install the POS-Metabolism script:

1. Access your **Keymaster** account
2. Download the **POS-Metabolism** script
3. Extract the downloaded files
4. Place the `POS-Metabolism` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Metabolism/     ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Metabolism/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Metabolism
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_metabolism_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Metabolism` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Metabolism    ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Metabolism loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Metabolism</strong></summary>

Configure POS-Metabolism to your liking:

1. Navigate to `resources/[POS]/POS-Metabolism/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **MaxHealth**: Maximum player health
   * **HudSettings**: Configure metabolism elements (food, water, temperature, etc.)
   * **Items**: Set up consumable items and their effects
   * **ClothesTemperature**: Configure clothing temperature values
   * **VoiceChat**: Set voice chat integration
   * **Commands**: Admin commands for metabolism management
4. **Save** your changes

```lua
Config.MaxHealth = 600

Config.HudSettings = {
    food = {
        enabled = true,
        decrease = 0.02,
        decreaseWhileRunning = 0.06,
        damage = 20,
        time = 5000
    },
    water = {
        enabled = true,
        decrease = 0.03,
        decreaseWhileRunning = 0.08,
        damage = 20,
        time = 5000
    },
    temperature = {
        enabled = true,
        time = 10000,
        damage = 15,
        coldValue = -10,
        hotValue = 40,
    },
}

Config.Items = {
    ["alcool"] = {
        playerStats = {
            water = 20,
            food = 0,
            health = 50,
            alcohol = 10,
            stress = -20,
        },
        animation = "drink",
    },
}
```

5. **Navigate** to `resources/[POS]/POS-Metabolism/shared/config.js`
6. **Configure** the HUD settings and language:

```javascript
TR = {
    LANG: 'EN',
    EN: {
        SAVE: "Save SETTINGS ", 
        HUD_STYLE: "🎮 HUD STYLE",
        COLOR_SETTINGS: "🌈 COLOR",
        SETTINGS: 'SETT<span style="color: white">INGS</span>',
    }
}

Config = {
    IconType: 3, // Change this 1, 2, 3
    icons: {
        health: {
            show: true,
            box: {
                text: true,
                icon: 'fa-solid fa-heart',
                mainColor: '#f44336',
            }
        },
        // ... other icon configurations
    }
};
```

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes metabolism rates, item effects, HUD appearance, and language settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Metabolism
   * Database connections established
   * Metabolism HUD displays correctly
   * Food and water decrease over time
   * Items can be consumed and affect stats
   * Temperature system responds to environment

#### Common Success Indicators

* ✅ No console errors related to POS-Metabolism
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Metabolism HUD displays and updates
* ✅ Food/water/temperature systems work
* ✅ Items affect player stats correctly
* ✅ Admin commands function properly
* ✅ Server starts without POS-Metabolism related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Metabolism is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Metabolism
* Verify POS-Core configuration is correct

**HUD Not Displaying**

* Check HudSettings configuration in config.lua
* Verify config.js HUD settings are correct
* Test with different HUD styles
* Ensure client-side scripts are loading

**Metabolism Not Working**

* Check that metabolism systems are enabled in config
* Verify update intervals are properly set
* Test with different metabolism rates

**Items Not Working**

* Check Items configuration in config.lua
* Verify item names match server database
* Test item consumption and effects

**Temperature System Issues**

* Check ClothesTemperature configuration
* Verify temperature thresholds are correct
* Test with different weather conditions

#### Getting Support

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Check POS-Core**: Ensure POS-Core is working properly
4. **Test Database**: Verify database operations are working
5. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Final Notes 

<details>

<summary><strong>📝 Final Notes & Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-Metabolism survival system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Metabolism depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test metabolism functionality thoroughly before going live

#### Next Steps

* Configure metabolism rates to match your server's gameplay
* Set up consumable items and their effects
* Configure HUD appearance and language settings
* Test temperature and survival mechanics
* Train your staff on the new metabolism system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive survival system that integrates seamlessly with the POS ecosystem!

</details>