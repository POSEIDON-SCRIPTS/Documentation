# POS-Deposits Installation Guide

## POS-Deposits Storage System

## Framework Independent

Welcome to the complete installation guide for POS-Deposits. This advanced deposit storage system provides secure item storage functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Deposits. POS-Deposits depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Deposits, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Deposits.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Deposits</strong></summary>

Download and install the POS-Deposits script:

1. Access your **Keymaster** account
2. Download the **POS-Deposits** script
3. Extract the downloaded files
4. Place the `POS-Deposits` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Deposits/       ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Deposits/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Deposits
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_deposits_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Deposits` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Deposits      ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Deposits loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Deposits</strong></summary>

Configure POS-Deposits to your liking:

1. Navigate to `resources/[POS]/POS-Deposits/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Deposit Locations**: Set up deposit locations and their positions
   * **Weight Limits**: Configure storage capacity and upgrades
   * **Pricing**: Set slot prices and upgrade costs
   * **Access Control**: Configure job and permission requirements
   * **Discord Webhooks**: Set up logging for deposit activities
4. **Save** your changes

```lua
Config.Deposits = {
    ['DepositSaintDenis'] = {
        showTitle = true,
        title = 'Deposit Saint Denis',
        description = 'Price per access: 0.15$',
        Weight = 250,
        SlotPrice = 1,
        Upgrades = {
            [1] = {
                Weight = 250,
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
        DepositTax = 0.15,
        TaxReductions = {jobs = nil},
        Positions = {
            vector3(3009.2632, 562.3879, 44.6934),
        },
        BlipModel = "blip_chest",
        Webhook = '',
    },
}
```

5. **Configure** access permissions and job requirements.

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes deposit locations, storage limits, pricing, and access control settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Deposits
   * POS-Core integration working properly
   * Database connections established
   * Deposit locations are accessible
   * Deposit UI opens correctly
   * Storage and retrieval functions work
   * Upgrade system functions properly

#### Common Success Indicators

* ✅ No console errors related to POS-Deposits
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Deposit locations appear with correct blips
* ✅ Deposit UI opens and functions correctly
* ✅ Items can be stored and retrieved
* ✅ Access taxes are properly charged
* ✅ Upgrade system works as configured
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-Deposits related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Deposits is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Deposits
* Verify POS-Core configuration is correct

**Deposit UI Not Opening**

* Check config.lua for proper deposit location settings
* Verify position coordinates are correct
* Test with different interaction methods
* Ensure client-side scripts are loading correctly

**Access Tax Issues**

* Verify player has sufficient funds for deposit access
* Check DepositTax configuration in config.lua
* Test with different tax reduction settings

**Storage Issues**

* Check Weight limits in configuration
* Verify upgrade system is properly configured
* Test with different item types and quantities

**Blip Issues**

* Verify BlipModel is set correctly in config
* Check that blip appears at configured positions
* Test with different blip models

**Discord Webhook Issues**

* Verify webhook URL is correct and active
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
Your POS-Deposits storage system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Deposits depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test deposit functionality thoroughly before going live

#### Next Steps

* Configure deposit locations to match your server's economy
* Set appropriate pricing for storage access and upgrades
* Configure access permissions for different user groups
* Set up Discord webhook notifications for deposit activities
* Train your staff on the new deposit system
* Review documentation for advanced configuration options

Your RedM server now has a powerful deposit storage system that integrates seamlessly with the POS ecosystem!

</details>