# in.tblDevicePerformance

​​​​Device Performance Counters.​​​

Null values complicate performance analysis. To prevent null values, missing values can be replaced with aggregates of values nearby in time.
E.g. suppose the following sequence of performance values was collected:

|               |   |   |    |      |      |    |    |
|---------------|---|---|----|------|------|----|----|
| TimeInterval: | 0​ | 1 | 2  | 3    | 4    | 5  | 6​  |
| Value:        | 0 | 5 | 15 | null | null | 45 | 60 |

We can replace null values with values on the straight line through ​the points in TimeIntervals 2 and 5.  
In this case, the Runlength column should show the number of replaced values, resulting in:

|               |   |   |    |    |    |    |    |
|---------------|---|---|----|----|----|----|----|
| TimeInterval: | 0 | 1 | 2  | 3  | 4  | 5  | 6  |
| Value:        | 0 | 5 | 15 | 25 | 35 | 45 | 60 |
| Runlength:    | 0 | 0 | 0  | 2  | 2  | 0  | 0  |

Device Performance tables are largely based on MapToolkit. Read [MAP: Performance Data​](https://social.technet.microsoft.com/wiki/contents/articles/13467.map-performance-data.aspx) for more info.

| Name                     | Data Type     | Mandatory | Key | Comment                                                                                                                      |
|--------------------------|---------------|-----------|-----|------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId             | varchar(32)   | Y         |     | Unique ID of the source of this record.                                                                                      |
| SrcDeviceId              | nvarchar(128) | Y         |     | Device on which this performance was recorded.                                                                               |
| TimeInterval​​             | int           |           |     | Consecutive number of this time interval, starting with 0.                                                                   |
| Runlength                | int           |           |     | Number of performance values that was extrapolated because performance collection did not produce a value in this timeframe. |
| StartDateTime            | datetime      | Y         |     | Start of this time interval.                                                                                                 |
| EndDateTime              | datetime      | Y         |     | End of this time interval.                                                                                                   |
| CpuPercentage            | float         |           |     |                                                                                                                              |
| CpuUserPercentage        | float         |           |     |                                                                                                                              |
| MemoryUsedGB             | float         |           |     |                                                                                                                              |
| MemoryAvailableGB        | float         |           |     |                                                                                                                              |
| DiskTotalTransfersPerSec | float         |           |     |                                                                                                                              |
| DiskWritesPerSec         | float         |           |     |                                                                                                                              |
| DiskReadsPerSec          | float         |           |     |                                                                                                                              |
| DiskUsedGB               | float         |           |     |                                                                                                                              |
| NetworkIoTotalMbps       | float         |           |     |                                                                                                                              |
| NetworkIoReadMbps        | float         |           |     |                                                                                                                              |
| NetworkIoWriteMbps       | float         |           |     |                                                                                                                              |
| MemoryPoolNonPagedBytes  | float         |           |     |                                                                                                                              |
| MemoryCacheBytes         | float         |           |     |                                                                                                                              |