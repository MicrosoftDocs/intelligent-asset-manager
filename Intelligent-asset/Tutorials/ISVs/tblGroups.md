--- 
title: in.tblGroups - UI Input Schema
---
# in.tblGroups - Input Schema Table

​Device-local and Domain Security Groups.​​

| Name         | Data Type     | Mandatory | Key                   | Comment                                                                             |
|--------------|---------------|-----------|-----------------------|-------------------------------------------------------------------------------------|
| DataSourceI​​d | varchar(32)   | Y         |                       | Unique ID of the source of this record.                                             |
| SrcId        | nvarchar(128) | Y         |                       | Unique ID of the group in its resp. data source                                     |
| SrcDeviceId  | nvarchar(128) |           | FK > tblDevices.SrcId​ | If this is a local group rather than domain-based, the device this group exists on. |
| Domain       | nvarchar(256) |           |                       |                                                                                     |
| Name         | nvarchar(256) |           |                       |                                                                                     |
| Description  | nvarchar(256) |           |                       |                                                                                     |
| GroupType    | varchar(32)   |           |                       | Domain-local, Global, or Universal​                                                  |
| IsSecurity   | bit           |           |                       |                                                                                     |
| Id           | int           |           |                       | Leave empty                                                                         |