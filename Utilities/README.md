# Utilities

General-purpose PowerShell utilities and connection scripts.

## Connection Scripts

### Connect to Multiple Services

```powershell
# Exchange Online
Connect-ExchangeOnline -UserPrincipalName admin@domain.com

# Security & Compliance
Connect-IPPSSession -UserPrincipalName admin@domain.com

# Microsoft Graph
Connect-MgGraph -Scopes "User.ReadWrite.All"

# Teams
Connect-MicrosoftTeams

# Azure AD (Legacy)
Connect-AzureAD

# SharePoint Online
Connect-SPOService -Url https://tenant-admin.sharepoint.com
```

### Disconnect All Sessions

```powershell
Disconnect-ExchangeOnline -Confirm:$false
Disconnect-MgGraph
Disconnect-MicrosoftTeams
Disconnect-AzureAD
Disconnect-SPOService
```

## RBAC (Role-Based Access Control)

Role assignment and permission management.

```powershell
# Get role assignments
Get-ManagementRoleAssignment -RoleAssignee admin@domain.com

# Add role group member
Add-RoleGroupMember -Identity "Organization Management" -Member admin@domain.com
```

## Misc Utilities

### UPN Change
```powershell
# Change user principal name
Set-MsolUserPrincipalName -UserPrincipalName old@domain.com -NewUserPrincipalName new@domain.com
```

### Remove Automapping
```powershell
# Remove automapping for shared mailbox
Add-MailboxPermission -Identity shared@domain.com -User user@domain.com -AccessRights FullAccess -AutoMapping $false

# Remove existing and re-add without automapping
Remove-MailboxPermission -Identity shared@domain.com -User user@domain.com -AccessRights FullAccess -Confirm:$false
Add-MailboxPermission -Identity shared@domain.com -User user@domain.com -AccessRights FullAccess -AutoMapping $false
```

### Bulk Operations Template
```powershell
# Import users from CSV and process
$users = Import-Csv "users.csv"
foreach ($user in $users) {
    # Your operation here
    Write-Host "Processing: $($user.UserPrincipalName)"
}
```

## Included Files

| File | Description |
|------|-------------|
| `CONNECT-Powershell-basic-extra.ps1` | Multi-service connection script |
| `changeUPN.txt` | UPN change reference |
| `remove automapping.docx/pdf` | Automapping removal guide |
