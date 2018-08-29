---
title: in.tsysImportErrorLog
---
# in.tsysImportErrorLog

Error details of failed Import processes. Read-only​.

When an error occurs during execution of [in].[sp_Import], error details are recorded here.​

| Name           | Data Type      | Mandatory | Key | Comment                                                                              |
|----------------|----------------|-----------|-----|--------------------------------------------------------------------------------------|
| ID             | int            | Y         |     | Unique ID of the Import process that failed.                                         |
| ErrorNumbe​​r    | int            |           |     | SQL ERROR_NUMBER of the last error that occurred in the Import process.              |
| ErrorState     | int            |           |     | SQL ERROR_STATE of the last error that occurred in the Import process.               |
| ErrorProcedure | nvarchar(128)  |           |     | Name of the stored procedure in which the error occurred that made the process fail. |
| ErrorLine      | int            |           |     | Line number of the stored procedure in which the error occurred.                     |
| ErrorMessage   | nvarchar(4000) |           |     | Error text message that the error returned.                                          |
