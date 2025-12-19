# Active Directory Administration Scripts

PowerShell scripts for Active Directory management and operations.

## Modules

### Groups
AD group creation, modification, and membership management.

```powershell
# Get group members
Get-ADGroupMember -Identity "GroupName"

# Add user to group
Add-ADGroupMember -Identity "GroupName" -Members "username"
```

### User Management
User creation, modification, and deprovisioning.

```powershell
# Create new user
New-ADUser -Name "John Doe" -SamAccountName "jdoe" -UserPrincipalName "jdoe@domain.com"

# Get locked out users
Search-ADAccount -LockedOut
```

### Permissions
AD and file system permission management.

### License Groups
Azure AD/Entra ID license group management and cleanup.

## Key Scripts

| Script | Description |
|--------|-------------|
| `AD_Groups.ps1` | AD group operations |
| `AD_Remove_Proxys_of_domain.ps1` | Remove proxy addresses for specific domain |
| `CreateADUser.ps1` | User creation with standard attributes |
| `Mailbox_Permissions.ps1` | Mailbox permission reporting |
| `Calendar_Permissions.ps1` | Calendar permission management |
| `Folder_Permissions.ps1` | Shared folder permissions |
| `Cloud_Mailbox_AuditLogs.ps1` | Mailbox audit log queries |
| `Automapping_fix_cloud.ps1` | Fix Outlook automapping issues |
| `LockedOut_Users.ps1` | Find and manage locked accounts |
| `Forwarding_Report.ps1` | Email forwarding audit |
| `tracking.ps1` | Message tracking utilities |

## Common Commands

```powershell
# Import AD module
Import-Module ActiveDirectory

# Find users by attribute
Get-ADUser -Filter {Department -eq "IT"} -Properties *

# Export users to CSV
Get-ADUser -Filter * -Properties * | Export-Csv -Path "users.csv" -NoTypeInformation

# Bulk password reset
Get-ADUser -Filter {Department -eq "Contractors"} | Set-ADAccountPassword -Reset -NewPassword (ConvertTo-SecureString "TempPass123!" -AsPlainText -Force)
```

## Hybrid Environment

For hybrid environments, sync changes with Azure AD Connect:

```powershell
# Force delta sync
Start-ADSyncSyncCycle -PolicyType Delta
```
