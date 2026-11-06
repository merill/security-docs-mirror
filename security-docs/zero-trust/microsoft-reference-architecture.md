---
layout: Conceptual
title: Microsoft Cybersecurity Reference Architectures (MCRA) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/microsoft-reference-architecture
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Plan security modernization with the help of the MCRA reference architectures.
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.date: 2026-11-06T00:00:00.0000000Z
locale: en-us
document_id: 9d8a2026-85e2-e89e-c4c5-4eaaa65e50dd
document_version_independent_id: 9d8a2026-85e2-e89e-c4c5-4eaaa65e50dd
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/microsoft-reference-architecture.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/microsoft-reference-architecture
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/microsoft-reference-architecture.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/302444b9-4a43-4841-8014-3d9e4251ff15
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/de19c5b8-e208-412e-9238-db3f631dea5b
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bebd8809-dac1-4c22-83e2-66d98af8a94d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ea7bf5d6-7154-4ba9-8ebc-59117ccacd49
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 7607e975-76b9-0aef-8863-0bb6532d8c72
---

# Microsoft Cybersecurity Reference Architectures (MCRA) | Microsoft Learn

The Microsoft Cybersecurity Reference Architecture (MCRA) provides an extensive set of technical architectures for use during Zero Trust security adoption and modernization.

MCRA architectures capture the end-to-end security journey for the *hybrid of everything* technology estate and span across legacy IT, multicloud, OT/IoT, AI, and more.

The architectures help you to accelerate planning and execution of security modernization using open standards, Microsoft’s security solutions, and third-party security technologies.

The MCRA is a component of the [Microsoft Security Adoption Framework (SAF)](security-adoption-model) that provides a standardized process for planning, prioritizing, designing, and implementing security modernization across an organization based on Zero Trust principles.

## Recent MCRA updates

[Download the latest version of the MCRA](https://download.microsoft.com/download/692e68d0-ddaf-44d7-8136-378f01d9f4a1/MCRA-June-2026.pptx), published in June 2026.

[![Screenshot of some of the diagrams included in the updated Microsoft Cybersecurity Reference Architecture.](media/reference-architecture-overview.png)](media/reference-architecture-overview.png#lightbox)

### Key changes

Key changes in the latest release from the earlier April 2025 version.

| \**Change/Update* | **Details** |
| --- | --- |
| **Main Menu** | Updated design to align to [security adoption model](security-adoption-model). |
| **Introduction** | Updated these slides: *Antipatterns*, *Security is hard*Added two assumptions, and Zero Trust description. |
| **Data Security Reference Architecture** | Added new diagram. |
| **Standards Mapping** | Updated proposed drafts of Zero Trust Reference Model standard (The Open Group), and Microsoft mapping to them. |
| **AI** | Updated most slides in the section. |
| **People** | Updated roles list from The Open Group.Added example guidance from CEO role. |
| **Microsoft Products** | Updated design to align to [security adoption model](security-adoption-model). |
| **New solution/service** | Added Microsoft Agent 365 to attack chain, standards mappings, role mappings, product references, and reference architectures (Capabilities, Identity, Security Operations, and Data Security). |
| **New solution/service** | Added Microsoft Foundry to Infrastructure and Multicloud reference architectures. |
| **Cross-slide** | Threat intelligence daily signals updated to 100+ trillion. |

## MCRA structure

MCRA illustrates how Microsoft capabilities work together and includes:

- Antipatterns (common mistakes) and best practices.
- Threat trends and attack patterns.
- The importance of end-to-end security and ruthlessly security work prioritization.
- Guidance for successful Zero Trust end-to-end security adoption.
- Mapping Microsoft capabilities to Zero Trust standards and roles.

MCRA architecture diagrams cover:

- Microsoft cybersecurity capabilities
- Zero Trust user access
- Security operations (SecOps/SOC)
- Operational technology (OT)
- Multicloud and cross-platform capabilities
- Attack chain coverage
- Infrastructure and development security
- Security organizational functions

## How do I use the MCRA?

You typically use the architectures as a:

- **Starting template for a security architecture** - Use MCRA architectures to define a target state for cybersecurity capabilities. It's useful because it covers capabilities across the modern enterprise estate that spans on-premises, mobile devices, multiple clouds, and OT/IoT Technology.
- **Comparison reference for security capabilities** - Compare Microsoft's recommendations with what you own and implement. Organizations often find they have technology they weren't aware of.
- **Learning tool for Microsoft** - In presentation mode, each capability has a "ScreenTip" with a short description of each capability, and a link to documentation to learn more.
- **Learning tool for security integration** - Architects and technical teams can identify and use integration points in Microsoft security capabilities and their existing capabilities.
- **Learning tool for cybersecurity** - For people new to cybersecurity, the resources provide a learning tool as they take their first steps.