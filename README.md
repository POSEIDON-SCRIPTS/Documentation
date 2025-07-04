---
description: Instalation
---

# POS-Inventory

## POS-Inventory Script Installation Guide

### Overview

The POS-Inventory script provides a comprehensive point-of-sale and inventory management system for your RedM server. This guide will walk you through the complete installation process from start to finish.

### Prerequisites

Before installing the POS-Inventory script, ensure you have the following:

#### Server Requirements

* **RedM Server** (latest version recommended)
* **Database**: MySQL 8.0+ or MariaDB 10.3+
* **Framework**: RedM Core Framework or compatible framework
* **Server Resources**: Minimum 2GB RAM, 10GB available storage

#### Dependencies

The following resources must be installed and running on your server:

* `redemrp_reboot` (or equivalent framework)
* `mysql-async` or `oxmysql`
* `redemrp_inventory` (base inventory system)
* `redemrp_businesses` (for business management)

### Step 1: Download and Extract

1. **Download the Script**
   * Access your purchase from our script store
   * Download the `pos-inventory.zip` file
   * Verify the download integrity using the provided checksum
2. **Extract Files**
   * Extract the ZIP file to a temporary location
   *   You should see the following structure:

       ```
       pos-inventory/├── client/├── server/├── config/├── sql/├── ui/├── stream/├── fxmanifest.lua└── README.md
       ```

### Step 2: Database Setup

1. **Import SQL Files**
   * Navigate to the `sql/` folder
   *   Import the files in the following order:

       ```sql
       -- 1. Main tablespos_inventory_tables.sql-- 2. Default datapos_inventory_data.sql-- 3. Business locations (optional)pos_inventory_locations.sql
       ```
2.  **Execute SQL Commands**

    * Using phpMyAdmin, HeidiSQL, or MySQL command line:

    ```bash
    mysql -u username -p database_name < sql/pos_inventory_tables.sql
    mysql -u username -p database_name < sql/pos_inventory_data.sql
    mysql -u username -p database_name < sql/pos_inventory_locations.sql
    ```
3. **Verify Database Installation**
   * Check that the following tables were created:
     * `pos_inventory_items`
     * `pos_inventory_transactions`
     * `pos_inventory_businesses`
     * `pos_inventory_employees`
     * `pos_inventory_settings`

### Step 3: Resource Installation

1. **Copy Resource Files**
   * Copy the `pos-inventory` folder to your server's `resources` directory
   * Path should be: `server/resources/pos-inventory/`
2.  **Configure server.cfg**

    * Add the following line to your `server.cfg`:

    ```cfg
    # POS-Inventory System
    ensure pos-inventory
    ```
3.  **Set Load Order**

    * Ensure the resource loads after dependencies by placing it after them in server.cfg:

    ```cfg
    # Framework and dependencies
    ensure redemrp_reboot
    ensure mysql-async
    ensure redemrp_inventory
    ensure redemrp_businesses

    # POS-Inventory (load after dependencies)
    ensure pos-inventory
    ```

### Step 4: Configuration

1.  **Edit config.lua**

    * Navigate to `config/config.lua`
    * Configure the following settings:

    ```lua
    Config = {}

    -- Database Configuration
    Config.Database = {
        type = "mysql-async", -- or "oxmysql"
        host = "localhost",
        database = "your_database_name",
        username = "your_username",
        password = "your_password"
    }

    -- Business Settings
    Config.Businesses = {
        maxEmployees = 10,
        taxRate = 0.05, -- 5% tax rate
        enableMultipleLocations = true
    }

    -- Inventory Settings
    Config.Inventory = {
        maxSlots = 50,
        enableAutoRestock = true,
        restockInterval = 3600000, -- 1 hour in milliseconds
        lowStockThreshold = 10
    }
    ```
2.  **Configure Permissions**

    * Edit `config/permissions.lua` to set up user roles:

    ```lua
    Config.Permissions = {
        ["admin"] = {
            canManageAllBusinesses = true,
            canEditPrices = true,
            canViewReports = true
        },
        ["manager"] = {
            canManageOwnBusiness = true,
            canEditPrices = true,
            canViewReports = true
        },
        ["employee"] = {
            canOperatePOS = true,
            canViewInventory = true
        }
    }
    ```

### Step 5: UI Configuration

1. **Web Interface Setup**
   * The UI files are located in the `ui/` folder
   * No additional configuration needed for basic setup
   * For custom styling, edit `ui/css/style.css`
2. **NUI Callbacks**
   * Verify NUI callbacks are properly registered
   * Check browser console (F12) for any JavaScript errors

### Step 6: Testing Installation

1. **Start the Server**
   * Start your RedM server
   * Monitor console for any errors during resource loading
2. **In-Game Testing**
   * Join your server with an admin character
   *   Test the following commands:

       ```
       /pos - Open POS interface/inventory - Open inventory management/business - Open business management
       ```
3. **Verify Functionality**
   * Create a test business
   * Add inventory items
   * Process a test transaction
   * Check database for proper data storage

### Step 7: Business Setup

1. **Create Your First Business**
   * Use the command: `/createbusiness [name] [type]`
   * Example: `/createbusiness "General Store" "retail"`
2. **Set Business Location**
   * Stand at your desired location
   * Use: `/setbusinesslocation [business_id]`
3. **Configure POS Stations**
   * Place POS stations using: `/createpos [business_id]`
   * Configure each station's settings through the management interface

### Troubleshooting

#### Common Issues

**Script Won't Start**

* Check console for dependency errors
* Verify all required resources are running
* Ensure database connection is working

**Database Errors**

* Verify SQL files were imported correctly
* Check database user permissions
* Ensure database name matches config

**UI Not Loading**

* Clear browser cache (Ctrl+F5)
* Check for JavaScript errors in console
* Verify NUI resource permissions

**Commands Not Working**

* Verify user permissions in config
* Check if framework integration is proper
* Ensure character data is loaded

#### Console Commands for Debugging

```bash
# Check resource status
status pos-inventory

# Restart resource
restart pos-inventory

# Check database connection
exec "SELECT 1"

# View recent logs
tail -f server.log | grep pos-inventory
```

### Support

If you encounter issues not covered in this guide:

1. **Check Documentation**: Review all configuration files for comments and examples
2. **Join Our Discord**: Get community support and updates
3. **Create Support Ticket**: For technical issues requiring direct assistance
4. **Check Updates**: Ensure you're running the latest version

### Post-Installation

#### Recommended Next Steps

1. **Configure Backup System**
   * Set up automated database backups
   * Include resource files in backup routine
2. **Performance Optimization**
   * Monitor server performance with the script running
   * Adjust config values based on player count
3. **Staff Training**
   * Train your staff on POS operations
   * Provide business management guidelines
4. **Regular Maintenance**
   * Check for script updates monthly
   * Monitor database growth and optimize as needed

***

**Installation Complete!** Your POS-Inventory script should now be fully functional. For additional features and customization options, refer to the Advanced Configuration guide.
