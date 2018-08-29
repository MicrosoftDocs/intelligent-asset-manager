---
title: in.tblWebApplications
---
# in.tblWebApplications

Web Applications hosted on Devices. This table is not intended for web applications that are used within the organization but not hosted on the organization's (hosted or on premise) infrastructure.​

| Name                  | Data Type     | Mandatory | Key                   | Comment                                                                                                  |
|-----------------------|---------------|-----------|-----------------------|----------------------------------------------------------------------------------------------------------|
| DataSourceId          | varchar(32)   | Y         |                       | Unique ID of the source of this record.                                                                  |
| SrcDeviceId           | nvarchar(128) | Y         | FK > tblDevices.SrcId | Device this web application is installed on.​​                                                             |
| Name                  | nvarchar(256) | Y         |                       | Web Application name.                                                                                    |
| AppRoot               | nvarchar(256) |           |                       |                                                                                                          |
| Path                  | nvarchar(256) |           |                       | Physical installation location.                                                                          |
| AppPoolId             | nvarchar(64)  |           |                       | If this is an IIS application, ID of the Application Pool.                                               |
| ManagedRuntimeVersion | nvarchar(20)  |           |                       | If this is an IIS application, version of the Managed .Net runtime.                                      |
| Technologies          | nvarchar(256) |           |                       | Semi-colon (;) separated string of technologies used by this app, such as aspx, html, java, php, ruby... |