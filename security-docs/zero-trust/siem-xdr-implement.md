---
layout: Conceptual
title: Zero Trust Security with Microsoft Sentinel and Defender XDR | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/siem-xdr-implement
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Transform your security posture with Microsoft Sentinel and Defender XDR. Benefit from AI-powered threat detection and incident response for Zero Trust.
ms.subservice: zero-trust
manager: raynemw
ms.date: 2025-02-05T00:00:00.0000000Z
ms.topic: how-to
ms.service: security
locale: en-us
document_id: c601f7d9-73a3-19eb-3c5b-1bfb5e95fc07
document_version_independent_id: c601f7d9-73a3-19eb-3c5b-1bfb5e95fc07
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/siem-xdr-implement.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/siem-xdr-implement
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/siem-xdr-implement.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1577a46d-8446-40bd-bfae-0578362f4d94
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/cdf3f22d-5420-4d59-a2bf-66d6b3d9c828
platformId: c80b973b-804a-d42a-f0fb-c6abd85cb04b
---

# Zero Trust Security with Microsoft Sentinel and Defender XDR | Microsoft Learn

Microsoft Defender XDR is an extended detection and response (XDR) solution that complements Microsoft Sentinel. An XDR pulls raw telemetry data from multiple services like cloud applications, email security, identity, and access management.

Using artificial intelligence (AI) and machine learning, the XDR performs automatic analysis, investigation, and real-time response. It also correlates security alerts into larger incidents, giving security teams greater visibility into attacks and prioritizing incidents to help analysts gauge threat risk levels.

With Microsoft Sentinel, you can connect to many security sources using built-in connectors and industry standards. With its AI, you can correlate multiple low-fidelity signals spanning multiple sources to create a complete view of the ransomware kill chain and prioritized alerts.

## Common attack order

This section covers a typical attack scenario involving a phishing attack and how to respond to the incident with Microsoft Sentinel and Microsoft Defender XDR.

[![Diagram of a common attack scenario and defenses provided by Microsoft security products.](media/common-attack-defense.svg)](media/common-attack-defense.svg#lightbox)

The diagram shows the Microsoft security products that detect each attack step and how attack signals and SIEM data flow to Microsoft Defender XDR and Microsoft Sentinel.

Here's a summary of the attack.

| Attack step | Detection service and signal source | Defenses in place |
| --- | --- | --- |
| 1. Attacker sends phishing email | Microsoft Defender for Office 365 | Protects mailboxes with advanced anti-phishing features that can protect against malicious impersonation-based phishing attacks. |
| 2. User opens attachment | Microsoft Defender for Office 365 | The Microsoft Defender for Office 365 Safe Attachments feature opens attachments in an isolated environment for more threat scanning (detonation). |
| 3. Attachment installs malware | Microsoft Defender for Endpoint | Protects endpoints from malware with its next generation protection features, such as cloud-delivered protection and behavior-based/heuristic/real-time antivirus protection. |
| 4. Malware steals user credentials | Microsoft Entra ID and Microsoft Entra ID Protection | Protects identities by monitoring user behavior and activities, detecting lateral movement, and alerting on anomalous activity. |
| 5. Attacker moves laterally across Microsoft 365 apps and data | Microsoft Defender for Cloud Apps | Can detect anomalous activity of users accessing cloud apps. |
| 6. Attacker downloads sensitive files from a SharePoint folder | Microsoft Defender for Cloud Apps | Can detect and respond to mass download events of files from SharePoint. |

If you onboarded your Microsoft Sentinel workspace to the Defender portal, SIEM data is available with Microsoft Sentinel directly in the Microsoft Defender portal.

## Incident response using Microsoft Sentinel and Microsoft Defender XDR

After observing a common attack, use Microsoft Sentinel and Microsoft Defender XDR for incident response.

Select the relevant tab for your workspace depending on whether you onboarded it to the Defender portal.

# [Defender portal](#tab/defender-portal)
After onboarding Microsoft Sentinel to the Defender portal, complete all incident response steps directly in the Microsoft Defender portal just as you do for other Microsoft Defender XDR incidents. Supported steps include everything from triage to investigation and resolution.

Use the Microsoft Sentinel area in the Microsoft Defender portal for features that aren't available with the Defender portal alone.

For more information, see [Respond to an incident using Microsoft Sentinel and Microsoft Defender XDR](respond-incident-defender).

# [Azure portal](#tab/azure-portal)
Use the following high-level process to respond to an incident with Microsoft Sentinel in the Azure portal together with Microsoft Defender XDR:

1. Triage the incident in the Microsoft Sentinel portal.
2. Move to the Microsoft Defender portal to start your investigation.
3. If needed, continue the investigation in the Microsoft Sentinel portal.
4. Resolve the incident in the Microsoft Sentinel portal.

The following diagram shows the process, starting with discovery and triage in Microsoft Sentinel.

[![Diagram of performing incident investigation using Microsoft Sentinel and Microsoft Defender XDR.](media/investigation-flow.svg)](media/investigation-flow.svg#lightbox)

For more information, see [Respond to an incident using Microsoft Sentinel and Microsoft Defender XDR](respond-incident-azure).

---