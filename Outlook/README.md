# Outlook Client Administration Scripts

PowerShell scripts and registry configurations for Outlook client management.

## Modules

### OWA (Outlook Web Access)
OWA configuration, folder localization, and autocomplete cache management.

### Signature
Email signature deployment and management.

### SMime
S/MIME certificate configuration for encrypted email.

**Documentation:**
- `Smime.docx` / `Smime.pdf` - S/MIME setup guide
- `mapi-smime-toolkit.txt` - MAPI toolkit reference

### Mobile
Mobile device management and policies.

## Registry Configurations

### Cloud-Only User Setup
```registry
; For cloud-only users
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\AutoDiscover]
"ExcludeScpLookup"=dword:00000001
"ExcludeHttpsRootDomain"=dword:00000001
```

### On-Premises User Setup
```registry
; For on-premises users
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\AutoDiscover]
"ExcludeExplicitO365Endpoint"=dword:00000001
```

### Teams Add-in Fix
```registry
; Enable Teams Meeting add-in
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect]
"LoadBehavior"=dword:00000003
```

### Delegate Sent Items
```registry
; Store sent items in delegate's folder
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Preferences]
"DelegateSentItemsStyle"=dword:00000001
```

## Included Files

| File | Description |
|------|-------------|
| `CLoud_ONLY-user.reg` | Registry for cloud-only Autodiscover |
| `ONPREM_ONLY-USER.reg` | Registry for on-premises Autodiscover |
| `Outlook_Teams_AddIn.reg` | Teams meeting add-in fix |
| `DelegateSentItemsStyle.reg` | Delegate sent items behavior |
| `fix.ps1` | General Outlook fixes |
| `fix.smtp.ps1` | SMTP address fixes |
| `sip_fix.ps1` | SIP address corrections |

## Common Fixes

### Reset Outlook Profile via PowerShell
```powershell
# Remove cached credentials
cmdkey /delete:MicrosoftOffice16_Data:SSPI

# Clear Outlook autocomplete cache
Remove-Item "$env:LOCALAPPDATA\Microsoft\Outlook\RoamCache\*" -Force
```

### Recreate OST File
```powershell
# Close Outlook first
Get-Process outlook -ErrorAction SilentlyContinue | Stop-Process -Force
Start-Sleep -Seconds 2

# Remove OST (will be recreated)
Get-ChildItem "$env:LOCALAPPDATA\Microsoft\Outlook\*.ost" | Remove-Item -Force
```
