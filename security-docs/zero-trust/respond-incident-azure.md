---
layout: Conceptual
title: Respond to Incidents from the Azure portal | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/respond-incident-azure
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: bagol
author: batamig
description: Learn how to resolve an incident using both Microsoft Sentinel in the Azure portal and Microsoft Defender XDR, including triage, investigation, and resolution.
ms.date: 2025-01-26T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- zerotrust-solution
- msftsolution-secops
- msftsolution-scenario
- zerotrust-azure
- usx-security
locale: en-us
document_id: 5a45370e-1790-12cd-45b4-a49231fdf3b4
document_version_independent_id: 5a45370e-1790-12cd-45b4-a49231fdf3b4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/respond-incident-azure.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/respond-incident-azure
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/respond-incident-azure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1577a46d-8446-40bd-bfae-0578362f4d94
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/cdf3f22d-5420-4d59-a2bf-66d6b3d9c828
platformId: b0408e57-3221-6e76-85ab-d9b6e3da7f70
---

# Respond to Incidents from the Azure portal | Microsoft Learn

This article explains how to resolve security incidents using Microsoft Sentinel in the Azure portal and Microsoft Defender XDR. Learn step-by-step guidance on triage, investigation, and resolution to ensure rapid incident response.

- Updates on lifecycle (status, owner, classification) are shared between the products.
- Evidence gathered during an investigation is shown in the Microsoft Sentinel incident.

For more information about the integration of Microsoft Defender with Microsoft Sentinel, see [Microsoft Defender XDR integration with Microsoft Sentinel](/en-us/azure/sentinel/microsoft-365-defender-sentinel-integration). This [interactive guide](https://mslearn.cloudguides.com/guides/Investigate%20security%20incidents%20in%20a%20hybrid%20environment%20with%20Azure%20Sentinel) steps you through detecting and responding to modern attacks with Microsoft’s unified security information and event management (SIEM) and extended detection and response (XDR) capabilities.

## Incident triage

Start triage in the Azure portal with Microsoft Sentinel to review incident details and take immediate action. On the **Incidents** page, locate the suspected incident and update details like owner name, status, and severity or add comments. Drill down for additional information to continue your investigation.

For more information, see [Navigate, triage, and manage Microsoft Sentinel incidents in the Azure portal](/en-us/azure/sentinel/incident-navigate-triage)

## Incident investigation

Use the Azure portal as your primary incident response tool, then switch to the Defender portal for more detailed investigation.

For example:

| Portal | Tasks |
| --- | --- |
| **In the Azure portal** | Use Microsoft Sentinel in the Azure portal to correlate the incident with your security processes, policies, and procedures (3P). On an incident details page, select **Investigate in Microsoft Defender XDR** to open the same incident in the Defender portal. |
| **In the Defender portal** | Investigate details such as the incident scope, asset timelines, and self-healing pending actions. You might also need to manually remediate entities, perform live response, and add prevention measures. On the incident details page's **Attack story** tab:  - View the attack story of the incident to understand its scope, severity, detection source, and what entities are affected. - Analyze the incident's alerts to understand their origin, scope, and severity with the alert story within the incident. - As needed, gather information on impacted devices, users, and mailboxes with the graph. Select any entity to open a flyout with all the details. - See how Microsoft Defender XDR has automatically resolved some alerts with the **Investigations** tab. - As needed, use information in the data set for the incident from the **Evidence and Response** tab. |
| **In the Azure portal** | Return to the Azure portal to perform extra incident actions, such as: - Performing 3P automated investigation and remediation actions - Creating custom security orchestration, automation, and response (SOAR) playbooks- Recording evidence for incident management, such as comments to record your actions and the results of your analysis.- Adding custom measures. |

For more information, see:

- [Investigate Microsoft Sentinel incidents in depth in the Azure portal](/en-us/azure/sentinel/investigate-incidents)
- [Manage incidents in Microsoft Defender](/en-us/defender-xdr/manage-incidents?toc=%2Fazure%2Fsentinel%2FTOC.json&amp;bc=%2Fazure%2Fsentinel%2Fbreadcrumb%2Ftoc.json)

## Automation with Microsoft Sentinel

Use Microsoft Sentinel's playbook and automation rule functionality:

- **A playbook** is a collection of investigation and remediation actions that you run from the Microsoft Sentinel portal as a routine. Playbooks help automate and orchestrate your threat response. They run manually on incidents, entities, or alerts, or automatically when triggered by an automation rule. For more information, see [Automate threat response with playbooks](/en-us/azure/sentinel/automate-responses-with-playbooks).
- **Automation rules** let you centrally manage automation in Microsoft Sentinel by defining and coordinating a small set of rules that apply across different scenarios. For more information, see [Automate threat response in Microsoft Sentinel with automation rules](/en-us/azure/sentinel/automate-incident-handling-with-automation-rules).

## Incident resolution

When your investigation concludes and you have fixed the incident in the portals, resolve it. For more information, see [Closing an incident in the Azure portal](/en-us/azure/sentinel/incident-navigate-triage#close-an-incident).

Report the incident to your incident response lead for potential follow-up actions. For example:

- Inform your Tier 1 security analysts to better detect the attack early.
- Research the attack in Microsoft Defender XDR Threat Analytics and the security community for a security attack trend.
- Record the workflow used to resolve the incident and update your standard workflows, processes, policies, and playbooks.
- Determine whether changes in your security configuration are needed and implement them.
- Create an orchestration playbook to automate your threat response for similar risks. For more information, see [Automate threat response with playbooks in Microsoft Sentinel](/en-us/azure/sentinel/automate-responses-with-playbooks).