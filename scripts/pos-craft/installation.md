# POS-Craft Installation Guide

## POS-Craft Crafting System

## Framework Independent

Welcome to the complete installation guide for POS-Craft. This advanced crafting system provides comprehensive item crafting functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Craft. POS-Craft depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Craft, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Craft.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Craft</strong></summary>

Download and install the POS-Craft script:

1. Access your **Keymaster** account
2. Download the **POS-Craft** script
3. Extract the downloaded files
4. Place the `POS-Craft` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Craft/          ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Craft/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Craft
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_craft_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Craft` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Craft         ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Craft loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Craft</strong></summary>

Configure POS-Craft to your liking:

1. Navigate to `resources/[POS]/POS-Craft/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Crafting Locations**: Set up crafting stations and their positions
   * **Job Requirements**: Configure which jobs can access specific crafting stations
   * **Recipes**: Define crafting recipes and requirements
   * **Categories**: Organize crafting items into categories
   * **Discord Webhooks**: Set up logging for crafting activities
4. **Save** your changes
5. **Navigate** to `resources/[POS]/POS-Craft/shared/config.js`
6. **Configure** the language settings.

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes crafting locations, job requirements, recipes, and UI language settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Craft
   * POS-Core integration working properly
   * Database connections established
   * Crafting stations respond to interactions
   * Crafting UI opens correctly
   * Recipes function as configured

#### Common Success Indicators

* ✅ No console errors related to POS-Craft
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Crafting stations appear at configured locations
* ✅ Crafting UI opens and functions correctly
* ✅ Items can be crafted according to recipes
* ✅ Job restrictions work properly
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-Craft related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Craft is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Craft
* Verify POS-Core configuration is correct

**Crafting UI Not Opening**

* Check config.lua for proper crafting station settings
* Verify position coordinates are correct
* Test with different interaction methods
* Ensure client-side scripts are loading correctly

**Recipe Issues**

* Verify recipe configuration in config.lua
* Check that required items exist in your server's item database
* Test with different recipe combinations
* Ensure crafting requirements are met

**Job Restrictions Not Working**

* Check job configuration in crafting stations
* Verify job names match your server's job system
* Test with different job grades and permissions

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
Your POS-Craft crafting system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Craft depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test crafting functionality thoroughly before going live

#### Next Steps

* Configure crafting recipes to match your server's economy
* Set up crafting stations at appropriate locations
* Configure job requirements for different crafting categories
* Set up Discord webhook notifications for crafting activities
* Train your staff on the new crafting system
* Review documentation for advanced configuration options

Your RedM server now has a powerful crafting system that integrates seamlessly with the POS ecosystem!

</details>