---
title: in.tblDevices
---
# in.tblDevices

​All network-enabled devices on which licensable software may be installed or executed.​

| Name                      | Data Type      | Mandatory | Key         | Comment                                                                                                                                         |
|---------------------------|----------------|-----------|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId              | varchar(32)    | Y         |             | Unique ID of the source of this record.|
| SrcI​​d                     | nvarchar(128)  | Y         | Primary Key | Unique ID of the device in its resp. data source|
| Site                      | varchar(32)    |           |             | A free text value the user can provide with the data source to indicate a site, environment, tenant, ​or other category these devices belong to.|
| Type                      | nvarchar(256)  |           |             | Server, Workstation, Mobile, Printer, or other indication of the type of device.|
| Name                      | nvarchar(256)  |           |             | Name of the device in its OS​.|
| DnsHostName               | nvarchar(256)  |           |             | ​​Hostname of the device in DNS, without domain.|
| Fqdn                      | nvarchar(512)  |           |             | Fully Qualified Domain Name.|
| Domain                    | nvarchar(256)  |           |             | Windows- or DNS domain.|
| PrimaryUserName           | nvarchar(256)  |           |             | Username of the user with the most logged on time on this device. Format: domain\user or user@domain.|
| Description               | nvarchar(512)  |           |             | Description of the device in the OS.|
| LastBoot                  | datetime       |           |             | Date and time the device was last booted.|
| LastScan                  | datetime       |           |             | Date and time the device was last scanned by the data source tool.|
| Manufacturer              | nvarchar(256)  |           |             | Must be an actual Manufacturer name or Empty.|
| Model                     | nvarchar(256)  |           |             | Must be an existing Model name or Empty.​|
| TotalMemoryMb             | bigint         |           |             |                                         |
| TotalDiskSpaceMB          | bigint         |           |             |                                         |
| SerialNumber              | nvarchar(256)  |           |             |                                         |
| Virtual                   | bit            |           |             | True if this is a virtual device.​​|
| WmiStatus                 | nvarchar(4000) |           |             | If the device info was retrieved using WMI, outcome of the last WMI scan. See [WMI Return Codes.](https://msdn.microsoft.com/en-us/library/aa394574)|
| SamAccountName            | nvarchar(256)  |           |             | Active Directory SAM-Account-Name attribute.|
| SamAccountType            | int            |           |             | Active Directory SAM-Account-Type property.|
| Enabled                   | bit            |           |             | Based on Active Directory AccountDisabled flag of the UserAccountControl property.|
| PwdRequired               | bit            |           |             | Based on Active Directory PASSWD_NOTREQD flag of the UserAccountControl property.|
| PwdCanChange              | bit            |           |             | Based on Active Directory PASSWD_CANT_CHANGE flag of the UserAccountControl property.|
| PwdExpires                | bit            |           |             | Based on Active Directory DONT_EXPIRE_PASSWORD flag of the UserAccountControl property.|
| NormalAccount             | bit            |           |             | Based on Active Directory NORMAL_ACCOUNT flag of the UserAccountControl property.|
| BiosCaption               | nvarchar(256)  |           |             |                                        |
| BiosManufacturer          | nvarchar(256)  |           |             | Must be an actual Manufacturer name or Empty.|
| BiosReleaseDate           | datetime       |           |             |                                        |
| BiosSerialNumber          | nvarchar(128)  |           |             |                                        |
| BiosSlicTable             | int            |           |             | OEM Activation version stored in ACPI SLIC table.|
| BiosMsdmTable             | int            |           |             | Does OEM Activation has an MSDM table (OA 3.0 or later).|
| BiosWindowsEdition        | nvarchar(256)  |           |             |                                        |
| BiosVersion               | nvarchar(128)  |           |             |                                        |
| BaseBoardManufacturer     | nvarchar(256)  |           |             | Must be an actual Manufacturer name or Empty.​|
| BaseBoardProduct          | nvarchar(256)  |           |             |                                        |
| BaseBoardSerialNumber     | nvarchar(128)  |           |             |                                        |
| BaseBoardVersion          | nvarchar(256)  |           |             |                                        |
| OsArchitectureBits        | tinyint        |           |             |                                        |
| OsFamily                  | nvarchar(256)  |           |             | Windows, Linux, Android, etc.          |
| OsInstallDate             | datetime       |           |             | Date and time the Operating System was installed.|
| OsLanguage                | int            |           |             |                                        |
| OsManufacturer            | nvarchar(256)  |           |             | Must be an actual Operating System Manufacturer name or Empty.|
| OsName                    | nvarchar(256)  |           |             |                                        |
| OsRegisteredUser          | nvarchar(256)  |           |             |                                        |
| OsSerialNumber            | nvarchar(256)  |           |             |                                        |
| OsServicePackMajorVersion | nvarchar(640)  |           |             |                                        |
| OsServicePackMinorVersion | nvarchar(64)   |           |             |                                        |
| OsSku                     | int            |           |             |                                        |
| OsVersion                 | nvarchar(256)  |           |             |                                        |
| AdCn                      | nvarchar(64)   |           |             | Active Directory Common name (CN)      |
| AdCompany                 | nvarchar(64)   |           |             |                                        |
| AdCreated                 | datetime       |           |             |                                        |
| AdDescription             | nvarchar(1024) |           |             | Active Directory Description.|
| AdDistinguishedName       | nvarchar(4000) |           |             |                                        |
| AdLastLogon               | datetime       |           |             | MAX(LastLogon, LastLogonTimestamp)     |
| AdLocation                | nvarchar(1024) |           |             |                                        |
| AdLogonCount              | int            |           |             |                                        |
| AdModified                | datetime       |           |             | Date and time the computer account was last modified in Active Directory.|
| AdCountryCode             | nvarchar(64)   |           |             |                                        |
| AdPwdLastSet              | datetime       |           |             |                                        |
| AdUserPrincipalName       | nvarchar(1048) |           |             |                                        |
| Id                        | int            |           |             | Generated during import. Leave empty.  |