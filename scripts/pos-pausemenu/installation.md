# POS-PauseMenu Installation Guide

## POS-PauseMenu Enhanced Menu System

## Framework Independent

Welcome to the complete installation guide for POS-PauseMenu. This advanced pause menu system provides comprehensive menu functionality with tutorials, rules, and commands for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-PauseMenu. POS-PauseMenu depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-PauseMenu, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-PauseMenu.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-PauseMenu</strong></summary>

Download and install the POS-PauseMenu script:

1. Access your **Keymaster** account
2. Download the **POS-PauseMenu** script
3. Extract the downloaded files
4. Place the `POS-PauseMenu` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-PauseMenu/      ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-PauseMenu` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-PauseMenu     ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-PauseMenu loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-PauseMenu</strong></summary>

Configure POS-PauseMenu to your liking:

1. Navigate to `resources/[POS]/POS-PauseMenu/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **GuideCommand**: Command to open the guide menu
   * **PauseMenu**: Configure top and left menu items
   * **Guides**: Set up tutorial categories and content
   * **Menu Functions**: Define actions for each menu item
4. **Save** your changes

```lua
Config.GuideCommand = 'guide' -- Command to open the guide menu or false

Config.PauseMenu = {
    top = {
        [1] = {
            title = 'DISCONNECT',
            action = function() TOP1() end 
        },
        [2] = {
            title = 'SETTINGS',
            link = 'https://www.google.com/',
            action = function() TOP2() end
        },
        [3] = {
            title = 'MAP',
            action = function() TOP3() end
        },
    },
    left = {
        [1] = {
            title = 'TUTORIALS',
            action = function() LEFT1() end
        },
        [2] = {
            title = 'SERVER RULES',
            action = function() LEFT2() end
        },
        [3] = {
            title = 'COMMANDS',
            action = function() LEFT3() end
        },
    }
}
```

5. **Navigate** to `resources/[POS]/POS-PauseMenu/shared/config.js`
6. **Configure** the language settings and images:

```javascript
TR = {
    LANG:'EN',
    EN: {
        PRESSTO: "PRESS",
        EXITMENU: "EXIT FROM MENU",
        TITLE: "PAUSE",
    },
    RO: {
        PRESSTO: "APASA",
        EXITMENU: "PENTRU A IESI DIN MENIU",
        TITLE: "PAUZA",
    }
}

BackgroundImage = 'assets/img/mask-group.png';
LogoImage = 'assets/img/dead-lands1-1.png'
```

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes menu items, tutorial content, server rules, and language settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-PauseMenu
   * Pause menu opens correctly
   * Guide command works (if enabled)
   * Menu items function properly
   * Tutorial content displays correctly

#### Common Success Indicators

* ✅ No console errors related to POS-PauseMenu
* ✅ POS-Core integration messages appear in console
* ✅ Pause menu opens with custom content
* ✅ Guide command functions properly
* ✅ Menu navigation works smoothly
* ✅ Tutorial and rules content displays
* ✅ Server starts without POS-PauseMenu related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-PauseMenu is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-PauseMenu
* Verify POS-Core configuration is correct

**Pause Menu Not Opening**

* Check config.lua for proper menu configuration
* Verify client-side scripts are loading correctly
* Test with default pause menu functionality

**Guide Command Not Working**

* Verify GuideCommand is set correctly in config.lua
* Check that command permissions are working
* Test with different command names

**Menu Items Not Functioning**

* Check action functions in config.lua
* Verify menu item configurations
* Test individual menu actions

**Content Not Displaying**

* Check Guides configuration in config.lua
* Verify HTML content is properly formatted
* Test with different content types

**Language/Images Not Loading**

* Verify config.js file is properly configured
* Check that image paths are correct
* Test with different language settings

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
Your POS-PauseMenu enhanced menu system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-PauseMenu depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure menu items to match your server's needs
* Set up tutorial content for new players
* Configure server rules and commands
* Customize language settings and images
* Train your staff on the new pause menu system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive pause menu system that integrates seamlessly with the POS ecosystem!

</details>