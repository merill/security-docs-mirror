---
layout: Conceptual
title: Incident response playbooks overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-operations-incident-response-playbooks
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Review SecOps incident response playbooks in SAF for common attack scenarios.
keywords: investigation, attack, microsoft threat protection, microsoft 365, search, query, telemetry, security events, antivirus, incident, response, incident response, playbook, guidance, compromise, Microsoft Defender XDR
search.product: DART
ms.service: security
ms.subservice: zero-trust
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.collection:
- msftsolution-secops
ms.topic: best-practice
ms.custom: cxdef-zt-ransomware
ms.date: 2024-03-08T00:00:00.0000000Z
locale: en-us
document_id: de82f3a4-d22a-ebca-96c9-082b4ef5bedd
document_version_independent_id: de82f3a4-d22a-ebca-96c9-082b4ef5bedd
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-operations-incident-response-playbooks.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-operations-incident-response-playbooks
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-operations-incident-response-playbooks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 7ef49bad-47c0-d404-ec78-38c157ee8e5b
---

# Incident response playbooks overview | Microsoft Learn

This article is part of the Security Operations (SecOps) discipline in the **Microsoft Security Adoption Framework (SAF)**. Use these playbooks to respond quickly to active attacks, contain impact, and improve response consistency across common scenarios.

As new widespread cyberattacks happen, Microsoft will respond with detailed incident response guidance through various communication channels, primarily through the [Microsoft Security Blog](https://www.microsoft.com/security/blog/topic/threat-intelligence/).

The following content is Microsoft best practice information, provided by [Microsoft Incident Response](https://www.microsoft.com/security/business/microsoft-incident-response). This team provides fast, flexible services that will remove a bad actor from your environment, build resilience for future attacks, and help mend your defenses after a breach.

Review the following incident response playbooks to understand how to detect and contain these different types of attacks:

- [Phishing](security-operations-playbook-phishing)
- [Password spray](security-operations-playbook-password-spray)
- [App consent grant](security-operations-playbook-app-consent)
- [Compromised and malicious applications](security-operations-playbook-compromised-malicious-app)
- [Token theft](security-operations-playbook-token-theft)

Each playbook includes:

- **Prerequisites:** The specific requirements you need to complete before starting the investigation. For example, logging that should be turned on and roles and permissions that are required.
- **Workflow:** The logical flow that you should follow to perform the investigation.
- **Checklist:** A list of tasks for the steps in the flow chart. This checklist can be helpful in highly regulated environments to verify what you have done.
- **Investigation steps:** Detailed step-by-step guidance for the specific investigation.

## Incident response resources

- [Plan incident response](security-adoption-discipline-security-operations-incidents) for strategy, process, and recovery guidance
- [Prepare for incident response](security-operations-incident-response-readiness) for SOC readiness activities
- [Microsoft Defender XDR](/en-us/microsoft-365/security/defender/incidents-overview) incident response
- [Microsoft Defender for Cloud (Azure)](/en-us/azure/defender-for-cloud/managing-and-responding-alerts)
- [Microsoft Sentinel](/en-us/azure/sentinel/investigate-incidents) incident response
- [Microsoft Incident Response team guide shares best practices for security teams and leaders](https://www.microsoft.com/security/blog/2023/12/11/new-microsoft-incident-response-team-guide-shares-best-practices-for-security-teams-and-leaders/)
- [Microsoft Incident Response guides help security teams analyze suspicious activity](https://www.microsoft.com/security/blog/2024/01/17/new-microsoft-incident-response-guides-help-security-teams-analyze-suspicious-activity/)