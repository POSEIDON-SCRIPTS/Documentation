# POS-Backpacks Installation Guide

## POS-Backpacks Inventory Management System

## Framework Independent

Welcome to the complete installation guide for POS-Backpacks. This advanced inventory management system provides enhanced backpack functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Backpacks. POS-Backpacks depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Backpacks, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Backpacks.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Backpacks</strong></summary>

Download and install the POS-Backpacks script:

1. Access your **Keymaster** account
2. Download the **POS-Backpacks** script
3. Extract the downloaded files
4. Place the `POS-Backpacks` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Backpacks/      ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Backpacks/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Backpacks
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_backpacks_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Backpacks` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Backpacks     ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Backpacks loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Backpacks</strong></summary>

Configure POS-Backpacks to your liking:

1. Navigate to `resources/[POS]/POS-Backpacks/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Save** your changes

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes backpack types, storage limits, and interaction settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Backpacks
   * POS-Core integration working properly
   * Database connections established
   * Backpack system responds to interactions
   * Inventory management functions correctly

#### Common Success Indicators

* ✅ No console errors related to POS-Backpacks
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Backpack UI opens and functions correctly
* ✅ Items can be stored and retrieved from backpacks
* ✅ Server starts without POS-Backpacks related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Backpacks is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Backpacks
* Verify POS-Core configuration is correct

**Backpack UI Not Opening**

* Check config.lua for proper UI settings
* Verify client-side scripts are loading correctly
* Test with different interaction methods 
* Make sure items in the config match the database.

**Items Not Saving in Backpacks**

* Verify database connection is working

**Performance Issues**

* Monitor server performance with backpack operations
* Check for database query optimization
* Verify memory usage during inventory operations

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
Your POS-Backpacks inventory management system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Backpacks depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test backpack functionality thoroughly before going live

#### Next Steps

* Configure backpack settings to match your server's style
* Test inventory management with different item types
* Train your staff on the new backpack system
* Review documentation for advanced configuration options
* Set up appropriate permissions for backpack usage

Your RedM server now has a powerful backpack system that integrates seamlessly with the POS ecosystem!

</details>