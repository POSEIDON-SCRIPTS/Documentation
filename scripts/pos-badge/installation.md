# POS-Badge Installation Guide

## POS-Badge System

## Framework Independent

Welcome to the complete installation guide for POS-Badge. This badge system provides enhanced badge functionality for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-Badge. POS-Badge depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-Badge, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-Badge.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Badge</strong></summary>

Download and install the POS-Badge script:

1. Access your **Keymaster** account
2. Download the **POS-Badge** script
3. Extract the downloaded files
4. Place the `POS-Badge` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Badge/          ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-Badge` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-Badge         ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Badge loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-Badge</strong></summary>

Configure POS-Badge to your liking:

1. Navigate to `resources/[POS]/POS-Badge/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Save** your changes

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes badge types, display settings, and interaction options.
{% endhint %}

**Key Configuration Areas:**

* **Badge Types**: Configure different badge styles and categories
* **Display Settings**: Adjust how badges appear on players
* **Interaction Options**: Set up how players interact with badges
* **Permission Levels**: Define who can assign/remove badges

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-Badge
   * POS-Core integration working properly
   * Badge system responds to interactions
   * Badge displays function correctly
   * Commands work as expected

#### Common Success Indicators

* ✅ No console errors related to POS-Badge
* ✅ POS-Core integration messages appear in console
* ✅ Badge UI opens and functions correctly
* ✅ Badges can be assigned and removed
* ✅ Badge displays show correctly on players
* ✅ Server starts without POS-Badge related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Badge is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-Badge
* Verify POS-Core configuration is correct

**Badge UI Not Opening**

* Check config.lua for proper UI settings
* Verify client-side scripts are loading correctly
* Test with different interaction methods (key bindings, commands)
* Ensure keybinds are not conflicting with other scripts

**Badges Not Displaying**

* Check badge configuration in config.lua
* Verify badge assets are properly loaded
* Test with different badge types and styles
* Ensure display settings are configured correctly

**Permission Issues**

* Verify permission levels are set correctly
* Check that admin/staff permissions are working
* Test badge assignment/removal permissions
* Ensure command permissions are properly configured

**Performance Issues**

* Monitor server performance with badge operations
* Check for script conflicts with other badge systems
* Verify memory usage during badge operations

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
Your POS-Badge system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-Badge depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability
* Test badge functionality thoroughly before going live

#### Next Steps

* Configure badge settings to match your server's style
* Test badge functionality with different badge types
* Train your staff on the new badge system
* Review documentation for advanced configuration options
* Set up appropriate permissions for badge management
* Create custom badges for your server's unique needs

Your RedM server now has a powerful badge system that integrates seamlessly with the POS ecosystem!

</details>
