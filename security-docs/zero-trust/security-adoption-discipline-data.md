---
layout: Conceptual
title: Establish a Data Security discipline during security adoption | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-data
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the Microsoft security adoption model to modernize secure data across the business, based on Zero Trust principles.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 0f650eb7-e69b-abe5-3a3a-229722e69dd5
document_version_independent_id: 0f650eb7-e69b-abe5-3a3a-229722e69dd5
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-data.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-data
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-data.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/486161dc-fa28-4625-9b1c-1a21d690bc8d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/5dd28c86-729c-4723-ab5a-57e26fcec2a8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a06aedbc-fe4a-7acc-b108-78720adab2d4
---

# Establish a Data Security discipline during security adoption | Microsoft Learn

This article helps security and technology teams establish and modernize a Data Security discipline that protects data wherever it's created, stored, processed, shared, or used, while still enabling collaboration, analytics, cloud services, and AI adoption.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**, a broader body of guidance for planning, prioritizing, and implementing end-to-end security modernization. SAF connects business scenarios, security disciplines, and technical implementation so that strategy, architecture, operations, and controls work together rather than as isolated recommendations.

Within SAF, Data Security is a technical strategy discipline that applies lifecycle-based protection aligned to business value and risk.

## Why this discipline

Data is the lifeblood of modern organizations. It underpins business operations, decision‑making, and innovation, but it's also one of the most valuable assets targeted by attackers.

Traditional, network‑centric data protection approaches are no longer sufficient in environments that use cloud services, encryption, mobile devices, and distributed collaboration. A modern Data Security discipline moves beyond perimeter controls to identity‑aware, lifecycle‑based protection, aligned to business value and risk. Without effective data security, organizations face material business risk, including:

- Unintentional data exposure by employees using cloud service, personal devices, and AI.
- Malicious insider activity targeting sensitive information.
- Threat actors bypassing perimeter‑based controls in distributed environments.
- Ransomware and extortion attacks disrupting operations.
- Regulatory penalties, reputational damage, and—in some industries—life‑safety impacts.

A dedicated Data Security discipline provides the structure needed to reduce these risks while enabling secure and productive use of data across the organization.

## Mission and outcomes

The mission of the Data Security discipline is to protect the confidentiality, integrity, and availability of data assets throughout their lifecycle, enabling secure business operations and informed decision‑making.

A mature Data Security discipline delivers these core outcomes:

- **Data confidentiality**: Ensure only authorized users and systems can access data.
- **Data integrity**: Prevent unauthorized alteration or corruption of data.
- **Data availability**: Ensure data is accessible to authorized users when needed.

Failure in these outcomes can lead to data theft and abuse, disrupt business operations, enable fraud, expose regulated data, or even cause physical harm to people.

When you establish clear ownership, classification, and protection strategies, data security becomes an enabler of business outcomes rather than a constraint.

[![Diagram of the CIA triad illustrating confidentiality, integrity, and availability as core data security principles.](media/security-adoption-discipline-data-safety.png)](media/security-adoption-discipline-data-safety.png#lightbox)

## How to apply this discipline

To apply the Data Security discipline effectively, focus on establishing a consistent approach to protecting data based on its sensitivity and business impact:

1. **Define a data protection strategy aligned to business priorities and risk** Establish a clear approach for identifying, classifying, and protecting data based on its value and the risks associated with its exposure or misuse.
2. **Apply protection consistently across the data lifecycle** Ensure that data is protected wherever it resides, moves, or is used, including across devices, applications, and cloud environments.
3. **Establish standardized data protection policies and controls** Provide clear guidance to ensure sensitive data is handled, accessed, and shared in a consistent and secure manner across the organization.
4. **Align data protection with critical business assets and scenarios** Prioritize controls that protect high-value and regulated data, especially in scenarios such as protecting critical assets and enabling secure collaboration.
5. **Continuously monitor and improve data protection** Use insights from data usage, risk signals, and security events to refine protections and reduce the risk of data exposure or loss over time.

### Manage change

Traditional data security approaches often rely on a single control point, such as network‑based data loss prevention (DLP). This model is ineffective in modern environments because it:

- Operates only at limited points in the data lifecycle.
- Must perfectly balance protection and productivity in a single moment,
- Fails when data is encrypted, shared via cloud services, or accessed on personal devices.

This diagram summarizes the challenges to overcome using a modern approach to data security.

[![Diagram of the data security lifecycle highlighting challenges at each stage, including creation, storage, and transfer.](media/security-adoption-discipline-data-challenges.png)](media/security-adoption-discipline-data-challenges.png#lightbox)

A modern Data Security discipline focuses on continuous visibility and control across the entire data lifecycle.

## Key focus areas

Modern data security strategies emphasize:

| **Focus** | **Details** |
| --- | --- |
| **Prioritize critical data** | Protect the most business‑critical data first. |
| **Collaborate, coverage, visibility** | Collaborate across the business for full visibility of structured and unstructured data across devices, apps, and clouds, preventing data silos. |
| **Discover data** | Know where data exists and what value or sensitivity it has. |
| **Classify data** | Apply consistent labels so security controls can be applied automatically. |
| **Lifecycle protection** | Secure data regardless of the location, technical platform, device, or environment.Apply this strategy throughout the lifecycle of the data: **create**, **consume**, **store**, **share**, and **dispose**. Secure data during creation and generation, storage at rest, during access/sharing/use, and in transit, as well as data that is no longer active and archived or deleted. |
| **Monitoring and enforcement** | Implement real-time visibility and automated enforcement to detect and respond to real-time unauthorized access or exfiltration. |
| **Learn and improve** | Continuously improve data security. Adapt strategy and data controls as data formats, platforms, and use cases evolve, including AI. |

This approach enables protection that scales with business and technology change.

This diagram illustrates a high level data security strategy that enables both security and productivity.

[![Diagram of a data security strategy showing Zero Trust foundation, enterprise collaboration, and data lifecycle stages.](media/security-adoption-discipline-data-balance.png)](media/security-adoption-discipline-data-balance.png#lightbox)

In the diagram:

- The Zero Trust foundation, shown by a dotted line, establishes a modern identity boundary and data loss prevention between internal functions and the external environment. This foundation prevents unauthorized data loss, but enables collaboration with authorized external parties.
- The enterprise collaboration environment, in lighter green, is where most of your organizational data is created, processed, and stored. Limit access to internal users only and apply least privilege by default.
- Critical apps and data, in darker green, represent the most sensitive data in the organization that must be restricted to a limited set of authorized users and applications. You can share this data within the enterprise collaboration environment and with some authorized external parties, but it must be protected and monitored always.

## Discipline roles and collaborators

Data security requires close collaboration across business, security, and technology teams. In larger organizations, roles are often distributed and formalized; in smaller organizations, responsibilities might be combined.

Primary roles in this discipline typically include:

- Data Officer / Data Governance teams
- Data and AI architects
- Data and AI engineering and operations teams

Key collaborators include:

- **Business leaders and data owners** – Define data value, usage, and classification.
- **Security strategy and governance teams** – Define policies, standards, and oversight.
- **Architecture roles** – Integrate data security controls into system and platform designs.
- **Developers** – Implement secure data handling within applications.
- **Security‑adjacent disciplines** – Align data security with privacy, risk, and compliance efforts.

## Alignment with other disciplines

The Data Security discipline works in close coordination with other disciplines:

- **Access and Identities discipline**– Identity and access policies determine who can access data.
- **Security Architecture discipline** – Architecture defines end-to-end patterns for protecting data.
- **Security Operations (SecOps) discipline** – Detects and responds to data-related incidents.
- **Security Posture discipline** – Measures and improves data protection maturity.

Clear ownership and shared accountability are essential as data responsibilities expand.

## Alignment to technology pillars

Data travels across systems, users, and environments. As a result, the Data Security discipline spans all technology pillars.

[![Diagram of Zero Trust foundation with layers for enterprise collaboration, critical data, and technology pillars.](media/security-adoption-discipline-data-technology.png)](media/security-adoption-discipline-data-technology.png#lightbox)

Aligned technology pillars include:

- **Identities**: Data security relies on identity security controls to enforce secure access to data through strong identity and access controls.
- **Endpoints**: Data security relies on endpoint security controls to prevent data theft from compromised or unmanaged devices.
- **Infrastructure**: Data security relies on infrastructure security controls to protect data stored or processed on servers, containers, and cloud platforms.
- **Apps**: Data security relies on app security controls to ensure apps securely access and handle sensitive data.
- **Data**: Data security relies on data security controls to discover, classify, protect, and monitor data throughout its lifecycle. *- Network*: Data security relies on data security controls to help discover and secure data as it is transferred between systems.
- **AI**: Data security relies on AI security controls to protect data used to train, analyze, and generate AI outputs.