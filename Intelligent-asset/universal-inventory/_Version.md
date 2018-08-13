# in.__Version

The version of the template this database was generated from. Read-Only.

There will be a single record in this table showing the version of this UI database. A Connector can check this value before execution. Queries might not work if the customer is running an older version of the UI database. If the version number found here is lower than the version your queries are designed for, you may want to halt execution and show a message informing the user of the minimum required UI database version. From the moment of initial release we will make sure the UI database is backward compatible, so there is no need to take any action if the version found here is higher than what your queries are designed for.

| Name         | Data Type | Mandatory | Key | Comment |
|--------------|-----------|-----------|-----|---------|
| MajorVersi​​on | int       | Y         |     |         |
| MinorVersion | int       | Y         |     |         |
|              |           |           |     |         |