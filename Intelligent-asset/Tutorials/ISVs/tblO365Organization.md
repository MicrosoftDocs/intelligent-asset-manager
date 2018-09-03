---
title: in.tblO365Organization - UI Input Schema
---
# in.tblO365Organization - Input Schema Table

​Definition in Office 365 of the subscribing organization.​

| Name         | Data Type     | Mandatory | Key                               | Comment                                                                                                                                                         |
|--------------|---------------|-----------|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId | varchar(32)   | Y         |                                   | Unique ID of the source of this record.                                                                                                                         |
| TenantId     | nvarchar(128) | Y         | FK > tblO365Organization.TenantId​​ | The unique identifier for the tenant.                                                                                                                           |
| Site         | varchar(32)   |           |                                   | A free text value the user can provide with the data source to indicate a site, environment, tenant, ​or other category this Office 365 subscription belongs to. |
| DisplayName  | nvarchar(256) |           |                                   | The display name for the tenant.                                                                                                                                |
| Country      | varchar(16)   |           |                                   | Two-letter country code.                                                                                                                                        |