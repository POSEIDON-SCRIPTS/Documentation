# POS-DataWipe Installation Guide

## POS-DataWipe Database Management System

## Framework Independent

Welcome to the complete installation guide for POS-DataWipe. This database management system provides automated data cleanup functionality for your RedM server and works seamlessly with the POS ecosystem.

***

## Prerequisites
<details>

<summary><strong>📋 Prerequisites</strong></summary>

Before beginning the installation process, ensure you have:

* **POS-Core** properly installed and running (required)
* **Server access** with file modification permissions
* **Keymaster** access for script downloads
* **Recent server backup** (highly recommended)
* **Database access** for configuration

{% hint style="danger" %}
**Critical Requirement**: POS-Core must be installed before POS-DataWipe. POS-DataWipe depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-DataWipe, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-DataWipe.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-DataWipe</strong></summary>

Download and install the POS-DataWipe script:

1. Access your **Keymaster** account
2. Download the **POS-DataWipe** script
3. Extract the downloaded files
4. Place the `POS-DataWipe` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-DataWipe/       ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-DataWipe` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-DataWipe     ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-DataWipe loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-DataWipe</strong></summary>

Configure POS-DataWipe to your liking:

1. Navigate to `resources/[POS]/POS-DataWipe/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following critical settings:
   * **CheckTime**: How often to check for inactive players (default: 1 hour)
   * **WipeTime**: How long before a player is considered inactive (default: 30 days)
   * **Tables**: Database tables to monitor for cleanup
   * **Webhook**: Discord webhook for notifications
4. **Save** your changes

```lua
Config.CheckTime = 3600 * 1000 -- 1 hour in milliseconds
Config.WipeTime = 3600 * 1000 * 24 * 30 -- 30 days in milliseconds

Config.Tables = {
    ["pos_clans_players"] = {
        identifier = "identifier",
        characterid = "characterid",
    }
}
```

{% hint style="danger" %}
**Critical Configuration**: Carefully configure the Tables section to match your database structure. Incorrect configuration could lead to data loss.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-DataWipe
   * Database cleanup system is active
   * Discord webhooks are functioning (if configured)

#### Common Success Indicators

* ✅ No console errors related to POS-DataWipe
* ✅ POS-Core integration messages appear in console
* ✅ Database monitoring is active
* ✅ Cleanup timers are functioning
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-DataWipe related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-DataWipe is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that database tables exist and have correct permissions
* Verify table names and column names match your configuration

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-DataWipe
* Verify POS-Core configuration is correct

**Data Cleanup Not Working**

* Check config.lua for proper table configuration
* Verify CheckTime and WipeTime settings
* Monitor console for cleanup activity messages

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
Your POS-DataWipe database management system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-DataWipe depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* **Be extremely careful** with table configuration to avoid data loss

#### Next Steps

* Configure cleanup settings to match your server's needs
* Test data cleanup functionality in a safe environment
* Set up Discord webhook notifications
* Train your staff on the new cleanup system
* Review documentation for advanced configuration options

Your RedM server now has a powerful database management system that integrates seamlessly with the POS ecosystem!

</details>
