# POS-Interactions Installation Guide

## POS-Interactions Animation System

## Framework Independent

Welcome to the complete installation guide for POS-Interactions. This advanced interaction system provides comprehensive animation and item usage functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Interactions. POS-Interactions depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Interactions, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Interactions.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Interactions</strong></summary>

Download and install the POS-Interactions script:

1. Access your **Keymaster** account
2. Download the **POS-Interactions** script
3. Extract the downloaded files
4. Place the `POS-Interactions` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Interactions/   ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Interactions` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Interactions  ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Interactions loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-Interactions</strong></summary>

Configure POS-Interactions to your liking:

1. Navigate to `resources/[POS]/POS-Interactions/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Controls**: Set keybinds for smoking controls
   * **Items**: Configure usable items and their actions
   * **ActionTypes**: Define item interaction behaviors
   * **Animation Positions**: Set smoking and interaction animations
   * **Language**: Set your preferred language
4. **Save** your changes

```lua
Config.Controls = {
    StopSmoke = 0x760A9C6F,
    Smoke = 0xB2F377E8,
    ChangePosition = 0x26E9DC00,
}

Config.Items = {
    ['ciuperca_halucinogena'] = {
        removeItem = false,
        returnOnRemove = true,
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'mushrooms',
        args = {
            animation = 'mushroom'
        },
    },
    ['tigara'] = {
        removeItem = false,
        returnOnRemove = true,
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'cigarette',
        args = {},
    },
    ['pipa'] = {
        removeItem = false,
        returnOnRemove = true,
        returnItems = false,
        requireAdditionalItems = false,
        actionType = 'pipe',
        args = {},
    },
}

Config.ActionTypes = {
    ['mushrooms'] = function(source, data)
        MushroomEvent(source, data.animation)
    end,
    ['cigarette'] = function(source)
        SmokeCigarette(source)
    end,
    ['pipe'] = function(source)
        SmokePipe(source)
    end,
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes item interactions, animations, controls, and language settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Interactions
   * Item interactions work correctly
   * Smoking animations function properly
   * Controls respond as expected
   * Animations and props display correctly

#### Common Success Indicators

* ✅ No console errors related to POS-Interactions
* ✅ POS-Core integration messages appear in console
* ✅ Item usage triggers correct animations
* ✅ Smoking controls work properly
* ✅ Props and animations display correctly
* ✅ Item removal and return systems function
* ✅ Server starts without POS-Interactions related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Interactions is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Interactions
* Verify POS-Core configuration is correct

**Item Interactions Not Working**

* Check config.lua for proper item configuration
* Verify item names match your server's item database
* Test with different item types
* Ensure actionType functions are properly defined

**Animation Issues**

* Check animation dictionaries are loading correctly
* Verify animation names and parameters
* Test with different animation positions
* Ensure props are spawning correctly

**Controls Not Responding**

* Check control configuration in config.lua
* Verify control hashes are correct
* Test with different control mappings
* Ensure controls are not conflicting with other scripts

**Smoking System Problems**

* Check smoking position configurations
* Verify smoking animations are properly set
* Test with different smoking items
* Ensure smoking controls work correctly

#### Getting Support

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Check POS-Core**: Ensure POS-Core is working properly
4. **Test Configuration**: Verify all config settings are correct
5. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Final Notes 

<details>

<summary><strong>📝 Final Notes & Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-Interactions animation system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Interactions depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure item interactions to match your server's items
* Test animation systems with different items
* Set up appropriate controls for your server
* Configure smoking and interaction animations
* Train your staff on the new interaction system
* Review documentation for advanced configuration options

Your RedM server now has a powerful interaction system that integrates seamlessly with the POS ecosystem!

</details>