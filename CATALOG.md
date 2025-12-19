# PShell Module Catalog

Complete index of all PowerShell scripts and modules organized by category.

---

## Exchange Administration

### Calendar Management
| Script | Purpose | Location |
|--------|---------|----------|
| CalendarLogs.PS1 | Query calendar diagnostic logs | Exchange/Calendar/ |
| CalendarLogs-short.PS1 | Quick calendar log queries | Exchange/Calendar/ |
| CalendarLogsOGV.PS1 | Calendar logs with GridView output | Exchange/Calendar/ |
| Restore_CalendarItems.ps1 | Restore deleted calendar items | Exchange/Calendar/ |

### Mailbox Operations
| Script | Purpose | Location |
|--------|---------|----------|
| DELETE-Mailbox-but-KEEP-User | Remove mailbox, retain AD user | Exchange/Mailbox/ |
| Delete-RECOVERABLE-ITEMS | Clear recoverable items folder | Exchange/Recoverableitems/ |
| Restore-mailbox | Mailbox restoration scripts | Exchange/Mailbox/ |
| Remove-Holds | Remove litigation/retention holds | Exchange/Retention/ |

### Distribution Lists & Groups
| Script | Purpose | Location |
|--------|---------|----------|
| DL-Groups-Convert | Convert DL to M365 Group | Exchange/DL-Groups/ |
| GROUP management | Group creation and management | Exchange/DL-Groups/ |

### Mail Flow
| Script | Purpose | Location |
|--------|---------|----------|
| Connectors-Certificates | Manage mail flow connectors | Exchange/Connectors/ |
| IntraorgConnector | Internal org connector config | Exchange/IntraorgConnector/ |
| DKIM configuration | DKIM signing setup | Exchange/DKIM/ |
| Spamfilter policies | Anti-spam configuration | Exchange/Spamfilter/ |
| Phishfilter | Anti-phishing rules | Exchange/Quarantine/ |
| Trackinglog | Message tracking queries | Exchange/TrackingLog/ |

### Permissions
| Script | Purpose | Location |
|--------|---------|----------|
| Folderpermissions | Mailbox folder permissions | Exchange/Folderpermissions/ |
| Calendar permissions | Calendar sharing settings | Exchange/Calendar/ |
| GAL management | Global Address List config | Exchange/GAL/ |
| Addressbook | Address book policies | Exchange/Addressbook/ |

### Public Folders
| Script | Purpose | Location |
|--------|---------|----------|
| PublicFolder management | PF hierarchy and content | Exchange/PublicFolder/ |

### OWA & Client Access
| Script | Purpose | Location |
|--------|---------|----------|
| OWA-AutocompleteCache | Clear OWA autocomplete | Exchange/OWA/ |
| OWA-Localizefoldernames | Localize folder names | Exchange/OWA/ |
| OWA.Folderpermissions | OWA folder permissions | Exchange/OWA/ |

---

## Microsoft 365 Cloud Services

### Microsoft Graph
| Script | Purpose | Location |
|--------|---------|----------|
| GraphOffice365Module.psm1 | Graph API PowerShell module | M365/MSGraph/ |
| EWSOAuth.psm1 | EWS with OAuth authentication | M365/MSGraph/ |
| EWSOAuthTestSuite.ps1 | OAuth test suite | M365/MSGraph/ |
| intune.ps1 | Intune device management | M365/MSGraph/ |

### Teams
| Script | Purpose | Location |
|--------|---------|----------|
| Teams management | Teams and channel admin | M365/Teams/ |

### Security & Compliance
| Script | Purpose | Location |
|--------|---------|----------|
| SCC scripts | Security & Compliance Center | M365/SCC/ |
| AuditLogs | Unified audit log queries | M365/AuditLogs/ |
| InformationBarriers | IB policy configuration | M365/InformationBarriers/ |

### Authentication
| Script | Purpose | Location |
|--------|---------|----------|
| Oauth scripts | OAuth token management | M365/Oauth/ |

---

## Active Directory

### User Management
| Script | Purpose | Location |
|--------|---------|----------|
| CreateADUser.ps1 | Create AD users | AD/ |
| Benutzer.ps1 | User management (German) | AD/ |
| UserExport.ps1 | Export user data | AD/ |
| LockedOut_Users.ps1 | Find locked accounts | AD/ |

### Group Management
| Script | Purpose | Location |
|--------|---------|----------|
| AD_Groups.ps1 | AD group operations | AD/Groups/ |
| Bereinigung_Lizenzgruppen | License group cleanup | AD/Groups/ |

### Permissions & Cleanup
| Script | Purpose | Location |
|--------|---------|----------|
| AD_Remove_Proxys_of_domain.ps1 | Remove proxy addresses | AD/ |
| Mailbox_Permissions.ps1 | Mailbox permission report | AD/ |
| Calendar_Permissions.ps1 | Calendar permission report | AD/ |
| Folder_Permissions.ps1 | Folder permission report | AD/ |

### Cloud Integration
| Script | Purpose | Location |
|--------|---------|----------|
| Cloud_Mailbox_AuditLogs.ps1 | Cloud mailbox auditing | AD/ |
| Automapping_fix_cloud.ps1 | Fix Outlook automapping | AD/ |

### Migration Support
| Script | Purpose | Location |
|--------|---------|----------|
| Migration_Doings.ps1 | Migration preparation | AD/ |
| Mercoline_AD_Source_remove.ps1 | Source cleanup | AD/ |
| Forwarding_Report.ps1 | Forwarding rule audit | AD/ |

---

## Outlook Client

### Registry Configurations
| File | Purpose | Location |
|------|---------|----------|
| CLoud_ONLY-user.reg | Cloud Autodiscover config | Outlook/ |
| ONPREM_ONLY-USER.reg | On-prem Autodiscover config | Outlook/ |
| Outlook_Teams_AddIn.reg | Teams meeting add-in fix | Outlook/ |
| DelegateSentItemsStyle.reg | Delegate sent items setting | Outlook/ |

### Fix Scripts
| Script | Purpose | Location |
|--------|---------|----------|
| fix.ps1 | General Outlook fixes | Outlook/ |
| fix.smtp.ps1 | SMTP address fixes | Outlook/ |
| sip_fix.ps1 | SIP address corrections | Outlook/ |

### S/MIME
| File | Purpose | Location |
|------|---------|----------|
| Smime.docx/pdf | S/MIME setup guide | Outlook/SMime/ |
| mapi-smime-toolkit.txt | MAPI toolkit reference | Outlook/SMime/ |

---

## Migration Tools

### Hybrid Configuration
| Script | Purpose | Location |
|--------|---------|----------|
| HCW scripts | Hybrid wizard support | Migration/HCW/ |
| Migrationendpoints | Endpoint configuration | Migration/Endpoints/ |

### Migration Types
| Script | Purpose | Location |
|--------|---------|----------|
| IMAP migration | IMAP migration tools | Migration/IMAP/ |
| SMTP relay | SMTP configuration | Migration/SMTP/ |
| RemoteMailbox scripts | Remote mailbox setup | Exchange/RemoteMailbox/ |

---

## Utilities

### Connection Scripts
| Script | Purpose | Location |
|--------|---------|----------|
| CONNECT-Powershell-basic-extra.ps1 | Multi-service connection | Utilities/ |

### Access Control
| Script | Purpose | Location |
|--------|---------|----------|
| RBAC scripts | Role-based access control | Utilities/RBAC/ |

### Miscellaneous
| File | Purpose | Location |
|------|---------|----------|
| changeUPN.txt | UPN change reference | Utilities/ |
| remove automapping.docx/pdf | Automapping removal guide | Utilities/ |

---

## Reporting

### Statistics
| Script | Purpose | Location |
|--------|---------|----------|
| FolderStats | Folder size analysis | Reporting/FolderStats/ |

### Logs
| Script | Purpose | Location |
|--------|---------|----------|
| Log analysis scripts | Log parsing utilities | Reporting/Logs/ |

---

## Repository Information

**Original repositories consolidated:**
- jahube/PShell (main, 837 commits)
- jahube/MSGraph
- jahube/AD (93 commits)
- jahube/OLK (27 commits)
- jahube/O365Docs (129 commits)
- jahube/Calendar (26 commits)
- jahube/SMime
- jahube/Hybrid-Delegation
- jahube/RemoteMailbox
- jahube/HCW
- jahube/SCC
- jahube/Logs
- jahube/AuditLogs
- jahube/ProfilePictureSync
- jahube/Folderpermissions
- jahube/DKIM
- jahube/OutSpam
- jahube/SMTP
- jahube/EWS
- jahube/Permissions
- jahube/Mobile

**Total original commits:** 1000+
**Languages:** PowerShell (primary), HTML, PHP
**Focus:** Exchange Server, Exchange Online, Microsoft 365, Active Directory
