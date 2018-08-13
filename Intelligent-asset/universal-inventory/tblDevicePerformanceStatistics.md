# in.tblDevicePerformanceStatistics

Statistics on Total, Successful, and Failed performance collection attempts on devices.​​

| Name               | Data Type     | Mandatory | Key                   | Comment                                  |
|--------------------|---------------|-----------|-----------------------|------------------------------------------|
| DataSourceId       | varchar(32)   | Y         |                       | Unique ID of the source of this record.  |
| SrcDevi​​ceId        | nvarchar(128) | Y         | FK > tblDevices.SrcId | Device this performance was recorded on. |
| SuccessfulAttempts | int           |           |                       |                                          |
| TotalAttempts      | int           |           |                       |                                          |
| FailureCode        | int           |           |                       |                                          |
|                    |               |           |                       |                                          |