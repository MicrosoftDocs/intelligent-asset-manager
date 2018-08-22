# in.tblNetworkAdapters

​Network adapters with MAC Addresses only.

| Name         | Data Type     | Mandatory | Key | Comment                                        |
|--------------|---------------|-----------|-----|------------------------------------------------|
| DataSourceId | varchar(32)   | Y         |     | Unique ID of the source of this record.        |
| SrcDeviceId  | nvarchar(128) | Y         |     | Device this network adapter is installed in.   |
| MacAddre​​​ss   | nvarchar(256) | Y         |     |                                                |
| Manufacturer | nvarchar(256) |           |     | Must be an actual Manufacturer name or Empty. |
| Name         | nvarchar(256) |           |     |                                                |
| Description  | nvarchar(256) |           |     |                                                |
| Id           | int           |           |     | Generated during import. Leave empty.          |