---
title: in.tblVms - UI Input Schema
description: Input Schema of Table in.tblVms, shows the data points and types included on this table.
---
# in.tblVms - Input Schema Table

Virtual Machines.​​​

| Name               | Data Type     | Mandatory | Key                   | Comment                                                                                                     |
|--------------------|---------------|-----------|-----------------------|-------------------------------------------------------------------------------------------------------------|
| DataSourceId       | varchar(32)   | Y         |                       | Unique ID of the source of this record.                                                                     |
| SrcDevi​​ceId        | nvarchar(128) |           | FK > tblDevices.SrcId | This virtual device in tblDevices. The Virtual field must be set on the corresponding device in tblDevices. |
| SrcVmHostId        | nvarchar(128) |           | FK > tblVmHosts.SrcId | Host this VM runs on at the time of data collection                                                         |
| AffinityRuleHostId | nvarchar(128) |           | FK > tblVmHosts.SrcId | Host this VM is pinned to by affinity rule, if any                                                          |
| PowerState         | varchar(16)   |           |                       | On, Off, or Suspended.                                                                                      |
| MemoryReservation  | int           |           |                       | Number of memory MB that are guaranteed available.                                                          |
| CpuReservation     | int           |           |                       | Number of CPU MHz that are guaranteed available.                                                            |
| CpuAssigned        | int           |           |                       | Number of virtual CPU's.                                                                                    |
| Name               | nvarchar(256) |           |                       |                                                                                                             |
| DnsName            | nvarchar(256) |           |                       |                                                                                                             |
| IsSnapshot         | bit           |           |                       | True if this is a VM snapshot.                                                                              |
| IsTemplate         | bit           |           |                       | True if this is a VM template.                                                                              |
| GuestHealth        | nvarchar(256) |           |                       | Possible values: OK, Warning, Critical, or Unknown.                                                         |
| Id                 | int           |           |                       | Generated during import. Leave empty.                                                                       |