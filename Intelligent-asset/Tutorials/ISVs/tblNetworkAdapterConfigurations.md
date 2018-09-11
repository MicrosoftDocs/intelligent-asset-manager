---
title: in.tblNetworkAdapterConfigurations - UI Input Schema
description: Input Schema of Table in.tblNetworkAdapterConfigurations, shows the data points and types included on this table.
---
# in.tblNetworkAdapterConfigurations - Input Schema Table

​​IP Configuration of Network Adapters.

| Name         | Data Type     | Mandatory | Key | Comment                                                                                     |
|--------------|---------------|-----------|-----|---------------------------------------------------------------------------------------------|
| DataSourceI​​d| varchar(32)   | Y         |     | Unique ID of the source of this record.                                                     |
| SrcDeviceId  | nvarchar(128) | Y         |     | Device this network configuration is defined on.                                            |
| MacAddress   | nvarchar(256) | Y         |     |                                                                                             |
| Ipaddress    | varchar(512)  |           |     | If this adapter has more than one IP configuration, separate addresses with semi-colon (;). |
| IpSubnet     | varchar(512)  |           |     | If this adapter has more than one IP configuration, separate addresses with semi-colon (;). |
| Description  | nvarchar(256) |           |     |                                                                                             |