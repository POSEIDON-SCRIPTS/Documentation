# POS-Alerts Installation Guide

## POS-Alerts Notification System

## Framework Independent

Welcome to the complete installation guide for POS-Alerts. This notification system provides advanced alert functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Alerts. POS-Alerts depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Alerts, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Alerts.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Alerts</strong></summary>

Download and install the POS-Alerts script:

1. Access your **Keymaster** account
2. Download the **POS-Alerts** script
3. Extract the downloaded files
4. Place the `POS-Alerts` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Alerts/         ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-Alerts/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Alerts
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_alerts_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Alerts` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Alerts        ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Alerts loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-Alerts</strong></summary>

Configure POS-Alerts to your liking:

1. Navigate to `resources/[POS]/POS-Alerts/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Save** your changes

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Alerts
   * POS-Core integration working properly
   * Database connections established
   * Alert system responds to triggers

#### Common Success Indicators

* ✅ No console errors related to POS-Alerts
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Alert notifications display correctly
* ✅ Server starts without POS-Alerts related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Alerts is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Alerts
* Verify POS-Core configuration is correct

**Alerts Not Displaying**

* Check config.lua for proper alert settings
* Verify client-side scripts are loading correctly
* Test with different alert trigger methods

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
Your POS-Alerts notification system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Alerts depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure alert settings to match your server's style
* Test alert functionality with different trigger methods
* Train your staff on the new alert system
* Review documentation for advanced configuration options

Your RedM server now has a powerful alert system that integrates seamlessly with the POS ecosystem!

</details>

