# POS-Blips Installation Guide

## POS-Blips Map Management System

## Framework Independent

Welcome to the complete installation guide for POS-Blips. This advanced blip management system provides enhanced map functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Blips. POS-Blips depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Blips, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Blips.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Blips</strong></summary>

Download and install the POS-Blips script:

1. Access your **Keymaster** account
2. Download the **POS-Blips** script
3. Extract the downloaded files
4. Place the `POS-Blips` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Blips/          ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Blips/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Blips
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_blips_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Blips` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Blips         ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Blips loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Blips</strong></summary>

Configure POS-Blips to your liking:

1. Navigate to `resources/[POS]/POS-Blips/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Save** your changes

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes blip types, colors, sizes, and visibility settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Blips
   * POS-Core integration working properly
   * Database connections established
   * Blip system responds to interactions
   * Map blips display correctly

#### Common Success Indicators

* ✅ No console errors related to POS-Blips
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Blips appear on the map correctly
* ✅ Blip management functions work properly
* ✅ Server starts without POS-Blips related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Blips is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Blips
* Verify POS-Core configuration is correct

**Blips Not Appearing on Map**

* Check config.lua for proper blip settings
* Verify client-side scripts are loading correctly
* Test with different blip types and colors
* Make sure blip coordinates are correct in the database

**Blip Management Issues**

* Verify database connection is working
* Check that blip data is being properly stored
* Ensure blip permissions are configured correctly
* Test blip creation and deletion functions

**Performance Issues**

* Monitor server performance with blip operations
* Check for database query optimization
* Verify memory usage during blip rendering
* Consider limiting the number of visible blips

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
Your POS-Blips map management system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Blips depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test blip functionality thoroughly before going live

#### Next Steps

* Configure blip settings to match your server's style
* Test blip management with different blip types
* Train your staff on the new blip system
* Review documentation for advanced configuration options
* Set up appropriate permissions for blip management
* Create custom blips for your server's unique locations

Your RedM server now has a powerful blip system that integrates seamlessly with the POS ecosystem!

</details>
