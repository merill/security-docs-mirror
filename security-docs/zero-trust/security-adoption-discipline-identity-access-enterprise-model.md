---
layout: Conceptual
title: Build an enterprise access architecture across the security adoption Identities and Access discipline | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-identity-access-enterprise-model
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to design an architecture for enterprise access within the security adoption Identities and Access discipline
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 87f613a2-d3e3-72de-820c-601ea51ea8a2
document_version_independent_id: 87f613a2-d3e3-72de-820c-601ea51ea8a2
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-identity-access-enterprise-model.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-identity-access-enterprise-model
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-identity-access-enterprise-model.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: ab3aae20-485b-8bb4-c9f9-3f708b6d33f9
---

# Build an enterprise access architecture across the security adoption Identities and Access discipline | Microsoft Learn

This article describes how to design an enterprise access model as part of an [Access and Identities discipline](security-adoption-discipline-identity-access).

It provides guidance for establishing an enterprise access architecture based on a coherent, Zero Trust model for understanding, designing, and governing all access paths to digital assets.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)** and provides architecture-level implementation guidance within the Access and Identities discipline.

## Why an enterprise access architecture?

Consistent and comprehensive policy enforcement is critical in preventing threat actors from using weak access controls to access your environment, and from escalating privileges during an attack.

Modern enterprises operate in complex environments where access isn't limited to internal users on corporate networks. People and processes who access include:

- Employees, partners, and customers
- Applications, services, and automation
- Administrators and operators with privileged permissions
- AI agents acting on behalf of users or autonomously

The enterprise access architecture provides a single architectural model for reasoning about all of these access paths consistently. Its purpose is to:

- Establish a shared way to understand how access is granted, controlled, and monitored.
- Unify general access and privileged access under Zero Trust principles.
- Prevent unintended privilege escalation across systems and environments.
- Support secure productivity across hybrid and multicloud platforms.

This architecture applies to logical access to digital assets. It doesn't address physical access to devices or facilities. Learn more about physical security in [Azure security fundamentals](/en-us/azure/security/fundamentals/physical-security).

## Architectural model overview

The enterprise access architecture organizes access using a few foundational concepts:

- **Architectural planes**, which describe where control and value reside
- **Access pathways** , which describe how users, systems, and administrators interact with assets.

Together, these concepts describe where business value lives, how it's accessed, and how attackers attempt to gain control.

### Data/Workload plane

The data and workload plane contains the systems where business value is created and stored, including:

- Business applications and services
- Data stores, models, and intellectual property

Because this plane holds the highest concentration of business value, it's the primary objective of most attacks.

[![Picture of enterprise access architecture data plane.](media/security-adoption-discipline-access-enterprise-data-plane.png)](media/security-adoption-discipline-access-enterprise-data-plane.png#lightbox)

## Management plane

The management plane enables organizations to deploy, configure, and operate workloads and platforms across on‑premises, cloud, and multicloud environments. Access to this plane allows operators to influence workloads at scale, making it a high‑value target for attackers.

## Control plan

The control plane enforces access decisions across the environment. It's typically anchored in enterprise identity systems and, where required, supporting network controls for constrained or legacy environments (for example, some OT systems).

Compromise of the control plane often enables indirect control of all other planes and therefore demands the strongest protections.

The diagram shows control and management planes in an enterprise access architecture. Both planes have inherent control over business‑critical assets, making them high‑value targets. Compromise of either plane often enables attackers to take control of the data/workload plane indirectly.

[![Picture of enterprise access architecture control and management planes.](media/security-adoption-discipline-access-enterprise-control-plane.png)](media/security-adoption-discipline-access-enterprise-control-plane.png#lightbox)

## Access pathways

To deliver business value, assets in these planes must be accessed through multiple pathways.

### User, agent, and application access

General access pathways include:

- **User access**: Employees, partners, and customers access systems through workstations and devices, often using remote access technologies.
- **Application access**: Services and workloads access other systems programmatically through APIs.
- **Agent access**: AI agents operating on behalf of users or acting autonomously using dedicated identities.

[![Picture of enterprise access architecture user, agent, and app access.](media/security-adoption-discipline-access-enterprise-user-app.png)](media/security-adoption-discipline-access-enterprise-user-app.png#lightbox)

Each of these pathways significantly expands the attack surface and must be governed consistently.

## Privileged access

In addition to general access, systems require privileged access for administration, operation, and maintenance.

Because privileged access enables broad control over business‑critical assets, it represents disproportionate risk and must be held to the highest assurance standards.

The enterprise access architecture ensures that privileged pathways are explicitly separated, controlled, and monitored, rather than being implicit extensions of general access.

[![Picture of enterprise access architecture privileged access.](media/security-adoption-discipline-access-enterprise-privileged.png)](media/security-adoption-discipline-access-enterprise-privileged.png#lightbox)

[Learn more](security-adoption-discipline-identity-access-privileged-model) about designing a privileged access architecture.

## Review core architectural principles

Effective enterprise access architectures consistently apply the following principles across all planes and pathways.

| **Principle** | **Details** |
| --- | --- |
| **Enforce Zero Trust** | Assume compromise of adjacent components.Explicitly validate trust for every access request.Apply least privilege consistently. |
| **Enable business processes** | Security controls must support legitimate work, not obstruct it. |
| **Apply consistent policy** | Enforce policy uniformly across users, admins, apps, APIs, and agents. |
| **Prevent privileges escalation** | Enforce clear separation between control, management, and workload planes. |
| **Continuously verify posture** | Audit configurations and monitor behavior indicative of attack |

## Evolution from the legacy AD tier model

The enterprise access architecture evolves the scope of the legacy Active Directory tier model, which focused on preventing privilege escalation in on‑premises Windows environments.

While effective for its time, the tier model didn't fully address modern realities such as:

- Cloud services and SaaS platforms
- External users and zero‑perimeter access
- APIs, service identities, and automation
- AI agents and multicloud environments

[![Picture of enterprise access modern.](media/security-adoption-discipline-access-enterprise-model.png)](media/security-adoption-discipline-access-enterprise-model.png#lightbox)

### Mapping legacy tiers

The enterprise access architecture preserves the security intent of the tier model while expanding it for modern environments.

- **Tier 0 &gt; Control plane**: Encompasses the full control plane, including identity systems, centralized access enforcement, and network controls.
- **Tier 1 &gt; Management and data/workload planes**: Separates into the management plane (protect enterprise-wide IT management functions) and per-workload administration performed by IT teams/business unities. This separation improves protection for high-value systems and DevOps operations.
- **Tier 2 &gt; General access pathways**: Covers users access (B2B, B2C, public) and expands to include application/API access pathways, and their attack surfaces.

## How to use this architecture

The enterprise access architecture isn't an implementation guide. Instead, it provides:

- A shared mental model for architects and security leaders
- A foundation for aligning identity, privileged access, and Zero Trust strategies
- A framework for evaluating and improving access‑related security decisions over time

Detailed implementation guidance is covered in related discipline and solution articles.