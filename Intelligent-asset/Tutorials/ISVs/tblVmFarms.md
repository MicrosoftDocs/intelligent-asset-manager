---
title: in.tblVmFarms - UI Input Schema
description: Input Schema of Table in.tblVmFarms, shows the data points and types included on this table.
---
# in.tblVmFarms - Input Schema Table

​Clusters/Farms of Virtualization Hosts.

| Name           | Data Type     | Mandatory | Key         | Comment                                            |
|----------------|---------------|-----------|-------------|----------------------------------------------------|
| DataSourceId   | varchar(32)   | Y         |             | Unique ID of the source of this record.            |
| Name​​           | nvarchar(256) | Y         | Primary Key |                                                    |
| HaModeEnabled  | bit           |           |             | True if High Availability is enabled on this farm. |
| DrsModeEnabled | bit           |           |             | True if Disaster Recovery is enabled on this farm. |
| Id             | int           |           |             | Generated during import. Leave empty.​              |