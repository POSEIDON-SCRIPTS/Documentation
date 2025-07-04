# POS-BuggyWagons Installation Guide

## POS-BuggyWagons Vehicle System

## Framework Independent

Welcome to the complete installation guide for POS-BuggyWagons. This advanced vehicle system provides enhanced buggy and wagon functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-BuggyWagons. POS-BuggyWagons depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-BuggyWagons, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-BuggyWagons.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-BuggyWagons</strong></summary>

Download and install the POS-BuggyWagons script:

1. Access your **Keymaster** account
2. Download the **POS-BuggyWagons** script
3. Extract the downloaded files
4. Place the `POS-BuggyWagons` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-BuggyWagons/    ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-BuggyWagons` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-BuggyWagons  ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-BuggyWagons loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-BuggyWagons</strong></summary>

Configure POS-BuggyWagons to your liking:

1. Navigate to `resources/[POS]/POS-BuggyWagons/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Save** your changes

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes vehicle spawning, customization options, and interaction settings.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-BuggyWagons
   * Vehicle system responds correctly
   * Buggy and wagon functionality works

#### Common Success Indicators

* ✅ No console errors related to POS-BuggyWagons
* ✅ POS-Core integration messages appear in console
* ✅ Vehicle spawning works correctly
* ✅ Buggy and wagon customization functions properly
* ✅ Server starts without POS-BuggyWagons related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-BuggyWagons is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-BuggyWagons
* Verify POS-Core configuration is correct

**Vehicle System Not Working**

* Check config.lua for proper vehicle settings
* Verify vehicle models are available on your server
* Test with different vehicle spawn methods

**Performance Issues**

* Monitor server performance with vehicle spawning
* Check for resource conflicts with other vehicle scripts
* Optimize configuration settings for your server size

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
Your POS-BuggyWagons vehicle system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-BuggyWagons depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure vehicle settings to match your server's style
* Test vehicle functionality with different models
* Train your staff on the new vehicle system
* Review documentation for advanced configuration options

Your RedM server now has a powerful vehicle system that integrates seamlessly with the POS ecosystem!

</details>
