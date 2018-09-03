---
title: Universal Inventory Data Model for ISVs
---
# Universal Inventory Data Model

After the [**ISV**](../../Overview/key-users.md) has reviewed the [**Technical Integration Process introduction**](introduction.md), you should understand the UI Data Model. 

To do you so, we recommend you download the Universal Inventory database template:

1. [**Download**](https://aka.ms/DownloadUI) and [**Install Universal Inventory**](../UI/installation.md)
2. Create a test Project in UI. Look at the empty database created with SQL Management Studio (The database name will be the name of your test project prefixed with "UI_").
 > [!TIP] 
 > ​​​​​Whenever the user creates a new ​Project in UI, a new UI Database is created from the Universal Inventory database template on the database server specified during installation. The database template is a [**.bacpac file**](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-import).  

 > [!NOTE]
 > UI databases require Micro​soft SQL​​ Server 2012 or later, Express Edition or higher.

A UI database has three schemas:

1. [**Input schema [in]**](Input-Schema.md): holds tables and procedures to import data into the UI Database. Push Connectors​ must fill tables in this schema.
2. **Permanent data store [dbo]**: permanently stores the Inventory.
3. **Output schema [out]**: tables and procedures to consult the Inventory. Inventory Consumers must use this schema.

![Universal Inventory overview Data Flow ](media/UI-Technical-Data-Flow.png)

Read [**Release Notes**](../UI/Release-notes.md) for the detailed description of release changes on the past versions of Universal Inventory. 