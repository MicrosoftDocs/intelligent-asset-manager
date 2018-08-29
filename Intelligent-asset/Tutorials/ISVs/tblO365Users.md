---
title: in.tblO365Users
---
# in.tblO365Users

​Office 365 (Azure AD) User Accounts.​​

| Name              | Data Type     | Mandatory | Key                               | Comment                                                                                                                                         |
|-------------------|---------------|-----------|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId      | varchar(32)   | Y         |                                   | Unique ID of the source of this record.                                                                                                         |
| UserId            | nvarchar(128) | Y         | Primary Key                       | The unique identifier for the user in Azure AD.                                                                                                 |
| TenantId          | nvarchar(128) | Y         | FK > tblO365Organization.TenantId​​ | The unique identifier for the tenant.                                                                                                           |
| UserPrincipalName | nvarchar(256) |           |                                   | The user principal name (UPN) of the user in Azure AD. The UPN is an Internet-style login name for the user based on Internet standard RFC 822. |
| DisplayName       | nvarchar(256) |           |                                   | The name displayed in the address book for the user.                                                                                            |
| Mail              | nvarchar(256) |           |                                   | The SMTP address for the user.                                                                                                                  |