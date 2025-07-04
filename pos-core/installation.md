# Installation

## POS-Core Foundation System

## Framework Independent

Welcome to the complete installation guide for POS-Core. This foundation system is required for all POS scripts to function properly and provides essential core functionality for the POS ecosystem across both VORP and RSG frameworks.

***

## Prerequisites

<details>

<summary><strong>📋 Prerequisites</strong></summary>

Before beginning the installation process, ensure you have:

* **Server access** with file modification permissions
* **Keymaster** access for script downloads
* **Recent server backup** (highly recommended)

{% hint style="warning" %}
Always backup your server before installing new scripts. POS-Core is a foundation system that other POS scripts depend on.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Prepare the POS Folder Structure</strong></summary>

First, you need to create the proper folder structure for POS scripts:

1. Navigate to your server's `resources` folder
2. Check if a `[POS]` folder exists (note the square brackets)
3. If it doesn't exist, create a new folder named exactly: `[POS]`

```
server/
└── resources/
   └── [POS]/          ← Create this folder
```

{% hint style="info" %}
**Note**: The square brackets `[POS]` are essential for proper resource categorization in RedM.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Core</strong></summary>

POS-Core is the foundation script required for all POS scripts to function properly:

1. Access your **Keymaster** account
2. Download the **POS-Core** script
3. Extract the downloaded files
4. Place the `POS-Core` folder inside your `[POS]` directory

```
[POS]/
└── POS-Core/
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Before proceeding with the installation, you must import the required database structure:

1. Navigate to the `[POS]/POS-Core/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Core
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>⚙️ Step 4: Configure Framework Settings</strong></summary>

Configure POS-Core for your specific framework:

1. Navigate to `resources/[POS]/POS-Core/fxmanifest.lua`
2. **Locate** the framework configuration line
3. **Set** the framework to your desired option:

```lua
framework "vorp" -- USE vorp/rsg/redemrp/custom
```

**Available Framework Options:**

* `"vorp"` - For VORP Framework
* `"rsg"` - For RSG Framework
* `"redemrp"` - For RedEM:RP Framework
* `"custom"` - For Custom Framework Integration

**Examples:**

**For VORP Framework:**

```lua
framework "vorp"
```

**For RSG Framework:**

```lua
framework "rsg"
```

**For RedEM:RP Framework:**

```lua
framework "redemrp"
```

**For Custom Framework:**

```lua
framework "custom"
```

{% hint style="info" %}
**Custom Framework**: When using `"custom"`, you need to configure the integration in `server/customFramework.lua` file.
{% endhint %}

</details>

<details>

<summary><strong>🔧 Step 5: Additional Configuration Options</strong></summary>

POS-Core provides several configuration options for advanced users:

**Main Configuration File:**

* Navigate to `resources/[POS]/POS-Core/shared/config.lua`
* This file contains the main configuration settings for POS-Core

**Custom Framework Integration:**

* If you want to use a custom framework, navigate to `resources/[POS]/POS-Core/server/customFramework.lua`
* Edit this file to integrate with your custom framework
* Make sure to set the framework to `'Custom'` in the fxmanifest.lua

**Override Default Framework Settings:**

* Navigate to `resources/[POS]/POS-Core/shared/overrides.lua`
* Use this file to override default framework settings without modifying core files
* This allows you to customize framework behavior while keeping updates clean

{% hint style="info" %}
**Configuration Priority:**

1. **fxmanifest.lua**: Select your framework
2. **config.lua**: Main configuration settings
3. **overrides.lua**: Override default framework settings
4. **customFramework.lua**: Custom framework integration (if using 'Custom')
{% endhint %}

</details>

<details>

<summary><strong>🔧 Step 6: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Core` directly after your framework core and inventory:

**For VORP Framework:**

```cfg
# VORP Framework
ensure vorp_core
ensure vorp_inventory
ensure POS-Core          ← Add this line here
```

**For RSG Framework:**

```cfg
# RSG Framework
ensure rsg-core
ensure rsg-inventory
ensure POS-Core          ← Add this line here
```

**For RedEM:RP Framework:**

```cfg
# RedEM:RP Framework
ensure redemrp_core
ensure redemrp_inventory
ensure POS-Core          ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Core loads after your framework core and inventory scripts but before any other POS scripts.
{% endhint %}

</details>

***

## Post-Installation Verification

<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

**Testing Your Installation**

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Core
   * Framework integration working properly
   * Database connections established

**Common Success Indicators**

* ✅ No console errors related to POS-Core
* ✅ Framework integration messages appear in console
* ✅ Database tables are accessible
* ✅ Server starts without POS-Core related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

**Common Issues**

**Console Errors About Load Order**

* Verify POS-Core is loaded after your framework core
* Check that framework core loads before POS-Core

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**Framework Integration Issues**

* Ensure the correct framework is specified in fxmanifest.lua using the format: `framework "frameworkname"`
* Available options: "vorp", "rsg", "redemrp", "custom"
* Check shared/config.lua for proper configuration settings
* If using "custom", verify server/customFramework.lua is properly configured
* Check shared/overrides.lua for any conflicting settings

**Getting Support**

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Final Notes

<details>

<summary><strong>📝 Final Notes &#x26; Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-Core foundation system is now installed and ready for use.
{% endhint %}

**Important Reminders**

* POS-Core must be installed before any other POS scripts
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

**Next Steps**

* Install other POS scripts (like POS-Inventory)
* Configure script-specific settings as needed
* Test functionality with your chosen framework
* Review documentation for additional POS scripts

Your RedM server now has the POS-Core foundation system installed and ready to support the entire POS ecosystem!

</details>

***

## Additional Dependencies

<details>

<summary><strong>📦 Required Dependencies</strong></summary>

{% hint style="danger" %}
**Important**: Regardless of your framework choice, you must install the following dependencies for POS-Core to function properly.
{% endhint %}

#### Required Scripts

**1. POS-ProgressBar (Free)**

* Download from the webstore (free script)
* Required for progress bar functionality

**2. Framework Dependencies** Download the following 4 scripts from: [https://github.com/POSEIDON-SCRIPTS/dependencies](https://github.com/POSEIDON-SCRIPTS/dependencies)

* **vorp\_menu** (required even if you're NOT using VORP framework)
* **PolyZone** (if you don't already have it)
* **gs\_gizmo** (if you don't already have it)
* **xsound** (if you don't already have it)

#### Installation Instructions

1. **Download** all required dependencies
2. **Extract** and place them in your `resources` folder
3. **Add** them to your server.cfg in the correct order:

```cfg
# Dependencies (load before POS-Core)
ensure vorp_menu
ensure PolyZone
ensure gs_gizmo
ensure xsound

# Your Framework
ensure your_framework_core
ensure your_framework_inventory
ensure POS-Core
ensure POS-ProgressBar      ← Load after POS-Core
```

{% hint style="warning" %}
**Load Order Critical**: vorp\_menu, PolyZone, gs\_gizmo, and xsound must load before POS-Core. POS-ProgressBar loads after POS-Core.
{% endhint %}

</details>
