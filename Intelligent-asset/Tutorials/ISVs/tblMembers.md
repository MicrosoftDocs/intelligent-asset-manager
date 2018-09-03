---
title: in.tblMembers - UI Input Schema
---
# in.tblMembers - Input Schema Table

​User Account members of Security Groups.

| Name         | Data Type     | Mandatory | Key | Comment                                            |
|--------------|---------------|-----------|-----|----------------------------------------------------|
| DataSourc​​eId | varchar(32)   | Y         |     | Unique ID of the source of this record.            |
| GroupDomain  | nvarchar(256) |           |     | Hostname if this is a local group.                 |
| GroupName    | nvarchar(256) | Y         |     |                                                    |
| UserDomain   | nvarchar(256) |           |     | Hostname if this is a local user account.          |
| UserName     | nvarchar(256) | Y         |     |                                                    |
| IsGroup      | bit           |           |     | Is this a nested group rather than a user account? |