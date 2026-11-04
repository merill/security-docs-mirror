---
layout: Conceptual
title: Monitor and detect threats in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-threat-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to monitor and detect threats in Microsoft's Secure Future Initiative (SFI).
ms.date: 2025-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 753b50eb-a8d3-79ee-46bb-5daee4d7788a
document_version_independent_id: 753b50eb-a8d3-79ee-46bb-5daee4d7788a
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-threat-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-threat-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-threat-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: db3f3fe0-0e22-a9c2-629c-b838c3884582
---

# Monitor and detect threats in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

The [Secure Future Initiative (SFI) initiative](secure-future-initiative-overview) is a multiyear, cross-Microsoft initiative to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services. SFI is build upon:

- A set of security principles that drive the way in which we innovate on security design, implement those innovations into Microsoft products as secure defaults and standards, and provide internal and external security guidance. [Learn more](secure-future-initiative-overview#security-principles).
- A set of prioritized security pillars and objectives. [Learn more](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist).

This article summarizes the "Monitor and detect threats" SFI pillar.

## Before you start

- [Learn about](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist) the SFI pillars.
- [Review and track the latest progress on pillar objectives](secure-future-initiative-whats-new#progress-on-pillar-objectives) in the SFI What's New article.
- Pillar objectives map to [Zero Trust principles](../zero-trust-overview), and to [NIST CSF functions and categories](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- [Get a list of NIST categories and acronyms](secure-future-initiative-overview#nist-functions) to help as you review the table in this article.

## Pillar and objectives

The aim of this pillar is to continuously monitor and rapidly detect security threats. Focus is on proactive, intelligence-driven detection to surface attacker behavior early, and enable rapid coordinated investigation across all business areas.

Microsoft objectives and Zero Trust/NIST mapping for this pillar are summarized in the following table.

| **Objective** | **Zero Trust** | **NIST mapping** |
| --- | --- | --- |
| **1. Centralize telemetry and infrastructure tracking**Maintain a current resource inventory across Microsoft production infrastructure and services. | **Verify explicitly**: Asset inventories and relevant logs provide the factual baseline required to continuously validate what exists and what should be monitored. Accurate inventories prevent resources not being visible, and ensure that decisions are based on correct and up-to-date assets.**Assume breach**: High-impact assets are prioritized for monitoring because compromise is assumed to be possible and impactful. | **ID-AM-01** (*Inventories of hardware managed by the organization are maintained*).Maintaining a complete inventory of physical infrastructure ensures defenders know which production assets must be monitored and protected.**ID-AM-02** (*Inventories of software, services, and systems managed by the organization are maintained*).Software and service inventories enable comprehensive telemetry collection across production environments.**ID-AM-05** (*Assets are prioritized based on classification, criticality, resources, and impact on the mission*).Asset prioritization ensures monitoring and protection focus on the most critical production components.**PR.PS-04** (*Log records are generated and made available for continuous monitoring*).Asset logging enables production systems to generate the telemetry required for threat detection. |
| **2. Security log retention standards**Retain security logs for at least two years, and make six months of appropriate logs available. | **Verify explicitly**: Retained logs allow validation of historical activity and investigative accuracy. You can validate who did what and when, and validate anomalous or malicious behavior.**Assume breach**: Long retention supports investigation of blended or persistent attack scenarios, even when attackers evade initial controls. External dependencies are monitored with the expectation that they might introduce risk. | **PR.PS-04** (*Log records are generated and made available for continuous monitoring*).Consistent log generation ensures that data exists to be retained and analyzed over time.**DE.CM-01** (*Networks and network services are monitored to find potentially adverse events*).Network logs retained over time support detection of patterns and delayed threat discovery.**DE.CM-02** (*The physical environment is monitored to find potentially adverse events*).Physical access logs contribute to long-term correlation of cyber and physical threats.**DE.CM-03** (*Personnel activity and technology usage are monitored to find potentially adverse events*).User and system activity logs provide evidence for insider and credential-based threat detection.**DE.CM-06** (*External service provider activities and services are monitored to find potentially adverse events*).Retained third-party activity logs support supply-chain threat detection and accountability.**DE.CM-09** (*Computing hardware and software, runtime environments, and their data are monitored to find potentially adverse events*).Endpoint and runtime telemetry retention enables forensic investigation and threat hunting. |
| **3. Centralized access to security logs**Retain security logs for at least two years, and make six months of appropriate logs available. | **Verify explicitly**: Centralized visibility enables validation across the entire environment.**Assume breach**: Multi-source correlation is required when attackers operate across systems. | **PR.PS-04** (*Log records are generated and made available for continuous monitoring*) Centralization requires logs to be consistently generated and accessible from production systems.**DE.AE-03** (*Information is correlated from multiple sources*)Centralized access enables correlation across network, identity, endpoint, and cloud telemetry. |
| **4. Rapid anomaly detection and response**Detect attacks quickly, and minimize the time in which attackers have access to internal resources. | **Verify explicitly**: Detection decisions are made on analyzed, validated evidence. Categorizing events ensures decisions are repeatable.**Assume breach**: Multi-source correlation is required when attackers operate across systems. | **DE.AE-02** (*Potentially adverse events are analyzed to better understand associated activities*).Analysis transforms raw signals into actionable indicators of compromise.**DE.AE-03** (*Information is correlated from multiple sources*).Correlation accelerates detection of complex, cross-domain attacks.**DE.AE-04** (*The estimated impact and scope of adverse events are understood*).Understanding scope and impact means faster prioritization of response actions.**DE.AE-06** (*Adverse events are categorized based on established classifications*).Classification supports consistent triage and escalation during active threats.**DE.AE-07** (*Events are analyzed to support determining the root cause of cybersecurity incidents*).Root-cause analysis enables durable remediation and prevention.**RS.CO-02** (*Internal and external stakeholders are notified of incidents*).Notifications ensure rapid coordination once anomalies are confirmed.**RS.MI-01** (*Incidents are contained, eradicated, and mitigated consistent with response plans*).Detected anomalies lead directly to mitigation and containment actions.**RS.MI-02** (*Incident response activities are tracked and communicated*).Tracking ensures response actions are coordinated, auditable, and effective. |