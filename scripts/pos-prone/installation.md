# POS-Prone Installation Guide

## POS-Prone Movement System

## Framework Independent

Welcome to the complete installation guide for POS-Prone. This advanced movement system provides prone/crawling mechanics for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Prone. POS-Prone depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Prone, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Prone.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Prone</strong></summary>

Download and install the POS-Prone script:

1. Access your **Keymaster** account
2. Download the **POS-Prone** script
3. Extract the downloaded files
4. Place the `POS-Prone` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Prone/          ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Prone` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Prone         ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Prone loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-Prone</strong></summary>

Configure POS-Prone to your liking:

1. Navigate to `resources/[POS]/POS-Prone/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Stamina Settings**: Set stamina requirements for sprinting
   * **Prone Settings**: Configure prone behavior and requirements
   * **Controls**: Key bindings for prone actions
   * **Functions**: Custom functions for prone effects
4. **Save** your changes

```lua
Config = {}

Config.StaminaRequiredToSprint = 4

Config.Functions = {
    ['active_prone'] = function()
        exports['POS-Metabolism']:UpdateStatus('shower', 2)
    end
}

Config.Settings = {
    requireOnlyProneKey = false, -- If true, only prone key needed, else prone + crouch
    proneFunctionInterval = 5000, -- How often the prone function is called
}
```

5. **Configure Controls**:

```lua
Config.Controls = {
    ToggleProne = 0x26E9DC00,    -- Toggle prone position
    Crouch = 0xDB096B85,         -- Crouch key
    MoveForward = 0x8FD015D8,    -- Move forward while prone
    MoveLeft = 0x7065027D,       -- Move left while prone
    MoveBackward = 0xD27782E3,   -- Move backward while prone
    MoveRight = 0xB4E465B4,      -- Move right while prone
    Sprint = 0x8FFC75D6,         -- Sprint key
    TurnOver = 0xD9D0E1C0        -- Turn over while prone
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes movement controls, stamina requirements, and prone mechanics.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Prone
   * Prone toggle functionality working
   * Movement controls functioning while prone
   * Stamina system integration working
   * Turn over mechanics operational

#### Common Success Indicators

* ✅ No console errors related to POS-Prone
* ✅ POS-Core integration messages appear in console
* ✅ Prone toggle responds to key presses
* ✅ Movement controls work while prone
* ✅ Stamina requirements enforced
* ✅ Turn over mechanics functional
* ✅ Server starts without POS-Prone related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Prone is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Prone
* Verify POS-Core configuration is correct

**Prone Toggle Not Working**

* Check ToggleProne key configuration
* Verify key bindings are not conflicting
* Test with different key combinations

**Movement Controls Issues**

* Check movement key configurations
* Verify prone state is properly detected
* Test with different movement keys

**Stamina System Problems**

* Check stamina integration with POS-Metabolism
* Verify stamina requirements are configured
* Test stamina consumption during prone

**Turn Over Mechanics Issues**

* Check TurnOver key configuration
* Verify turn over animation works
* Test with different prone positions

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
Your POS-Prone movement system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Prone depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure prone controls to match your server's preferences
* Set up stamina requirements for realistic gameplay
* Test prone mechanics with different scenarios
* Train your staff on the new movement system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive prone movement system that integrates seamlessly with the POS ecosystem!

</details>