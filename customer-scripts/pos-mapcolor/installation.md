# POS-MapColor Installation Guide

## POS-MapColor Map Enhancement System

## Framework Independent

Welcome to the complete installation guide for POS-MapColor. This advanced map enhancement system provides customizable map coloring and visual effects for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-MapColor. POS-MapColor depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-MapColor, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-MapColor.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-MapColor</strong></summary>

Download and install the POS-MapColor script:

1. Access your **Keymaster** account
2. Download the **POS-MapColor** script
3. Extract the downloaded files
4. Place the `POS-MapColor` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-MapColor/       ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-MapColor` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-MapColor      ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-MapColor loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-MapColor</strong></summary>

Configure POS-MapColor to your liking:

1. Navigate to `resources/[POS]/POS-MapColor/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **MapSettings**: Enable/disable fog, map coloring, and dark mode
   * **MapZones**: Configure zone colors for different map areas
   * **Colors**: Define color mappings for different zones
4. **Save** your changes

```lua
Config.MapSettings = {
    fog = false,
    mapColor = true,
    darkMode = true,
}

Config.MapZones = {
    -- New Hanover
    { zone = 0x41332496, color = 'brown'},    -- New Hanover Full int
    { zone = 0x5CD2A36F, color = 'black'},    -- New Hanover Full ext
    { zone = 0x724E7654, color = 'Green'},    -- The Heartlands
    { zone = 0x30FAE29B, color = 'Green'},    -- Roanoke Ridge
    
    -- Ambarino
    { zone = 0x3B8DD21A, color = 'white'},    -- Ambarino Full Int
    { zone = 0x3BBA228A, color = 'black'},    -- Ambarino Full Ext
    { zone = 0xD41D039A, color = 'white'},    -- Grizzlies West Int
    { zone = 0x943198D3, color = 'yellow'},   -- Grizzlies East Int
    
    -- West Elizabeth
    { zone = 0xD69B5B49, color = 'Grey'},     -- West Elizabeth Full Int
    { zone = 0xF030C0B2, color = 'black'},    -- West Elizabeth Full Ext
    { zone = 0x763A8A87, color = 'white'},    -- Tall Tree
    { zone = 0x8DCC574F, color = 'white'},    -- Big Valley
}

Config.Colors = {
    ['brown'] = 'BLIP_MODIFIER_MP_ENEMY_HOLDING',
    ['black'] = 'BLIP_MODIFIER_SP_DOWNED',
    ['Green'] = 'BLIP_MODIFIER_MP_COLOR_8',
    ['white'] = 'BLIP_MODIFIER_MP_COLOR_32',
    ['yellow'] = 'BLIP_MODIFIER_MP_COLOR_6',
    ['Grey'] = 'BLIP_MODIFIER_MISSION_UNAVAILABLE',
    ['BLUE'] = 'BLIP_MODIFIER_MP_COLOR_25',
    ['orange'] = 'BLIP_MODIFIER_MP_COLOR_4',
    ['Red'] = 'BLIP_MODIFIER_MP_ENEMY_HOLDING'
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes map visual settings, zone colors, and blip modifiers.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-MapColor
   * Map displays with configured colors
   * Zone colors appear correctly
   * Map settings take effect
   * Dark mode functions (if enabled)

#### Common Success Indicators

* ✅ No console errors related to POS-MapColor
* ✅ POS-Core integration messages appear in console
* ✅ Map colors display correctly
* ✅ Zone-specific colors work
* ✅ Map settings apply properly
* ✅ Dark mode functions correctly
* ✅ Server starts without POS-MapColor related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-MapColor is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-MapColor
* Verify POS-Core configuration is correct

**Map Colors Not Displaying**

* Check MapSettings configuration in config.lua
* Verify mapColor is set to true
* Test with different color configurations
* Ensure client-side scripts are loading

**Zone Colors Not Working**

* Check MapZones configuration in config.lua
* Verify zone hashes are correct
* Test with different zone configurations
* Ensure Colors mapping is correct

**Dark Mode Issues**

* Check darkMode setting in MapSettings
* Verify dark mode functionality
* Test with different map settings

**Performance Issues**

* Monitor server performance with map coloring
* Check for conflicts with other map scripts
* Optimize zone configurations

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
Your POS-MapColor map enhancement system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-MapColor depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure map colors to match your server's theme
* Set up zone-specific coloring for different areas
* Test map visual effects with different settings
* Configure dark mode and fog settings
* Train your staff on the new map system
* Review documentation for advanced configuration options

Your RedM server now has an enhanced map system that integrates seamlessly with the POS ecosystem!

</details>