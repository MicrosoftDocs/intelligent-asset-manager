# in.tblMailServers

​Instances of licensable mail servers of all brands (IBM, Microsoft, ​​CommuniGate...). One record per installed instance.

| Name         | Data Type     | Mandatory | Key         | Comment                                               |
|--------------|---------------|-----------|-------------|-------------------------------------------------------|
| DataSourceId | varchar(32)   | Y         |             | Unique ID of the source of this record.               |
| SrcId        | nvar​char(128) | Y         | Primary Key​ | Unique ID of the mail server in its resp. data source |
| SrcDeviceId  | nvarchar(128) |           |             | Device this mail server is installed on.              |
| ServerName   | nvarchar(256) |           |             |                                                       |
| InstallPath  | nvarchar(256) |           |             |                                                       |
| ProductName  | nvarchar(256) |           |             |                                                       |
| Version      | nvarchar(256) |           |             |                                                       |
| Edition      | nvarchar(256) |           |             |                                                       |
| Enterprise   | bit           |           |             | Are Enterprise-features enabled/used?                 |
| ServicePack  | nvarchar(256) |           |             |                                                       |
| Id           | int           |           |             | Generated during import. Leave empty.​                 |