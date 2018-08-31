---
title: in.tblVmHosts - Table
---
# in.tblVmHosts - Input Schema Table

Virtualization Hosts.​

| Name             | Data Type     | Mandatory | Key                   | Comment                                                   |
|------------------|---------------|-----------|-----------------------|-----------------------------------------------------------|
| DataSour​​ceId     | varchar(32)   | Y         |                       | Unique ID of the source of this record.​                   |
| SrcDeviceId      | nvarchar(128) | Y         | FK > tblDevices.SrcId | Device this virtualization host is installed on.          |
| ​SrcId            | ​nvarchar(128) | Y         | Primary Key​           | Unique ID of this host in its resp. data source.​​          |
| FarmName         | nvarchar(256) |           | FK > tblVmFarms&#46;Name  | Name of the farm or cluster​ this host belongs to, if any. |
| Name             | nvarchar(256) | Y​​​         |                       |                                                           |
| MigrationEnabled | bit           |           |                       | True if Migration is enabled on this host.                |
| OsVersion        | nvarchar(256) |           |                       | Version of the Operating System installed on this host.   |
| NumberOfCores    | int           |           |                       | Total number of CPU cores installed in this host.         |
| Id               | int           |           |                       | Generated during import. Leave empty.                     |