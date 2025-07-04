# POS-ProgressBar Installation Guide

## POS-ProgressBar UI Dependency

## Framework Independent

Welcome to the complete installation guide for POS-ProgressBar. This essential UI dependency provides progress bar functionality for POS scripts on your RedM server and serves as a core component for the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-ProgressBar. POS-ProgressBar depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-ProgressBar, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-ProgressBar.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-ProgressBar</strong></summary>

Download and install the POS-ProgressBar dependency:

1. Access your **Keymaster** account
2. Download the **POS-ProgressBar** script
3. Extract the downloaded files
4. Place the `POS-ProgressBar` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-ProgressBar/    ← Add this folder
```

{% hint style="warning" %}
**Important**: POS-ProgressBar should be placed in the same [POS] folder as other POS scripts for consistency.
{% endhint %}

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-ProgressBar` **after** POS-Core but **before** other POS scripts:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-ProgressBar   ← Add this line after POS-Core
ensure POS-[OtherScripts]
```

{% hint style="danger" %}
**Critical Load Order**: POS-ProgressBar must load AFTER POS-Core but BEFORE all other POS scripts that depend on it. This is essential for proper functionality.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-ProgressBar</strong></summary>

Configure POS-ProgressBar to your liking:

1. Navigate to `resources/[POS]/POS-ProgressBar/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **StopKey**: Set the key to cancel progress bars
4. **Save** your changes

```lua
Config = {}

Config.StopKey = 0x156F7119 -- Backspace (default)
```

{% hint style="info" %}
**Configuration**: The progress bar system is lightweight and requires minimal configuration. The StopKey setting allows players to cancel progress bars when needed.
{% endhint %}
</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-ProgressBar
   * POS-Core integration working properly
   * Progress bar system loads without errors
   * Other POS scripts can access progress bar functions

#### Common Success Indicators

* ✅ No console errors related to POS-ProgressBar
* ✅ POS-Core integration messages appear in console
* ✅ Progress bar resource starts successfully
* ✅ Other POS scripts load without progress bar related errors
* ✅ Progress bar functions are available to other scripts
* ✅ Server starts without POS-ProgressBar related errors

#### Testing Progress Bar Functionality

If you have other POS scripts installed that use progress bars:
* Test progress bar display and functionality
* Verify progress bar cancellation works with configured key
* Check that progress bars complete successfully

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-ProgressBar is loaded AFTER POS-Core but BEFORE other POS scripts
* Check that POS-Core is running without errors
* Ensure no conflicts with other progress bar systems

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-ProgressBar
* Verify POS-Core configuration is correct

**Progress Bar Not Displaying**

* Check that POS-ProgressBar is properly loaded
* Verify client-side scripts are loading correctly
* Test with different progress bar configurations
* Ensure no UI conflicts with other scripts

**Other POS Scripts Reporting Progress Bar Errors**

* Verify POS-ProgressBar loads before the reporting script
* Check that POS-ProgressBar exports are available
* Ensure POS-ProgressBar configuration is correct
* Test POS-ProgressBar functionality independently

**Key Binding Issues**

* Check StopKey configuration in config.lua
* Verify key hash is correct
* Test with different key bindings
* Ensure key doesn't conflict with other scripts

**Performance Issues**

* Monitor server performance with progress bars active
* Check for memory leaks or excessive resource usage
* Optimize progress bar usage in other scripts

#### Getting Support

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Check POS-Core**: Ensure POS-Core is working properly
4. **Check Load Order**: Ensure proper load order with POS-Core
5. **Test Independently**: Verify POS-ProgressBar works without other scripts
6. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Usage Information

<details>

<summary><strong>🔧 Usage Information for Developers</strong></summary>

#### For Other POS Scripts

POS-ProgressBar provides exports that can be used by other scripts:

#### Integration Notes

* POS-ProgressBar must be ensured after POS-Core but before scripts that use it
* Progress bars can be cancelled using the configured StopKey
* Progress bars support various control disable options
* Progress bars can be used while dead or alive depending on configuration

</details>

***

## Final Notes 

<details>

<summary><strong>📝 Final Notes & Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-ProgressBar dependency is now installed and ready for use by other POS scripts.
{% endhint %}

#### Important Reminders

* POS-ProgressBar depends on POS-Core - ensure POS-Core is always running
* POS-ProgressBar must load AFTER POS-Core but BEFORE other POS scripts that depend on it
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Install other POS scripts that require POS-ProgressBar
* Configure progress bar settings to match your server's needs
* Test progress bar functionality with dependent scripts
* Review other POS script documentation for progress bar usage

#### Scripts That Require POS-ProgressBar

Many POS scripts depend on POS-ProgressBar for UI functionality:
* POS-Craft (for crafting progress bars)
* POS-Farming (for planting/harvesting progress)
* POS-Housing (for furniture placement progress)
* And many other POS scripts

Your RedM server now has the essential progress bar dependency that enables enhanced UI functionality across the POS ecosystem!

</details>