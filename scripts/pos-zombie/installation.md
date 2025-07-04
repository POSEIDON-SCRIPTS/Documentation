# POS-Zombie Installation Guide

## POS-Zombie Survival System

## Framework Independent

Welcome to the complete installation guide for POS-Zombie. This advanced zombie survival system provides comprehensive zombie mechanics, safe zones, and airdrops for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Zombie. POS-Zombie depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Zombie, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Zombie.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Zombie</strong></summary>

Download and install the POS-Zombie script:

1. Access your **Keymaster** account
2. Download the **POS-Zombie** script
3. Extract the downloaded files
4. Place the `POS-Zombie` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Zombie/         ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Zombie/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Zombie
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_zombie_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Zombie` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Zombie        ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Zombie loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Zombie</strong></summary>

Configure POS-Zombie to your liking:

1. Navigate to `resources/[POS]/POS-Zombie/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Safe Zone Settings**: Configure safe zones with weapon/damage restrictions
   * **Zombie Settings**: Set up zombie behavior and sounds
   * **Looting System**: Configure zombie and airdrop looting
   * **Airdrop System**: Set up supply drops
   * **Commands**: Admin commands for zone/airdrop management
4. **Save** your changes

```lua
Config.SafeZone = {
    show = true,
    disableWeapon = true,
    invincible = true,
    disableMelee = true,
}

Config.ZombieSettings = {
    sound = 'https://www.youtube.com/watch?v=z7NJYzvDIVE',
    distance = 25.0,
    zombieSounds = {
        {
            name = "ZombieAmbient_1",
            index = 1,
            playing = false,
            delay = 0,
            lastStart = 0
        },
    },
    walks = {
        {"default", "very_drunk"},
        {"murfree", "very_drunk"},
        {"default", "dehydrated_unarmed"},
    }
}
```

5. **Configure Looting System**:

```lua
Config.Looting = {
    enabled = true,
    deleteAfterLoot = true,
    chances = {
        money = 30,
        item = 50,
        receiveBoth = 20,
    },
    
    moneyAmounts = {
        min = 1,
        max = 100
    },

    itemList = {
        { name = "WEAPON_PISTOL_MAUSER", amount = 1, chance = 2 }, 
        { name = "empty_bucket", amount = 1, chance = 20 }, 
        { name = "apple_seeds", amount = 1, chance = 78 }, 
    }
}
```

6. **Configure Airdrop System**:

```lua
Config.AirDrops = {
    enabled = true,
    velocity = -0.5,
    cooldown = { 60000, 120000 },
    deleteAfterLoot = true,
    notification = true,
    locations = {
        [1] = {
            prop = {
                model = 'p_toolshed02x',
                offset = -6.5
            },
            blip = {
                model = 'blip_mission_area_bounty',
                size = 25.0,
                modifier = 'BLIP_MODIFIER_AREA'
            },
            coords = {
                vector4(2395.3281, -1369.6479, 44.7530, 55.6714)
            },
        }
    },
}
```

7. **Navigate** to `resources/[POS]/POS-Zombie/shared/configs/zombies.lua`
8. **Configure** zombie models and health:

```lua
Config.Zombies = {
    {
        model = 'CS_MrAdler',
        outfit = 1,
        health = 300,
    },
    {
        model = 'CS_ODProstitute',
        outfit = 0,
        health = 300,
    },
    {
        model = 'CS_SwampFreak',
        outfit = 0,
        health = 300,
    },
    -- Add more zombie configurations as needed
}
```

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes zombie behavior, safe zones, loot systems, and airdrop mechanics.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Zombie
   * Database connections established
   * Safe zone system functioning
   * Zombie spawning and behavior working
   * Looting system operational
   * Airdrop system functional

#### Common Success Indicators

* ✅ No console errors related to POS-Zombie
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Safe zones work correctly
* ✅ Zombie system spawns and behaves properly
* ✅ Looting mechanics function
* ✅ Airdrop system operational
* ✅ Admin commands work
* ✅ Server starts without POS-Zombie related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Zombie is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Zombie
* Verify POS-Core configuration is correct

**Zombie System Not Working**

* Check zombie configuration in zombies.lua
* Verify zombie models and outfits are valid
* Test zombie spawning and AI behavior

**Safe Zone Issues**

* Check safe zone configuration settings
* Verify safe zone creation commands work
* Test safe zone boundaries and restrictions

**Looting System Problems**

* Check looting configuration settings
* Verify loot table items exist in database
* Test looting mechanics and chances

**Airdrop System Issues**

* Check airdrop configuration settings
* Verify airdrop spawn locations are accessible
* Test airdrop spawning and looting

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
Your POS-Zombie survival system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Zombie depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test zombie functionality thoroughly before going live

#### Next Steps

* Configure zombie models and behavior for your server
* Set up safe zones in appropriate locations
* Configure loot tables to match your server's economy
* Set up airdrop locations and schedules
* Train your staff on the new zombie system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive zombie survival system that integrates seamlessly with the POS ecosystem!

</details>