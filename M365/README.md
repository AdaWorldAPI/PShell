# Microsoft 365 Administration Scripts

PowerShell scripts for Microsoft 365 cloud services administration.

## Modules

### MSGraph
Microsoft Graph API scripts and PowerShell modules.

```powershell
# Connect to Graph
Connect-MgGraph -Scopes "User.Read.All", "Group.ReadWrite.All"

# Get all users
Get-MgUser -All
```

**Included modules:**
- `GraphOffice365Module.psm1` - Office 365 operations via Graph
- `EWSOAuth.psm1` - EWS OAuth authentication
- `intune.ps1` - Intune device management

### Teams
Microsoft Teams administration and configuration.

```powershell
# Get Teams
Get-Team

# Get Team members
Get-TeamUser -GroupId <TeamId>
```

### Bookings
Microsoft Bookings service management.

### SCC (Security & Compliance Center)
Security and Compliance Center operations.

```powershell
# Connect to SCC
Connect-IPPSSession -UserPrincipalName admin@domain.com

# Content search
New-ComplianceSearch -Name "Search Name" -ExchangeLocation All
```

### Oauth
OAuth token management and authentication flows.

### AuditLogs
Unified audit log queries and exports.

```powershell
# Search audit log
Search-UnifiedAuditLog -StartDate (Get-Date).AddDays(-7) -EndDate (Get-Date) -Operations "FileAccessed"
```

### InformationBarriers
Information barrier policy configuration.

## Prerequisites

```powershell
# Install Microsoft Graph SDK
Install-Module Microsoft.Graph -Force

# Install Teams module
Install-Module MicrosoftTeams -Force

# Install Exchange Online Management (includes SCC)
Install-Module ExchangeOnlineManagement -Force
```
