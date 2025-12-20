# Documentation

Additional guides, troubleshooting tips, and best practices.

## Quick Reference

### Connection Cheat Sheet

| Service | Module | Command |
|---------|--------|---------|
| Exchange Online | ExchangeOnlineManagement | `Connect-ExchangeOnline` |
| Security & Compliance | ExchangeOnlineManagement | `Connect-IPPSSession` |
| Microsoft Graph | Microsoft.Graph | `Connect-MgGraph` |
| Azure AD | AzureAD | `Connect-AzureAD` |
| Teams | MicrosoftTeams | `Connect-MicrosoftTeams` |
| SharePoint | Microsoft.Online.SharePoint.PowerShell | `Connect-SPOService` |

### Required Permissions

| Task | Exchange Role | Graph Scope |
|------|--------------|-------------|
| Manage mailboxes | Mail Recipients | `User.ReadWrite.All` |
| Manage groups | Distribution Groups | `Group.ReadWrite.All` |
| View audit logs | View-Only Audit Logs | `AuditLog.Read.All` |
| eDiscovery | eDiscovery Manager | `eDiscovery.ReadWrite.All` |
| Compliance | Compliance Administrator | `Compliance.ReadWrite.All` |

## Troubleshooting

### Common Issues

**Cannot connect to Exchange Online:**
- Verify MFA is configured
- Check if BasicAuth is disabled (use Modern Auth)
- Update ExchangeOnlineManagement module

**Graph permission denied:**
- Verify app registration consent
- Check scope requirements
- Request admin consent if needed

**Hybrid mail flow issues:**
- Verify connector configuration
- Check certificate validity
- Test MX record resolution

### Useful Diagnostic Commands

```powershell
# Test Exchange connectivity
Test-OutlookConnectivity -ProbeIdentity OutlookRpc

# Check hybrid configuration
Get-HybridConfiguration

# Verify federation trust
Test-FederationTrust -UserIdentity admin@domain.com

# Check organization relationship
Get-OrganizationRelationship
```

## Best Practices

1. **Always use -WhatIf** before bulk operations
2. **Export before delete** - backup data before removing
3. **Use transactions** where possible
4. **Log all changes** for audit trail
5. **Test in lab** before production

## Additional Resources

- [Microsoft Learn - Exchange Online](https://learn.microsoft.com/exchange/exchange-online)
- [Microsoft Graph Documentation](https://learn.microsoft.com/graph/)
- [Exchange PowerShell Reference](https://learn.microsoft.com/powershell/exchange/)
