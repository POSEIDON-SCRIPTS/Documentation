# POS-ItemStacks Installation Guide

## POS-ItemStacks Item Management System

## Framework Independent

Welcome to the complete installation guide for POS-ItemStacks. This advanced item management system provides enhanced item stacking and transformation functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-ItemStacks. POS-ItemStacks depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-ItemStacks, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-ItemStacks.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-ItemStacks</strong></summary>

Download and install the POS-ItemStacks script:

1. Access your **Keymaster** account
2. Download the **POS-ItemStacks** script
3. Extract the downloaded files
4. Place the `POS-ItemStacks` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-ItemStacks/     ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-ItemStacks` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-ItemStacks   ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-ItemStacks loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-ItemStacks</strong></summary>

Configure POS-ItemStacks to your liking:

1. Navigate to `resources/[POS]/POS-ItemStacks/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Items**: Define item transformation rules
   * **removeItems**: Items to remove during transformation
   * **addItems**: Items to add during transformation
   * **cash**: Cash rewards for transformations
   * **Language**: Set your preferred language
4. **Save** your changes

```lua
Config.Items = {
    ['sticla_apa'] = {
        removeItems = {
            { item = 'sticla_apa', count = 1, chance = 100 },
        },
        addItems = {
            { item = 'sfoara', count = 1, chance = 100 },
            { item = 'WEAPON_PISTOL_MAUSER', count = 1, chance = 50 },
        },
        cash = {1, 5},
    }
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes item transformation rules, cash rewards, and probability settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-ItemStacks
   * Item transformation system works correctly
   * Cash rewards are distributed properly
   * Inventory management functions properly

#### Common Success Indicators

* ✅ No console errors related to POS-ItemStacks
* ✅ POS-Core integration messages appear in console
* ✅ Item transformations work as configured
* ✅ Cash rewards are properly distributed
* ✅ Inventory space checks function correctly
* ✅ Probability systems work as expected
* ✅ Server starts without POS-ItemStacks related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-ItemStacks is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-ItemStacks
* Verify POS-Core configuration is correct

**Item Transformation Not Working**

* Check config.lua for proper item configuration
* Verify item names match your server's item database
* Test with different items and transformation rules

**Inventory Space Issues**

* Verify inventory space checks are functioning
* Check that players have sufficient inventory space
* Test with different inventory management systems

**Cash Rewards Not Working**

* Check cash reward configuration in config.lua
* Verify cash range settings are correct
* Test cash distribution with different amounts

**Probability System Issues**

* Check chance percentages in item configuration
* Verify probability calculations are working
* Test with different chance values

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
Your POS-ItemStacks item management system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-ItemStacks depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure item transformation rules to match your server's economy
* Test item transformations with different combinations
* Set up cash rewards that balance your server's economy
* Train your staff on the new item management system
* Review documentation for advanced configuration options

Your RedM server now has a powerful item management system that integrates seamlessly with the POS ecosystem!

</details>
