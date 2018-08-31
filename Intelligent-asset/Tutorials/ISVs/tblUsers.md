---
title: in.tblUsers - Table
---
# in.tblUsers - Input Schema Table

Device-local and Domain User Accounts.​

For local users accounts: enter the SrcDeviceId of the corresponding device from tblDevices. Leave Active Directory fields empty (such as SamAccountName, SamAccountType ...)
Conversely for domain accounts: leave SrcDeviceId empty and fill out Active Directory fields

| Name                | Data Type      | Mandatory | Key                   | Comment                                                                                                                                                                             |
|---------------------|----------------|-----------|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DataSourceId        | varchar(32)    | Y         |                       | Unique ID of the source of this record.                                                                                                                                             |
| SrcId​​               | nvarchar(128)  | Y         | Primary Key           | Unique ID of the user account in its resp. data source                                                                                                                              |
| SrcDeviceId         | nvarchar(128)  |           | FK > tblDevices.SrcId | If this is a local user account rather than a domain account, device the account exists on.                                                                                         |
| Site                | varchar(32)    |           |                       | A free text value the user can provide with the data source to indicate a site, environment, tenant, ​or other category these users belong to.                                       |
| Cn                  | nvarchar(64)   |           |                       | Active Directory Common Name.                                                                                                                                                       |
| DisplayName         | nvarchar(256)  |           |                       |                                                                                                                                                                                     |
| UserPrincipalName   | nvarchar(256)  |           |                       | The user principal name (UPN) of the user. The UPN is an Internet-style login name for the user based on Internet standard RFC 822. Active Directory User-Principal-Name attribute. |
| Domain              | nvarchar(256)  |           |                       | For local accounts: empty or the computer name where the device is defined.                                                                                                         |
| SamAccountName      | nvarchar(256)  |           |                       | Active Directory samAccountName attribute. Local user accounts do not have a samAccountName.                                                                                        |
| SamAccountType      | int            |           |                       | Active Directory samAccountType attribute.                                                                                                                                          |
| Created             | datetime       |           |                       | Date and time this user account was created.                                                                                                                                        |
| Modified            | datetime       |           |                       | Date and time this user account was last modified.                                                                                                                                  |
| Enabled             | bit            |           |                       | Based on Win32_UserAccount.Disabled, or AccountDisabled flag of the Active Directory UserAccountControl property.                                                                   |
| PwdRequired         | bit            |           |                       | Based on Win32_UserAccount.PasswordRequired, or PASSWD_NOTREQD flag of the Active Directory UserAccountControl property.                                                            |
| PwdCanChange        | bit            |           |                       | Based on Win32_UserAccount.PasswordChangeable, or PASSWD_CANT_CHANGE flag of the Active Directory UserAccountControl property.                                                      |
| PwdExpires          | bit            |           |                       | Based on Win32_UserAccount.PasswordExpires, or DONT_EXPIRE_PASSWORD flag of the Active Directory UserAccountControl property.                                                       |
| NormalAccount       | bit            |           |                       | Based on NORMAL_ACCOUNT flag of the Active Directory UserAccountControl property.                                                                                                   |
| AdDistinguishedName | nvarchar(4000) |           |                       | Active Directory distinguishedName attribute of the user account.                                                                                                                   |
| AdLastLogon         | datetime       |           |                       | MAX(LastLogon, LastLogonTimestamp) attributes in Active Directory.                                                                                                                  |
| LogonCount          | int            |           |                       | Number of times the user successfully logged on to Active Directory.                                                                                                                |
| Id                  | int            |           |                       | Generated during import. Leave empty.                                                                                                                                               |