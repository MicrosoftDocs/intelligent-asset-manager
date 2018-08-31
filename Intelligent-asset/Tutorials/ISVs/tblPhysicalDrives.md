---
title: in.tblPhysicalDrives
---
# in.tblPhysicalDrives - Input Schema Table

​​Physical Drives per Device.​

| Name         | Data Type     | Mandatory | Key                   | Comment                                       |
|--------------|---------------|-----------|-----------------------|-----------------------------------------------|
| DataSourceId | varchar(32)   | Y         |                       | Unique ID of the source of this record.       |
| SrcDeviceId  | nvar​​char(128) | Y         | FK > tblDevices.SrcId | Device this drive is installed in.            |
| DeviceId     | nvarchar(256) | Y         |                       | Win32_DiskDrive.DeviceId                      |
| Name         | nvarchar(256) |           |                       |                                               |
| Manufacturer | nvarchar(256) |           |                       | Must be an actual Manufacturer name or Empty. |
| Model        | nvarchar(256) |           |                       |                                               |
| Interface    | nvarchar(256) |           |                       | For example "IDE", "SCSI", or "USB".          |
| SizeMB       | int           |           |                       |                                               |
| SerialNumber | nvarchar(256) |           |                       |                                               |
| Id           | int           |           |                       | Generated during import. Leave empty.         |