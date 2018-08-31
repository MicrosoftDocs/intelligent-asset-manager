---
title: The Input Schema 
---
# Universal Inventory Input schema [in]

Make sure you understand the [**UI Data Model**](Data_Model.md) before reading about The Input schema [in].

The Input Schema [in] holds all tables and procedures to import data into the Inventory. [**Connectors**](Push_Connectors.md)​​ must inject data into the inventory through this schema.

## Relationships

To facilitate the import process​, foreign key relationships are not hard-coded in the Input [in] schema, but represented ​in the following way:

- Parent tables have a ​**SrcId** field. This is the Unique ID of an entity <ins>in its respective Data Source</ins>.
  It can be the SID of a device in Active Directly, the DeviceNumber of a device retrieved from MapToolkit, or any other ID of an entity relative to their Data Source. The data type of SrcId is nvarchar(128) so that any existing data type can be converted to SrcId.  
  Put the ID of the entity in your data source in this field.

- Child tables have **SrcDeviceId, SrcUserId, SrcDatabaseServerId...** fields that point at the SrcId in the corresponding parent table. These foreign key fields are documented in the pages below.

## Duplicates​​

Duplicate records may exist in [in] tables. That is because data can be imported from multiple Data Sources. When the Customer chooses to import data from e.g. his Active Directory and a virtualization system, records representing the same device will be uploaded from both sources. The Import process will identify and eliminate most duplicates, and the user can manually ​identify and eliminate missed ones through the UI Client.

## DataSourceId

A​ll records in all [in​] tables have a **DataSourceId** field, used to uniquely identify the Data Source of the record. The DataSourceId is a concatenation of a type identifier of the Connector and an ordered number. E.g. if a customer imports data from Active Directory and two MapToolkit databases, the corresponding DataSourceIds would be AD_1, Map9x_1, and Map9x_2. Map9x in this case means "MapToolkit 9.0 and later".

Propose a DataSourceId for your Connector by mail to SAM-UI@microsoft.com. We will keep track of all DataSourceId's and make sure they are unique.

When creating a [Push Connector](Push_Connectors.md), please keep in mind:

- ​It is not necessary to fill all tables. ​ Only insert data that is available in your data source.

- When unable to determine the correct value, leave the corresponding field    empty (NULL). Do not provide default values, such as "0" for integer, or SqlDateTime.MinValue for date/time values. NULL values are not processed, default values are. If you don't have values for mandatory fields, leave the entire table empty.

- Date/time values must be in UTC.

## Tables

| Name                            | Description​                                                                                                                 |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| [__Version](_Version.md)                       | This Database Version. Read-only.                                                                                           |
| [tblActiveSync​](tblActiveSync.md)                   | Detected ActiveSync connections.                                                                                            |
| [tblCpus](tblCpus.md)                         | CPUs per Device. One record per CPU.                                                                                        |
| [tblDa​​​tabases](tblDatabases.md)                    | ​Databases running on a licensable database server.                                                                          |
| [tblDatabaseServers](tblDatabaseServers.md)              | Instances of licensable database servers. One record per installed instance.                                                |
| [tblDeviceLogons](tblDeviceLogons.md)                 | Number of times a user account has successfully logged on to a device, and total logon time.                                |
| [tblDevicePerformance](tblDevicePerformance.md)           | Device Performance Counters.                                                                                                |
| [tblDevicePerformanceStatistics](tblDevicePerformanceStatistics.md)  | Device Performance Statistics on Total, Successful, and Failed performance collection attempts.                             |
| [tblDevices](tblDevices.md)​                      | All network-enabled devices on which licensable software may be installed or executed.                                      |
| [tblGroups](tblGroups.md)                       | Device-local and Domain Security Groups.                                                                                    |
| [tblLogicalDrives](tblLogicalDrives.md)                | Logical Drives per Device.                                                                                                  |
| [tblMailboxes](tblMailboxes.md)                    | Mailboxes on mail servers.                                                                                                  |
| [tblMailServers](tblMailServers.md)                  | Instances of licensable mail servers. One record per installed instance.                                                    |
| [tblMembers​](tblMembers.md)                      | User Accounts members of security Groups.                                                                                   |
| [tblMemory](tblMemory.md)                       | Physical/Virtual Memory per Device.                                                                                         |
| [tblNetworkAdapterConfigurations](tblNetworkAdapterConfigurations.md) | IP Configuration of Network Adapters.                                                                                       |
| [tblNetworkAdapters](tblNetworkAdapters.md)              | Network adapters with MAC Addresses.                                                                                        |
| [tblO365AssignedPlans](tblO365AssignedPlans.md)            | Office 365 Service Plans assigned to users or to the entire organization.                                                   |
| [tblO365Domains](tblO365Domains.md)                  | Domain names defined in an Office 365 subscription. Corresponds to the Domains tab in the Office 365 administration portal. |
| [tblO365Organization](tblO365Organization.md)​             | Definition in Office 365 of the subscribing organization.                                                                   |
| [tblO365ServicePlans](tblO365ServicePlans.md)             | Office 365 Service Plans that are available with a subscription and their provisioning status.                              |
| [tblO365Subscriptions](tblO365Subscriptions.md)            | Information about an Office 365 service SKU that a company is subscribed to.                                                |
| [tblO365Users](tblO365Users.md)                    | Office 365 (Azure AD) User Accounts.                                                                                        |
| [tblPhysicalDrives](tblPhysicalDrives.md)               | Physical Drives per Device.                                                                                                 |
| [tblServices](tblServices.md)                     | Services/Daemons installed on Devices.                                                                                      |
| [tblSoftware​](tblSoftware.md)                     | Software installed on Devices, excluding OS.                                                                                |
| [tblUsers](tblUsers.md)                        | Device-local and Domain User Accounts.                                                                                      |
| [tblVmEvents](tblVmEvents.md)​                     | Virtualization Events, limited to Created, Cloned, Removed, Migrated, and Migrated for Disaster Recovery.                   |
| [tblVmFarms](tblVmFarms.md)                      | Clusters/Farms of Virtualization Hosts.                                                                                     |
| [tblVmHosts](tblVmHosts.md)                     | Virtualization Hosts.                                                                                                       |
| [tblVms](tblVms.md)                          | Virtual Machines.                                                                                                           |
| [tblWebApplications](tblWebApplications.md)             | Web Applications hosted on Devices.                                                                                         |
| [tblWebBrowsers](tblWebBrowsers.md)                  | Web Browsers installed on Devices.                                                                                          |
| [tsysImportLog](tsysImportLog.md)                   | Import process results. Read-only                                                                                           |
| [tsysImportErrorLog​](tsysImportErrorLog.md)              | Error details of failed Import processes. Read-only                                                                         |

## Stored Procedures

| ​Name               | Parameters​                                                                  | Description​                                                                                                                |
|--------------------|-----------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| ​sp_CleanDataSource | Input: DataSourceId of t​he executing Connector. <br/> ​Output: -None-               | ​Must be executed before data is uploaded.Cleans existing records with the specified DataSourceId from Input schema tables. |
| sp_Import​          | Input: -​None- <br/> Output: nvarchar(4000) holding the last returned error message​​ | Must be executed after data is uploaded.Imports data from the Input schema into permanent storage.                         |