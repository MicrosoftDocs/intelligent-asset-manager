---
title: in.tblLogicalDrives - UI Input Schema
description: Input Schema of Table in.tblLogicalDrives, shows the data points and types included on this table.
---
# in.tblLogicalDrives - Input Schema Table

​​​Logical Drives per Device.​​​​

| Name               | Data Type     | Mandatory | Key                          | Comment                                                                                  |
|--------------------|---------------|-----------|------------------------------|------------------------------------------------------------------------------------------|
| DataSource​Id       | varchar(32)   | Y         |                              | Unique ID of the source of this record.                                                  |
| SrcDeviceId        | nvarchar(128) | Y         | FK > tblDevices.SrcId        | Device this drive is defined on.                                                         |
| SrcPhysicalDriveId | nvarchar(128) |           | FK > tblPhysicalDrives.SrcId | If this is a volume on a local physical drive, the corresponding tblPhysicalDrive.SrcId. |
| VolumeName         | nvarchar(256) |           |                              |                                                                                          |
| DriveLetter        | nvarchar(256) |           |                              |                                                                                          |
| Description        | nvarchar(256) |           |                              |                                                                                          |
| Type               | int           |           |                              | Win32_LogicalDisk.DriveType.                                                             |
| FileSystem         | nvarchar(256) |           |                              |                                                                                          |
| SizeMB             | int           |           |                              |                                                                                          |
| FreeSpaceMB        | int           |           |                              |                                                                                          |
| Wwn                | nvarchar(256) |           |                              | World Wide Name of attached storage.                                                     |