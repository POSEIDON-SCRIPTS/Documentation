# VORP Installation Guide

Welcome to the official installation guide for **POS-Inventory** with seamless **VORP Framework** integration. This guide will walk you through every step to upgrade your RedM server’s inventory system, ensuring reliability and compatibility.

---

## Prerequisites

<details>
<summary><strong>📋 Prerequisites</strong></summary>

Before you begin, make sure you have:

- **VORP Framework** installed and running
- **Server access** with permission to modify files
- **Keymaster** access for script downloads
- **Recent server backup** (highly recommended)

> **Warning:**  
> Always back up your server before installing new scripts. This process will replace your existing `vorp_inventory` script.
</details>

---

## Installation Steps

<details>
<summary><strong>🚀 Step 1: Prepare the POS Folder Structure</strong></summary>

1. Go to your server’s `resources` folder.
2. Check for a `[POS]` folder (with square brackets).
3. If it doesn’t exist, create a folder named **exactly** `[POS]`.

```plaintext
server/
└── resources/
   └── [POS]/          ← Create this folder
```

> **Note:**  
> The `[POS]` folder name (with brackets) is required for proper resource categorization in RedM.
</details>

<details>
<summary><strong>📦 Step 2: Download and Install POS-Core</strong></summary>

1. Log in to your **Keymaster** account.
2. Download the **POS-Core** script.
3. Extract the files.
4. Place the `POS-Core` folder inside `[POS]`.

```plaintext
[POS]/
└── POS-Core/
```
</details>

<details>
<summary><strong>📥 Step 3: Download POS-Inventory</strong></summary>

1. Download **POS-Inventory** from Keymaster.
2. Extract the files.
3. Place the `POS-Inventory` folder inside `[POS]`.

```plaintext
[POS]/
├── POS-Core/
└── POS-Inventory/
```
</details>

<details>
<summary><strong>🗄️ Step 4: Import Database Tables</strong></summary>

> **Critical:**  
> The script requires specific database tables.

1. Go to `[POS]/POS-Inventory/sql/`.
2. Open your database tool (phpMyAdmin, HeidiSQL, etc.).
3. Select your server’s database.
4. Import or execute the SQL file(s) in the `sql` folder.

> **Tip:**  
> You can use phpMyAdmin, HeidiSQL, MySQL Workbench, or the command line.

**After Import:**

- Confirm new tables (e.g., `pos_*`) exist.
- Ensure no errors occurred.
</details>

<details>
<summary><strong>🗂️ Step 5: Backup and Remove Old Inventory</strong></summary>

> **Critical:**  
> Always back up your existing inventory!

1. **Backup:** Copy your current `vorp_inventory` folder to a safe location.
2. **Remove:** Delete or move the old `vorp_inventory` from `resources/`.
</details>

<details>
<summary><strong>🔄 Step 6: Rename POS-Inventory</strong></summary>

1. In `[POS]`, rename `POS-Inventory` to `vorp_inventory`.
2. Move `vorp_inventory` to the main `resources/` directory.

```plaintext
resources/
├── [POS]/
│   └── POS-Core/
└── vorp_inventory/     ← Renamed POS-Inventory folder
```
</details>

<details>
<summary><strong>🖼️ Step 7: Setup Item Images</strong></summary>

1. Go to `resources/vorp_inventory/html/img/`.
2. Create a folder named `items`.
3. Place all item images in this folder.

```plaintext
vorp_inventory/
└── html/
   └── img/
      └── items/
         ├── apple.png
         ├── bread.png
         └── ...
```
</details>

<details>
<summary><strong>⚙️ Step 8: Configure VORP Settings</strong></summary>

1. Open `resources/vorp_inventory/shared/configs/config.lua`.
2. Find the VORP configuration section.
3. Update these settings:

```lua
Config.UseMaxWeightVORP = true      -- Use max weight from config
Config.ItemsInDatabaseVORP = true   -- Use items in database
Config.UseLoadoutTableVORP = true   -- Enable loadout table for weapons
```

> **Details:**  
> - `UseMaxWeightVORP`: Use config-based weight limits  
> - `ItemsInDatabaseVORP`: Store items in database  
> - `UseLoadoutTableVORP`: Ensure weapon scripts work properly
</details>

<details>
<summary><strong>🔧 Step 9: Update Server Configuration</strong></summary>

1. Open `server.cfg`.
2. Ensure the following load order:

```cfg
# VORP Framework
ensure vorp_core
ensure vorp_inventory
ensure POS-Core          ← Add this line here
```

> **Warning:**  
> POS-Core must load immediately after vorp_inventory.
</details>

<details>
<summary><strong>🔄 Step 10: Configure Data Migration (For Live Servers)</strong></summary>

> **Live Server Warning:**  
> Only perform this if you have active players with inventories.

1. In `resources/vorp_inventory/shared/configs/config.lua`, find:

```lua
Config.ImportInventoryVORP = false
```

2. Change `false` to your migration command, e.g.:

```lua
Config.ImportInventoryVORP = 'loadOldInventory'
```

3. Restart your server (no players online).
4. Run the command in your server console:

```plaintext
loadOldInventory
```

5. Wait 10 seconds for migration.
6. Set the config back to `false` and restart the server.

```lua
Config.ImportInventoryVORP = false
```
</details>

---

## Post-Installation Verification

<details>
<summary><strong>✅ Post-Installation Verification</strong></summary>

**Test Your Installation:**

1. Start your server and check the console for errors.
2. Join with a test character and verify:
   - Inventory opens
   - Items display correctly
   - Weight system works
   - Database interactions function

**Success Indicators:**

- No console errors for POS-Core or vorp_inventory
- Inventory UI loads
- Item images display
- Inventories persist after restart
</details>

---

## Troubleshooting

<details>
<summary><strong>🔧 Troubleshooting</strong></summary>

**Common Issues & Solutions:**

- **Console Errors (Load Order):**  
  Ensure POS-Core loads after vorp_inventory, and vorp_core loads first.

- **Missing Item Images:**  
  Confirm the `items` folder exists and image names match database entries.

- **Database Issues:**  
  Check VORP database settings and migration completion.

- **Inventory Not Opening:**  
  Verify the script is renamed to `vorp_inventory` and check for errors.

**Need Help?**

1. Check the console for errors.
2. Review each installation step.
3. Contact support with logs and error details.
</details>

---

## Final Notes & Next Steps

<details>
<summary><strong>📝 Final Notes & Next Steps</strong></summary>

> **Success:**  
> Your POS-Inventory system is now integrated with VORP Framework!

**Reminders:**

- Keep your backup of the original `vorp_inventory`
- Monitor server performance
- Update item images as needed
- Regularly back up your server

**Next Steps:**

- Configure item weights in your database
- Train staff on new inventory features
- Customize the UI for your server’s theme

Enjoy your enhanced, VORP-integrated inventory system!
</details>
