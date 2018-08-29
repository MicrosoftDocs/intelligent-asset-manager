---
title: in.tblO365AssignedPlans
---
# in.tblO365AssignedPlans

​Office 365 Service Plans assigned to users or to the entire organization.​

| Name                   | Data Type     | Mandatory | Key                               | Comment                                                                      |
|------------------------|---------------|-----------|-----------------------------------|------------------------------------------------------------------------------|
| DataSourceId​           | varchar(32)   | Y         |                                   | Unique ID of the source of this record.                                      |
| ServicePlanId          | nvarchar(128) | Y         |                                   | A GUID that identifies the service plan.                                     |
| TenantId               | nvarchar(128) | Y         | FK > tblO365Organization.TenantId | The unique identifier for the tenant.                                        |
| AssignedOrganizationId | nvarchar(128) |           |                                   | If this ServicePlan is assigned to the entire organization, Organization ID. |
| AssignedUserId         | nvarchar(128) |           |                                   | If this ServicePlan is assigned to a user, the User ID.                      |
| ServiceName            | nvarchar(256) |           |                                   | The name of the service; for example, “Exchange”.                            |
| CapabilityStatus       | varchar(32)   |           |                                   | For example, "Enabled", or "Provisioned"                                     |
| AssignedDateTime       | datetime      |           |                                   | Data and time at which the service plan was assigned.                        |