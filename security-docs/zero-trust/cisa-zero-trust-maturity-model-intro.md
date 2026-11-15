---
layout: Conceptual
title: Configure Microsoft cloud services for the CISA Zero Trust Maturity Model | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/cisa-zero-trust-maturity-model-intro
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: jricketts
description: Enable Zero Trust capabilities with integrated security tools for a secure and resilient cybersecurity framework.
ms.service: security
ms.topic: solution-overview
ms.date: 2026-11-04T00:00:00.0000000Z
ms.subservice: zero-trust
manager: martinco
ms.reviewer: kbrewer
locale: en-us
document_id: 7c59bb0a-168e-e5ce-1dbe-588b0b988cd6
document_version_independent_id: 7c59bb0a-168e-e5ce-1dbe-588b0b988cd6
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/cisa-zero-trust-maturity-model-intro.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/cisa-zero-trust-maturity-model-intro
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/cisa-zero-trust-maturity-model-intro.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: 89044d32-36d4-9fff-358a-cb19a12ad750
---

# Configure Microsoft cloud services for the CISA Zero Trust Maturity Model | Microsoft Learn

As cyber threats become increasingly sophisticated, the need for robust cybersecurity measures is more critical than ever. The U.S. Cybersecurity & Infrastructure Security Agency ([CISA](https://www.cisa.gov/)) plays a central role in defending cyberspace, spearheading national efforts to enhance the resilience of vital functions, and promoting a strong technology ecosystem. The CISA mission includes maintaining cyber situational awareness among Federal Civilian Executive Branch (FCEB) agencies, and securing the **.gov** domain. CISA assists federal agencies and industry partners with effective management of significant cyber incidents. In April 2023, CISA released the [Zero Trust Maturity Model Version 2.0](https://www.cisa.gov/zero-trust-maturity-model) (ZTMM).

Note

In this guidance, the term **organization** refers to FCEB agencies and industry partners.

The rapid adoption of new technologies, and the evolving threat landscape, pose ongoing challenges to cybersecurity. [Executive Order 14028: Improving the Nation's Cybersecurity](https://www.federalregister.gov/documents/2021/05/17/2021-10460/improving-the-nations-cybersecurity) emphasizes a renewed focus on modernizing federal cybersecurity, and endorses a Zero Trust Architecture ([ZTA](/en-us/security/zero-trust/zero-trust-overview)) as the preferred security model for government entities. The order mandates that organizations develop comprehensive plans for ZTA implementation. The order requires an assessment of the current cybersecurity posture and to prepare for full deployment.

The CISA ZTMM serves as a crucial roadmap for organizations to evaluate their security posture rigorously and implement necessary changes to transition to ZTA. By adopting this model, organizations can enhance their resilience significantly against cyber threats, ensure stronger protection of critical information assets, and fortify the overall security framework.

In support of this transition, Office of Management and Budget (OMB) [Memorandum M-22-09](https://www.whitehouse.gov/wp-content/uploads/2022/01/M-22-09.pdf) outlines actions to adopt in alignment with the ZTMM pillars. The Federal ZTA strategy requires organizations to meet key cybersecurity objectives and to consider **Executive Order (EO) 14028** and **M-22-09** as they develop and implement their Zero Trust strategies.

Microsoft offers an expanding range of Zero Trust capabilities powered by a unified platform of integrated security tools. The platform provides comprehensive coverage across CISA ZTMM pillars and the cross-cutting capabilities, described in the following section. These solutions support organizations in their journey toward effective Zero Trust implementation, helping to ensure a secure, and resilient, federal cybersecurity framework.

## How the CISA Zero Trust Maturity Model maps to SAF

The CISA Zero Trust Maturity Model (ZTMM) organizes Zero Trust maturity around five pillars and three cross-cutting capabilities. SAF uses a different but complementary model to organize the security work needed to achieve and sustain these outcomes.

The mapping below connects CISA Zero Trust maturity areas to relevant SAF security disciplines and technologies. It does not replace the CISA ZTMM or imply a one-to-one relationship between the two models. Organizations can use the mapping to identify the security work, technology areas, and Microsoft implementation guidance that support their Zero Trust maturity objectives.

In SAF, security disciplines describe the work needed to manage security risk and improve security capabilities, while technologies identify what must be protected. **The CISA cross-cutting capabilities span multiple technology areas and map primarily to SAF security disciplines.**

| CISA area | Primary SAF security disciplines | SAF technologies | Mapping rationale |
| --- | --- | --- | --- |
| **Identity** | [Access and Identity](security-adoption-discipline-identity-access); [Security Posture Management](security-adoption-discipline-posture); [SecOps](security-adoption-discipline-security-operations) | [Identity](deploy/identity); [Applications](deploy/applications) | Identity lifecycle, authentication, authorization, risk, access policy, and monitoring. |
| **Devices** | [Infrastructure Security](security-adoption-discipline-infrastructure); [Security Posture Management](security-adoption-discipline-posture); [SecOps](security-adoption-discipline-security-operations) | [Endpoints](deploy/endpoints); [Infrastructure](deploy/infrastructure) | Device identity, configuration, health, compliance, threat detection, and response. |
| **Networks** | [Infrastructure Security](security-adoption-discipline-infrastructure); [Security Architecture](security-adoption-discipline-architecture); [SecOps](security-adoption-discipline-security-operations) | [Network](deploy/networks); [Infrastructure](deploy/infrastructure) | Segmentation, traffic enforcement, network access, telemetry, and threat detection. |
| **Applications and workloads** | [Development Security](security-adoption-discipline-development); [Security Architecture](security-adoption-discipline-architecture); [Access and Identity](security-adoption-discipline-identity-access); [SecOps](security-adoption-discipline-security-operations) | [Applications](deploy/applications); [Infrastructure](deploy/infrastructure); [AI](/en-us/security/saf/technologies/ai/overview) where applicable | Secure development, workload identity, application access, runtime protection, and monitoring. |
| **Data** | [Data Security](security-adoption-discipline-data); [Access and Identity](security-adoption-discipline-identity-access); [Security Architecture](security-adoption-discipline-architecture) | [Data](deploy/data) | Discovery, classification, protection, access, encryption, and governance. |
| **Visibility and analytics** | [SecOps](security-adoption-discipline-security-operations); [Security Posture Management](security-adoption-discipline-posture) | [Spans technologies](deploy/overview) | Telemetry, detection, investigation, posture measurement, and analytics. |
| **Automation and orchestration** | [SecOps](security-adoption-discipline-security-operations); [Security Strategy, Integration, and Governance](security-adoption-discipline-strategy); [Development Security](security-adoption-discipline-development) where appropriate | [Spans technologies](deploy/overview) | Automated response, policy enforcement, orchestration, and integration. |
| **Governance** | [Security Strategy, Integration, and Governance](security-adoption-discipline-strategy); [Security Architecture](security-adoption-discipline-architecture); [Security Posture Management](security-adoption-discipline-posture) | [Spans technologies](deploy/overview) | Policy, ownership, risk management, measurement, and oversight. |

Microsoft implementation guidance is the downstream layer for applying these concepts with Microsoft technologies. It can support applicable CISA ZTMM objectives and capabilities, but it does not replace the authoritative CISA ZTMM and does not by itself demonstrate organizational achievement, maturity, or compliance. Start with the canonical [Security standards and frameworks](security-standards-and-frameworks) hub for related mappings and SAF guidance.

## Pillars, functions, capabilities, and ZTMM journey stages

The CISA ZTMM is built upon **five pillars** that encompass **functions** to enhance Zero Trust protection areas. Use the following links to go to sections of the guide:

- Introduction
- [Identity](cisa-zero-trust-maturity-model-identity)
- [Devices](cisa-zero-trust-maturity-model-devices)
- [Networks](cisa-zero-trust-maturity-model-networks)
- [Applications and workloads](cisa-zero-trust-maturity-model-apps)
- [Data](cisa-zero-trust-maturity-model-data)

Each pillar has three **cross-cutting capabilities**, which emphasize activities that enhance function interoperability across the pillars:

- **Visibility and analytics**: Visibility refers to observable artifacts from the characteristics of, and events in, enterprise-wide environments. The focus on cyber-related data analysis helps inform policy decisions, facilitate response activities, and build a risk profile to develop proactive security measures.
- **Automation and orchestration**: Zero Trust uses automated tools and workflows for security response functions across products and services. It helps enterprises maintain oversight, security, and development process interaction for such functions, products, and services.
- **Governance**: In this document, governance is the enforcement of enterprise cybersecurity policies, procedures, and processes, in and across pillars. Governance mitigates security risks in support of Zero Trust principles and to fulfill federal requirements.

    Note

    Visibility and analytics, automation and orchestration, and governance capabilities enable organizations to integrate advancements across pillars. The following image illustrates the pillars and cross-cutting capabilities.

    ![Diagram of the pillars and capabilities.](media/cisa-zero-trust-maturity-model/pillars-and-capabilities.png)

### ZTMM journey stages

The pillars span the ZTMM journey's four stages.

- **Traditional**: Manually configured lifecycles, for instance from establishment to decommission, and attribute assignments such as security and logging. Static security policies and solutions address pillars with dependencies on external systems. Least privilege is established at provisioning. Siloed pillars of policy enforcement; manual response and mitigation deployment, and limited correlation of dependencies, logs, and telemetry.
- **Initial**: Start automation of attribute assignment, lifecycle configuration, policy decisions, and enforcement. Initial cross-pillar solutions and external systems integration. Some responsive changes to least privilege after provisioning. Aggregated visibility for internal systems.
- **Advanced**: Where applicable, automate control of identity and access lifecycles, as well as configuration and policy assignment, with coordination across security pillars. Centralize visibility, identity control, and policy enforcement across the environment.

    Base responses on predefined mitigations, and dynamically adjust access toward least privilege based on risk signals and posture assessments. Extend awareness and governance across the entire enterprise, including externally hosted resources.
- **Optimal**: Automated, just-in-time (JIT) lifecycles and attribute assignments to assets and resources that can self-report with dynamic policies, based on automated and observed triggers. Use dynamic least privileged access, just-enough access (JEA) and within thresholds for assets and their dependencies; Enable cross-pillar interoperability with continuous monitoring, and centralized visibility with comprehensive situational awareness.

### Maturity model criteria

Use the following criteria to identify the maturity stage for Zero Trust technology pillars and provide consistency across the model:

[![Table of criteria for maturity stages.](media/cisa-zero-trust-maturity-model/maturity-stages.png)](media/cisa-zero-trust-maturity-model/maturity-stages-expanded.png#lightbox)

## Scope of guidance

Use this guidance to help meet the goals for ZTMM functions and make progress through maturity stages. We assume organizations are, at least, at the **Traditional** stage.

In the following sections, pillars are divided into function areas with tables that have the ZTMM journey stage descriptions with Microsoft guidance and recommendations. Use the tables to learn how Microsoft cloud services align to the ZTMM. Each function has guidance for maturity stages. For example, organizations that implement guidance at the **Optimal** stage, implemented **Advanced** stage guidance.

Note

Guidance is scoped to features in General Availability (GA), or in Public Preview, in Microsoft commercial clouds.

## Implementation approach

In most instances, multiple teams collaborate to guide an organization through lifecycle stages. Microsoft recommends your approach includes the following principles:

- Create a team with clear ownership of pillars and cross-cutting capabilities
- Ensure there are defined lines of communication and regularly updated status
- Integrate products across ZTMM pillars including cross-cutting capabilities

Organizations can reduce complexity, cost, and risk by using integrated solutions that meet the cross-cutting capabilities in the ZTMM. [Microsoft Security](/en-us/security/) products are integrated natively with [Microsoft Azure](/en-us/azure/cloud-adoption-framework/get-started/what-is-azure) and [Microsoft 365](/en-us/microsoft-365/admin/admin-overview/what-is-microsoft-365-for-business?view=o365-worldwide&amp;preserve-view=true). For instance, organizations can deploy [Microsoft Sentinel](/en-us/azure/sentinel/) as the security information and event management (SIEM) and security orchestration, automation, and response (SOAR) solution. In addition, incorporating extended detection and response ([XDR](/en-us/defender-xdr/microsoft-365-defender)) can strengthen the capabilities with insights and streamlined threat detection. Align these products across the ZTMM pillars to improve and enhance organizational cybersecurity capabilities.