# Mastering Microsoft Teams Phone – Companion Repository

Scripts and code samples from the book **Mastering Microsoft Teams Phone** by Drago Petrovic, Microsoft MVP for Microsoft 365 and Microsoft Teams.

Every code listing in the book is available here as its own file. The file name starts with the listing number used in the book, so `Listing 13.10` in the book is `13.10-…` in this repository. The index below lists every script with its chapter, section and the page in the print edition.

> **Disclaimer:** All scripts are provided as-is, without warranty of any kind. They are examples for learning and adaptation. Test every script in a non-production tenant before using it in production, review it against your own security standards, and follow your organization's change process.

## Contents

- [Getting started](#getting-started)
- [Conventions](#conventions)
- [Repository structure](#repository-structure)
- [Script index](#script-index)
- [Feedback and contributions](#feedback-and-contributions)
- [License](#license)

## Getting started

1. Clone the repository or download it as a ZIP file.
2. Install the prerequisites:
   - PowerShell 7.4 (recommended) or Windows PowerShell 5.1
   - The **MicrosoftTeams** PowerShell module: `Install-Module MicrosoftTeams -Scope CurrentUser`
   - The **Microsoft Graph PowerShell SDK** for the Graph listings: `Install-Module Microsoft.Graph -Scope CurrentUser`
   - For Azure Automation listings: the **Az** modules and an Automation account with a managed identity (Chapters 13 and 15)
3. Open the script you need, read the header and the related section in the book, and replace the placeholder values.
4. Save PowerShell scripts with the extension `.ps1` before running them. The files are stored as `.txt` so that they can be read and copied safely in any browser or editor.
5. Run scripts against a test tenant first. Scripts that change configuration should be run in dry-run mode where available (see Chapters 8, 13 and 15).

Required roles and permissions are described in the book: Teams administration roles in Chapters 13 and 19, Microsoft Graph permissions in Chapter 14 and Appendix B.

## Conventions

- **Variables** such as `$upn`, `$TenantId`, `$AppId`, `$Thumbprint` or `$ra` stand for values from your environment and are defined at the top of a listing or explained in the book.
- **Placeholders** in angle brackets, such as `<policy name>`, must be replaced before running a command.
- **Domains, phone numbers and names** (contoso.com, +41 44 123 45 67, anna.meier) are fictitious.
- **Header:** each PowerShell file starts with a comment block that names the listing, chapter, section and print page.
- **Shared functions:** some listings use helper functions from earlier listings, for example `Get-GraphAll` (Listing 14.2) or the shared module from Listing 13.9.
- **Encoding:** files are UTF-8; Listing 11.3 contains German text-to-speech prompts and is saved with a byte order mark so that Windows PowerShell 5.1 reads the umlauts correctly.

## Repository structure

```
mastering-teams-phone/
├── README.md          this file
├── LICENSE            MIT License
└── chapters/
    ├── 00-how-to-use/           Listing P.1
    ├── 01-architecture/         Listings 1.1–1.3
    ├── 02-licensing/            Listings 2.1–2.3
    ├── 03-pstn-connectivity/    Listing 3.1
    ├── 04-network/              Listings 4.1–4.2
    ├── 05-numbers/              Listings 5.1–5.3
    ├── 06-direct-routing/       Listings 6.1–6.8
    ├── 07-oc-calling-plans/     Listings 7.1–7.6
    ├── 08-users/                Listings 8.1–8.8
    ├── 09-emergency/            Listings 9.1–9.4
    ├── 10-calling-features/     Listings 10.1–10.8
    ├── 11-voice-apps/           Listings 11.1–11.3
    ├── 12-devices/              Listings 12.1–12.2
    ├── 13-powershell/           Listings 13.1–13.10
    ├── 14-graph/                Listings 14.1–14.9
    ├── 15-config-as-code/       Listings 15.1–15.8
    ├── 16-monitoring/           Listings 16.1–16.3
    ├── 17-troubleshooting/      Listing 17.1
    ├── 18-security/             Listings 18.1–18.5
    ├── 20-ai/                   Listings 20.1–20.2
    ├── 22-scenarios/            Listings 22.1–22.2
    └── appendix-a/              Listing A.1
```

## Script index

93 scripts and code samples. Page numbers refer to the print edition (7 × 10 in).

### How to Use This Book

Folder: [`chapters/00-how-to-use/`](chapters/00-how-to-use/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [P.1](chapters/00-how-to-use/P.01-Example-of-a-code-listing.txt) | Example of a code listing |  | xvi | PowerShell |

### Chapter 1 – Teams Phone Architecture

Folder: [`chapters/01-architecture/`](chapters/01-architecture/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [1.1](chapters/01-architecture/1.01-Inspecting-the-voice-configuration-of-a-single-user.txt) | Inspecting the voice configuration of a single user | 1.8 Where Configuration Lives: Users, Numbers and Policies | 19 | PowerShell |
| [1.2](chapters/01-architecture/1.02-Checking-a-phone-number-assignment.txt) | Checking a phone number assignment | 1.8 Where Configuration Lives: Users, Numbers and Policies | 19 | PowerShell |
| [1.3](chapters/01-architecture/1.03-Retrieving-a-call-record-with-sessions-and-segments.txt) | Retrieving a call record with sessions and segments | 1.9 The Management and Identity Plane | 20 | PowerShell |

### Chapter 2 – Licensing Demystified

Folder: [`chapters/02-licensing/`](chapters/02-licensing/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [2.1](chapters/02-licensing/2.01-Listing-the-license-SKUs-in-a-tenant.txt) | Listing the license SKUs in a tenant | 2.9 Assigning and Checking Licenses at Scale | 33 | PowerShell |
| [2.2](chapters/02-licensing/2.02-Finding-users-whose-licensing-and-voice-configuration-do-not-match.txt) | Finding users whose licensing and voice configuration do not match | 2.9 Assigning and Checking Licenses at Scale | 34 | PowerShell |
| [2.3](chapters/02-licensing/2.03-Listing-resource-accounts-with-their-licenses.txt) | Listing resource accounts with their licenses | 2.9 Assigning and Checking Licenses at Scale | 34 | PowerShell |

### Chapter 3 – PSTN Connectivity Options Compared

Folder: [`chapters/03-pstn-connectivity/`](chapters/03-pstn-connectivity/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [3.1](chapters/03-pstn-connectivity/3.01-Overview-of-number-types-and-Direct-Routing-gateways.txt) | Overview of number types and Direct Routing gateways | 3.9 Mixing Models in One Tenant | 47 | PowerShell |

### Chapter 4 – Network Readiness

Folder: [`chapters/04-network/`](chapters/04-network/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [4.1](chapters/04-network/4.01-Configuring-DSCP-marking-for-the-Teams-client-on-Windows.txt) | Configuring DSCP marking for the Teams client on Windows | 4.7 Quality of Service | 58 | PowerShell |
| [4.2](chapters/04-network/4.02-Creating-a-network-region-site-subnets-and-a-trusted-IP.txt) | Creating a network region, site, subnets and a trusted IP | 4.9 Network Topology in the Teams Admin Center | 60 | PowerShell |

### Chapter 5 – Number Planning and Migration

Folder: [`chapters/05-numbers/`](chapters/05-numbers/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [5.1](chapters/05-numbers/5.01-Creating-assigning-and-testing-a-tenant-dial-plan.txt) | Creating, assigning and testing a tenant dial plan | 5.5 Dial Plans and Normalization Rules | 67 | PowerShell |
| [5.2](chapters/05-numbers/5.02-A-caller-ID-policy-that-presents-the-number-of-a-resource-account.txt) | A caller ID policy that presents the number of a resource account | 5.6 Caller ID | 68 | PowerShell |
| [5.3](chapters/05-numbers/5.03-Assigning-numbers-and-policies-for-a-migration-wave.txt) | Assigning numbers and policies for a migration wave | 5.8 Migrating from a Legacy PBX | 71 | PowerShell |

### Chapter 6 – Direct Routing in Depth

Folder: [`chapters/06-direct-routing/`](chapters/06-direct-routing/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [6.1](chapters/06-direct-routing/6.01-Pairing-an-SBC-with-the-tenant.txt) | Pairing an SBC with the tenant | 6.2 Pairing the SBC with Teams | 78 | PowerShell |
| [6.2](chapters/06-direct-routing/6.02-Creating-PSTN-usages.txt) | Creating PSTN usages | 6.4 Configuring Voice Routing | 81 | PowerShell |
| [6.3](chapters/06-direct-routing/6.03-Creating-voice-routes.txt) | Creating voice routes | 6.4 Configuring Voice Routing | 81 | PowerShell |
| [6.4](chapters/06-direct-routing/6.04-Creating-voice-routing-policies.txt) | Creating voice routing policies | 6.4 Configuring Voice Routing | 81 | PowerShell |
| [6.5](chapters/06-direct-routing/6.05-Assigning-a-voice-routing-policy-to-a-user-and-to-a-group.txt) | Assigning a voice routing policy to a user and to a group | 6.4 Configuring Voice Routing | 81 | PowerShell |
| [6.6](chapters/06-direct-routing/6.06-Translation-rules-for-a-carrier-that-uses-national-format.txt) | Translation rules for a carrier that uses national format | 6.5 Number Translation Rules | 83 | PowerShell |
| [6.7](chapters/06-direct-routing/6.07-Enabling-media-bypass-on-a-gateway.txt) | Enabling media bypass on a gateway | 6.7 Media Bypass | 84 | PowerShell |
| [6.8](chapters/06-direct-routing/6.08-Direct-Routing-calls-of-the-last-day-grouped-by-final-SIP-code.txt) | Direct Routing calls of the last day, grouped by final SIP code | 6.10 Monitoring Direct Routing | 86 | PowerShell |

### Chapter 7 – Setting up Operator Connect and Calling Plans

Folder: [`chapters/07-oc-calling-plans/`](chapters/07-oc-calling-plans/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [7.1](chapters/07-oc-calling-plans/7.01-Assigning-a-Calling-Plan-number-with-an-emergency-location.txt) | Assigning a Calling Plan number with an emergency location | 7.2 Calling Plans | 92 | PowerShell |
| [7.2](chapters/07-oc-calling-plans/7.02-Listing-numbers-with-their-type-capability-and-assignment.txt) | Listing numbers with their type, capability and assignment | 7.3 Number Types and Capacity | 93 | PowerShell |
| [7.3](chapters/07-oc-calling-plans/7.03-Moving-a-user-from-Direct-Routing-to-Operator-Connect.txt) | Moving a user from Direct Routing to Operator Connect | 7.4 Moving Numbers Between Models | 94 | PowerShell |
| [7.4](chapters/07-oc-calling-plans/7.04-Sending-only-a-legacy-PBX-number-range-to-Direct-Routing.txt) | Sending only a legacy PBX number range to Direct Routing | 7.6 Calling Plans and Direct Routing in the Same Tenant | 95 | PowerShell |
| [7.5](chapters/07-oc-calling-plans/7.05-Updating-the-emergency-location-of-Calling-Plan-numbers.txt) | Updating the emergency location of Calling Plan numbers | 7.7 Changing Emergency Addresses and Releasing Numbers | 95 | PowerShell |
| [7.6](chapters/07-oc-calling-plans/7.06-Calling-Plan-calls-of-the-last-week-by-call-type.txt) | Calling Plan calls of the last week by call type | 7.8 Monitoring Usage and Costs | 96 | PowerShell |

### Chapter 8 – Enabling Users for Voice

Folder: [`chapters/08-users/`](chapters/08-users/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [8.1](chapters/08-users/8.01-Assigning-numbers-of-different-types.txt) | Assigning numbers of different types | 8.3 Assigning Phone Numbers | 100 | PowerShell |
| [8.2](chapters/08-users/8.02-Group-policy-assignment-and-checking-the-source-of-an-effective-policy.txt) | Group policy assignment and checking the source of an effective policy | 8.5 Policy Precedence and Assignment Methods | 102 | PowerShell |
| [8.3](chapters/08-users/8.03-Assigning-a-calling-policy-to-a-migration-wave-in-one-batch.txt) | Assigning a calling policy to a migration wave in one batch | 8.5 Policy Precedence and Assignment Methods | 103 | PowerShell |
| [8.4](chapters/08-users/8.04-Bulk-assignment-with-validation-and-dry-run.txt) | Bulk assignment with validation and dry run | 8.7 Bulk Assignment with Validation | 105 | PowerShell |
| [8.5](chapters/08-users/8.05-Checking-number-and-effective-policies-of-a-user.txt) | Checking number and effective policies of a user | 8.8 Verifying a User | 106 | PowerShell |
| [8.6](chapters/08-users/8.06-Enabling-a-user-for-Shared-Calling.txt) | Enabling a user for Shared Calling | 8.10 Enabling Shared Calling Users | 107 | PowerShell |
| [8.7](chapters/08-users/8.07-Exporting-voice-users-and-finding-disabled-accounts-with-numbers.txt) | Exporting voice users and finding disabled accounts with numbers | 8.11 Reporting and Reconciliation | 107 | PowerShell |
| [8.8](chapters/08-users/8.08-Comparing-the-number-plan-with-actual-assignments.txt) | Comparing the number plan with actual assignments | 8.11 Reporting and Reconciliation | 108 | PowerShell |

### Chapter 9 – Emergency Calling

Folder: [`chapters/09-emergency/`](chapters/09-emergency/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [9.1](chapters/09-emergency/9.01-Working-with-emergency-addresses-and-places-in-PowerShell.txt) | Working with emergency addresses and places in PowerShell | 9.3 Emergency Addresses and Places | 112 | PowerShell |
| [9.2](chapters/09-emergency/9.02-Adding-network-identifiers-to-the-LIS.txt) | Adding network identifiers to the LIS | 9.4 Dynamic Emergency Calling | 114 | PowerShell |
| [9.3](chapters/09-emergency/9.03-Emergency-calling-policy-for-security-desk-notification.txt) | Emergency calling policy for security desk notification | 9.5 Emergency Policies | 115 | PowerShell |
| [9.4](chapters/09-emergency/9.04-Emergency-call-routing-policy-for-Direct-Routing-users-in-Zurich.txt) | Emergency call routing policy for Direct Routing users in Zurich | 9.5 Emergency Policies | 116 | PowerShell |

### Chapter 10 – Calling Features

Folder: [`chapters/10-calling-features/`](chapters/10-calling-features/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [10.1](chapters/10-calling-features/10.01-A-standard-calling-policy.txt) | A standard calling policy | 10.1 Calling Policies | 120 | PowerShell |
| [10.2](chapters/10-calling-features/10.02-Configuring-forwarding-and-unanswered-call-handling-for-users.txt) | Configuring forwarding and unanswered call handling for users | 10.2 Forwarding, Simultaneous Ring and Unanswered Calls | 121 | PowerShell |
| [10.3](chapters/10-calling-features/10.03-User-voicemail-settings.txt) | User voicemail settings | 10.3 Voicemail | 122 | PowerShell |
| [10.4](chapters/10-calling-features/10.04-Adding-a-delegate.txt) | Adding a delegate | 10.4 Delegation and Shared Line Appearance | 123 | PowerShell |
| [10.5](chapters/10-calling-features/10.05-Assigning-a-private-line.txt) | Assigning a private line | 10.5 Private Line | 123 | PowerShell |
| [10.6](chapters/10-calling-features/10.06-A-call-park-policy-for-the-warehouse-team.txt) | A call park policy for the warehouse team | 10.7 Call Park | 124 | PowerShell |
| [10.7](chapters/10-calling-features/10.07-Custom-music-on-hold.txt) | Custom music on hold | 10.9 Music on Hold | 125 | PowerShell |
| [10.8](chapters/10-calling-features/10.08-A-compact-view-of-a-user-s-call-handling.txt) | A compact view of a user's call handling | 10.12 Supporting Users | 126 | PowerShell |

### Chapter 11 – Voice Applications

Folder: [`chapters/11-voice-apps/`](chapters/11-voice-apps/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [11.1](chapters/11-voice-apps/11.01-Creating-and-licensing-a-resource-account.txt) | Creating and licensing a resource account | 11.2 Resource Accounts | 130 | PowerShell |
| [11.2](chapters/11-voice-apps/11.02-Creating-a-call-queue-and-associating-its-resource-account.txt) | Creating a call queue and associating its resource account | 11.7 Building Voice Applications with PowerShell | 134 | PowerShell |
| [11.3](chapters/11-voice-apps/11.03-Creating-an-auto-attendant-with-a-menu-that-transfers-to-the-queue.txt) | Creating an auto attendant with a menu that transfers to the queue | 11.7 Building Voice Applications with PowerShell | 134 | PowerShell |

### Chapter 12 – Devices

Folder: [`chapters/12-devices/`](chapters/12-devices/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [12.1](chapters/12-devices/12.01-An-IP-phone-policy-for-hot-desking-phones.txt) | An IP phone policy for hot-desking phones | 12.2 Teams Phones | 139 | PowerShell |
| [12.2](chapters/12-devices/12.02-Allowing-SIP-devices-in-a-calling-policy.txt) | Allowing SIP devices in a calling policy | 12.5 SIP Gateway | 141 | PowerShell |

### Chapter 13 – Teams PowerShell for Voice Administrators

Folder: [`chapters/13-powershell/`](chapters/13-powershell/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [13.1](chapters/13-powershell/13.01-Installing-updating-and-checking-the-MicrosoftTeams-module.txt) | Installing, updating and checking the MicrosoftTeams module | 13.2 Installing and Updating the Module | 150 | PowerShell |
| [13.2](chapters/13-powershell/13.02-Discovering-cmdlets-in-the-module.txt) | Discovering cmdlets in the module | 13.3 How the Module Works | 151 | PowerShell |
| [13.3](chapters/13-powershell/13.03-Interactive-and-device-code-sign-in.txt) | Interactive and device code sign-in | 13.4 Connecting | 152 | PowerShell |
| [13.4](chapters/13-powershell/13.04-Creating-a-certificate-and-connecting-as-an-application.txt) | Creating a certificate and connecting as an application | 13.4 Connecting | 153 | PowerShell |
| [13.5](chapters/13-powershell/13.05-Preparing-a-managed-identity-and-connecting-from-a-runbook.txt) | Preparing a managed identity and connecting from a runbook | 13.4 Connecting | 154 | PowerShell |
| [13.6](chapters/13-powershell/13.06-Server-side-filtering-with-Get-CsOnlineUser.txt) | Server-side filtering with Get-CsOnlineUser | 13.6 Working Efficiently in Large Tenants | 155 | PowerShell |
| [13.7](chapters/13-powershell/13.07-Paging-through-all-phone-number-assignments.txt) | Paging through all phone number assignments | 13.6 Working Efficiently in Large Tenants | 156 | PowerShell |
| [13.8](chapters/13-powershell/13.08-Resolving-number-owners-with-a-lookup-table.txt) | Resolving number owners with a lookup table | 13.6 Working Efficiently in Large Tenants | 156 | PowerShell |
| [13.9](chapters/13-powershell/13.09-The-core-of-a-shared-voice-module.txt) | The core of a shared voice module | 13.8 Building a Script Library | 159 | PowerShell |
| [13.10](chapters/13-powershell/13.10-Exporting-the-voice-configuration-to-JSON.txt) | Exporting the voice configuration to JSON | 13.9 Exporting the Voice Configuration | 160 | PowerShell |

### Chapter 14 – Microsoft Graph for Telephony

Folder: [`chapters/14-graph/`](chapters/14-graph/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [14.1](chapters/14-graph/14.01-Connecting-to-Microsoft-Graph-as-an-application.txt) | Connecting to Microsoft Graph as an application | 14.2 App Registrations, Permissions and Consent | 165 | PowerShell |
| [14.2](chapters/14-graph/14.02-A-paging-helper-for-Graph-requests.txt) | A paging helper for Graph requests | 14.3 Calling Graph Reliably | 165 | PowerShell |
| [14.3](chapters/14-graph/14.03-Reading-a-call-record-with-sessions-and-segments.txt) | Reading a call record with sessions and segments | 14.4 Call Records | 167 | PowerShell |
| [14.4](chapters/14-graph/14.04-Failed-Direct-Routing-calls-by-trunk-and-SIP-code.txt) | Failed Direct Routing calls by trunk and SIP code | 14.5 PSTN and Direct Routing Logs | 168 | PowerShell |
| [14.5](chapters/14-graph/14.05-PSTN-calls-and-minutes-by-call-type.txt) | PSTN calls and minutes by call type | 14.5 PSTN and Direct Routing Logs | 168 | PowerShell |
| [14.6](chapters/14-graph/14.06-Creating-a-subscription-for-new-call-records.txt) | Creating a subscription for new call records | 14.6 Change Notifications for Call Records | 169 | PowerShell |
| [14.7](chapters/14-graph/14.07-Presence-of-all-members-of-an-agent-group.txt) | Presence of all members of an agent group | 14.7 Presence | 170 | PowerShell |
| [14.8](chapters/14-graph/14.08-Voice-enabled-users-and-their-numbers-from-the-Teams-user-configuration-API.txt) | Voice-enabled users and their numbers from the Teams user configuration API | 14.8 Teams Administration APIs | 171 | PowerShell |
| [14.9](chapters/14-graph/14.09-Collecting-yesterday-s-PSTN-and-Direct-Routing-logs.txt) | Collecting yesterday's PSTN and Direct Routing logs | 14.10 A Small Reporting Pipeline | 172 | PowerShell |

### Chapter 15 – Configuration as Code

Folder: [`chapters/15-config-as-code/`](chapters/15-config-as-code/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [15.1](chapters/15-config-as-code/15.01-Desired-state-for-voice-routes-and-voice-routing-policies-routing-json.txt) | Desired state for voice routes and voice routing policies (routing.json) | 15.2 The Core Loop | 176 | JSON |
| [15.2](chapters/15-config-as-code/15.02-Comparing-the-desired-and-actual-routing-configuration.txt) | Comparing the desired and actual routing configuration | 15.3 Comparing Desired and Actual State | 177 | PowerShell |
| [15.3](chapters/15-config-as-code/15.03-Applying-the-route-plan-with-a-dry-run-by-default.txt) | Applying the route plan with a dry run by default | 15.4 Applying Changes in the Right Order | 179 | PowerShell |
| [15.4](chapters/15-config-as-code/15.04-A-simple-drift-check-between-two-exports.txt) | A simple drift check between two exports | 15.6 Detecting Drift | 181 | PowerShell |
| [15.5](chapters/15-config-as-code/15.05-Generating-a-Markdown-overview-of-voice-routes.txt) | Generating a Markdown overview of voice routes | 15.7 Documentation from Code | 181 | PowerShell |
| [15.6](chapters/15-config-as-code/15.06-A-runbook-that-exports-routes-and-stores-them-in-Azure-Storage.txt) | A runbook that exports routes and stores them in Azure Storage | 15.8 Running It on a Schedule | 183 | PowerShell |
| [15.7](chapters/15-config-as-code/15.07-Sending-an-alert-to-a-workflow-that-posts-to-Teams.txt) | Sending an alert to a workflow that posts to Teams | 15.8 Running It on a Schedule | 183 | PowerShell |
| [15.8](chapters/15-config-as-code/15.08-Exporting-voice-configuration-and-comparing-exports-with-Microsoft365DSC.txt) | Exporting voice configuration and comparing exports with Microsoft365DSC | 15.10 Microsoft365DSC and UTCM | 184 | PowerShell |

### Chapter 16 – Monitoring and Call Quality

Folder: [`chapters/16-monitoring/`](chapters/16-monitoring/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [16.1](chapters/16-monitoring/16.01-The-15-columns-of-the-building-file-in-the-required-order.txt) | The 15 columns of the building file, in the required order | 16.6 Building Data | 194 | Text |
| [16.2](chapters/16-monitoring/16.02-Creating-a-CQD-building-file-from-the-Teams-network-topology.txt) | Creating a CQD building file from the Teams network topology | 16.6 Building Data | 195 | PowerShell |
| [16.3](chapters/16-monitoring/16.03-An-hourly-failure-ratio-per-trunk-from-the-Direct-Routing-log.txt) | An hourly failure ratio per trunk from the Direct Routing log | 16.9 Your Own Monitoring | 197 | PowerShell |

### Chapter 17 – The Troubleshooting Playbook

Folder: [`chapters/17-troubleshooting/`](chapters/17-troubleshooting/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [17.1](chapters/17-troubleshooting/17.01-Collecting-the-voice-configuration-facts-for-one-user.txt) | Collecting the voice configuration facts for one user | 17.6 Playbooks | 206 | PowerShell |

### Chapter 18 – Security and Compliance

Folder: [`chapters/18-security/`](chapters/18-security/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [18.1](chapters/18-security/18.01-Restricting-outbound-calls-with-outbound-calling-restriction-policies.txt) | Restricting outbound calls with outbound calling restriction policies | 18.3 Toll Fraud | 214 | PowerShell |
| [18.2](chapters/18-security/18.02-Daily-check-for-international-calls-outside-business-hours.txt) | Daily check for international calls outside business hours | 18.3 Toll Fraud | 215 | PowerShell |
| [18.3](chapters/18-security/18.03-Blocking-inbound-calls-from-a-number-range.txt) | Blocking inbound calls from a number range | 18.4 Inbound Calls and Caller ID | 216 | PowerShell |
| [18.4](chapters/18-security/18.04-Allowing-end-to-end-encryption-for-one-to-one-calls.txt) | Allowing end-to-end encryption for one-to-one calls | 18.5 Encryption | 217 | PowerShell |
| [18.5](chapters/18-security/18.05-Assigning-a-compliance-recording-policy.txt) | Assigning a compliance recording policy | 18.6 Call Recording | 218 | PowerShell |

### Chapter 20 – AI in Teams Phone

Folder: [`chapters/20-ai/`](chapters/20-ai/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [20.1](chapters/20-ai/20.01-Configuring-Copilot-in-calls-with-calling-policies.txt) | Configuring Copilot in calls with calling policies | 20.2 Copilot in Calls | 236 | PowerShell |
| [20.2](chapters/20-ai/20.02-Managing-voicemail-transcription.txt) | Managing voicemail transcription | 20.3 Transcription, Captions and Voicemail | 237 | PowerShell |

### Chapter 22 – Real-World Scenarios

Folder: [`chapters/22-scenarios/`](chapters/22-scenarios/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [22.1](chapters/22-scenarios/22.01-Enabling-Location-Based-Routing-on-network-sites-Direct-Routing.txt) | Enabling Location-Based Routing on network sites (Direct Routing) | 22.3 Scenario C: A Multinational with a Regulated Country | 257 | PowerShell |
| [22.2](chapters/22-scenarios/22.02-Analysis-queries-for-an-inherited-tenant.txt) | Analysis queries for an inherited tenant | 22.4 Scenario D: Cleaning Up an Inherited Tenant | 259 | PowerShell |

### Appendix A – PowerShell Cmdlet Reference

Folder: [`chapters/appendix-a/`](chapters/appendix-a/)

| Listing | Description | Section | Page | Type |
|---|---|---|---|---|
| [A.1](chapters/appendix-a/A.01-Finding-cmdlets-by-noun-and-verb.txt) | Finding cmdlets by noun and verb |  | 274 | PowerShell |

## Feedback and contributions

If a script does not work as described, please open an issue with the module version, the error message and the steps to reproduce it. Do not include tenant IDs, user names or other data from your environment.

Microsoft changes Teams, its PowerShell module and Microsoft Graph regularly. Updated versions of scripts are published here; where a script differs from the printed listing, the repository version reflects those changes.

## About the book

*Mastering Microsoft Teams Phone* covers the full lifecycle of a Teams Phone environment: architecture, licensing, PSTN connectivity, network readiness, number planning, Direct Routing, Operator Connect and Calling Plans, emergency calling, voice applications, devices, automation with PowerShell and Microsoft Graph, configuration as code, monitoring, troubleshooting, security, governance, AI and contact center integration.

Author: **Drago Petrovic** · Blog: [msb365.net](https://www.msb365.net) · LinkedIn: [drago-petrovic](https://www.linkedin.com/in/drago-petrovic/)

## License

The code samples are licensed under the [MIT License](LICENSE). Microsoft, Microsoft Teams, Teams Phone and related names are trademarks of the Microsoft group of companies. This repository is not affiliated with or endorsed by Microsoft.
