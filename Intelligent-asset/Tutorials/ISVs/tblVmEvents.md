---
title: in.tblVmEvents
---
# in.tblVmEvents

Virtualization Events, limited to Created, Cloned, Removed, Migrated, and Migrated for Disaster Recovery.​ To establish license compliance, it is important to make the distinction between the latter two.​

| Name         | Data Type     | Mandatory | Key               | Comment                                  |
|--------------|---------------|-----------|-------------------|------------------------------------------|
| DataSourceId | varchar(32)   | Y         |                   | Unique ID of the source of this record.  |
| SrcVmId      | nvarchar(128) | Y         | FK > tblVms.SrcId​ | VM this event occurred for.              |
| EventType    | varchar(32)   | Y         |                   | For example Cloned, Removed, Migrated... |
| EventTime    | datetime      | Y         |                   | Date and time the event occurred.        |
| UserName     | nvarchar(64)  |           |                   | User that initiated the event, if any    |