---
layout: Conceptual
title: Securing privileged access interfaces - Privileged access | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/privileged-access-workstations/privileged-access-interfaces
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: None
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Securing interfaces is only one part of the privileged access story
ms.service: security
ms.subservice: privileged-access
ms.topic: best-practice
ms.date: 2024-06-20T00:00:00.0000000Z
ms.reviewer: mas
locale: en-us
document_id: 2cd70c5b-09b3-0f5d-8315-357431e078b4
document_version_independent_id: 2cd70c5b-09b3-0f5d-8315-357431e078b4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/privileged-access-workstations/privileged-access-interfaces.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: privileged-access-workstations/privileged-access-interfaces
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/privileged-access-workstations/privileged-access-interfaces.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ddab3cd8-636f-4a91-896e-1c23f399a6bd
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f409bb5d-e203-40c5-9d95-0ee717231beb
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 62490da3-ee43-00c9-5441-e63112b04ad4
---

# Securing privileged access interfaces - Privileged access | Microsoft Learn

A critical component of [securing privileged access](overview) is the application of zero trust policy to ensure that devices, accounts, and intermediaries meet security requirements before providing access.

This policy ensures users and devices initiating the inbound session are known, trusted, and allowed to access the resource (via the interface). The policy enforcement is performed by the Microsoft Entra Conditional Access policy engine that evaluates policy assigned to the specific application interface (such as Azure portal, Salesforce, Office 365, AWS, Workday, and others).

![Protecting resources by protecting interfaces](media/privileged-access-interfaces/control-access-using-interfaces.png)

This guidance defines three security levels for interface security that you can use for assets with different sensitivity levels. These levels are configured in the [securing privileged access rapid modernization plan (RAMP)](security-rapid-modernization-plan) and correspond to [security levels of accounts and devices](privileged-access-security-levels).

The security requirements for inbound sessions to interfaces apply to accounts and the source device, whether it’s a direct connection from [physical devices](privileged-access-devices) or a Remote Desktop / Jump server [intermediary](privileged-access-intermediaries). Intermediaries can accept sessions from personal devices to provide enterprise security level (for some scenarios), but specialized or privileged intermediaries shouldn't allow connections from lower levels because of the security sensitive nature of their roles.

Note

These technologies provide strong end to end access control to the application interface, but the resource itself must also be secured from out of band attacks on the application code/functionality, unpatched vulnerabilities or configuration errors in the underlying operating system or firmware, on data at rest or in transit, supply chains, or other means.

Ensure to assess and discover risks to the assets themselves for complete protection. Microsoft provides tooling and guidance to help you with that including [Microsoft Defender for Cloud](/en-us/azure/security-center/security-center-introduction), [Microsoft Secure Score](/en-us/microsoft-365/security/mtp/microsoft-secure-score), and [threat modelling guidance](https://www.microsoft.com/securityengineering/sdl/threatmodeling).

## Interface examples

Interfaces come in different forms, typically as:

- Cloud service/application websites such as Azure portal, AWS, Office 365
- Desktop Console managing an on-premises application (Microsoft Management Console (MMC) or custom application)
- Scripting/Console Interface such as Secure Shell (SSH) or PowerShell

While some of these directly support Zero Trust enforcement via the Microsoft Entra Conditional Access policy engine, some of them will need to be published via an [intermediary](privileged-access-intermediaries) such as Microsoft Entra application proxy or Remote Desktop / jump server.

## Interface security

The ultimate goal of interface security is to ensure that each inbound session to the interface is known, trusted, and allowed:

- Known – User is authenticated with strong authentication and device is authenticated (with exceptions for personal devices using a Remote Desktop or VDI solution for enterprise access)
- Trusted – Security health is explicitly validated and enforced for [accounts](privileged-access-accounts) and [devices](privileged-access-devices) using a Zero Trust policy engine
- Allowed – Access to the resources follows least privilege principle using a combination of controls to ensure it can only be accessed
    - By the right users
    - At the right time (just in time access, not permanent access)
    - With the right approval workflow (as needed)
    - At an acceptable risk/trust level

## Interface security controls

Establishing interface security assurances requires a combination of security controls including:

- Zero Trust policy enforcement - using Conditional Access to ensure that the inbound sessions meet the requirements for:
    - Device Trust to ensure the device at minimum:
        - Is managed by the enterprise
        - Has endpoint detection and response on it
        - Is [compliant with organizations configuration requirements](/en-us/mem/intune/protect/device-compliance-get-started)
        - Isn't infected or under attack during the session
    - User Trust is high enough based on signals including:
        - Multifactor authentication usage during initial sign in (or added later to increase trust)
        - Whether this session matches historical behavior patterns
        - Whether the account or current session triggers any alerts based on threat intelligence
        - [Microsoft Entra ID Protection risk](/en-us/azure/active-directory/identity-protection/overview-identity-protection#risk-detection-and-remediation)
- Role-based access control (RBAC) model that combines enterprise directory groups/permissions and application-specific roles, groups, and permissions
- Just in time access workflows that ensure specific requirements for privileges (peer approvals, audit trail, privileged expiration, etc.) are enforced before allowing privileges the account is eligible for.

## Interface security levels

This guidance defines three levels of security. For more information on these levels, see Keep it Simple - Personas and Profiles. For implementation guidance, see the [rapid modernization plan](security-rapid-modernization-plan).

![Controlling resources access to specific interface security levels](media/privileged-access-interfaces/interface-security-levels.png)

### Enterprise interface

Enterprise interface security is suitable for all enterprise users and productivity scenarios. Enterprise also serves as a starting point for higher sensitivity workloads that you can incrementally build on to reach specialized and privileged access levels of assurance.

- Zero Trust policy enforcement - on inbound sessions using Conditional Access to ensure that users and devices are secured at the enterprise or higher level
    - To support, bring your own device (BYOD) scenarios, personal devices, and partner-managed devices may be allowed connect if they use an enterprise intermediary such as a dedicated [Windows Virtual Desktop (WVD)](/en-us/azure/virtual-desktop/security-guide) or similar Remote Desktop / Jump server solution.
- Role-Based Access Control (RBAC) - Model should ensure that the application is administered only by roles at the specialized or privileged security level

### Specialized interface

Security controls for specialized interfaces should include

- Zero Trust policy enforcement - on inbound sessions using Conditional Access to ensure that users and devices are secured at the specialized or privileged level
- Role-Based Access Control (RBAC) - Model should ensure that the application is administered only by roles at the specialized or privileged security level
- Just in time access workflows (optional) - that enforce least privilege by ensuring privileges are used only by authorized users during the time they're needed.

### Privileged interface

Security controls for privileged interfaces should include

- Zero Trust policy enforcement - on inbound sessions using Conditional Access to ensure that users and devices are secured at the privileged level
- Role-Based Access Control (RBAC) - Model should ensure that the application is administered only by roles at the privileged security level
- Just in time access workflows (required) that enforce least privilege by ensuring privileges are used only by authorized users during the time they're needed.