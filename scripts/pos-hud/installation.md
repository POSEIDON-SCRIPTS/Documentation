# POS-Hud Installation Guide

## POS-Hud User Interface System

## Framework Independent

Welcome to the complete installation guide for POS-Hud. This advanced HUD system provides customizable user interface elements for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Hud. POS-Hud depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Hud, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Hud.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Hud</strong></summary>

Download and install the POS-Hud script:

1. Access your **Keymaster** account
2. Download the **POS-Hud** script
3. Extract the downloaded files
4. Place the `POS-Hud` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Hud/            ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Hud` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Hud           ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Hud loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-Hud</strong></summary>

Configure POS-Hud to your liking:

1. Navigate to `resources/[POS]/POS-Hud/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **DefaultEnabled**: Set if HUD is enabled by default
   * **HudCommand**: Command to toggle HUD visibility
   * **HudVersion**: Select HUD design version
   * **HudSettings**: Configure displayed values and icons
   * **DynamicHide**: Set auto-hide conditions
   * **UpdateInterval**: Set refresh rate
4. **Save** your changes

```lua
Config.DefaultEnabled = true
Config.HudCommand = 'hud' -- Command to toggle the HUD or false to disable it
Config.HudVersion = 1

Config.HudSettings = {
    [1] = {
        TopValues = {
            {
                name = "Hour",
                icon = {
                    icon = "fa-solid fa-clock",
                    color = "white" 
                },
                value = "hour"
            },
            {
                name = "Players",
                icon = {
                    icon = "fa-solid fa-users",
                    color = "white" 
                },
                value = "players"
            }            
        },
        NormalValues = {
            {
                name = "Money",
                icon = {
                    icon = "fa-solid fa-sack-dollar",
                    color = "#28A745"
                },
                value = function(source)
                    return '$' .. exports['POS-Core']:GetMoney(source)
                end
            }
        }
    }
}
```

5. **Navigate** to `resources/[POS]/POS-Hud/shared/config.js`
6. **Configure** the language settings and logo:

```javascript
TR = {
    LANG: 'EN',
    EN: {
        // Translation entries
    }
},

Months = ["ian.", "feb.", "mar.", "apr.", "mai", "iun.", "iul.", "aug.", "sept.", "oct.", "nov.", "dec."]

LogoImage = "assets/img/dead-lands1-1.png"
```

{% hint style="info" %}
**Configuration**: Review all available options in both config files and adjust them to match your server's needs. This includes HUD elements, colors, update intervals, and language settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Hud
   * HUD elements display correctly
   * Toggle command works (if enabled)
   * Dynamic hide features function properly
   * Values update correctly

#### Common Success Indicators

* ✅ No console errors related to POS-Hud
* ✅ POS-Core integration messages appear in console
* ✅ HUD displays correctly on screen
* ✅ Toggle command functions properly
* ✅ Values update at configured intervals
* ✅ Dynamic hide features work as expected
* ✅ Server starts without POS-Hud related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Hud is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Hud
* Verify POS-Core configuration is correct

**HUD Not Displaying**

* Check config.lua for proper HUD settings
* Verify client-side scripts are loading correctly
* Test with different HUD versions
* Ensure DefaultEnabled is set to true

**Values Not Updating**

* Check UpdateInterval setting in config.lua
* Verify value functions are properly configured
* Test with different update intervals
* Ensure POS-Core exports are working

**Toggle Command Issues**

* Verify HudCommand is set correctly in config.lua
* Check that command permissions are working
* Test with different command names

**Dynamic Hide Not Working**

* Check DynamicHide settings in config.lua
* Verify hide conditions are properly configured
* Test with different hide scenarios

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
Your POS-Hud user interface system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Hud depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure HUD elements to match your server's style
* Test HUD functionality with different versions
* Set up appropriate toggle commands
* Configure dynamic hide features
* Train your staff on the new HUD system
* Review documentation for advanced configuration options

Your RedM server now has a powerful HUD system that integrates seamlessly with the POS ecosystem!

</details>