---
layout: Conceptual
title: Security standards and frameworks | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-standards-and-frameworks
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how to use the Microsoft Security Adoption Framework (SAF) to align security work with security standards and frameworks and connect it to practical security guidance and technology implementation.
ms.date: 2026-11-10T00:00:00.0000000Z
ai-usage: ai-assisted
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 6e354630-7374-0fb4-27ca-81358a98fff9
document_version_independent_id: 6e354630-7374-0fb4-27ca-81358a98fff9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-standards-and-frameworks.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-standards-and-frameworks
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-standards-and-frameworks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
platformId: d11afc9b-2e3f-b03f-815a-8e5a2af64e65
---

# Security standards and frameworks | Microsoft Learn

Security standards and frameworks help organizations define security objectives, practices, and requirements. The Microsoft Security Adoption Framework (SAF) helps translate these standards and frameworks into coordinated security work across business, technology, and security roles and connects that work to technology implementation. You don't need to adopt SAF instead of an existing standard or framework. SAF can help translate the objectives and requirements you already use into coordinated security work and technology implementation.

This guidance helps organizations understand how established security standards and frameworks relate to SAF and Microsoft security technologies. The framework mappings provide more detailed alignment where available.

Organizations can use this guidance and the mappings to:

- **Translate standards and framework objectives into actionable security work.** Connect objectives, practices, and requirements to SAF security disciplines, roles, and responsibilities.
- **Plan and implement security improvements.** Identify relevant security capabilities, technologies, implementation guidance, and Microsoft products that can help address framework objectives and organizational priorities.
- **Coordinate work across business, technology, and security teams.** Provide shared context for planning, architecture, implementation, operations, and security oversight.
- **Assess progress and communicate alignment.** Relate security improvements and implemented capabilities back to the objectives and requirements of the standard or framework.

These mappings help organizations apply standards and frameworks using SAF and Microsoft security technologies. They don't replace authoritative standards, frameworks, or requirements, and they don't by themselves demonstrate compliance.

Security and compliance have different purposes, but they reinforce each other. Effective, risk-driven security establishes repeatable controls, clear ownership, operational processes, and measurable evidence. Organizations can map applicable regulatory, contractual, and industry requirements to those security practices and controls. Good security makes compliance easier to achieve, demonstrate, and sustain, but it doesn't automatically satisfy every compliance obligation.

## Zero Trust

Zero Trust provides the security principles that underpin SAF. SAF helps organizations apply these principles across business decisions, security practices, technology design, implementation, and operations.

Use these resources to understand Zero Trust and connect it to SAF:

- [Zero Trust overview](zero-trust-overview) explains the Zero Trust principles and how organizations can apply them across their security strategy.
- [Zero Trust frameworks and standards](security-zero-trust-frameworks) connects Zero Trust guidance to established frameworks, standards, and related implementation guidance.

## Framework mappings

Use these mappings to connect objectives from established security frameworks and strategies to SAF security disciplines and technologies. From there, use technical solutions and Microsoft product guidance to support implementation. **This connects each framework to SAF while preserving its original structure, terminology, and intent.**

### NIST Cybersecurity Framework 2.0

Use the [NIST Cybersecurity Framework 2.0 mapping](/en-us/security/saf/framework-mappings/nist-cybersecurity-framework) to connect the CSF Core, Organizational Profiles, and Tiers to SAF disciplines, current role actions, technologies, technical solutions, and relevant Microsoft implementation guidance.

### CIS Controls and CIS Benchmarks

Use the [CIS Controls and CIS Benchmarks mapping](/en-us/security/saf/framework-mappings/cis-controls-benchmarks) to distinguish organization-level CIS Controls and Implementation Groups from technology-specific CIS Benchmarks, assign role actions, and connect the work to SAF and implementation guidance.

### The Open Group Zero Trust model

Use [The Open Group Zero Trust model mapping](/en-us/security/saf/framework-mappings/open-group-zero-trust) to connect current Zero Trust capabilities, security roles, and Architecture Building Blocks (ABBs) to SAF and selected Microsoft technology examples. The page distinguishes published Open Group material from evolving draft and Snapshot material.

### CISA Zero Trust Maturity Model

Use the [CISA Zero Trust Maturity Model mapping and implementation guidance](cisa-zero-trust-maturity-model-intro) to connect CISA's five pillars and three cross-cutting capabilities to relevant SAF security disciplines and technologies, then continue to Microsoft implementation guidance.

### DoD Zero Trust Strategy

Use the [DoD Zero Trust Strategy mapping and implementation guidance](dod-zero-trust-strategy-intro) to navigate from DoD Zero Trust pillars and capability areas to relevant SAF security disciplines and technologies, then continue to Microsoft implementation guidance.

## Use a standard or framework as a SAF starting point

Build security around business and security risk, then map applicable compliance requirements to the resulting practices and controls. You can also use a standard or framework as a practical starting point when your organization already uses it, must meet specific requirements, or wants established structure for security improvements.

To use a standard or framework as a SAF starting point:

1. **Identify business and security risks and the outcomes that matter.**
2. **Identify relevant objectives, practices, or requirements** from the applicable standard or framework.
3. **Connect them to SAF security disciplines** to understand the work, ownership, and operational processes needed.
4. **Identify the technologies that must be protected** and the roles involved.
5. **Use technical solutions and Microsoft product guidance** to select implementation options.
6. **Map applicable compliance requirements to the resulting practices and controls**, and collect measurable evidence through normal operations.
7. **Assess progress and alignment** against organizational outcomes and applicable framework or standard objectives.

Security does not equal compliance. Alignment or compliance alone doesn't define security success, and effective security doesn't automatically establish compliance. SAF helps organizations connect framework-driven work to broader security outcomes, strategy, architecture, implementation, and operations while reusing consistent controls, ownership, processes, and evidence across applicable requirements.

## Choose your path

### Security leaders and governance teams

- [Organize the security improvement program with SAF](security-adoption-model).
- [Use SAF effectively across the adoption journey](security-adoption-journey).
- Continue to the framework mappings to connect requirements and objectives to security work, roles, and technologies.

### Architects and practitioners

- [Plan integrated capabilities with MCRA](microsoft-reference-architecture).
- [Modernize end-to-end security architecture](security-adoption-discipline-architecture).
- [Connect Microsoft security products and platforms to outcomes](security-platform).
- [Continue from framework objectives to technical solutions](implement-overview).

## Related SAF guidance

- [Microsoft Security Adoption Framework (SAF)](security-adoption-model)
- [Using SAF effectively](security-adoption-journey)
- [Security disciplines overview](security-adoption-discipline-overview)
- [Technologies](deploy/overview)
- [Technical solutions](implement-overview)