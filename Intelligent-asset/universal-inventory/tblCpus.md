# in.tblCpus

​​​​​CPUs per Device. One record per CPU.

| Name                      | Data Type     | Mandatory | Key                   | Comment                                 |
|---------------------------|---------------|-----------|-----------------------|-----------------------------------------|
| DataSourceI​d              | varchar(32)   | Y         |                       | Unique ID of the source of this record. |
| SrcDeviceId               | nvarchar(128) | Y         | FK > tblDevices.SrcId | Device this CPU is installed in.        |
| DeviceId                  | nvarchar(256) | Y         |                       | Win32_Processor.DeviceId                |
| DataWidth                 | tinyint       |           |                       |                                         |
| Manufacturer              | nvarchar(256) |           |                       |                                         |
| MaxClockSpeed             | bigint        |           |                       |                                         |
| Name                      | nvarchar(256) |           |                       |                                         |
| NumberOfCores             | int           |           |                       |                                         |
| NumberOfLogicalProcessors | int           |           |                       |                                         |
| HyperThreadingCapable     | bit           |           |                       |                                         |