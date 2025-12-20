# Reporting & Analysis Scripts

PowerShell scripts for mailbox statistics, folder analysis, and audit reporting.

## Modules

### FolderStats
Mailbox and folder size statistics.

```powershell
# Get mailbox folder statistics
Get-MailboxFolderStatistics -Identity user@domain.com |
    Select-Object Name, FolderPath, ItemsInFolder, FolderSize

# Get large folders
Get-MailboxFolderStatistics -Identity user@domain.com |
    Where-Object { $_.FolderSize -gt 1GB } |
    Sort-Object FolderSize -Descending
```

### Logs
Log parsing, analysis, and export utilities.

```powershell
# Export admin audit log
Search-AdminAuditLog -StartDate (Get-Date).AddDays(-30) -EndDate (Get-Date) |
    Export-Csv "admin-audit.csv" -NoTypeInformation

# Get sign-in logs via Graph
Get-MgAuditLogSignIn -Filter "createdDateTime ge 2024-01-01" -All
```

### Screenshots
Documentation screenshots and visual guides.

## Common Reports

### Mailbox Size Report
```powershell
Get-Mailbox -ResultSize Unlimited |
    Get-MailboxStatistics |
    Select-Object DisplayName, TotalItemSize, ItemCount |
    Sort-Object TotalItemSize -Descending |
    Export-Csv "mailbox-sizes.csv" -NoTypeInformation
```

### Forwarding Rules Report
```powershell
Get-Mailbox -ResultSize Unlimited |
    Where-Object { $_.ForwardingSmtpAddress -ne $null -or $_.ForwardingAddress -ne $null } |
    Select-Object DisplayName, PrimarySmtpAddress, ForwardingSmtpAddress, ForwardingAddress |
    Export-Csv "forwarding-rules.csv" -NoTypeInformation
```

### Inbox Rules Report
```powershell
$mailboxes = Get-Mailbox -ResultSize Unlimited
foreach ($mbx in $mailboxes) {
    Get-InboxRule -Mailbox $mbx.PrimarySmtpAddress |
        Where-Object { $_.ForwardTo -ne $null -or $_.RedirectTo -ne $null } |
        Select-Object @{n='Mailbox';e={$mbx.PrimarySmtpAddress}}, Name, ForwardTo, RedirectTo
}
```

### License Report
```powershell
Get-MgUser -All -Property DisplayName, UserPrincipalName, AssignedLicenses |
    Select-Object DisplayName, UserPrincipalName, @{n='Licenses';e={$_.AssignedLicenses.SkuId -join ','}} |
    Export-Csv "license-report.csv" -NoTypeInformation
```

### Stale Accounts Report
```powershell
# Accounts not signed in for 90 days
$staleDate = (Get-Date).AddDays(-90)
Get-MgUser -All -Property DisplayName, UserPrincipalName, SignInActivity |
    Where-Object { $_.SignInActivity.LastSignInDateTime -lt $staleDate } |
    Select-Object DisplayName, UserPrincipalName, @{n='LastSignIn';e={$_.SignInActivity.LastSignInDateTime}}
```
