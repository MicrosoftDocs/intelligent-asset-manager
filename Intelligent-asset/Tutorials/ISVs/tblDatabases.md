# in.tblDatabases

​​​​​Databases running on a licensable database server.

| Name​                | Data Type     | Mandatory | Key                           | Comment                                 |
|---------------------|---------------|-----------|-------------------------------|-----------------------------------------|
| DataSourceId        | varchar(32)   | Y         |                               | Unique ID of the source of this record. |
| SrcDatabaseServerId | nvarchar(128) | Y         | FK > tblDatabaseServers.SrcId​​ | Device this database is running on.     |
| Name                | nvarchar(256) |           |                               |                                         |
| DataFileSizeMB      | int           |           |                               |                                         |
| LogFileSizeMB       | int           |           |                               |                                         |
| LogFileUsedSizeMB   | int           |           |                               |                                         |