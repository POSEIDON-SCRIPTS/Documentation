# POS-Farming Installation Guide

## POS-Farming Agricultural System

## Framework Independent

Welcome to the complete installation guide for POS-Farming. This advanced agricultural system provides comprehensive farming functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Farming. POS-Farming depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Farming, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Farming.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Farming</strong></summary>

Download and install the POS-Farming script:

1. Access your **Keymaster** account
2. Download the **POS-Farming** script
3. Extract the downloaded files
4. Place the `POS-Farming` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Farming/        ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Farming/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Farming
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_farming_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Farming` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Farming       ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Farming loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Farming</strong></summary>

Configure POS-Farming to your liking:

1. Navigate to `resources/[POS]/POS-Farming/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Plant Configuration**: Set up available plants and their growth requirements
   * **Zones**: Configure farming zones and restrictions
   * **Items**: Define water buckets, fertilizer items, and tools
   * **Growth Settings**: Configure plant growth times and conditions
   * **Discord Webhooks**: Set up logging for farming activities
   * **Commands**: Admin commands for zone management
4. **Save** your changes

```lua
Config.Plants = {
    ['corn_harvest'] = {
        item = 'corn_cob',
        amount = {
            min = 2,
            max = 6
        },
        required = {
            water = true,
            fertilizer = true,
        },
        removeAfterHarvest = true,
        time = 1800, -- 30 minutes
        type = 'corn',
        description = 'Golden corn stalks that produce nutritious corn cobs.',
        seedChance = 45,
        temp = {
            min = 15,
            max = 35,
        }
    },
}

Config.BucketItems = {
    ['galeata_goala'] = {
        value = 50, -- water to increase
        uses = 3, -- how many times can you water before empty
    }
}

Config.FertilizerItems = {
    ['fertilizant'] = {
        value = 50, -- fertilizer to increase
    }
}
```

5. **Navigate** to `resources/[POS]/POS-Farming/shared/config.js`
6. **Configure** the language settings:

```javascript
TR = {
    LANG: 'EN',
    EN: {
        GROWTH: "Growth", 
        FERTILITY: "Fertility",
        WATER: "Water",
    },
}
```

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes plant types, growth requirements, zone settings, and UI language.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Farming
   * POS-Core integration working properly
   * Database connections established
   * Plant system responds to interactions
   * Zone creation commands work
   * Farming UI displays correctly

#### Common Success Indicators

* ✅ No console errors related to POS-Farming
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Plants can be planted and harvested
* ✅ Water and fertilizer systems work
* ✅ Zone management commands function
* ✅ Plant growth timers operate correctly
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-Farming related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Farming is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Farming
* Verify POS-Core configuration is correct

**Plant System Not Working**

* Check plant configuration in config.lua
* Verify plant types and growth requirements
* Test with different plant varieties
* Ensure required items exist in server database

**Zone System Issues**

* Verify zone creation commands work properly
* Check zone boundaries and restrictions
* Test zone-specific plant permissions

**Water/Fertilizer System Problems**

* Check bucket and fertilizer item configurations
* Verify item names match server database
* Test water and fertilizer application

**Growth Timer Issues**

* Check Duration settings in config.lua
* Verify rain detection function works
* Test plant growth progression

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
Your POS-Farming agricultural system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Farming depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test farming functionality thoroughly before going live

#### Next Steps

* Configure plant varieties to match your server's economy
* Set up farming zones in appropriate locations
* Configure water and fertilizer systems
* Set up Discord webhook notifications for farming activities
* Train your staff on the new farming system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive agricultural system that integrates seamlessly with the POS ecosystem!

</details>