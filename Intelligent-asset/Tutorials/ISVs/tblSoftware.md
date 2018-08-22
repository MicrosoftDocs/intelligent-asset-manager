# in.tblSoftware

​Software installed/running on Devices, excluding Operating Systems.​​

| Name              | Data Type      | Mandatory | Key                   | Comment                                                                                         |
|-------------------|----------------|-----------|-----------------------|-------------------------------------------------------------------------------------------------|
| DataSourceId      | varchar(32)    | Y         |                       | Unique ID of the source of this record.                                                         |
| SrcDeviceId       | nvarchar(128)  | Y         | FK > tblDevices.SrcId​​ | Device this software product is installed on.                                                   |
| Publisher         | nvarchar(256)  |           |                       | Win32_Product.Vendor. Name of the software supplier. Must be an actual Publisher name or Empty. |
| DiscoveredProduct | nvarchar(256)  |           |                       | Name of the software product as discovered on the device.                                       |
| DiscoveredVe​rsion | nvarchar(256)  |           |                       | Version of the software product discovered on the device.                                       |
| ​FileName          | nvarchar(256)​  | ​          | ​                      | ​                                                                                                |
| InstallLocation   | nvarchar(1024) |           |                       |                                                                                                 |
| InstallDate       | datetime       |           |                       | Date and time the software was installed on this device.                                        |
| SoftwareCode      | nvarchar(256)  |           |                       | Win32_Product.IdentifyingNumber                                                                 |
| SwidUniqueId      | nvarchar(256)  |           |                       | Software Identification Tag as defined in ISO/IEC 19770-2.                                      |
| SwidLicensorId    | nvarchar(256)  |           |                       | Software Licensor ID as defined in ISO/IEC 19770-2.                                             |
| Id                | int            |           |                       | Generated during import. Leave empty.                                                           |