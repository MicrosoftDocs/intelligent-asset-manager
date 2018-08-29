---
title: UI Release Notes
---
# Universal Inventory Release Notes

**Version 2.10** (​Announced as "Universal Inventory v1.1")

*Universal Inventory*

- Client-service communication now uses SSL/TLS (HTTPS)
- Universal Inventory now supports patching:
  Fixes will automatically be installed when placed in the Patches subfolder
- MAP Toolkit connector fixes:
  - Incorrect number of devices
  - Incorrect number of CPU's
  - Conversion failed when converting datetime from character string
  - Incorrect OS Version prevents normalization of OS names
  - Hyper-V VMs with an empty name
- Active Directory connector user account collection fixed
- Fixed 'Invalid date' on the Project overview
- Removed obsolete collector scripts
- Custom collector scripts implementation has changed: scripts are not copied to the Projects folder anymore, but custom scripts will be executed when placed in a Projects subfolder of the Work folder
- Log file is created in a sub-folder of the Work folder
- New log file is created when it reaches 1MB. Maximum 4 log files are kept
- Increased logging for normalization and for registration with the normalization provider
- PII removed from the log file
- Parameters in the database are encrypted
- Parameters in the configuration file are encrypted

*Universal Inventory Setup*

- UISetup now supports uninstall
- UISetup now supports updating from a previous version\
- Fixed launching Universal Inventory after setup exits
- Check of permissions on the Work folder during installation is improved
- Check of TCP port during installation is improved

*IAM Encryption/Decryption tool*
- Decryption fails when executed on a device with a non-English version of Windows

**Version 0.14** (tblSoftware changed)

- ​The colum​n "FileName" was added to [in].tblSoftware

**Versions 0.6 - 0.14**

- Changes were mainly functional, do not impact on the schema described on these instruction pages.

**Version 0.6** (Input schema renamed)

- The Input schema previously called [cnct] is renamed to [in].  
  **Partners that have started creating queries for Push Connectors should modify their scripts to accomodate this change.**
- Added Descriptions to fields and tables in the Input schema.
- Renamed to UniversalInventory.bacpac.
- Corrected typos and errors on field names and data types.

**Version 0.5** (Performance revisited)

- View out.DevicePerformanceRows added. This view shows one record per device. time interval, and metric type.
  The existing out.DevicePerformance view shows all metric types per device and time on a single row, with a column for each metric type.
- TotalDiskSpaceMB field added to tblDevices.

**Version 0.4** (Web Applications)

- Web-based applications are stored in tblWebApplications
  This table should only hold web applications hosted in the scanned infrastructure. It is not intended for web application usage, e.g. web apps hosted externally only accessed on user devices.
- Added the [out] schema for data consumption. The data store should be consulted through this schema. Changes to the permanent data store will not impact data consumers this way.

​​​​**Version 0.3** (vSphere & Performance)  

Virtualization tables restructured to accomodate for the new vSphere Connector:
- tblVmEvents: Events that occur on Virtualization hosts with virtual machines, limited to VM Creation, -Cloning, -Removal, -Migration, and Migration for Disaster Recovery.
  It is important to make the distinction between the latter two.
- tblVmFarms: Clusters and Farms of Virtualization hosts.
- tblVmHosts: Virtualization hosts.
- tblVms: Virtual machines
Performance data on Devices is stored in tblDevicePerformance. (Performance of applications is planned for a later release.)

​​**Version 0.2** (Office 365)
  
Tables for the Office 365 Connector:​
- tblO365AssignedPlans: Office 365 Service Plans assigned to users or the entire organization.
- tblO365Domains: DNS domain names linked to an Office 365 subscription. Corresponds to the Domains tab in the Office 365 administration portal.
- tblO365Organization: The subscribing organization.
- tblO365ServicePlans: Office 365 Service Plans part of a subscription and their provisioning status.
- tblO365Subscriptions
- tblO365Users

**Version 0.1** (Initial Draft)
  
- Tables for Devices, Hardware, Software, Users, and Group Membership.  
- Created for Connectors to Active Directory, MapToolkit, Lansweeper, and SCCM.