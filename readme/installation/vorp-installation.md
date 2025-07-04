# VORP Installation Guide

## POS-Inventory Installation Guide

## VORP Framework

Welcome to the complete installation guide for POS-Inventory with VORP Framework integration. This advanced inventory system will enhance your RedM server's inventory management capabilities while maintaining full compatibility with VORP.

***

## Prerequisites
<details>


<summary><strong>📋 Prerequisites</strong></summary>

Before beginning the installation process, ensure you have:

* **VORP Framework** properly installed and running
* **Server access** with file modification permissions
* **Keymaster** access for script downloads
* **Recent server backup** (highly recommended)

{% hint style="warning" %}
Always backup your server before installing new scripts. This installation will replace your existing vorp_inventory script.
{% endhint %}

</details>

***


## Installation Steps

<details>

<summary><strong>🚀 Step 1: Prepare the POS Folder Structure</strong></summary>

First, you need to create the proper folder structure for POS scripts:

1. Navigate to your server's `resources` folder
2. Check if a `[POS]` folder exists (note the square brackets)
3. If it doesn't exist, create a new folder named exactly: `[POS]`

```
server/
└── resources/
   └── [POS]/          ← Create this folder
```

{% hint style="info" %}
**Note**: The square brackets `[POS]` are essential for proper resource categorization in RedM.
{% endhint %}

</details>

<details>

<summary><strong>📦 Step 2: Download and Install POS-Core</strong></summary>

POS-Core is the foundation script required for POS-Inventory to function properly:

1. Access your **Keymaster** account
2. Download the **POS-Core** script
3. Extract the downloaded files
4. Place the `POS-Core` folder inside your `[POS]` directory

```
[POS]/
└── POS-Core/
```

</details>

<details>

<summary><strong>📥 Step 3: Download POS-Inventory</strong></summary>

Now download the main POS-Inventory script:

1. From your **Keymaster** account, download **POS-Inventory**
2. Extract the downloaded files
3. Place the `POS-Inventory` folder inside your `[POS]` directory

```
[POS]/
├── POS-Core/
└── POS-Inventory/
```

</details>

<details>

<summary><strong>🗄️ Step 4: Import Database Tables</strong></summary>

{% hint style="danger" %}
**Critical Database Step**: The script requires specific database tables to function properly.
{% endhint %}

Before proceeding with the installation, you must import the required database structure:

1. Navigate to the `[POS]/POS-Inventory/sql/` folder
2. **Open** your database management tool (phpMyAdmin, HeidiSQL, etc.)
3. **Select** your server's database
4. **Import** or **execute** the SQL file(s) found in the sql folder

```sql
-- Example: Execute the SQL file in your database
-- This will create the necessary tables for POS-Inventory
```

{% hint style="info" %}
**Database Tools**: You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line to execute the SQL files.
{% endhint %}

**Verify Database Import:**

* Check that new tables have been created in your database
* Look for tables with names starting with `pos_` or similar
* Ensure no errors occurred during the import process

</details>

<details>

<summary><strong>🗂️ Step 5: Backup and Remove Old Inventory</strong></summary>

{% hint style="danger" %}
**Critical Step**: Always backup your existing inventory before proceeding!
{% endhint %}

1. **Create a backup** of your current `vorp_inventory` script
   * Copy the entire `vorp_inventory` folder to a safe location
   * This allows you to restore if needed
2. **Remove the old script** from your resources folder
   * Delete or move the existing `vorp_inventory` folder from `resources/`

</details>

<details>

<summary><strong>🔄 Step 6: Rename POS-Inventory</strong></summary>

This step integrates POS-Inventory as your new inventory system:

1. Navigate to your `[POS]` folder
2. **Rename** the `POS-Inventory` folder to `vorp_inventory`
3. **Move** the renamed folder from `[POS]/` to your main `resources/` directory

```
resources/
├── [POS]/
│   └── POS-Core/
└── vorp_inventory/     ← Renamed POS-Inventory folder
```

</details>

<details>

<summary><strong>🖼️ Step 7: Setup Item Images</strong></summary>

Configure the inventory images for your items:

1. Navigate to `resources/vorp_inventory/html/img/`
2. **Create** a new folder called `items`
3. **Transfer** all your inventory item images into this new `items` folder

```
vorp_inventory/
└── html/
   └── img/
      └── items/      ← Create this folder
         ├── apple.png
         ├── bread.png
         └── ...
```

</details>

<details>

<summary><strong>🔧 Step 8: Configure Image Path</strong></summary>

Configure the correct image path for VORP Framework:

1. Navigate to `resources/vorp_inventory/shared/configs/config.js`
2. **Locate** the IMAGEPATH setting:

```javascript
IMAGEPATH = "images/"
```

3. **Replace** it with the VORP-specific path:

```javascript
IMAGEPATH = "img/items/"
```

{% hint style="info" %}
**Framework-Specific Paths:**

* **VORP**: `"img/items/"`
* **RSG**: `"images/"`

Make sure the image path matches your framework for proper image loading.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 9: Configure VORP Settings</strong></summary>

Enable the VORP-specific configurations:

1. Navigate to `resources/vorp_inventory/shared/configs/config.lua`
2. **Locate** the VORP configuration section
3. **Update** the following settings:

```lua
-- VORP Framework Integration Settings
Config.UseMaxWeightVORP = true      -- Use max weight from config
Config.ItemsInDatabaseVORP = true   -- Use items in database
Config.UseLoadoutTableVORP = true   -- Enable loadout table for weapons
```

{% hint style="info" %}
**Configuration Details:**

* `UseMaxWeightVORP`: Set to `true` to use config-based weight limits.
* `ItemsInDatabaseVORP`: Set to `true` to store items in database.
* `UseLoadoutTableVORP`: Set to `true` to ensure weapon scripts work properly.
{% endhint %}

</details>

<details>

<summary><strong>🚫 Step 10: Disable RSG Configuration</strong></summary>

To prevent conflicts, make sure the RSG configuration is disabled:

1. Open `resources/vorp_inventory/shared/configs/config.lua`
2. Find the following settings and ensure they are set to `false`:

```lua
Config.RSG = false
Config.RSGStores = false
```

{% hint style="warning" %}
**Important:** Both `Config.RSG` and `Config.RSGStores` must be set to `false` for proper VORP integration.
{% endhint %}

</details>

<details>

<summary><strong>🔧 Step 11: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Locate** the `ensure vorp_inventory` line
3. **Add** `ensure POS-Core` directly after it

```cfg
# VORP Framework
ensure vorp_core
ensure vorp_inventory
ensure POS-Core          ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Core loads right after vorp_inventory. Check this order if you encounter console errors.
{% endhint %}

</details>

<details>

<summary><strong>🔄 Step 12: Configure Data Migration (For Live Servers)</strong></summary>

If your server is live with existing players, you'll need to migrate inventory data:

{% hint style="danger" %}
**Live Server Warning**: Only perform this step if you have active players with existing inventories.
{% endhint %}

1. Navigate to `resources/vorp_inventory/shared/configs/config.lua`
2. **Find** the migration setting:

```lua
Config.ImportInventoryVORP = false -- Default setting
```

3. **Replace** `false` with a command name in quotes:

```lua
Config.ImportInventoryVORP = 'loadOldInventory' -- Your chosen command
```

4. **Restart** your server
5. **Ensure** no players are connected
6. **Execute** the command in your server console:

```
loadOldInventory
```

7. **Wait** exactly 10 seconds for the migration to complete
8. **Change** the setting back to `false`:

```lua
Config.ImportInventoryVORP = false
```

9. **Restart** your server again

</details>

***

## Post-Installation Verification
<details>


<summary><strong>✅ Post-Installation Verification</strong></summary>

#### Testing Your Installation

1. **Start your server** and monitor the console for errors
2. **Join with a test character** and verify:
   * Inventory opens correctly
   * Items display properly
   * Weight system functions
   * Database interactions work

#### Common Success Indicators

* ✅ No console errors related to POS-Core or vorp_inventory
* ✅ Inventory UI loads without issues
* ✅ Item images display correctly
* ✅ Player inventories persist after server restart

</details>

***

## Troubleshooting

<details>


<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Core is loaded immediately after vorp_inventory
* Check that vorp_core loads before both scripts

**Missing Item Images**

* Ensure the `items` folder exists in `html/img/`
* Verify image file names match your database entries

**Database Connection Issues**

* Confirm VORP database settings are properly configured
* Check that migration (Step 12) completed successfully

**Inventory Not Opening**

* Verify the script renamed correctly to `vorp_inventory`
* Check console for JavaScript/Lua errors

#### Getting Support

If you encounter issues not covered here:

1. **Check Console**: Look for specific error messages
2. **Verify Steps**: Ensure each installation step was completed
3. **Contact Support**: Reach out with console logs and specific error descriptions

</details>

***

## Final Notes 

<details>

<summary><strong>📝 Final Notes & Next Steps</strong></summary>

{% hint style="success" %}
**Installation Complete!**\
Your POS-Inventory system is now integrated with VORP Framework and ready for use.
{% endhint %}

#### Important Reminders

* Keep your backup of the original vorp_inventory script
* Monitor server performance after installation
* Update item images as needed for new items
* Regular backups are essential for server stability

#### Next Steps

* Configure item weights in your database
* Train your staff on the new inventory features
* Customize the UI to match your server's theme

Your RedM server now has a powerful, VORP-integrated inventory system that will enhance the player experience significantly!

</details>

