---
layout: Conceptual
title: Overview - Security disciplines | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about security disciplines in the Microsoft security adoption model.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: a8075e57-d6eb-75a6-93ae-8e7dc468619b
document_version_independent_id: a8075e57-d6eb-75a6-93ae-8e7dc468619b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
platformId: 662add93-f4e5-6f97-8d50-29b082398e0b
---

# Overview - Security disciplines | Microsoft Learn

This article provides an overview of security disciplines in the **Microsoft Security Adoption Framework (SAF)**.

In SAF, security disciplines provide the middle layer between [business scenarios](security-adoption-business-scenarios-overview) and [technical implementation](implement-overview), helping organizations turn strategic priorities into coordinated execution.

Security disciplines are **structured areas of accountability** that help organizations translate business security goals into coordinated action across the enterprise. They provide a consistent way to organize strategy, architecture, and operations to manage risk and protect critical business outcomes.

Rather than treating security as isolated controls or individual tools, security disciplines organize processes, skills, and technologies into repeatable capability areas. This helps ensure that security investments deliver measurable, end‑to‑end outcomes, not fragmented improvements.

Collectively, the security disciplines form a complete security operating model that enables:

- Clear security strategy and governance,
- Coherent, end‑to‑end architectures.
- Consistent technical implementation and operations.

Security disciplines are applied through business scenarios, such as securing remote work or protecting critical assets. These scenarios define where security efforts should be focused to reduce risk and support the business.

Tip

Microsoft offers a rich set of security adoption workshops - the *Security Adoption Framework (SAF) workshops*. Our structured adoption model, including security discipline guidance, that we describe here aligns with the expert-led guidance available in the workshops. Learn more about our [SAF workshops](workshop-business-overview).

## Security disciplines in adoption

In SAF, security disciplines provide an organizational structure between business scenarios and technical implementation.

- [**Business scenarios**](security-adoption-business-scenarios-overview) define **why** security investment is needed and what outcomes matter.
- Security disciplines define ownership and accountability across teams, clarifying **who** is responsible for delivering each area of security capability across the organization.
- [Technical solutions](implement-overview) define **how** security is implemented across specific [technology pillars](deploy/overview).

[![Diagram showing how disciplines bridge business outcomes and technical implementation, organized by discipline type.](media/disciplines.png)](media/disciplines.png#lightbox)

## How to use security disciplines

Security disciplines are used throughout in our structured adoption model. They align to Zero Trust guidance to support different audiences:

- Business leaders and program owners use disciplines to understand how security business scenarios come to life to protect assets and manage business risk.
- Security leaders and architects use disciplines to shape end‑to‑end designs and ensure consistency across technology pillars.
- Implementation and operations teams use disciplines to guide tooling choices, control deployment, detection, and ongoing improvement.

## Discipline categories

Each security discipline fits into one of three categories, based on the type of decisions it supports and when it is applied in the security lifecycle.

- **Planning and oversight disciplines**: These disciplines establish direction, alignment, and accountability across the entire security program. They define what success looks like and how progress is measured and governed.
- **Technical strategy disciplines**: These disciplines define how security is designed and implemented technically. They provide architectural direction that guides control selection, tooling, and execution across multiple technology areas.
- **Operational disciplines**: These disciplines define how security runs day to day, including continuous visibility, detection, response, and improvement as threats and environments change.

The diagram below illustrates how security categories and disciplines, and how they align across technology pillars.

[![Diagram of security disciplines guiding security adoption.](media/security-adoption-disciplines.png)](media/security-adoption-disciplines.png#lightbox)

## Security disciplines

The following table shows the disciplines, the category they belong to, and the technology pillars that they're focused on protecting.

| **Disciplined/Category** | **Discipline** | **Pillar** |
| --- | --- | --- |
| **[Security Strategy, Integration, and Governance](security-adoption-discipline-strategy)**Planning and oversight. | Establishes the overall security vision, priorities, policies and success measures. It ensures security efforts are aligned to business goals and risk tolerance, and that progress is measurable and governed. | All pillars. |
| **[Security Architecture](security-adoption-discipline-architecture)**Planning and oversight. | Ensures that security controls, technologies, and processes work together as a cohesive system. It aligns architecture decisions across identity, data, applications, infrastructure, and operations to deliver consistent outcomes. | All pillars. |
| **[Access and Identity](security-adoption-discipline-identity-access)**Technical strategy | Secures how users, devices, applications, and workloads access organizational assets. This discipline drives a consistent, identity‑centric approach using Zero Trust principles across all access paths, including networking and privileged access. | Identity, networks, endpoints. |
| **[Infrastructure Security](security-adoption-discipline-infrastructure)** Technical strategy | Ensures that the workloads and platforms that run the business are secure across hybrid and multicloud environments for new development and legacy apps. | Infrastructure. |
| **[Development Security](security-adoption-discipline-development)** Technical strategy | Ensures applications and services are designed, built, and maintained securely as pat of a DevSecOps approach and a security development lifecycle (SDL). This includes secure coding practices, and application security testing. | Apps. |
| **[Data Security](security-adoption-discipline-data)** Technical strategy | Protects data assets such as intellectual property, trade secrets, and regulated information. This discipline applies security controls throughout the full data lifecycle, regardless of where data is stored or how it moves. It is a critical enabler of safe Generative AI usage. | Data. |
| **[OT/IoT Security](security-adoption-discipline-iot)** Technical strategy | Secures OT/IoT systems that interact with physical processes and the physical world, including industrial control systems and SCADA environments. | Endpoints. |
| **[Security Posture Management](security-adoption-discipline-posture)**Operational | Continuously discovers, measures, and prioritizes security risks. It helps organizations focus remediation efforts on the most impactful vulnerabilities and attack paths. | All pillars. |
| **[SecOps](security-adoption-discipline-security-operations)** Operational | Detects, responds to, and recovers from active threats. This discipline focuses on rapid response, to minimize the time attackers have access after compromise, and thus limiting their business impact. | All pillars. |