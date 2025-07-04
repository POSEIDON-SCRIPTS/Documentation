# POS-IdentityCard Installation Guide

## POS-IdentityCard Identity Management System

## Framework Independent

Welcome to the complete installation guide for POS-IdentityCard. This advanced identity management system provides comprehensive identity card functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-IdentityCard. POS-IdentityCard depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-IdentityCard, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-IdentityCard.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-IdentityCard</strong></summary>

Download and install the POS-IdentityCard script:

1. Access your **Keymaster** account
2. Download the **POS-IdentityCard** script
3. Extract the downloaded files
4. Place the `POS-IdentityCard` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-IdentityCard/   ← Add this folder
```

</details>

<details>

<summary><strong>🗄️ Step 3: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Import the required database structure:

1. Navigate to the `[POS]/POS-IdentityCard/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-IdentityCard
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_identitycard_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🔧 Step 4: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-IdentityCard` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-IdentityCard  ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-IdentityCard loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 5: Configure POS-IdentityCard</strong></summary>

Configure POS-IdentityCard to your liking:

1. Navigate to `resources/[POS]/POS-IdentityCard/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Resources**: Enable/disable integration with other POS scripts
   * **Locations**: Set up identity card office locations
   * **Prices**: Configure pricing for different services
   * **Age Settings**: Set minimum and maximum ages
   * **Discord Webhooks**: Set up logging for identity activities
   * **Items**: Configure identity card items
4. **Save** your changes

```lua
Config.Resources = {
    ['POS-Housing'] = true,
}

Config.DiscordWebhooks = true

Config.AgeSettings = {
    min = 18, -- Minimum age to get a card
    max = 99, -- Maximum age to get a card
}

Config.Prices = {
    normal = {
        register = 100,
        update = 50,
        buy = 50,
    },
    fake = {
        register = 100,
        update = 50,
        delete = 50,
        buy = 50,
    }
}

Config.Locations = {
    [1] = {
        name = 'Saint Denis Station',
        position = vector4(2748.0706, -1396.3884, 45.1831, 30.7514),
        blip = {
            blip = 'blip_special_series_1',
            modifier = false,
        },
        fake = false,
        ped = {
            model = 'CS_mradler'
        }
    },
}

Config.Items = {
    identity_card = 'buletin',
    fake_card = 'buletin_fals',
}
```

5. **Navigate** to `resources/[POS]/POS-IdentityCard/shared/config.js`
6. **Configure** the language settings:

```javascript
TR = {
    LANG: 'EN',
    EN: {
        FIRST_NAME_PLACEHOLDER: "First name",
        LAST_NAME_PLACEHOLDER: "Last name",
        DOB_PLACEHOLDER: "Date of birth",
        CITY_PLACEHOLDER: "City",
        EYES_PLACEHOLDER: "Eye color",
        HAIR_PLACEHOLDER: "Hair color",
        WEIGHT_PLACEHOLDER: "Weight",
        HEIGHT_PLACEHOLDER: "Height",
        SEX_PLACEHOLDER: "Sex",
        JOB_PLACEHOLDER: "Occupation",
    },
}
```

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes office locations, pricing, webhook settings, and UI language.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-IdentityCard
   * Database connections established
   * Identity card offices appear with NPCs
   * Menu opens correctly at offices
   * Identity card registration works
   * Fake card system functions (if configured)

#### Common Success Indicators

* ✅ No console errors related to POS-IdentityCard
* ✅ POS-Core integration messages appear in console
* ✅ Database tables are accessible
* ✅ Identity card offices appear on map
* ✅ NPCs spawn at configured locations
* ✅ Identity card registration works
* ✅ Fake card system functions properly
* ✅ Discord webhooks send notifications (if configured)
* ✅ Server starts without POS-IdentityCard related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-IdentityCard is loaded after POS-Core
* Check that POS-Core is running without errors

**Database Connection Issues**

* Confirm database settings are properly configured
* Check that all SQL files were imported successfully
* Verify database tables exist and have correct permissions

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-IdentityCard
* Verify POS-Core configuration is correct

**Identity Card Offices Not Appearing**

* Check location configuration in config.lua
* Verify position coordinates are correct
* Test with different blip settings
* Ensure NPC models are available

**Menu Not Opening**

* Check interaction distance settings
* Verify menu controls are properly configured
* Test with different menu alignment settings
* Ensure client-side scripts are loading

**Registration/Update Issues**

* Check pricing configuration
* Verify player has sufficient funds
* Test with different age settings
* Ensure items are properly configured

**Fake Card System Problems**

* Check fake card location settings
* Verify fake card pricing configuration
* Test fake card deletion functionality
* Ensure fake card items exist

**Discord Webhook Issues**

* Verify webhook URLs are correct and active
* Check Discord server permissions
* Test webhook functionality independently
* Ensure webhook events are properly configured

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
Your POS-IdentityCard identity management system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-IdentityCard depends on POS-Core - ensure it's always running
* Keep your database backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test identity card functionality thoroughly before going live

#### Next Steps

* Configure identity card offices in appropriate locations
* Set up pricing to match your server's economy
* Configure fake card locations (if desired)
* Set up Discord webhook notifications
* Train your staff on the new identity card system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive identity management system that integrates seamlessly with the POS ecosystem!

</details>