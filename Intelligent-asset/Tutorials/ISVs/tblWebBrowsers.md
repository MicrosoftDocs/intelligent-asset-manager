---
title: in.tblWebBrowsers - UI Input Schema
---
# in.tblWebBrowsers - Input Schema Table

Web Browsers installed on Devices.​

| Name         | Data Type     | Mandatory | Key                   | Comment                                                                              |
|--------------|---------------|-----------|-----------------------|--------------------------------------------------------------------------------------|
| DataSourceId​​ | varchar(32)   | Y         |                       | Unique ID of the source of this record.                                              |
| SrcDeviceId  | nvarchar(128) | Y         | FK > tblDevices.SrcId | Device this browser is installed on.                                                 |
| BrowserName  | nvarchar(64)  |           |                       | Name of the web browser, such as Chrome, Edge, FireFox, Internet Explorer, Safari... |
| IsDefault    | bit           |           |                       | True if this is the default browser on this device.                                  |