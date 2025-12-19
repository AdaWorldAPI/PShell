# Exchange Administration Scripts

PowerShell scripts for Microsoft Exchange Server and Exchange Online administration.

## Modules

### Calendar
Calendar management, logging, permission handling, and item restoration.

```powershell
# Get calendar logs
Get-CalendarDiagnosticLog -Identity user@domain.com -Subject "Meeting Title"

# Get calendar permissions
Get-MailboxFolderPermission -Identity user@domain.com:\Calendar
```

### Connectors
Mail flow connectors and certificate management for hybrid environments.

### DKIM
DomainKeys Identified Mail (DKIM) configuration scripts.

```powershell
# Enable DKIM for a domain
New-DkimSigningConfig -DomainName "domain.com" -Enabled $true
```

### DL-Groups
Distribution list and mail-enabled group management, including conversions.

```powershell
# Convert DL to Microsoft 365 Group
Upgrade-DistributionGroup -DlIdentities "sales@domain.com"
```

### EWS
Exchange Web Services scripts for advanced mailbox operations.

### Hybrid-Delegation
Delegate access configuration in hybrid Exchange environments.

### Mailbox
Core mailbox operations including creation, deletion, recovery, and maintenance.

```powershell
# Restore deleted mailbox
Undo-SoftDeletedMailbox -SoftDeletedObject user@domain.com

# Get mailbox statistics
Get-MailboxStatistics -Identity user@domain.com
```

### OOO (Out of Office)
Automatic reply and out-of-office management.

```powershell
# Set out of office
Set-MailboxAutoReplyConfiguration -Identity user@domain.com -AutoReplyState Enabled
```

### PublicFolder
Public folder hierarchy and content management.

### Quarantine
Message quarantine and spam review operations.

### RemoteMailbox
Remote and shared mailbox management for hybrid environments.

### Retention
Retention policies, tags, and legal hold management.

```powershell
# Apply retention policy
Set-Mailbox -Identity user@domain.com -RetentionPolicy "Corporate Policy"
```

### Rooms
Room and resource mailbox configuration.

### Spamfilter
Anti-spam and phishing filter policies.

### TrackingLog
Message tracking and transport log analysis.

```powershell
# Track message
Get-MessageTrackingLog -Sender user@domain.com -Start (Get-Date).AddDays(-7)
```

## Common Connection

```powershell
# Connect to Exchange Online
Connect-ExchangeOnline -UserPrincipalName admin@domain.com

# Connect to on-premises Exchange
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://exchserver/PowerShell/
Import-PSSession $Session
```
