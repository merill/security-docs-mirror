---
layout: Conceptual
title: Limit the impact that ransomware attacks can have | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/ransomware/protect-against-ransomware-phase2
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: pauloliveria
author: poliveria
manager: orspodek
ms.service: security
ms.subservice: ''
ms.date: 2024-10-16T00:00:00.0000000Z
ms.topic: best-practice
ms.collection:
- msftsolution-ransomware
ms.custom: cx-rw
description: How to prevent ransomware attacks by protecting privileged roles in your organization and limiting the scope of damage a cybercriminal attacker can do.
locale: en-us
document_id: 155db32e-33d8-299e-a081-0ae7e190ed5d
document_version_independent_id: 155db32e-33d8-299e-a081-0ae7e190ed5d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/ransomware/protect-against-ransomware-phase2.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: ransomware/protect-against-ransomware-phase2
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/ransomware/protect-against-ransomware-phase2.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/6ab06385-661e-4214-8870-bbe4071c960d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/131ba09e-4280-4ae7-8622-1f9f1c0daad1
platformId: 00dceb55-fbbd-c3b2-a1c6-3fe59feab8f7
---

# Limit the impact that ransomware attacks can have | Microsoft Learn

The next step to limit the impact of ransomware attacks is to *protect privileged roles* -- the kind of jobs where people handle a lot of privileged information in an organization.

This phase of ransomware prevention aims to prevent threat actors from getting a lot of access to your systems.

The more access a cybercriminal has to your organization and devices, the higher the potential damage to your data and systems.

Important

**Read ransomware prevention series, and make your organization hard to cyber attack.**

- [Have a recovery plan](protect-against-ransomware-phase1)
- [A plan to limit the harm done](protect-against-ransomware-phase2)
- [Make it hard to get in](protect-against-ransomware-phase3)

## Create a ransomware privileged access strategy

You must apply a thorough and comprehensive strategy to reduce the risk of privileged access compromise.

Any other security control you apply can easily be invalidated by a threat actor with privileged access in your environment. Malicious actors can gain access using social engineering and even leverage AI to generate and render malicious code and URLs. Ransomware threat actors use privileged access as a quick path to control all critical assets in the organization for attack and subsequent extortion.

### Who is accountable in the program or project

This table describes a privileged access strategy to prevent ransomware in terms of a sponsorship/program management/project management hierarchy to drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| CISO or CIO |  | Executive sponsorship |
| Program lead |  | Drive results and cross-team collaboration |
|  | IT and [Security Architects](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) | Prioritize components integrate into architectures |
|  | [Identity and Key Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-identity-keys) | Implement identity changes |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Productivity / End User Team | Implement changes to devices and Office 365 tenant |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |
|  | User Education Team | Update any password guidance |
|  |  |  |

### Ransomware privileged access strategy checklist

Build a multi-part strategy using the guidance at https://aka.ms/SPA that includes this checklist.

| Done | Task | Description |
| --- | --- | --- |
|  | Enforce end-to-end session security. | Explicitly validates the trust of users and devices before allowing access to administrative interfaces (using [Microsoft Entra Conditional Access](/en-us/azure/active-directory/conditional-access/overview)). |
|  | Protect and monitor identity systems. | Prevents privilege escalation attacks including directories, identity management, administrator accounts and groups, and consent grant configuration. |
|  | Mitigate lateral traversal. | Ensures that compromising a single device does not immediately lead to control of many or all other devices using local account passwords, service account passwords, or other secrets. |
|  | Ensure rapid threat response. | Limits an adversary's access and time in the environment. See [Detection and Response](protect-against-ransomware-phase2#ransomware-detection-and-response) for more information. |
|  |  |  |

### Implementation results and timelines

Try to achieve these results in 30-90 days:

- 100% of admins are required to use secure workstations
- 100% local workstation/server passwords are randomized
- 100% privilege escalation mitigations are deployed

## Ransomware detection and response

Your organization needs responsive detection and remediation of common attacks on endpoints, email, and identities. Minutes matter.

You must quickly remediate common attack entry points to limit the threat actor's time to laterally traverse your organization.

### Who is accountable in the program or project

This table describes the improvement of your detection and response capability against ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| CISO or CIO |  | Executive sponsorship |
| Program lead from [Security Operations](/en-us/azure/cloud-adoption-framework/organize/cloud-security-operations-center) |  | Drive results and cross-team collaboration |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Infrastructure Team | Implement client and server agents/features |
|  | [Security Operations](/en-us/azure/cloud-adoption-framework/organize/cloud-security-operations-center) | Integrate any new tools into security operations processes |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Productivity / End User Team | Enable features for Defender for Endpoint, Defender for Office 365, Defender for Identity, and Defender for Cloud Apps |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Identity Team | Implement Microsoft Entra security and Defender for Identity |
|  | [Security Architects](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) | Advise on configuration, standards, and tooling |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |
|  |  |  |

### Ransomware detection and response checklist

Apply these best practices for improving your detection and response.

| Done | Task | Description |
| --- | --- | --- |
|  | Prioritize common entry points:  - Use integrated Extended Detection and Response (XDR) tools like [Microsoft Defender XDR](/en-us/microsoft-365/security/mtp/microsoft-threat-protection) to provide high quality alerts and minimize friction and manual steps during response.  - Monitor for brute-force attempts like [password spray](/en-us/defender-for-identity/compromised-credentials-alerts). | Ransomware (and other) operators favor endpoint, email, identity, and RDP as entry points. |
|  | Monitor for an adversary disabling security (this is often part of an attack chain), such as:  - Event log clearing, especially the Security Event log and PowerShell Operational logs.  - Disabling of security tools and controls. | Threat actors target security detection facilities to continue their attack more safely. |
|  | Don’t ignore commodity malware. | Ransomware threat actors regularly purchase access to target organizations from dark markets. |
|  | Integrate outside experts into processes to supplement expertise, such as the [Microsoft Detection and Response Team (DART)](https://aka.ms/dart). | Experience counts for detection and recovery. |
|  | Use [Defender for Endpoint](/en-us/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) to rapidly isolate impacted devices. | Windows 11 and 10 integration makes this easy. |
|  |  |  |