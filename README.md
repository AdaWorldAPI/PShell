# PShell - PowerShell Administration Toolkit

A comprehensive collection of PowerShell scripts and modules for Microsoft 365, Exchange Server, Active Directory, and Azure administration.

## Overview

This repository consolidates years of practical PowerShell scripts used for enterprise IT administration. Originally developed for managing hybrid Exchange environments, Microsoft 365 tenants, and Active Directory infrastructures.

## Module Categories

### Exchange & Mail Flow
| Module | Description |
|--------|-------------|
| [Calendar](./Exchange/Calendar/) | Calendar management, logging, and restoration scripts |
| [Connectors](./Exchange/Connectors/) | Mail connectors and certificate management |
| [DKIM](./Exchange/DKIM/) | DKIM/DMARC configuration scripts |
| [DL-Groups](./Exchange/DL-Groups/) | Distribution list and group management |
| [EWS](./Exchange/EWS/) | Exchange Web Services scripts |
| [Hybrid-Delegation](./Exchange/Hybrid-Delegation/) | Hybrid delegate access configuration |
| [IntraorgConnector](./Exchange/IntraorgConnector/) | Internal organization connector setup |
| [Mailbox](./Exchange/Mailbox/) | Mailbox operations (delete, restore, recovery) |
| [OOO](./Exchange/OOO/) | Out of Office management |
| [PublicFolder](./Exchange/PublicFolder/) | Public folder administration |
| [Quarantine](./Exchange/Quarantine/) | Quarantine and spam management |
| [RemoteMailbox](./Exchange/RemoteMailbox/) | Remote and shared mailbox management |
| [Retention](./Exchange/Retention/) | Retention policies and holds |
| [Rooms](./Exchange/Rooms/) | Room and resource mailbox management |
| [Spamfilter](./Exchange/Spamfilter/) | Spam and phishing filter configuration |
| [TrackingLog](./Exchange/TrackingLog/) | Message tracking and logs |

### Microsoft 365 & Cloud Services
| Module | Description |
|--------|-------------|
| [MSGraph](./M365/MSGraph/) | Microsoft Graph API scripts and modules |
| [Teams](./M365/Teams/) | Microsoft Teams administration |
| [Bookings](./M365/Bookings/) | Microsoft Bookings management |
| [SCC](./M365/SCC/) | Security & Compliance Center scripts |
| [Oauth](./M365/Oauth/) | OAuth authentication and tokens |
| [AuditLogs](./M365/AuditLogs/) | Audit log queries and exports |
| [InformationBarriers](./M365/InformationBarriers/) | Information barrier policies |

### Active Directory
| Module | Description |
|--------|-------------|
| [AD-Management](./AD/) | Active Directory user and group management |
| [AD-Groups](./AD/Groups/) | AD group operations |
| [USERimport](./AD/USERimport/) | User import and license assignment |
| [Permissions](./AD/Permissions/) | AD and folder permission management |

### Outlook & Client
| Module | Description |
|--------|-------------|
| [OLK](./Outlook/) | Outlook client configuration and registry fixes |
| [OWA](./Outlook/OWA/) | Outlook Web Access configuration |
| [Signature](./Outlook/Signature/) | Email signature management |
| [SMime](./Outlook/SMime/) | S/MIME encryption configuration |
| [Mobile](./Outlook/Mobile/) | Mobile device management |

### Migration & Hybrid
| Module | Description |
|--------|-------------|
| [HCW](./Migration/HCW/) | Hybrid Configuration Wizard scripts |
| [Migrationendpoints](./Migration/Endpoints/) | Migration endpoint configuration |
| [SMTP](./Migration/SMTP/) | SMTP relay and migration |
| [IMAP-Migration](./Migration/IMAP/) | IMAP migration tools |

### Reporting & Analysis
| Module | Description |
|--------|-------------|
| [FolderStats](./Reporting/FolderStats/) | Folder statistics and analysis |
| [Logs](./Reporting/Logs/) | Log parsing and analysis |
| [Screenshots](./Reporting/Screenshots/) | Documentation screenshots |

### Utilities
| Module | Description |
|--------|-------------|
| [CONNECT](./Utilities/) | Connection scripts for various services |
| [RBAC](./Utilities/RBAC/) | Role-based access control |
| [Misc](./Utilities/Misc/) | Miscellaneous utilities |

## Quick Start

### Connecting to Exchange Online

```powershell
# Basic connection
Connect-ExchangeOnline -UserPrincipalName admin@domain.com

# With MFA
Connect-ExchangeOnline -UserPrincipalName admin@domain.com -ShowBanner:$false
```

### Connecting to Microsoft Graph

```powershell
# Using the MSGraph module
Import-Module ./M365/MSGraph/GraphOffice365Module.psm1
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"
```

## Repository Structure

```
PShell/
├── AD/                    # Active Directory scripts
├── Exchange/              # Exchange Server & Online scripts
│   ├── Calendar/
│   ├── Connectors/
│   ├── DKIM/
│   ├── DL-Groups/
│   ├── EWS/
│   ├── Hybrid-Delegation/
│   ├── Mailbox/
│   ├── OOO/
│   ├── PublicFolder/
│   ├── Quarantine/
│   ├── RemoteMailbox/
│   ├── Retention/
│   ├── Rooms/
│   ├── Spamfilter/
│   └── TrackingLog/
├── M365/                  # Microsoft 365 cloud scripts
│   ├── MSGraph/
│   ├── Teams/
│   ├── Bookings/
│   ├── SCC/
│   ├── Oauth/
│   ├── AuditLogs/
│   └── InformationBarriers/
├── Migration/             # Migration tools
│   ├── HCW/
│   ├── Endpoints/
│   ├── SMTP/
│   └── IMAP/
├── Outlook/               # Outlook client scripts
│   ├── OWA/
│   ├── Signature/
│   ├── SMime/
│   └── Mobile/
├── Reporting/             # Reporting and analysis
│   ├── FolderStats/
│   ├── Logs/
│   └── Screenshots/
├── Utilities/             # General utilities
│   ├── RBAC/
│   └── Misc/
└── Docs/                  # Documentation
```

## Requirements

- PowerShell 5.1 or PowerShell 7+
- Exchange Online Management Module
- Microsoft Graph PowerShell SDK
- Azure AD PowerShell Module (legacy) or Microsoft Graph
- Appropriate admin permissions for your tenant/environment

## Installation

```powershell
# Install required modules
Install-Module ExchangeOnlineManagement -Force
Install-Module Microsoft.Graph -Force
Install-Module AzureAD -Force  # Legacy, use Microsoft.Graph where possible
```

## Documentation

Additional documentation and guides are available in the [Docs](./Docs/) folder, including:
- Connection guides
- Troubleshooting tips
- Best practices
- Migration checklists

## Original Repositories

This is a consolidation of scripts from multiple specialized repositories:
- PShell (main collection)
- MSGraph
- AD
- OLK
- O365Docs
- Calendar
- SMime
- And more...

## Contributing

Feel free to submit issues and pull requests for improvements.

## License

These scripts are provided as-is for educational and administrative purposes.

---

*Last updated: December 2025*
