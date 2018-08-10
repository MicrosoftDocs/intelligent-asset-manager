# Overview of Universal Inventory

## Components

Universal Inventory is made up of three components:

- **Universal Inventory service**
A Windows service that does the actual work: connect to data sources to import data and store it in the Universal Inventory database.

- **Universal Inventory database server**  
A SQL Server instance that holds the actual inventory databases as well as other databases that Universal Inventory needs:

  - **UniversalInventory** is a single database where Universal Inventory stores the configuration and status of projects, data sources, and other artifacts. This database does not hold inventory data.

  - **UniversalInventoryCatalogs** <a name=\"#catalogs\"></a> is a single database where Universal Inventory stores standard names of processors, software titles, and manufacturers.\r\n  - **UI\\_xxx** databases hold actual inventory data. A new UI\\_xxx database is created for every Project created with Universal Inventory.

  - **Universal Inventory client**  \r\nThe front-end application you use to manage Universal Inventory: create projects, define data sources, and import, refine, and export your inventory.

Components can be installed on the same or on different computers:

- During installation you can specify a SQL Server instance to be used as Universal Inventory database server. This can be a local or remote SQL Server instance.

- After installation, you can install the Universal Inventory client on a separate workstation to manage the Universal Inventory server.

![UI Components](media/ui-overview01.png )