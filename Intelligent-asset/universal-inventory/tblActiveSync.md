# in.tblActiveSync

​​​​​Detected ActiveSync connections.​​​

| Name                          | Data Type     | Mandatory | Key                   | Comment                                                                                                                     |
|-------------------------------|---------------|-----------|-----------------------|-----------------------------------------------------------------------------------------------------------------------------|
| DataSourceId                  | varchar(32)   | Y         |                       | Unique ID of the source of this record.                                                                                     |
| SrcDeviceID                   | nvarchar(128) | Y         | ​​FK > tblDevices.SrcId | Device the ActiveSync connection was made to. This is probably anExchange or other server exposing the ActiveSync service.  |
| ActiveSyncVersion             | varchar(16)   |           |                       |                                                                                                                             |
| FirstSyncTime                 | datetime      |           |                       |                                                                                                                             |
| LastPolicyUpdate              | datetime      |           |                       |                                                                                                                             |
| LastSyncAttempt               | datetime      |           |                       |                                                                                                                             |
| LastSuccessSync               | datetime      |           |                       |                                                                                                                             |
| LastDeviceWipeRequest         | datetime      |           |                       |                                                                                                                             |
| LastDeviceWipeRequestor       | nvarchar(64)  |           |                       |                                                                                                                             |
| DeviceWipeRequestTime         | datetime      |           |                       |                                                                                                                             |
| DeviceWipeSentTime            | datetime      |           |                       |                                                                                                                             |
| DeviceWipeAckTime             | datetime      |           |                       |                                                                                                                             |
| DeviceAccessState             | nvarchar(64)  |           |                       |                                                                                                                             |
| DevicePolicyApplicationStatus | nvarchar(64)  |           |                       |                                                                                                                             |
|                               |               |           |                       |                                       |