# POS-DoorLocks Installation Guide

## POS-DoorLocks Security System

## Framework Independent

Welcome to the complete installation guide for POS-DoorLocks. This advanced security system provides comprehensive door locking functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-DoorLocks. POS-DoorLocks depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-DoorLocks, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-DoorLocks.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-DoorLocks</strong></summary>

Download and install the POS-DoorLocks script:

1. Access your **Keymaster** account
2. Download the **POS-DoorLocks** script
3. Extract the downloaded files
4. Place the `POS-DoorLocks` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-DoorLocks/      ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-DoorLocks/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-DoorLocks
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_doorlocks_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-DoorLocks` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-DoorLocks    ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-DoorLocks loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-DoorLocks</strong></summary>

Configure POS-DoorLocks to your liking:

1. Navigate to `resources/[POS]/POS-DoorLocks/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **DistanceToUnlockDoor**: Interaction distance (default: 3)
   * **Discord Webhooks**: Enable/disable webhook notifications
   * **Lockpick Settings**: Configure lockpick items and durability
   * **Commands**: Admin commands for door management
   * **Controls**: Key bindings for door interactions
4. **Save** your changes

```lua
Config.DistanceToUnlockDoor = 3
Config.DiscordWebhooks = true

Config.Lockpicks = {
    ["lockpick"] = {
        durability = 100,
        returnOnRemove = true,
        returnItems = false,
        requireAdditionalItems = false,
    },
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes door interaction settings, lockpick mechanics, and permission systems.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-DoorLocks
   * Door locking system responds correctly
   * Database connections are established
   * Admin commands are functional

#### Common Success Indicators

* ✅ No console errors related to POS-DoorLocks
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Door creation and management commands work
* ✅ Door locking/unlocking functions properly
* ✅ Lockpick system is operational (if configured)
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-DoorLocks related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-DoorLocks is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-DoorLocks
* Verify POS-Core configuration is correct

**Door Creation/Management Issues**

* Check admin permissions for door management commands
* Verify door coordinates are correctly set
* Test door interaction distance settings

**Lockpick System Not Working**

* Verify lockpick items are properly configured
* Check that minigame system is installed (if required)
* Test lockpick durability and return settings

**Discord Webhook Issues**

* Verify webhook URL is correct and active
* Check Discord server permissions
* Test webhook functionality independently

#### Getting Support

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Check POS-Core**: Ensure POS-Core is working properly
4. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Final Notes 

<details>

<summary><strong>📝 Final Notes & Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-DoorLocks security system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-DoorLocks depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure door settings to match your server's security needs
* Create initial door configurations for important locations
* Set up Discord webhook notifications
* Train your staff on the new door management system
* Review documentation for advanced configuration options

Your RedM server now has a powerful security system that integrates seamlessly with the POS ecosystem!

</details>
