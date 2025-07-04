# POS-TimeSync Installation Guide

## POS-TimeSync Time & Weather Synchronization System

## Framework Independent

Welcome to the complete installation guide for POS-TimeSync. This advanced time and weather synchronization system provides comprehensive time/weather management for your RedM server and works seamlessly with the POS ecosystem.

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
**Critical Requirement**: POS-Core must be installed before POS-TimeSync. POS-TimeSync depends on POS-Core for core functionality.
{% endhint %}

</details>

***

## Installation Steps

<details>

<summary><strong>🚀 Step 1: Verify POS-Core Installation</strong></summary>

Before installing POS-TimeSync, ensure POS-Core is properly installed:

1. Navigate to your `resources/[POS]/` folder
2. Verify that `POS-Core` folder exists
3. Check that POS-Core is running without errors in your server console

```
resources/
└── [POS]/
   └── POS-Core/        ← This must exist
```

{% hint style="warning" %}
**Important**: If POS-Core is not installed, please install it first before proceeding with POS-TimeSync.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-TimeSync</strong></summary>

Download and install the POS-TimeSync script:

1. Access your **Keymaster** account
2. Download the **POS-TimeSync** script
3. Extract the downloaded files
4. Place the `POS-TimeSync` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-TimeSync/       ← Add this folder
```

</details>

<details>

<summary><strong>🔧 Step 3: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Add** `ensure POS-TimeSync` after POS-Core:

```cfg
# POS Scripts
ensure POS-Core
ensure POS-TimeSync      ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-TimeSync loads after POS-Core but can load before or after other POS scripts.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 4: Configure POS-TimeSync</strong></summary>

Configure POS-TimeSync to your liking:

1. Navigate to `resources/[POS]/POS-TimeSync/shared/config.lua`
2. **Review** and **modify** the configuration settings as needed
3. **Configure** the following key settings:
   * **Time Settings**: Enable/disable time synchronization
   * **Weather Settings**: Configure weather patterns and real-world weather
   * **Pattern Settings**: Define custom weather patterns
   * **Commands**: Admin commands for time/weather management
4. **Save** your changes

```lua
Config = {
    -- Time synchronization settings
    UseTime = true,  -- Whether to use the in-game time synchronization system
    RealTime = false,  -- Whether to use real-world time
    DayDuration = 4 * 3600,  -- Duration of the in-game day (in seconds)
    NightDuration = 2 * 3600,  -- Duration of the in-game night (in seconds)
    
    DefaultTransition = 5000.0,  -- Default transition time for weather and time changes

    -- Weather synchronization settings
    UseWeather = true,  -- Whether to use weather synchronization
    CityRealWeather = 'Bucharest',  -- City name for real-time weather data
    RealWeatherCache = 180,  -- Time to cache real-world weather data
    
    -- Weather pattern settings
    WeatherPattern = false,  -- Default weather pattern
    SnowInWeatherSnow = true,  -- Snow on ground when weather is snowy
    DayTime = {6, 18}  -- Daytime hours range
}
```

5. **Configure Weather Patterns**:

```lua
Config.Pattern = {
    Cycle = 60000,  -- Time to cycle weather patterns (in ms)
    
    Patterns = {
        Christmas = {
            weather = {
                'sunny', 'sunny', 'snow', 'overcast', 'sunny', 'misty', 'snow', 'fog'
            },
            transition = 15 * 1000,  -- 15 seconds transition
            snow = true,  -- Snow will be on the ground
        },
        
        Summer = {
            weather = {'sunny', 'sunny', 'sunny', 'clouds', 'thunderstorm'},
            transition = 15 * 1000,
            snow = false,
        },
        
        Apocalypse = {
            weather = {'hurricane', 'thunderstorm', 'sandstorm', 'blizzard'},
            transition = 15 * 1000,
            snow = false,
        },
    }
}
```

{% hint style="info" %}
**Configuration**: Review all available options in the config.lua file and adjust them to match your server's needs. This includes time cycles, weather patterns, and real-world weather integration.
{% endhint %}

</details>

***

## Post-Installation Verification
<details>

<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * No console errors related to POS-TimeSync
   * Time synchronization working correctly
   * Weather changes functioning properly
   * Admin commands operational

#### Common Success Indicators

* ✅ No console errors related to POS-TimeSync
* ✅ POS-Core integration messages appear in console
* ✅ Time synchronization active and working
* ✅ Weather patterns cycling correctly
* ✅ Real-world weather integration (if enabled)
* ✅ Admin commands functional
* ✅ Server starts without POS-TimeSync related errors

</details>

***

## Troubleshooting

<details>

<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-TimeSync is loaded after POS-Core
* Check that POS-Core is running without errors

**POS-Core Integration Issues**

* Ensure POS-Core is properly installed and running
* Check that POS-Core loads before POS-TimeSync
* Verify POS-Core configuration is correct

**Time Synchronization Not Working**

* Check UseTime setting in config.lua
* Verify time duration settings are correct
* Test with different time configurations

**Weather System Issues**

* Check UseWeather setting in config.lua
* Verify weather pattern configurations
* Test with different weather patterns

**Real-World Weather Not Working**

* Check CityRealWeather setting
* Verify internet connectivity for weather API
* Test with different city names

**Admin Commands Not Working**

* Check command permissions in config.lua
* Verify user groups have correct permissions
* Test with different admin levels

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
Your POS-TimeSync time and weather system is now installed and ready for use.
{% endhint %}

#### Important Reminders

* POS-TimeSync depends on POS-Core - ensure it's always running
* Keep your server backup safe for recovery purposes
* Monitor server performance after installation
* Regular backups are essential for server stability

#### Next Steps

* Configure time cycles to match your server's gameplay
* Set up weather patterns for different seasons/events
* Configure real-world weather integration (if desired)
* Test admin commands for time/weather management
* Train your staff on the new time/weather system
* Review documentation for advanced configuration options

Your RedM server now has a comprehensive time and weather management system that integrates seamlessly with the POS ecosystem!

</details>