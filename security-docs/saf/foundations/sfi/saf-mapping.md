---
layout: Conceptual
title: How Microsoft Secure Future Initiative (SFI) informs SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/foundations/sfi/saf-mapping
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn how lessons, principles, and priorities from Microsoft's Secure Future Initiative inform Security Adoption Framework guidance.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 474abbea-e3ab-22e9-dc6d-3cb3da31eeee
document_version_independent_id: 474abbea-e3ab-22e9-dc6d-3cb3da31eeee
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/foundations/sfi/saf-mapping.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/foundations/sfi/saf-mapping
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/foundations/sfi/saf-mapping.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 01c9b90f-6486-ffcc-c26a-8216b1f42359
---

# How Microsoft Secure Future Initiative (SFI) informs SAF | Microsoft Learn

The Microsoft Secure Future Initiative (SFI) and Security Adoption Framework (SAF) serve different but complementary purposes:

- **SFI** is Microsoft's internal, multiyear security transformation program. It provides lessons from Microsoft's experience improving security across engineering, operations, governance, architecture, and organizational practices.
- **SAF** is customer-facing guidance for structuring and sustaining security modernization based on an organization's business priorities and risks.

SAF incorporates relevant lessons and practices from Microsoft's SFI experience without reproducing SFI's internal organizational model. Organizations can use these lessons within their own security programs while adapting them to their risks, technology estate, capabilities, regulatory requirements, and organizational structure.

## How SFI informs SAF

SFI provides several types of experience that inform SAF guidance:

1. **Culture and governance**: Microsoft's transformation reinforces the importance of executive accountability, security culture, governance, risk management, organizational roles, and security architecture.
2. **Security principles**: Secure by Design, Secure by Default, and Secure Operations inform how security is planned, designed, implemented, and operated.
3. **Engineering priorities**: SFI's six engineering pillars show where Microsoft prioritized improvements across identity, tenants, networks, engineering systems, detection, and response.
4. **Implementation experience**: Practices developed and refined through SFI provide examples of how organizations can make security improvements repeatable, measurable, and sustainable.

These SFI concepts inform SAF, but they do not become a separate SAF taxonomy. SAF organizes customer security modernization around business priorities and risk, security disciplines, technologies that must be protected, and technical implementation.

## Culture, governance, and architecture

Microsoft's SFI transformation extends beyond technical controls. It also includes changes to culture, governance, accountability, risk management, and architecture.

These elements connect primarily to the following SAF security disciplines:

| SFI area | Relevant SAF security discipline |
| --- | --- |
| Security culture, training, and organizational accountability | Strategy, Integration, and Governance |
| Cybersecurity governance and policy | Strategy, Integration, and Governance |
| Managing and mitigating security risk at scale | Strategy, Integration, and Governance; Security Posture |
| End-to-end security architecture | Security Architecture |

These mappings illustrate relationships between Microsoft's SFI experience and customer-facing SAF guidance. Organizations should adapt these practices to their own governance structures, decision rights, risk management processes, and operating models.

## SFI security principles

SFI is guided by three security principles:

- **Secure by Design**: Integrate security requirements into architectures and engineering decisions from the beginning.
- **Secure by Default**: Design and operate technologies with strong baseline protections and safer default configurations.
- **Secure Operations**: Continuously detect, respond, recover, and improve based on threat intelligence, operational evidence, and lessons learned.

These principles apply broadly across SAF rather than mapping to a single discipline or technology. They influence security strategy, architecture, development, implementation, and operations.

SFI also applies Zero Trust principles throughout Microsoft's security transformation. SAF provides customer-facing guidance for applying Zero Trust across business and security decisions, architecture, technologies, implementation, and operations.

## Map SFI engineering priorities to SAF

SFI execution is organized around six engineering pillars. These pillars identify areas where Microsoft prioritized change within its own environment.

The following mapping provides a navigation bridge from SFI priorities to relevant SAF guidance. It does not imply structural equivalence between SFI and SAF and is not an objective-by-objective or activity-by-activity crosswalk.

| SFI engineering priority | Relevant SAF security disciplines | Relevant SAF technologies |
| --- | --- | --- |
| Protect identities and secrets | Access and Identity; Security Architecture | Identity; Applications |
| Protect tenants and isolate systems | Access and Identity; Security Architecture; Infrastructure Security | Identity; Infrastructure; Network |
| Protect networks | Infrastructure Security; Access and Identity; Security Architecture | Network; Infrastructure |
| Protect engineering systems | Development Security; Security Architecture | Applications; Infrastructure |
| Monitor and detect cyberthreats | SecOps/SOC; Security Posture | Cross-technology telemetry and security signals |
| Accelerate response and remediation | SecOps/SOC; Security Posture; Strategy, Integration, and Governance | Cross-technology response and remediation |

Many SFI priorities span multiple SAF disciplines and technologies. This reflects the cross-functional nature of security work rather than a one-to-one relationship between the two models.

## Learn from SFI implementation experience

SFI also provides implementation lessons that can help organizations translate security priorities into repeatable practices.

For example, SFI uses **paved paths** to make secure practices easier to adopt consistently. Paved paths provide approved patterns, tools, and approaches that help teams perform common work in a secure and repeatable way.

Paved paths are an SFI implementation approach, not a SAF taxonomy. SAF can incorporate lessons from approaches such as paved paths while allowing organizations to select implementation models appropriate to their own technologies, teams, risks, and operating environments.

## How to use this mapping

Use SFI, this mapping, and SAF for different purposes:

- **Use SFI** to understand Microsoft's security priorities, transformation experience, and lessons learned.
- **Use this mapping** to identify SAF security disciplines and technologies related to those lessons.
- **Use SAF** to organize security modernization around your organization's business priorities, risks, roles, technology estate, and implementation needs.
- **Use Microsoft architecture, technology, and product guidance** to design, implement, and sustainably operate the resulting security capabilities.

This approach lets organizations learn from Microsoft's experience without assuming that Microsoft's internal organizational structure or implementation model should be reproduced directly.