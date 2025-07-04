# RSG Installation Guide

## POS-Inventory Installation Guide

## RSG Framework

Welcome to the complete installation guide for POS-Inventory with RSG Framework integration. This advanced inventory system will enhance your RedM server's inventory management capabilities while maintaining full compatibility with RSG.

***

## Prerequisites
<details>


<summary><strong>📋 Prerequisites</strong></summary>

Before beginning the installation process, ensure you have:

* **RSG Framework** properly installed and running
* **Server access** with file modification permissions
* **Keymaster** access for script downloads
* **Recent server backup** (highly recommended)

{% hint style="warning" %}
Always backup your server before installing new scripts. This installation will replace your existing rsg-inventory script.
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

1. **Create a backup** of your current `rsg-inventory` script
   * Copy the entire `rsg-inventory` folder to a safe location
   * This allows you to restore if needed
2. **Remove the old script** from your resources folder
   * Delete or move the existing `rsg-inventory` folder from `resources/`

</details>

<details>

<summary><strong>🔄 Step 6: Rename POS-Inventory</strong></summary>

This step integrates POS-Inventory as your new inventory system:

1. Navigate to your `[POS]` folder
2. **Rename** the `POS-Inventory` folder to `rsg-inventory`
3. **Move** the renamed folder from `[POS]/` to your main `resources/` directory

```
resources/
├── [POS]/
│   └── POS-Core/
└── rsg-inventory/     ← Renamed POS-Inventory folder
```

</details>

<details>

<summary><strong>🖼️ Step 7: Setup Item Images</strong></summary>

Configure the inventory images for your items:

1. Navigate to `resources/rsg-inventory/html/`
2. **Create** a new folder called `images`
3. **Transfer** all your inventory item images into this new `images` folder

```
rsg-inventory/
└── html/
   └── images/         ← Create this folder
      ├── apple.png
      ├── bread.png
      └── ...
```

</details>

<details>

<summary><strong>🔧 Step 8: Configure Image Path</strong></summary>

Configure the correct image path for RSG Framework:

1. Navigate to `resources/rsg-inventory/shared/configs/config.js`
2. **Locate** the IMAGEPATH setting:

```javascript
IMAGEPATH = "img/items/"
```

3. **Replace** it with the RSG-specific path:

```javascript
IMAGEPATH = "images/"
```

{% hint style="info" %}
**Framework-Specific Paths:**

* **VORP**: `"img/items/"`
* **RSG**: `"images/"`

Make sure the image path matches your framework for proper image loading.
{% endhint %}

</details>

<details>

<summary><strong>⚙️ Step 9: Configure RSG Settings</strong></summary>

Enable the RSG-specific configurations:

1. Navigate to `resources/rsg-inventory/shared/configs/config.lua`
2. **Locate** the RSG configuration section
3. **Update** the following settings:

```lua
-- RSG Framework Integration Settings
Config.RSG = true                   -- Enable RSG framework
Config.RSGStores = true             -- Enable RSG stores
```

{% hint style="info" %}
**Configuration Details:**

* `RSG`: Set to `true` to enable RSG framework integration.
* `RSGStores`: Set to `true` to enable RSG store functionality.
{% endhint %}

</details>

<details>

<summary><strong>� Step 10: Update Server Configuration</strong></summary>

Configure your server.cfg with the proper load order:

1. Open your `server.cfg` file
2. **Locate** the `ensure rsg-inventory` line
3. **Add** `ensure POS-Core` directly after it

```cfg
# RSG Framework
ensure rsg_core
ensure rsg-inventory
ensure POS-Core          ← Add this line here
```

{% hint style="warning" %}
**Load Order is Critical:** Make sure POS-Core loads right after rsg-inventory. Check this order if you encounter console errors.
{% endhint %}

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
   * RSG stores function properly

#### Common Success Indicators

* ✅ No console errors related to POS-Core or rsg-inventory
* ✅ Inventory UI loads without issues
* ✅ Item images display correctly
* ✅ Player inventories persist after server restart
* ✅ RSG store integration works properly

</details>

***

## Troubleshooting

<details>


<summary><strong>🔧 Troubleshooting</strong></summary>

#### Common Issues

**Console Errors About Load Order**

* Verify POS-Core is loaded immediately after rsg_inventory
* Check that rsg_core loads before both scripts

**Missing Item Images**

* Ensure the `images` folder exists in `html/`
* Verify image file names match your database entries

**Database Connection Issues**

* Confirm RSG database settings are properly configured
* Verify all required database tables were imported properly

**Inventory Not Opening**

* Verify the script renamed correctly to `rsg-inventory`
* Check console for JavaScript/Lua errors

**RSG Store Issues**

* Ensure `Config.RSGStores = true` is set correctly
* Verify RSG framework is properly installed and running

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
Your POS-Inventory system is now integrated with RSG Framework and ready for use.
{% endhint %}

#### Important Reminders

* Keep your backup of the original rsg-inventory script
* Monitor server performance after installation
* Update item images as needed for new items
* Regular backups are essential for server stability

#### Next Steps

* Configure item weights in your database
* Train your staff on the new inventory features
* Customize the UI to match your server's theme
* Test RSG store functionality thoroughly

Your RedM server now has a powerful, RSG-integrated inventory system that will enhance the player experience significantly!

</details>
