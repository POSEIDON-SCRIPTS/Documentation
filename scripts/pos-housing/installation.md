# POS-Housing Installation Guide

## POS-Housing Property Management System

## Framework Independent

Welcome to the complete installation guide for POS-Housing. This advanced property management system provides comprehensive housing functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Housing. POS-Housing depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Housing, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Housing.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Housing</strong></summary>

Download and install the POS-Housing script:

1. Access your **Keymaster** account
2. Download the **POS-Housing** script
3. Extract the downloaded files
4. Place the `POS-Housing` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Housing/        ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Housing/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Housing
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_housing_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Housing` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Housing       ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Housing loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Housing</strong></summary>

Configure POS-Housing to your liking:

1. Navigate to `resources/[POS]/POS-Housing/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **House Types**: Define different house categories and their features
   * **Furniture System**: Configure furniture categories and items
   * **Locksmith System**: Set up locksmith locations and pricing
   * **Blips**: Configure map markers for different property types
   * **Access Control**: Set up job and permission restrictions
   * **Discord Webhooks**: Set up logging for housing activities
   * **Commands**: Admin commands for house management
4. **Save** your changes

```lua
Config.HouseTypes = {
    [1] = {
        stash = 500, 
        furniture = {
            outfit = false,
            stash = true,
            phone = false,
            crafting = false,
        },
        farming = false,
    },
    [2] = {
        stash = 1000,
        furniture = {
            outfit = false,
            stash = true,
            phone = false,
            crafting = false,
        },
        farming = false,
    },
    [5] = {
        stash = 2500,
        furniture = {
            outfit = true,
            stash = true,
            phone = true,
            crafting = true,
        },
        farming = true,
    },
}

Config.Locksmith = {
    enableNpc = true,
    Jobs = {
        'police',
    },
    Items = {
        stash = 'cheie_cufar',
        house = 'cheie_casa',
        door = 'cheie_usa',
        locksmith = 'mdt',
    },
    Positions = {
        vector4(2715.8452, -1194.2130, 50.6709, 104.6428)
    },
}
```

5. **Navigate** to `resources/[POS]/POS-Housing/shared/configs/furniture.lua`
6. **Configure** furniture categories and items:

```lua
Config.Furniture = {
    distance = 400,
    max = 50,
    returnToPlayer = true,
    returnMoneyPercentage = 0.5,
    furnitureType = 3, -- 1 = items, 2 = menu, 3 = both
    
    stores = {
        [1] = {
            mainCoords = vector4(2626.0398, -1442.5376, 45.4752, 278.9376),
            categories = {
                [1] = {
                    name = "TABLES",
                    furniture = {
                        [1] = { item = "kitchencounter", prop = "p_kitchenhutch01x", itemType = "normal", price = 350 },
                        [2] = { item = "p_table02x", prop = "p_table02x", itemType = "normal", price = 210 },
                    }
                },
                [5] = {
                    name = "STORAGE",
                    furniture = {
                        [1] = { item = "bookcase", prop = "p_cabinetdoctor01x", itemType = "stash", price = 200 },
                        [2] = { item = "p_nbmbookshelves01x", prop = "p_nbmbookshelves01x", itemType = "stash", price = 250 },
                    }
                },
            }
        }
    }
}
```

7. **Navigate** to `resources/[POS]/POS-Housing/shared/config.js`
8. **Configure** the language settings:

```javascript
TR = {
    LANG: 'EN',
    EN: {
        OWNER: "Owner", 
        PERSONAL: "Personal",
        SALE: "Sale",
    },
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config files and adjust them to match your server's needs. This includes house types, furniture systems, locksmith settings, and UI language.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Housing
   * POS-Core integration working properly
   * Database connections established
   * House creation commands work
   * Furniture system responds correctly
   * Locksmith system functions properly
   * Housing UI displays correctly

#### Common Success Indicators

* ✅ No console errors related to POS-Housing
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Houses can be created and managed
* ✅ Furniture system works correctly
* ✅ Locksmith system functions properly
* ✅ House buying and selling works
* ✅ Access control systems function
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-Housing related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Housing is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Housing
* Verify POS-Core configuration is correct

**House Creation/Management Issues**

* Check admin permissions for house management commands
* Verify house coordinates are correctly set
* Test house interaction distance settings

**Furniture System Problems**

* Check furniture configuration in furniture.lua
* Verify furniture store locations and coordinates
* Test furniture placement and removal

**Locksmith System Issues**

* Verify locksmith NPC spawns correctly
* Check locksmith item configurations
* Test key generation and usage

**Access Control Problems**

* Check job and permission configurations
* Verify house access lists work correctly
* Test tenant management system

**Discord Webhook Issues**

* Verify webhook URLs are correct and active
* Check Discord server permissions
* Test webhook functionality independently

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
Your POS-Housing property management system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Housing depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test housing functionality thoroughly before going live

#### Next Steps

* Configure house types to match your server's economy
* Set up furniture stores in appropriate locations
* Configure locksmith locations and pricing
* Set up Discord webhook notifications for housing activities
* Train your staff on the new housing management system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive property management system that integrates seamlessly with the POS ecosystem!

</details>