---
layout: Conceptual
title: Centralize access to security logs - Microsoft Secure Future Initiative | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/centralize-access-to-security-logs
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Centralize access to security logs is part of the Monitor and detect threats pillar of the Secure Future Initiative (SFI). This pillar supports Microsoft environments providing high-fidelity signals, comprehensive visibility, and advanced detection capabilities to identify and respond to evolving threats
ms.date: 2025-10-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: c355eb7e-ba26-4590-7d0b-9b4583b86dc7
document_version_independent_id: c355eb7e-ba26-4590-7d0b-9b4583b86dc7
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/centralize-access-to-security-logs.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/centralize-access-to-security-logs
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/centralize-access-to-security-logs.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
platformId: 5ba69fdf-670e-61c1-65e8-619eaa2af411
---

# Centralize access to security logs - Microsoft Secure Future Initiative | Microsoft Learn

**Pillar name: Monitor and detect threats** **Pattern name: Centralize access to security logs**

Security logs are essential for monitoring threats and supporting investigations, but without centralization and standardization, they can create more management overhead and slow down response times. Microsoft addressed these challenges by centralizing log access, standardizing data capture, and extending retention periods, enabling faster, more effective investigations. These measures, alongside AI-powered detection and expanded log retention for customers, improve overall security and forensic capabilities.

## Context and problem

Security logs are critical tools for security staff, as they reveal who accessed what, when, and how. Logs support continuous monitoring of threat activity, speed up incident response, and provide forensic records for security investigations.

Yet without centralization and standardization, logs can create more problems than they solve. Inconsistent formats, disparate storage locations, and variable retention periods make it difficult to quickly piece together a complete picture of an attack. At Microsoft, investigations were slowed by fragmented log sources and gaps in retention that left security teams unable to trace initial access points or lateral movement paths.

## Solution

As part of SFI, Microsoft centralized access to security logs and extended retention policies. Key measures include:

- **Standardized security logging library**: Ensures consistent data capture across services, reducing observability gaps.
- **Centralized log collection**: Specialized investigator accounts provide unified access to cross-service logs, simplifying correlation and speeding up investigations.
- **Extended log retention**: Audit logs retained for up to two years across Microsoft services, to enable forensic investigation of long-term attack patterns.
- **Advanced detection analytics**: Integration of machine learning and AI-powered models improves detection of complex attack techniques and reduces false positives.
- **Expanded customer logging**: Microsoft increased standard audit log retention for Microsoft 365 customers to 180 days, with options for longer retention.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Standardized logging | - Use Microsoft Purview auditing solution for Microsoft Entra and Microsoft 365 applications logs (for example, Exchange Online, SharePoint, OneDrive).<br>- Implement a common log library across applications and services to enforce consistent fields (identity, actions, timestamps). | - [Learn about auditing solutions in Microsoft Purview](/en-us/purview/audit-solutions-overview)<br>- [Microsoft Sentinel data lake overview](/en-us/azure/sentinel/datalake/sentinel-lake-overview) |
| Central log storage | - Use Microsoft Sentinel's data lake to transform SIEM with AI and unified security data.<br>- Direct all security logs into a central repository, accessible to authorized investigators.<br>- Centralize access to logs with Azure's Monitor and Log Analytics to reduce blind spots.<br>- Use Microsoft Sentinel's security information and event management (SIEM) solution to enhance visibility and context for security logs and data, threat investigation, and response. | - [Microsoft Sentinel data lake overview - Microsoft Security](/en-us/azure/sentinel/datalake/sentinel-lake-overview)<br>- [Azure Monitor Logs](/en-us/azure/azure-monitor/logs/data-platform-logs)<br>- [Microsoft Sentinel data connectors](/en-us/azure/sentinel/connect-data-sources?tabs=defender-portal)<br>- [Microsoft Entra security operations for infrastructure](/en-us/entra/architecture/security-operations-infrastructure) |
| Encryption and immutable storage | - In Azure Monitor, you can secure log data in transit and encrypt Log Analytics data at rest in Azure Storage using Microsoft-managed keys (MMK)<br>- Encrypt logs in transit and at rest, and store them immutably to preserve forensic integrity, using Microsoft Sentinel's data tiering for cost-efficient retention.<br>- We recommend using immutable to protect from overwrites and deletes. | - [Log Analytics workspace overview](/en-us/azure/azure-monitor/logs/log-analytics-workspace-overview)<br>- [Secure your Azure Monitor deployment](/en-us/azure/azure-monitor/fundamentals/best-practices-security)<br>- [Encryption at rest in Azure Storage](/en-us/azure/storage/common/storage-service-encryption#about-azure-storage-service-side-encryption)<br>- [Immutable storage](/en-us/azure/storage/blobs/immutable-storage-overview)<br>- [Manage data tiers and retention in Microsoft Sentinel](/en-us/azure/sentinel/manage-data-overview) |
| Real-time monitoring | - Set up continuous monitoring and alerts with Azure Monitor and Microsoft Sentinel to detect suspicious activity or logging coverage gaps.<br>- In Azure Monitor and Log Analytics, you can monitor, improve logging coverage, and alert on suspicious activities using KQL queries and alert rules<br>- Microsoft Sentinel provides advanced monitoring and detection features such as real-time log ingestion, analytics rules to watch ingested data, log matching against threat intelligence, alert grouping into incidents, and security orchestration, automation, and response (SOAR) capabilities. | - [Log queries in Azure Monitor](/en-us/azure/azure-monitor/logs/log-query-overview)<br>- [Azure Monitor diagnostics settings](/en-us/azure/azure-monitor/essentials/diagnostics-settings-policies-deployifnotexists)<br>- [Monitor Azure resources with Azure Monitor](/en-us/azure/azure-monitor/platform/monitor-azure-resource)<br>- [Log ingestion with data connectors](/en-us/azure/sentinel/connect-data-sources)<br>- [Detect and analyze anomalies using KQL in Azure Monitor](/en-us/azure/azure-monitor/logs/kql-machine-learning-azure-monitor)<br>- [Quick threat detection with near-real-time (NRT) analytics rules in Microsoft Sentinel](/en-us/azure/sentinel/near-real-time-rules) |
| Advanced analytics | - Correlate logs across services using AI/ML and integrate with threat intelligence feeds.<br>- Correlate logs in Azure Monitor and Log Analytics using KQL queries to connect signals across data sources.<br>- Apply advanced analytics in Microsoft Sentinel with prebuilt rule libraries that map to common attack patterns, user and entity behavior analytics (UEBA) for anomaly detection, AI-powered alert correlation, ML-driven anomaly detection, and logs enriched with threat intelligence. | - [Microsoft Sentinel documentation](/en-us/azure/sentinel/)<br>- [Threat detection in Microsoft Sentinel](/en-us/azure/sentinel/threat-detection)<br>- [Advanced threat detection with User and Entity Behavior Analytics (UEBA) in Microsoft Sentinel](/en-us/azure/sentinel/identify-threats-with-entity-behavior-analytics)<br>- [Alert correlation in Microsoft Sentinel](/en-us/azure/sentinel/relate-alerts-to-incidents)<br>- [Threat intelligence - Microsoft Sentinel](/en-us/azure/sentinel/understand-threat-intelligence) |
| Review cadence | - Conduct quarterly reviews to validate coverage, retention compliance, and pipeline integration.<br>- Optimize SOC processes with Microsoft best practices and guidance on security operations. | - [Azure Monitor best practices](/en-us/azure/azure-monitor/best-practices-security#log-ingestion-and-storage)<br>- [Optimize security operations](/en-us/azure/sentinel/soc-optimization/soc-optimization-access?tabs=defender-portal) |

## Benefits

- **Improved visibility:** Provides security teams with a unified view of activity across identities, infrastructure, applications and endpoint devices.
- **Faster investigations:** Investigators can correlate events across services without manual searches or format conversion.
- **Forensic readiness:** Extended retention ensures security teams can analyze long-term attack campaigns.
- **Proactive detection:** AI-driven analytics surface emerging attack patterns earlier.
- **Regulatory alignment:** Supports compliance with standards requiring centralized, retained audit evidence.

## Trade-offs

- **Increased storage costs:** Extending retention and centralizing logs requires scalable infrastructure.
- **Access governance complexity:** Centralized investigator accounts must be strictly controlled to prevent misuse.
- **Operational overhead:** Teams must maintain log libraries, pipelines, and monitoring tools across services.
- **Signal-to-noise balance:** Centralized logging increases data volume, requiring investment in advanced filtering and analytics.

## Key success factors

To track success, measure the following: 

- Percentage of services using the standardized logging library.
- Number of pipelines and services successfully forwarding logs to the central repository.
- Mean time to investigate (MTTI) reduced by centralized access.
- Compliance with two-year audit log retention standard.
- Detection accuracy improvements from AI/ML-enhanced analytics.

## Summary

Centralizing access to security logs transforms fragmented monitoring data into actionable intelligence. By standardizing log formats, consolidating collection, extending retention, and applying AI-driven analytics, Microsoft has improved both the speed and effectiveness of its threat detection and investigation.

Organizations can adopt this approach by ensuring consistent log formats, enforcing central storage and immutability, extending retention for forensic readiness, and integrating logs with advanced analytics platforms. These steps enable security teams to monitor and detect threats with clarity and precision---turning logs from scattered records into a powerful, unified security capability.

**Centralize your security logs today to reduce blind spots, accelerate investigations, and stay ahead of evolving threats.**