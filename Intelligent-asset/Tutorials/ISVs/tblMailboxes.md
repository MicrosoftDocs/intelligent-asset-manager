---
title: in.tblMailboxes - UI Input Schema
---
# in.tblMailboxes - Input Schema Table

​​​Mailboxes on mail servers.​

| Name                 | Data Type     | Mandatory | Key                       | Comment                                                  |
|----------------------|---------------|-----------|---------------------------|----------------------------------------------------------|
| DataSourceId         | varchar(32)   | Y         |                           | Unique ID of the source of this record.                  |
| SrcMailServerId      | nvarchar(128) | Y         | FK > tblMailServers.SrcId | Mail server this mailbox exists on.                      |
| SrcUserId            | nvarchar(128) |           | FK > tblUsers.SrcId       | If known, unique ID of the mailbox owner.​​                |
| PrimaryMail          | nvarchar(255) |           |                           | Primary mail address of this mailbox.​                    |
| Created              | datetime      |           |                           | Date and time this mailbox was created.​                  |
| IsEnterprise         | bit           |           |                           | True if Enterprise features are enabled on this mailbox. |
| UsesActiveSync       | bit           |           |                           | True if ActiveSync is enabled on this mailbox.           |
| UsesJournaling       | bit           |           |                           | True if Journaling is enabled on this mailbox.           |
| UsesManagedFolders   | bit           |           |                           | True if Managed Folders are enabled on this mailbox.     |
| UsesUnifiedMessaging | bit           |           |                           | True if Unified Messaging is enabled on this mailbox.    |
| OwaEnabled           | bit           |           |                           | True if Outlook Web Access is enabled on this mailbox.​   |