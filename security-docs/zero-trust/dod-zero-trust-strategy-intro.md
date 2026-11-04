---
layout: Conceptual
title: Configure Microsoft cloud services for the DoD Zero Trust Strategy | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/dod-zero-trust-strategy-intro
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: jricketts
description: Minimize DoD attack surface, reduce risks, enable data-sharing and collaboration, safeguard the technical estate, and disrupt adversarial activities.
ms.service: security
ms.topic: solution-overview
ms.date: 2024-04-10T00:00:00.0000000Z
ms.subservice: zero-trust
manager: martinco
ms.reviewer: ehudi
locale: en-us
document_id: 760f5be0-84fb-46bb-66d2-b4c74a8fd574
document_version_independent_id: 760f5be0-84fb-46bb-66d2-b4c74a8fd574
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/dod-zero-trust-strategy-intro.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/dod-zero-trust-strategy-intro
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/dod-zero-trust-strategy-intro.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/486161dc-fa28-4625-9b1c-1a21d690bc8d
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/5dd28c86-729c-4723-ab5a-57e26fcec2a8
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
platformId: 0fffd6c3-ac65-657e-1c38-fc6f414bddef
---

# Configure Microsoft cloud services for the DoD Zero Trust Strategy | Microsoft Learn

The U.S. Department of Defense (DoD) Zero Trust Portfolio Management Office (ZT PfMO) was established to orchestrate DoD-wide Zero Trust adoption and execution. In November 2022, the DoD ZT PfMO released the [DoD Zero Trust Strategy and Roadmap](https://www.defense.gov/News/Releases/Release/Article/3225919/department-of-defense-releases-zero-trust-strategy-and-roadmap/).

The strategy and accompanying execution plans outline a path to adopt a new cybersecurity framework to facilitate well-informed, risk-based decisions. This model incorporates Zero Trust principles by eliminating traditional perimeters and trust assumptions, enabling a more efficient architecture that enhances security, user experience, and mission performance. The Zero Trust Framework aims to minimize DoD attack surface, reduce risks, enable effective data-sharing and collaboration, proactively safeguard its technical estate, and disrupt adversarial activities.

The strategy has four goals.

- **Zero Trust Cultural Adoption** - A Zero Trust security framework and mindset that guides the design, development, integration, and deployment of information technology across the DoD Zero Trust ecosystem.
- **Department of Defense Information Systems are Secured and Defended** - DoD cybersecurity practices incorporate and operationalize Zero Trust to achieve enterprise resilience in DoD information systems.
- **Technology Acceleration** - Zero Trust technologies deploy at a pace equal to, or that exceeds, industry advancements to remain ahead of the changing threat environment.
- **Zero Trust Enablement** - DoD Zero Trust execution integrates with DoD, and component-level processes, resulting in seamless and coordinated Zero Trust execution.

Microsoft has an expanding array of Zero Trust capabilities powered by a unified identity platform and pre-integrated, fit-for-purpose security tools. These security tools provide comprehensive coverage across the seven pillars of the DoD Zero Trust Strategy for target and advanced activities.

## Pillars, capabilities, and activities

The DoD Zero Trust Strategy covers seven pillars representing protection areas for Zero Trust. Use the following links to go to sections of the guide.

- Introduction
- [User](dod-zero-trust-strategy-user)
- [Device](dod-zero-trust-strategy-device)
- [Applications and workloads](dod-zero-trust-strategy-apps)
- [Data](dod-zero-trust-strategy-data)
- [Network](dod-zero-trust-strategy-network)
- [Automation and orchestration](dod-zero-trust-strategy-automation)
- [Visibility and analytics](dod-zero-trust-strategy-visibility)

The pillars span **45 Zero Trust capabilities**. Capabilities are achieved by completing one or more implementation activities. In the following tables, activities are tagged with `Target` or `Advanced`, based on Zero Trust phases defined by the DoD. A capability might include target activities, advanced activities, or both. See, Table 1. There are **152 activities** in total, 92 target and 60 advanced. DoD Zero Trust Capability Execution Roadmap sets a timeline for achieving **Target Level ZT** by 2027 and **Advanced Level ZT by 2032**.

![Table of zero trust capabilities and the seven pillars.](media/dod-zero-trust-strategy/zero-trust-capabilities.png)

Activity details are outlined in the [Zero Trust Capabilities and Activities Execution Roadmap](https://dodcio.defense.gov/Portals/0/Documents/Library/ZT-CapabilitiesActivities.pdf). The activities cover a range of technical and nontechnical tasks. Technical tasks deploy, configure, and adopt security tools. Nontechnical tasks procure tools, create policies and standards, and assemble teams to operationalize the Zero Trust strategy.

## Scope of guidance

This document has summary guidance for 45 Zero Trust capabilities and prescriptive guidance for completing 152 Zero Trust activities with Microsoft cloud services. In each table, the **Microsoft guidance and recommendations** column has activity-level guidance based on activity descriptions and outcomes in the context of the activity parent capability. Use the activity-level guidance with capability summaries to learn how Microsoft cloud services align to the DoD Zero Trust Strategy. Guidance is scoped to features generally available (GA) or in public preview in Microsoft 365 DoD cloud and Azure for US Government cloud.

Important

When activities have more than one part, Microsoft guidance assumes you implemented the previous parts. For example, if an activity has three parts, finish Pt1, then Pt2, and then Pt3.

This document prioritizes recommendations by product, or feature area, listing the most essential items first. When implementation actions span features in different Microsoft services, these actions are ordered in the required configuration sequence. Activity-level guidance lists all recommendations relevant for each activity. Your organization might complete the activity by doing a portion of the recommended configuration or implementing alternative solutions.

The DoD Zero Trust Strategy assigns activities to target or advanced phases. This guide indicates `Target` and `Adanced` in the activity title. Target-level ZT is achieved by completing all target activities. Advanced-level ZT is achieved by completing all advanced activities. You don't need to finish all target activities before starting advanced activities. Configuring one feature might complete target and advanced activities at the same time. We recommend implementing key protections first, following the [Microsoft Zero Trust Rapid Modernization Plan](/en-us/security/zero-trust/zero-trust-ramp-overview).