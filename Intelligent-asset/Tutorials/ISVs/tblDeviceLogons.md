---
title: in.tblDeviceLogons
---
# in.tblDeviceLogons - Input Schema Table

​Number of times a user account has successfully logged on to a device, and total logon time. Only local device logons, not Active Directory logons.

| Name              | Data Type     | Mandatory | Key | Comment                                   |
|-------------------|---------------|-----------|-----|-------------------------------------------|
| DataSourceId      | varchar(32)   | Y         |     | Unique ID of the source of this record.   |
| SrcDeviceId​​       | nvarchar(128) |           |     | Device the user logged on to.             |
| UserDomain        | nvarchar(256) |           |     | Hostname if this is a local user account. |
| UserName          | nvarchar(256) |           |     |                                           |
| LogonCount        | int           |           |     |                                           |
| TotalLogonMinutes | int           |           |     |                                           |