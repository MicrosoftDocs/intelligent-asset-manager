---
title: in.tblO365Subscriptions
---
# in.tblO365Subscriptions - Input Schema Table

Information about an Office 365 service SKU that a company is subscribed to.​​​​​

| Name                  | Data Type     | Mandatory | Key                               | Comment                                                                                                                                                          |
|-----------------------|---------------|-----------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId          | varchar(32)   | Y         |                                   | Unique ID of the source of this record.                                                                                                                          |
| SubscriptionId​​        | nvarchar(128) | Y         | Primary Key                       | The unique identifier (GUID) for the subscription.                                                                                                               |
| TenantId              | nvarchar(128) | Y         | FK > tblO365Organization.TenantId | The unique identifier for the tenant.                                                                                                                            |
| CapabilityStatus      | varchar(32)   |           |                                   | For example, "Enabled", or "Provisioned".                                                                                                                        |
| SkuPartNumber         | varchar(256)  |           |                                   | The SKU part number; for example: "AAD_PREMIUM" or "RMSBASIC".                                                                                                   |
| AppliesTo             | varchar(32)   |           |                                   | The object the subscription applies to. Possible values:<br/>"User" - subscription applies to individual users.<br/>"Company" - subscription applies to the entire tenant. |
| ConsumedUnits         | int           |           |                                   | The number of licenses that have been assigned.                                                                                                                  |
| PrepaidUnitsSuspended | int           |           |                                   | The number of prepaid units that are suspended.                                                                                                                  |
| PrepaidUnitsEnabled   | int           |           |                                   | The number of prepaid units that are enabled.                                                                                                                    |
| PrepaidUnitsWarning   | int           |           |                                   | The number of prepaid units that are in warning status.                                                                                                          |