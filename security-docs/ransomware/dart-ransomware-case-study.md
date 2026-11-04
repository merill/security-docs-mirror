---
layout: Conceptual
title: Microsoft Incident Response ransomware case study | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/ransomware/dart-ransomware-case-study
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: pauloliveria
author: poliveria
manager: orspodek
ms.service: security
ms.subservice: ''
description: Understand how the Microsoft Incident Response team detected and responded to a ransomware attack.
keywords: investigation, attack, microsoft threat protection, microsoft 365, search, query, telemetry, security events, antivirus, incident, response, incident response, playbook, guidance, Microsoft Defender XDR
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.collection:
- msftsolution-ransomware
ms.topic: example-scenario
ms.date: 2024-05-24T00:00:00.0000000Z
ms.custom: cx-rw
locale: en-us
document_id: cdddaf62-a1e4-e45d-673c-e6a3ee6bc004
document_version_independent_id: cdddaf62-a1e4-e45d-673c-e6a3ee6bc004
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/ransomware/dart-ransomware-case-study.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: ransomware/dart-ransomware-case-study
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/ransomware/dart-ransomware-case-study.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c671beaa-a830-4c9f-aceb-97379ee031ca
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ddab3cd8-636f-4a91-896e-1c23f399a6bd
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/8921374c-4dbe-4ed0-b011-a39e18bfbd98
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f409bb5d-e203-40c5-9d95-0ee717231beb
platformId: f86cdeb3-c16e-94c7-14af-e8a18df69f09
---

# Microsoft Incident Response ransomware case study | Microsoft Learn

Human-operated ransomware continues to maintain its position as one of the most impactful cyberattack trends world-wide and is a significant threat that many organizations have faced in recent years. These attacks take advantage of network misconfigurations and thrive on an organization's weak interior security. Although these attacks pose a clear and present danger to organizations and their IT infrastructure and data, they are a [preventable disaster](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/).

The [Microsoft Incident Response team (formerly DART/CRSP)](https://www.microsoft.com/security/blog/microsoft-detection-and-response-team-dart-blog-series/) responds to security compromises to help customers become cyber-resilient. Microsoft Incident Response provides onsite reactive incident response and remote proactive investigations. Microsoft Incident Response leverages Microsoft's strategic partnerships with security organizations around the world and internal Microsoft product groups to provide the most complete and thorough investigation possible.

This article describes how Microsoft Incident Response investigated a recent ransomware incident with details on the attack tactics and detection mechanisms.

See [Part 1](https://www.microsoft.com/en-us/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/) and [Part 2](https://www.microsoft.com/en-us/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/) of Microsoft Incident Response's guide to combatting human-operated ransomware for more information.

## The attack

Microsoft Incident Response leverages incident response tools and tactics to identify threat actor behaviors for human operated ransomware. Public information regarding ransomware events focuses on the end impact, but rarely highlights the details of the operation and how threat actors were able to escalate their access undetected to discover, monetize, and extort.

Here are some common techniques that attackers use for ransomware attacks based on [MITRE ATT&CK tactics](https://attack.mitre.org/).

[![Common techniques that attackers use for ransomware attacks.](media/dart-ransomware-case-study/dart-ransomware-case-study-attack-methods.png)](media/dart-ransomware-case-study/dart-ransomware-case-study-attack-methods.png#lightbox)

Microsoft Incident Response used Microsoft Defender for Endpoint to track the attacker through the environment, create a story depicting the incident, and then eradicate the threat and remediate. Once deployed, Defender for Endpoint began detecting successful logons from a brute force attack. When Microsoft Incident Response discovered this, they reviewed the security data and found several vulnerable Internet-facing devices using the Remote Desktop Protocol (RDP).

After initial access was gained, the threat actor used the Mimikatz credential harvesting tool to dump password hashes, scanned for credentials stored in plaintext, created backdoors with Sticky Key manipulation, and moved laterally throughout the network using remote desktop sessions.

For this case study, here is the highlighted path that the attacker took.

[![The path the ransomware attacker took for this case study.](media/dart-ransomware-case-study/dart-ransomware-case-study-attack-path.png)](media/dart-ransomware-case-study/dart-ransomware-case-study-attack-path.png#lightbox)

The following sections describe additional details based on the MITRE ATT&CK tactics and include examples of how the threat actor activities were detected with the Microsoft Defender portal.

## Initial access

Ransomware campaigns use well-known vulnerabilities for their initial entry, typically using phishing emails or weaknesses in perimeter defense such as devices with the enabled Remote Desktop service exposed on the Internet.

For this incident, Microsoft Incident Response managed to locate a device that had TCP port 3389 for RDP exposed to the Internet. This allowed threat actors to perform a brute-force authentication attack and gain the initial foothold.

Defender for Endpoint used threat intelligence to determine that there were numerous sign-ins from known brute-force sources and displayed them in the Microsoft Defender portal. Here's an example.

![An example of known brute-force sign-ins in the Microsoft Defender portal.](media/dart-ransomware-case-study/dart-ransomware-case-study-brute-force-sign-in.png)

## Reconnaissance

Once the initial access was successful, environment enumeration and device discovery began. These activities allowed the threat actors to identify information about the organization's internal network and target critical systems such as domain controllers, backup servers, databases, and cloud resources. After the enumeration and device discovery, the threat actors performed similar activities to identify vulnerable user accounts, groups, permissions, and software.

The threat actor leveraged Advanced IP Scanner, an IP address scanning tool, to enumerate the IP addresses used in the environment and perform subsequent port scanning. The threat actor scanned open ports to discover devices that were accessible from the initially compromised device.

This activity was detected in Defender for Endpoint and used as an indicator of compromise (IoC) for further investigation. Here's an example.

![An example of port scanning in the Microsoft Defender portal.](media/dart-ransomware-case-study/dart-ransomware-case-study-port-scan.png)

## Credential theft

After threat actors gained initial access, they performed credential harvesting using the Mimikatz password retrieval tool and by searching for files containing “password” on initially compromised systems. These actions enabled the threat actors to access additional systems with legitimate credentials. In many situations, threat actors use these accounts to create additional accounts to maintain persistence after the initial compromised accounts are identified and remediated.

Here's an example of the detected use of the Mimikatz in the Microsoft Defender portal.

![An example of Mimikatz detection in the Microsoft Defender portal](media/dart-ransomware-case-study/dart-ransomware-case-study-mimikatz.png)

## Lateral movement

Movement across endpoints can vary between different organizations, but threat actors commonly use different varieties of remote management software that already exists on the device. By utilizing methods of remote access that the IT department commonly uses in their day-to-day activities, threat actors can fly under the radar for extended periods of time.

Microsoft Incident Response used Microsoft Defender for Identity to map out the path that the threat actor took between devices, displaying the accounts that were used and accessed. Here's an example.

![The path that the threat actor took between devices in Microsoft Defender for Identity.](media/dart-ransomware-case-study/dart-ransomware-case-study-threat-actor-path.png)

## Defense evasion

To avoid detection, the threat actors used defense evasion techniques to avoid identification and achieve their objectives throughout the attack cycle. These techniques include disabling or tampering with anti-virus products, uninstalling or disabling security products or features, modifying firewall rules, and using obfuscation techniques to hide the artifacts of an intrusion from security products and services.

The threat actor for this incident used PowerShell to disable real-time protection for Microsoft Defender on Windows 11 and Windows 10 devices and local networking tools to open TCP port 3389 and allow RDP connections. These changes decreased the chances of detection in an environment because they modified system services that detect and alert on malicious activity.

Defender for Endpoint, however, cannot be disabled from the local device and was able to detect this activity. Here's an example.

![An example of detecting the use of PowerShell to disable real-time protection for Microsoft Defender.](media/dart-ransomware-case-study/dart-ransomware-case-study-mde-detect-powershell.png)

## Persistence

Persistence techniques include actions by threat actors to maintain consistent access to systems after efforts are made by security staff to regain control of compromised systems.

The threat actors for this incident used the Sticky Keys hack because it allows for remote execution of a binary inside the Windows operating system without authentication. They then used this capability to launch a Command Prompt and perform further attacks.

Here's an example of the detection of the Sticky Keys hack in the Microsoft Defender portal.

![An example of detecting the Sticky Keys hack in the Microsoft Defender portal.](media/dart-ransomware-case-study/dart-ransomware-case-study-detect-sticky-keys.png)

## Impact

Threat actors typically encrypt files using applications or features that already exist within the environment. The use of PsExec, Group Policy, and Microsoft Endpoint Configuration Management are methods of deployment that allow an actor to quickly reach endpoints and systems without disrupting normal operations.

The threat actor for this incident leveraged PsExec to remotely launch an interactive PowerShell Script from various remote shares. This attack method randomizes distribution points and makes remediation more difficult during the final phase of the ransomware attack.

### Ransomware execution

Ransomware execution is one of the primary methods that a threat actor uses to monetize their attack. Regardless of the execution methodology, distinct ransomware frameworks tend to have a common behavioral pattern once deployed:

- Obfuscate threat actor actions
- Establish persistence
- Disable windows error recovery and automatic repair
- Stop a list of services
- Terminate a list of processes
- Delete shadow copies and backups
- Encrypt files, potentially specifying custom exclusions
- Create a ransomware note

Here's an example of a ransomware note.

![An example of a ransomware note.](media/dart-ransomware-case-study/dart-ransomware-case-study-ransom-note-example.png)

## Additional ransomware resources

Key information from Microsoft:

- [The growing threat of ransomware](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), Microsoft On the Issues blog post on July 20, 2021
- [Human-operated ransomware](human-operated-ransomware)
- [Rapidly protect against ransomware and extortion](protect-against-ransomware)
- [2021 Microsoft Digital Defense Report](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (see pages 10-19)
- [Ransomware: A pervasive and ongoing threat](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) threat analytics report in the Microsoft Defender portal
- [Microsoft Incident Response ransomware approach and best practices](/en-us/security/ransomware/incident-response-playbook-dart-ransomware-approach)

Microsoft 365:

- [Deploy ransomware protection for your Microsoft 365 tenant](/en-us/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Maximize Ransomware Resiliency with Azure and Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Recover from a ransomware attack](/en-us/microsoft-365/security/office-365-security/recover-from-ransomware)
- [Malware and ransomware protection](/en-us/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Protect your Windows 10 PC from ransomware](https://support.microsoft.com/windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [Handling ransomware in SharePoint Online](/en-us/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Threat analytics reports for ransomware](https://security.microsoft.com/threatanalytics3?page_size=30&amp;filters=tags%3DRansomware&amp;ordering=-lastUpdatedOn&amp;fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) in the Microsoft Defender portal

Microsoft Defender XDR:

- [Find ransomware with advanced hunting](/en-us/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Defender for Cloud Apps:

- [Create anomaly detection policies in Defender for Cloud Apps](/en-us/cloud-app-security/anomaly-detection-policy)

Microsoft Azure:

- [Azure Defenses for Ransomware Attack](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Maximize Ransomware Resiliency with Azure and Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Backup and restore plan to protect against ransomware](/en-us/azure/security/fundamentals/backup-plan-to-protect-against-ransomware)
- [Help protect from ransomware with Microsoft Azure Backup](https://www.youtube.com/watch?v=VhLOr2_1MCg) (26 minute video)
- [Recovering from systemic identity compromise](/en-us/azure/security/fundamentals/recover-from-identity-compromise)
- [Advanced multistage attack detection in Microsoft Sentinel](/en-us/azure/sentinel/fusion#ransomware)
- [Fusion Detection for Ransomware in Microsoft Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Security team blog posts:

- [3 steps to prevent and recover from ransomware (September 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [A guide to combatting human-operated ransomware: Part 1 (September 2021)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

    Key steps on how Microsoft Incident Response conducts ransomware incident investigations.
- [A guide to combatting human-operated ransomware: Part 2 (September 2021)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

    Recommendations and best practices.
- [Becoming resilient by understanding cybersecurity risks: Part 4—navigating current threats (May 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

    See the **Ransomware** section.
- [Human-operated ransomware attacks: A preventable disaster (March 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

    Includes attack chain analyses of actual attacks.
- [Ransomware response—to pay or not to pay? (December 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro responds to ransomware attack with transparency (December 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)