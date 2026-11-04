---
layout: Conceptual
title: Incident Response -- Resolve Incidents in the Microsoft Defender Portal. | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/respond-incident-defender
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: bagol
author: batamig
description: This article provides incident response guidance using Microsoft Sentinel in the Defender portal, covering triage, investigation, and resolution.
ms.date: 2025-01-23T00:00:00.0000000Z
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
document_id: c073f895-eb90-4196-c2a7-53239f02a726
document_version_independent_id: c073f895-eb90-4196-c2a7-53239f02a726
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/respond-incident-defender.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/respond-incident-defender
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/respond-incident-defender.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: 41cf359f-c249-a322-ae76-951428b9a4c2
---

# Incident Response -- Resolve Incidents in the Microsoft Defender Portal. | Microsoft Learn

This article explains how to respond to an incident using Microsoft Sentinel in the Defender portal, covering triage, investigation, and resolution.

## Prerequisites

Investigate incidents in the Defender portal:

- Your Log Analytics workspace used for Microsoft Sentinel must be onboarded to the Defender portal. For more information, see [Connect Microsoft Sentinel to the Microsoft Defender portal](/en-us/defender-xdr/microsoft-sentinel-onboard?toc=/security/zero-trust/integrate/TOC.json?bc=/security/zero-trust/breadcrumb/toc.json&amp;toc=/security/zero-trust/toc.json).

## Incident response process

When working in the Defender portal, do your initial triage, resolution, and follow-up steps as you would otherwise. When investigating, make sure to:

- Understand the incident and its scope by reviewing asset timelines.
- Review self-healing pending actions, manually remediate entities, and perform live response.
- Add prevention measures.

The added **Microsoft Sentinel** area of the Defender portal helps you deepen your investigation, including:

- Understanding the scope of the incident by correlating it with your security processes, policies, and procedures (3P).
- Performing 3P automated investigation and remediation actions and creating custom security orchestration, automation, and response (SOAR) playbooks.
- Recording evidence for incident management.
- Adding custom measures.

For more information, see:

- [Investigate incidents in Microsoft Defender XDR](/en-us/microsoft-365/security/defender/investigate-incidents)
- [Incident response with Microsoft Defender XDR](/en-us/microsoft-365/security/defender/incidents-overview)
- [Entity pages in Microsoft Sentinel](/en-us/azure/sentinel/entity-pages?tabs=defender-portal)

## Automation with Microsoft Sentinel

Make sure to take advantage of Microsoft Sentinel's playbook and automation rule functionality:

- **A playbook** is a collection of investigation and remediation actions that can be run from the Microsoft Sentinel portal as a routine. Playbooks can help automate and orchestrate your threat response. They can be run manually on-demand on incidents, entities, and alerts, or set to run automatically in response to specific alerts or incidents, when triggered by an automation rule. For more information, see [Automate threat response with playbooks](/en-us/azure/sentinel/automate-responses-with-playbooks).
- **Automation rules** are a way to centrally manage automation in Microsoft Sentinel, by allowing you to define and coordinate a small set of rules that can apply across different scenarios. For more information, see [Automate threat response in Microsoft Sentinel with automation rules](/en-us/azure/sentinel/automate-incident-handling-with-automation-rules).

After you onboard the Microsoft Sentinel workspace to the Defender portal, note that there are differences in how automation functions in your workspace. For more information, see [Automation with Microsoft Sentinel in the Defender portal](/en-us/azure/sentinel/automation).

## Post-incident response

After you've resolved the incident, report the incident to your incident response lead for possible follow-up to determine more actions. For example:

- Inform your Tier 1 security analysts to better detect the attack early.
- Research the attack in Microsoft Defender XDR Threat Analytics and the security community for a security attack trend. For more information, see [Threat analytics in Microsoft Defender XDR](/en-us/microsoft-365/security/defender/threat-analytics).
- As needed, record the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks.
- Determine whether changes in your security configuration are needed and implement them.
- Create an orchestration playbook to automate and orchestrate your threat response for a similar risk in the future. For more information, see [Automate threat response with playbooks in Microsoft Sentinel](/en-us/azure/sentinel/automate-responses-with-playbooks).