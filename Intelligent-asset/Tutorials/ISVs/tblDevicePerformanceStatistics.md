---
title: in.tblDevicePerformanceStatistics - UI Input Schema
description: Input Schema of Table in.tblDevicePerformanceStatistics, shows the data points and types included on this table.
---
# in.tblDevicePerformanceStatistics - Input Schema Table

Statistics on Total, Successful, and Failed performance collection attempts on devices.​​

| Name               | Data Type     | Mandatory | Key                   | Comment                                  |
|--------------------|---------------|-----------|-----------------------|------------------------------------------|
| DataSourceId       | varchar(32)   | Y         |                       | Unique ID of the source of this record.  |
| SrcDevi​​ceId        | nvarchar(128) | Y         | FK > tblDevices.SrcId | Device this performance was recorded on. |
| SuccessfulAttempts | int           |           |                       |                                          |
| TotalAttempts      | int           |           |                       |                                          |
| FailureCode        | int           |           |                       |                                          |