---
layout: Conceptual
title: Securing privileged access Enterprise access model - Privileged access | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/privileged-access-workstations/privileged-access-access-model
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: None
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Securing privileged access is part of an enterprise access model
ms.service: security
ms.subservice: privileged-access
ms.topic: concept-article
ms.date: 2026-05-06T00:00:00.0000000Z
ms.reviewer: mas
locale: en-us
document_id: 0b36b279-1be4-1202-7d28-f00730da46c3
document_version_independent_id: 0b36b279-1be4-1202-7d28-f00730da46c3
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/privileged-access-workstations/privileged-access-access-model.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: privileged-access-workstations/privileged-access-access-model
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/privileged-access-workstations/privileged-access-access-model.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/b1cfdec6-b0c3-4209-818c-736879856e0e
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d0723c1-cf38-4c30-ab3d-5df787b33270
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 5cf17754-4929-65a0-75e9-309686d923ac
---

# Securing privileged access Enterprise access model - Privileged access | Microsoft Learn

This document describes an overall enterprise access model that includes context of how a [privileged access strategy](privileged-access-strategy) fits in. For a roadmap on how to adopt a privileged access strategy, see the [rapid modernization plan (RaMP)](security-rapid-modernization-plan). For implementation guidance to deploy this, see [privileged access deployment](privileged-access-deployment)

Privileged access strategy is part of an overall enterprise access control strategy. This enterprise access model shows how privileged access fits into an overall enterprise access model.

The primary stores of business value that an organization must protect are in the Data/Workload plane:

![Data/workload plane](media/privileged-access-strategy/data-workload-plane.png)

The applications and data typically store a large percentage of an organization's:

- **Business processes** in applications and workloads
- **Intellectual property** in data and applications

The enterprise IT organization manages and supports the workloads and the infrastructure they are hosted on, whether it's on-premises, on Azure, or a third-party cloud provider, creating a **management plane**. Providing consistent access control to these systems across the enterprise requires a **control plane** based on centralized enterprise identity system(s), often supplemented by network access control for older systems like operational technology (OT) devices.

![Control, management, and data/workload planes](media/privileged-access-strategy/control-management-data-workload-planes.png)

Each of these planes has control of the data and workloads by virtue of their functions, creating an attractive pathway for attackers to abuse if they can gain control of either plane.

For these systems to create business value, they must be accessible to internal users, partners, and customers using their workstations or devices (often using remote access solutions) - creating **user access** pathways. They must also frequently be available programmatically via application programming interfaces (APIs) to facilitate process automation, creating **application access** pathways.

![Adding user and application access pathways](media/privileged-access-strategy/user-app-control-management-data-workload-planes.png)

Finally, these systems must be managed and maintained by IT staff, developers, or others in the organizations, creating **privileged access** pathways. Because of the high level of control they provide over business critical assets in the organization, these pathways must be stringently protected against compromise.

![Privileged access pathway to manage and maintain](media/privileged-access-strategy/privileged-access-over-underlying-planes.png)

Providing consistent access control in the organization that enables productivity and mitigates risk requires you to

- Enforce Zero Trust principles on all access
    - Assume Breach of other components
    - Explicit validation of trust
    - Least privilege access
- Pervasive security and policy enforcement across
    - Internal and external access to ensure consistent policy application
    - All access methods including users, admins, APIs, service accounts, etc.
- Mitigate unauthorized privilege escalation
    - Enforce hierarchy – to prevent control of higher planes from lower planes (via attacks or abuse of legitimate processes)
        - Control plane
        - Management plane
        - Data/workload plane
    - Continuously audit for configuration vulnerabilities enabling inadvertent escalation
    - Monitor and respond to anomalies that could represent potential attacks

## Evolution from the AD tier model

The enterprise access model builds on the AD tier model, which focused on containing unauthorized escalation of privilege in an on-premises Windows Server Active Directory environment.

![AD tier model](media/privileged-access-strategy/legacy-tier-model.png)

The enterprise access model incorporates these elements as well as full access management requirements of a modern enterprise that spans on-premises, multiple clouds, internal or external user access, and more.

![Complete enterprise access model from old tiers](media/privileged-access-strategy/legacy-tier-model-comparison-new.png)

### Tier 0 scope expansion

Tier 0 expands to become the control plane and addresses all aspects of access control, including networking where it is the only/best access control option, such as legacy OT options

### Tier 1 splits

To increase clarity and actionability, what was tier 1 is now split into the following areas:

- **Management plane** – for enterprise-wide IT management functions
- **Data/Workload plane** – for per-workload management, which is sometimes performed by IT personnel and sometimes by business units

This split ensures focus for protecting business critical systems and administrative roles that have high intrinsic business value, but limited technical control. Additionally, this split better accommodates developers and DevOps models vs. focusing too heavily on classic infrastructure roles.

### Tier 2 splits

To ensure coverage for application access and the various partner and customer models, Tier 2 was split into the following areas:

- **User access** – which includes all B2B, B2C, and public access scenarios
- **App access** – to accommodate API access pathways and resulting attack surface