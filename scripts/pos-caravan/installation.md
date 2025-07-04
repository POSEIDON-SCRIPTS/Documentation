# POS-Caravan Installation Guide

## POS-Caravan Trading System

## Framework Independent

Welcome to the complete installation guide for POS-Caravan. This advanced trading caravan system provides mobile trading functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Caravan. POS-Caravan depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Caravan, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Caravan.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Caravan</strong></summary>

Download and install the POS-Caravan script:

1. Access your **Keymaster** account
2. Download the **POS-Caravan** script
3. Extract the downloaded files
4. Place the `POS-Caravan` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Caravan/        ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Caravan` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Caravan       ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Caravan loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-Caravan</strong></summary>

Configure POS-Caravan to your liking:

1. Navigate to `resources/[POS]/POS-Caravan/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Caravan Routes**: Set up trading routes and destinations
   * **Security Settings**: Configure caravan protection
   * **Pricing**: Set item prices and trade values
4. **Save** your changes

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes caravan routes, trading items, schedules, and security settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Caravan
   * POS-Core integration working properly
   * Caravan system responds to interactions

#### Common Success Indicators

* ✅ No console errors related to POS-Caravan
* ✅ POS-Core integration messages appear in console
* ✅ Caravan routes function properly
* ✅ Server starts without POS-Caravan related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Caravan is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Caravan
* Verify POS-Core configuration is correct

**Caravan Not Spawning**

* Check caravan spawn times in config.lua
* Verify spawn positions are accessible
* Test with different time settings
* Ensure server time is configured correctly

**Trading UI Issues**

* Check config.lua for proper trading settings
* Verify client-side scripts are loading correctly
* Test with different interaction methods
* Ensure item configurations are correct

**Route Issues**

* Verify start and end positions are correct
* Check that caravan paths are accessible
* Test with different route configurations

**Performance Issues**

* Monitor server performance with caravan operations
* Check for conflicts with other vehicle scripts
* Optimize caravan spawn intervals

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
Your POS-Caravan trading system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Caravan depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test caravan functionality thoroughly before going live

#### Next Steps

* Configure caravan routes to match your server's map
* Train your staff on the new caravan trading system
* Review documentation for advanced configuration options

Your RedM server now has a dynamic trading caravan system that integrates seamlessly with the POS ecosystem!

</details>