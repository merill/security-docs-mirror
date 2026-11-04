---
layout: Conceptual
title: Complete production infrastructure inventory – Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/complete-production-infrastructure-inventory
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Complete production infrastructure inventory is part of the monitor and detect threats pillar of the Secure Future Initiative (SFI), focusing on maintaining a complete, accurate, and close to real-time inventory of all production assets.
ms.date: 2025-08-05T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 08dcfe0e-2cdd-c42f-ca5f-28e4450938da
document_version_independent_id: 08dcfe0e-2cdd-c42f-ca5f-28e4450938da
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/complete-production-infrastructure-inventory.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/complete-production-infrastructure-inventory
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/complete-production-infrastructure-inventory.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
platformId: c9e7f9cc-d96c-dfa2-8753-a5bb0c4e8b65
---

# Complete production infrastructure inventory – Zero Trust | Microsoft Learn

**Pillar name: Monitor and detect threats** **Pattern name: Complete production infrastructure inventory**

Complete production infrastructure inventory is part of the monitor and detect threats pillar of the Secure Future Initiative (SFI). This pillar is focused on ensuring that Microsoft’s environments provide high-fidelity telemetry, comprehensive visibility, and advanced detection capabilities to identify and respond to evolving threats.

A complete, accurate, and close to real-time inventory of all production assets is foundational to powering this pillar—enabling consistent policy enforcement, trusted telemetry, and accelerated threat detection and response.

## Context and problem

As enterprise environments grow increasingly complex—with a mix of legacy systems, cloud workloads, APIs, and user identities—maintaining visibility across the entire production infrastructure becomes increasingly difficult.

Without complete real-time understanding of what exists in the environment:

- Threats can go undetected due to telemetry blind spots
- Security policies may be inconsistently applied
- Misconfigured or unmanaged assets may introduce avoidable vulnerabilities
- Applications and services can persist long after they're abandoned, further expanding the attack surface

Incomplete asset inventories contribute to:

- Delayed threat detection
- Inconsistent enforcement of Zero Trust policies
- Operational inefficiencies

Even at Microsoft’s scale, it became clear that incomplete asset inventories were contributing to delayed detection, inconsistent enforcement of Zero Trust policies, and operational inefficiencies.

Treating infrastructure visibility as a core security priority becomes essential to eliminating blind spots and reducing risk.

## Solution

To address this challenge, Microsoft launched the complete production infrastructure inventory objective under the Secure Future Initiative. The goal: continuously maintain a real-time inventory of 100% of production infrastructure assets—including cloud, on-premises, hybrid, and containerized environments. This effort required significant cross-team coordination and investment in scalable automation.

From it, Microsoft:

- Defined and discovered all production assets, including devices, services, APIs, workloads, and third-party integrations
- Centralized inventory management in a system capable of tracking changes in near-real time
- Extended audit log and telemetry coverage to ensure all assets emitted standardized logs via centrally managed agents
- Integrated the inventory system with detection platforms, enriching SIEM and threat analytics with real-time metadata
- Remediated unused applications—over 730,000 apps so far have been flagged and safely removed using automated log analysis on Azure Kubernetes Service, hosted in confidential containers
- Implemented an application remediation workflow for unused applications that haven't demonstrated activity or maintenance and were flagged and evaluated for safe removal

To date, Microsoft centrally tracks more than 97% of production infrastructure assets. In addition, 99% of network devices and more than 95% of nodes/machines have central security log collection with a two-year retention policy enforced.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Asset identification | - Inventory all devices, services, APIs, workloads, and third-party applications | [Critical asset management](/en-us/security-exposure-management/critical-asset-management) |
| Real-time asset detection | - Use automated discovery tools and IP attribution systems to detect assets in real time | [Critical asset management](/en-us/security-exposure-management/critical-asset-management) |
| Centralized inventory | - Consolidate records into a system that supports classification and lifecycle visibility<br>- Establish continuous update mechanism | - [Asset lifecycle states](/en-us/dynamics365/supply-chain/asset-management/setup-for-objects/object-stages)<br>- [Overview of the update process for Microsoft 365 Apps](/en-us/microsoft-365-apps/updates/overview-update-process-microsoft-365-apps) |
| Telemetry standardization | - Deploy centrally managed agents to enforce consistent logging<br>- Confirm API logging coverage and track observability gaps | - [Set up and view enhanced telemetry in Application Insights for Standard workflows in Azure Logic Apps](/en-us/azure/logic-apps/enable-enhanced-telemetry-standard-workflows?tabs=portal)<br>- [Application Insights telemetry data model](/en-us/azure/azure-monitor/app/data-model-complete)<br>- [Tutorial: Monitor published APIs](/en-us/azure/api-management/api-management-howto-use-azure-monitor) |
| Threat detection integration | - Correlate logs with inventory metadata to improve detection fidelity<br>- Use analytics and ML to proactively identify anomalies | - [Microsoft Defender Threat Intelligence](https://www.microsoft.com/en-sg/security/business/siem-and-xdr/microsoft-defender-threat-intelligence)<br>- [Application Insights telemetry data model](/en-us/azure/azure-monitor/app/data-model-complete)<br>- [Microsoft Defender Threat Intelligence](/en-us/azure/security/fundamentals/threat-detection) |
| Unused app remediation | - Identify inactive apps using usage and sign-in logs<br>- Validate with service owners and allow for business-critical exceptions<br>- Apply soft deletion with a grace period, followed by permanent removal<br>- Run sensitive workloads in a trusted execution environment | - [Microsoft Entra recommendation: Remove unused credentials from apps](/en-us/entra/identity/monitoring-health/recommendation-remove-unused-credential-from-apps?tabs=microsoft-entra-admin-center)<br>- [Microsoft Entra recommendation: Remove unused applications](/en-us/entra/identity/monitoring-health/recommendation-remove-unused-apps?tabs=microsoft-entra-admin-center)<br>- [Data retention, deletion, and destruction in Microsoft 365](/en-us/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)<br>- [Quickstart: Create confidential VM on in the Azure portal](/en-us/azure/confidential-computing/quick-create-confidential-vm-portal) |
| Run sensitive workloads in a trusted execution environment | Create confidential VM on the Azure portal for sensitive workloads | [Create a confidential VM in the Azure portal](/en-us/azure/confidential-computing/quick-create-confidential-vm-portal) |
|  |  |  |

## Outcomes

Microsoft’s implementation of a centralized, comprehensive infrastructure inventory has led to:

- Faster threat detection and incident response due to improved signal clarity
- Consistent enforcement of Zero Trust policies across all managed assets
- Elimination of outdated or orphaned applications, reducing attack surface area
- Proactive posture management rooted in trusted, real-time telemetry

### Benefits

- 97% continuous tracking coverage across production environments
- Faster threat detection and incident response due to improved signal clarity
- Consistent Zero Trust enforcement across all managed assets
- Reduced attack surface by eliminating outdated or orphaned applications
- Trusted telemetry for proactive posture management

### Trade-offs

- Requires significant engineering investment in automation and telemetry standardization
- Demands cultural change to prioritize asset visibility across teams
- Restricts use of unmanaged or personal devices in favor of domain-joined systems
- Introduces risk of disruption if inactive but critical apps were removed without validation

## Key success factors

To track success, measure the following:

- Percentage of production assets with full inventory coverage
- Number of unmanaged or orphaned systems remediated
- Coverage percentage of infrastructure telemetry logging
- Time-to-detect and time-to-respond metrics before and after inventory implementation
- Volume of unused applications safely remediated per quarter

## Summary

A complete production infrastructure inventory is a foundational enabler of Secure by Design, Secure by Default, and Secure Operations in Microsoft’s Secure Future Initiative.

Organizations that commit to real-time asset visibility and telemetry standardization can strengthen their security posture, reduce operational risk, and enable faster, more effective response. Building a complete infrastructure inventory isn't only the best practice; it’s a critical requirement for resilient, scalable cybersecurity in the modern enterprise.

**Start building your inventory today—and enable threat detection that works with clarity, consistency, and confidence.**