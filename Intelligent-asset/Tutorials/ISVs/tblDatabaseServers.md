---
title: in.tblDatabaseServers
---
# in.tblDatabaseServers

​​​​​Instances of licensable database servers from all vendors (IBM, Microsoft, MySql, Oracle​, PostgreSQL...). One record per installed instance.​

| Name​                 | Data Type      | Mandatory | Key                   | Comment                                                                      |
|----------------------|----------------|-----------|-----------------------|------------------------------------------------------------------------------|
| DataSourceId         | varchar(32)    | Y         |                       | Unique ID of the source of this record.                                      |
| SrcDeviceId​          | nvarchar(128)  | Y         | FK > tblDevices.SrcId | Device this database server is running on.                                   |
| SrcId                | nvarchar(128)  | Y         | Primary Key           | Unique ID of the database server in its resp. data source                    |
| InstallLocation      | nvarchar(1024) |           |                       |                                                                              |
| ProductName          | nvarchar(256)  |           |                       |                                                                              |
| Version              | varchar(64)    |           |                       |                                                                              |
| Edition              | nvarchar(256)  |           |                       |                                                                              |
| ServicePack          | nvarchar(256)  |           |                       |                                                                              |
| IsIntegratedSecurity | bit            |           |                       |                                                                              |
| DataPath             | nvarchar(1024) |           |                       | Default path for new databases                                               |
| ServiceName          | nvarchar(256)  |           |                       |                                                                              |
| State                | nvarchar(256)  |           |                       | Service state                                                                |
| StartMode            | nvarchar(256)  |           |                       | Service startmode                                                            |
| Clustered            | bit            |           |                       |                                                                              |
| InstanceId           | nvarchar(256)  |           |                       |                                                                              |
| InstanceName         | nvarchar(256)  |           |                       |                                                                              |
| Sku                  | nvarchar(256)  |           |                       |                                                                              |
| SqlServiceType       | int            |           |                       | WMI SqlService.SqlServiceType                                                |
| Environment          | nvarchar(256)  |           |                       | User supplied info to allow license assignment. E.g. production vs. dev/test |
| Isv                  | nvarchar(256)  |           |                       | Specify vendor if included in separate ISV license.                          |
| Id                   | int            |           |                       | Generated during import. Leave empty.​                                        |