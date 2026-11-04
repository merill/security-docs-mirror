---
layout: Conceptual
title: Accelerate response and remediation in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-response-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to accelerate response and remediation in Microsoft's Secure Future Initiative (SFI).
ms.date: 2025-11-03T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 5b28eda7-bccd-d887-869d-55c569ca1c20
document_version_independent_id: 5b28eda7-bccd-d887-869d-55c569ca1c20
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-response-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-response-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-response-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
platformId: c44608af-14bd-712b-3344-2438cafeb01b
---

# Accelerate response and remediation in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

The [Secure Future Initiative (SFI) initiative](secure-future-initiative-overview) is a multiyear, cross-Microsoft initiative to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services. SFI is build upon:

- A set of security principles that drive the way in which we innovate on security design, implement those innovations into Microsoft products as secure defaults and standards, and provide internal and external security guidance. [Learn more](secure-future-initiative-overview#security-principles).
- A set of prioritized security pillars and objectives. [Learn more](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist).

This article summarizes the "Accelerate response and remediation" SFI pillar.

## Before you start

- [Learn about](secure-future-initiative-overview#sfi-pillars-zero-trust-and-nist) the SFI pillars.
- [Review and track the latest progress on pillar objectives](secure-future-initiative-whats-new#progress-on-pillar-objectives) in the SFI What's New article.
- Pillar objectives map to [Zero Trust principles](../zero-trust-overview), and to [NIST CSF functions and categories](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- [Get a list of NIST categories and acronyms](secure-future-initiative-overview#nist-functions) to help as you review the table in this article.

## Pillar and objectives

The aim of this pillar is to quickly contain threats, restore trust, and improve resilience. It aims to minimize the impact and duration of security events and attacker dwell time in internal networks.

Microsoft objectives and Zero Trust/NIST mapping for this pillar are summarized in the following table.

| **Objective** | **Zero Trust** | **NIST mapping** |
| --- | --- | --- |
| **1. Accelerate vulnerability mitigation**Reduce "Time to Mitigation" for high-severity cloud security vulnerabilities with accelerated response. | **Verify explicitly**: Make decisions based on continuously validated vulnerability signals to ensure that mitigation actions are timely and accurate.**Assume breach**: Remediate with the assumption that vulnerabilities might already be exploited. | **ID.RA-01** (*Vulnerabilities in assets are identified, validated, and recorded*).  Ensures that vulnerabilities are accurately identified and validated so mitigation efforts focus on confirmed, high-risk exposures.**RS.AN-03** (*Analysis is performed to determine what has taken place during an incident and the root cause of the incident*).MRoot-cause analysis informs remediation by clarifying how vulnerabilities are exploited and what controls must be strengthened to prevent recurrence.**RS.MA-02** (*Incident reports are triaged and validated*).Vulnerability-driven incidents are triaged and validated to ensure remediation actions are based on reliable incident data.**RS.MA-03** (*Incidents are categorized and prioritized*).Categorization and prioritization ensure mitigation efforts address the most critical vulnerabilities first, reducing overall risk exposure.**RC.RP-01** (*Recovery plan is executed*).Recovery plans are executed to restore secure operations after vulnerabilities are mitigated or exploited.**RC.RP-02** (*Recovery actions are selected, scoped, prioritized, and performed*).Recovery actions are scoped and prioritized to align remediation speed with business impact and risk severity. |
| **2. Transparency of cloud vulnerabilities**Increase transparency of mitigated cloud vulnerabilities with the adoption and release of Common Weakness Enumeration (CWE) and Common Platform Enumeration (CPE) industry standards. Release high severity Common Vulnerabilities and Exposures (CVEs) affecting the cloud. | **Verify explicitly**: Public messaging is information by verified incident analysis, vulnerability status, and remediation process. **Use least privileged access**: Access to vulnerability data, reporting pipelines and disclosure mechanisms are governed and information is shared appropriately. | **ID.RA-01** (*Vulnerabilities in assets are identified, validated, and recorded*).Accurate identification and validation of cloud vulnerabilities ensures transparency is based on verified exposure rather than assumptions.**RS.CO-02** (*Internal and external stakeholders are notified of incidents*).Customers and partners are notified when cloud vulnerabilities represent meaningful security risk, enabling timely defensive action.**RS.CO-03** (*Information is shared with designated internal and external stakeholders*).Vulnerability information is shared in a structured and role-appropriate manner to support coordinated mitigation without unnecessary disclosure. |
| **3. Enhance public messaging and engagement**Improve the accuracy, effectiveness, transparency, and velocity of public messaging and customer engagement. | **Verify explicitly**: Public messaging is information by verified incident analysis, vulnerability status, and remediation process so that messaging is accurate and timely. | **GV-OV-01** (*Cybersecurity risk management strategy outcomes are reviewed to inform and adjust strategy and direction*).Public messaging reflects reviewed outcomes of cybersecurity risk management activities rather than isolated technical events.**GV-OV-02** (*The cybersecurity risk management strategy is reviewed and adjusted to ensure coverage of organizational requirements and risks*).Engagement activities are aligned with evolving organizational risk and stakeholder expectations.**GV-OV-03** (*Organizational cybersecurity risk management performance is measured and reviewed to confirm and adjust strategic direction*).Performance metrics inform transparent communication about progress, gaps, and improvement areas.**GV-RR-01** (*Organizational leadership is responsible and accountable for cybersecurity risk and fosters a culture that is risk-aware, ethical, and continually improving*).Leadership accountability ensures public engagement is credible, consistent, and aligned with organizational values.**GV-RR-02** (*Roles, responsibilities, and authorities related to cybersecurity risk management are established, communicated, and enforced*).Clear ownership of communication responsibilities prevents inconsistent or unauthorized public messaging.**GV-RR-03** (*Adequate resources are allocated consistent with the cybersecurity risk management strategy*).Sufficient resourcing enables sustained engagement with customers, researchers, and the broader ecosystem.**RS.CO-03** (*Information is shared with designated internal and external stakeholders*).Structured information sharing supports coordinated and trustworthy public engagement during security events.**RS.CO-04** (*Public updates on incident recovery are shared using approved methods and messaging*).Structured information sharing supports coordinated and trustworthy public engagement during security events.**RC.CO-03** (*Recovery activities and progress in restoring operational capabilities are communicated to designated internal and external stakeholders*).Structured information sharing supports coordinated and trustworthy public engagement during security events. |