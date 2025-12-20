# Migration Tools

PowerShell scripts for Exchange migrations and hybrid configurations.

## Modules

### HCW (Hybrid Configuration Wizard)
Hybrid Configuration Wizard troubleshooting and supplementary scripts.

### Endpoints
Migration endpoint configuration and management.

```powershell
# Create migration endpoint
New-MigrationEndpoint -ExchangeRemoteMove -Name "Hybrid Endpoint" -RemoteServer "mail.domain.com"

# Get migration endpoints
Get-MigrationEndpoint
```

### SMTP
SMTP relay configuration and migration.

### IMAP
IMAP migration tools and batch operations.

```powershell
# Create IMAP migration endpoint
New-MigrationEndpoint -IMAP -Name "IMAP Migration" -RemoteServer "imap.source.com" -Port 993 -Security SSL

# Create migration batch
New-MigrationBatch -Name "IMAP Batch 1" -SourceEndpoint "IMAP Migration" -CSVData ([System.IO.File]::ReadAllBytes("users.csv"))
```

## Migration Types

### Cutover Migration
For small organizations (< 150 mailboxes):

```powershell
# Create cutover batch
New-MigrationBatch -Name "Cutover" -SourceEndpoint "Cutover Endpoint" -AutoStart
```

### Staged Migration
For larger on-premises Exchange organizations:

```powershell
# Stage mailboxes in batches
New-MigrationBatch -Name "Batch1" -SourceEndpoint "Staged Endpoint" -CSVData $csvBytes
```

### Hybrid Migration
For ongoing coexistence:

```powershell
# Move mailbox to Exchange Online
New-MoveRequest -Identity user@domain.com -Remote -RemoteHostName "mail.domain.com" -TargetDeliveryDomain "tenant.mail.onmicrosoft.com"
```

## Pre-Migration Checklist

- [ ] DNS records configured (MX, Autodiscover, SPF, DKIM)
- [ ] Firewall ports open (443, 25)
- [ ] Certificates valid
- [ ] Migration endpoint tested
- [ ] Source mailboxes prepared
- [ ] User communication sent

## Common Issues

### Migration Stalled
```powershell
# Get migration statistics
Get-MigrationUser -Identity user@domain.com | Get-MigrationUserStatistics

# Resume stalled migration
Resume-MigrationBatch -Identity "BatchName"
```

### Endpoint Connectivity
```powershell
# Test migration endpoint
Test-MigrationServerAvailability -ExchangeRemoteMove -RemoteServer "mail.domain.com" -Credentials (Get-Credential)
```
