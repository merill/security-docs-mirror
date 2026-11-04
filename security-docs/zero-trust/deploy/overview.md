---
layout: Conceptual
title: Zero Trust deployment for technology pillars overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/deploy/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to deploy Zero Trust solutions to keep your organization secure.
ms.date: 2025-02-26T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: checklist
locale: en-us
document_id: 241412a7-aa89-5648-2860-4aa3e8e4c204
document_version_independent_id: a90de4a9-78c1-45d8-e77a-67035ace1b0d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/deploy/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/deploy/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/deploy/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: bad8ce03-c2e9-cf81-62cf-63c97c6bb30a
---

# Zero Trust deployment for technology pillars overview | Microsoft Learn

This article summarizes technology pillars in our [Zero Trust adoption model](../security-adoption-model).

Technology pillars represent the core areas of your security architecture. They group related capabilities and controls into logical domains such as identity, endpoints, data, apps, infrastructure, networks, and security operations.

Each pillar answers the same fundamental question:

**How do we apply Zero Trust principles to this part of the environment?**

Instead of thinking in terms of individual products or features, pillars provide a stable way to organize security design and implementation across your environment.

![Diagram of elements of visibility, automation, and orchestration in Zero Trust.](../media/diagram-zero-trust-security-elements.png)

## Technology pillars in the adoption model

Our structured adoption model focuses on three components:

- [Business scenarios](../security-adoption-business-scenarios-overview) - Define the most critical security outcomes for the organization. They focus on **why** we're adopting Zero Trust security.
- [Security disciplines](../security-adoption-discipline-overview) - Guide teams to define strategy, architecture, processes, and controls across common areas of security so that we can deliver the business scenarios. They focus on **what** Zero Trust capabilities are required.
- **Technology pillars** - Secure specific areas of the organization such as identity, data, and devices. They focus on **where** security capabilities are implemented.
- [Technical solutions](../implement-overview) - As adoption moves towards deployment, technical solutions provide detailed guidance for implementing security controls across technology pillars. They focus on **how** security is implemented.

In the Zero Trust adoption model, technology pillars sit between strategy and implementation.

Technology pillars don't define outcomes (business solutions) or steps (technical solutions), but they do:

- Define technical boundaries where security controls are applied. These boundaries are used by solutions to organize implementation guidance and logic.
- Act as the bridge between intent (why) and implementation (how).

## Pillars

| Technology pillar | Description |
| --- | --- |
| [![Fingerprint icon](../media/icon-identity-small.png)](identity)[Identities](identity) | Control access decisions. Every request starts with identity verification and enforcement of least privilege. |
| [![Endpoints icon.](../media/icon-endpoints-small.png)](endpoints)[Endpoints](endpoints) | Evaluate and enforce device trust. Access depends on device health, compliance, and risk. |
| [![Ones and zeroes icon.](../media/icon-data-small.png)](data)[Data](data) | Protect the asset itself. Security persists with the data through classification, labeling, encryption, and access control. |
| [![Application window icon.](../media/icon-applications-small.png)](applications)[Apps](applications) | Govern how data is accessed. Apply controls at the application and API layer, including permissions and session controls. |
| [![Data storage disks icon.](../media/icon-infrastructure-small.png)](infrastructure)[Infrastructure](infrastructure) | Secure compute resources. Harden servers, VMs, containers, and services through configuration, access control, and monitoring. |
| [![Network diagram icon.](../media/icon-networks-small.png)](networks)[Network](networks) | Control connectivity and movement. Segment and monitor traffic to prevent lateral movement and enforce secure communication. |
| [![Gear icon.](../media/icon-visibility-automation-orchestration-small.png)](visibility-automation-orchestration)[SecOps](visibility-automation-orchestration) | Integrate and operationalize all pillars. Detect, investigate, and respond using signals from across the environment. |

## Zero Trust implementation workshops

Microsoft's Zero Trust implementation workshops are available for each pillar. [Learn more](../workshop-zero-trust-overview).

## What's next?

- [Review](../implement-overview) technical solutions.
- [Learn about](../security-adoption-model) our Zero Trust adoption model.
- [Review](../security-adoption-business-scenarios-overview) critical security business scenarios.