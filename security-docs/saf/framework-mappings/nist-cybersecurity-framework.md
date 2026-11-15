---
layout: Conceptual
title: Map NIST Cybersecurity Framework 2.0 to SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/framework-mappings/nist-cybersecurity-framework
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Use NIST Cybersecurity Framework 2.0 outcomes, Profiles, and Tiers with Microsoft Security Adoption Framework roles, disciplines, technologies, and implementation guidance.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: df9fe62c-b963-6e62-5a38-6ebc4fab4812
document_version_independent_id: df9fe62c-b963-6e62-5a38-6ebc4fab4812
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/framework-mappings/nist-cybersecurity-framework.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/framework-mappings/nist-cybersecurity-framework
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/framework-mappings/nist-cybersecurity-framework.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
platformId: 746a2443-d33c-3845-6de4-09cdcd2c5298
---

# Map NIST Cybersecurity Framework 2.0 to SAF | Microsoft Learn

Organizations use the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF) 2.0 to understand, assess, prioritize, and communicate cybersecurity outcomes. The Microsoft Security Adoption Framework (SAF) helps organize the work and role actions needed to move from current to target outcomes.

Use the models together without treating them as structurally equivalent:

- **NIST CSF 2.0** defines cybersecurity outcomes and provides a common language for managing cybersecurity risk.
- **Zero Trust principles** inform security decisions across the lifecycle.
- **SAF business scenarios, security disciplines, technologies, and technical solutions** connect risk and desired outcomes to coordinated planning and execution.
- **Microsoft technologies and services** can implement parts of that work, but product deployment alone doesn't demonstrate achievement of a CSF outcome.

Important

NIST remains the authoritative source for the CSF. This mapping is interpretive guidance for using CSF 2.0 with SAF; it isn't a NIST endorsement, a control mapping, or evidence of compliance.

## Understand the CSF 2.0 operating model

CSF 2.0 has three complementary components:

- **Core**: A taxonomy of cybersecurity outcomes organized into Functions, Categories, and Subcategories. The six Functions are GOVERN, IDENTIFY, PROTECT, DETECT, RESPOND, and RECOVER.
- **Organizational Profiles**: A way to describe an organization's current and target cybersecurity outcomes. Use a Current Profile and Target Profile to identify and prioritize gaps in organizational context.
- **Tiers**: A way to characterize the rigor of cybersecurity risk governance and management practices. Use Tiers as context for improvement and communication, not as a simplistic maturity score or certification level.

The Core describes **what outcomes matter**. Profiles identify **where the organization is and where it intends to go**. Tiers help leaders discuss **how consistently cybersecurity risk is governed and managed**. SAF helps define **who acts, what work they perform, and where implementation applies**.

## Connect CSF Functions to SAF work and roles

Role names in this mapping follow the role model used in [Security roles and responsibilities in SAF](/en-us/security/zero-trust/security-adoption-roles), which is based on The Open Group Security Roles and Glossary material.

| NIST CSF 2.0 Function | Primary SAF work | Typical role actions | Technology scope |
| --- | --- | --- | --- |
| **GOVERN (GV)** | Strategy, Integration, and Governance; Security Architecture; Security Posture Management | Members of the Board of Directors and executive, product, and business leaders set priorities, risk tolerance, and accountability. Security Business Architects/Analysts, Security Compliance Management, Cyber Supply Chain Risk Management, and Security Posture Management translate direction into policy, roadmaps, measures, and oversight. Chief, Enterprise, and Security Architects establish architectural direction. | Cross-cutting across all technologies |
| **IDENTIFY (ID)** | Security Posture Management; Security Architecture; Strategy, Integration, and Governance | Product and Business Line Leaders, Product Owners, and Business Architects/Analysts identify critical business operations and assets. Security Posture Management measures exposure and gaps. Security Architects and technical engineering and operations roles maintain inventories, dependencies, ownership, and risk context. | Identities, Endpoints, Apps, Data, Infrastructure, Network, AI, and OT/IoT where applicable |
| **PROTECT (PR)** | Access and Identity; Data Security; Development Security; Infrastructure Security; OT/IoT Security; Security Architecture | Security, Access, Infrastructure, Data, Solution, and Software/Application Architects define reusable patterns and requirements. Identity, Network, User Endpoint, Infrastructure/Platform, Data, OT/ICS, and Security Engineers implement and operate safeguards. Software Security Engineers and development roles build protections into applications and delivery processes. Security Posture Management measures control coverage and drift. | All technologies, based on the assets and business processes in scope |
| **DETECT (DE)** | Security Operations (SecOps/SOC); Security Posture Management; Security Architecture | SecOps Platform and Data Engineers provide reliable telemetry and analytics. Detection Engineers design and test detections. Threat Intelligence informs priorities. Triage and Investigation Analysts validate and investigate activity. Security Architects ensure telemetry and detection requirements are designed into systems. | Cross-cutting across all technologies |
| **RESPOND (RS)** | Security Operations (SecOps/SOC), with affected business, technology, legal, communications, and governance roles | Incident Coordination and Management orchestrates the response. Triage and Investigation Analysts, Threat Hunters, Digital Forensics Specialists, and Reverse Engineers determine scope and impact. Technical engineering and operations roles contain and remediate. Accountable leaders make authorized business and risk decisions; Legal and Communications/Public Relations manage their respective obligations. | Cross-cutting, driven by affected assets and business operations |
| **RECOVER (RC)** | Business Management and Operations; Infrastructure Security; Data Security; SecOps/SOC; Security Posture Management; Security Architecture | Product Line Managers/Directors and Product Owners set business restoration priorities. Technical engineering and operations roles restore services and data to a trusted state. Incident Coordination and Management coordinates recovery. Investigation and Digital Forensics roles preserve evidence and lessons. Posture and architecture roles feed corrective actions into baselines, designs, and roadmaps. | Primarily Infrastructure, Data, Identities, and Apps, with dependencies across the estate |

These are typical actions, not a universal RACI model. Assign one accountable decision-maker for each material outcome, delegate responsibilities explicitly, and document escalation and exception paths.

## Use CSF Categories as a navigation layer

Use the Category-level mapping to find the primary SAF work and continue to detailed implementation guidance.

| CSF Function and Categories | Primary SAF security disciplines | Useful SAF starting points |
| --- | --- | --- |
| **GOVERN** (GV.OC, GV.RM, GV.RR, GV.PO, GV.OV, GV.SC) | Strategy, Integration, and Governance; Security Architecture; Security Posture Management | [Strategy, Integration, and Governance](/en-us/security/zero-trust/security-adoption-discipline-strategy), [Security Architecture](/en-us/security/zero-trust/security-adoption-discipline-architecture), [security roles](/en-us/security/zero-trust/security-adoption-roles) |
| **IDENTIFY** (ID.AM, ID.RA, ID.IM) | Security Posture Management; Security Architecture; Strategy, Integration, and Governance | [Security Posture Management](/en-us/security/zero-trust/security-adoption-discipline-posture), [technologies](/en-us/security/zero-trust/deploy/overview), [Zero Trust assessment](/en-us/security/zero-trust/assessment/overview) |
| **PROTECT** (PR.AA, PR.AT, PR.DS, PR.PS, PR.IR) | Access and Identity; Data Security; Development Security; Infrastructure Security; OT/IoT Security; Security Architecture | [Security disciplines](/en-us/security/zero-trust/security-adoption-discipline-overview), [technologies](/en-us/security/zero-trust/deploy/overview), [technical solutions](/en-us/security/zero-trust/implement-overview) |
| **DETECT** (DE.CM, DE.AE) | Security Operations (SecOps/SOC); Security Posture Management; Security Architecture | [SecOps/SOC](/en-us/security/zero-trust/security-adoption-discipline-security-operations), [SecOps operating patterns](/en-us/security/saf/disciplines/security-operations/implementation-patterns), [SecOps roles](/en-us/security/zero-trust/security-adoption-discipline-security-operations-roles) |
| **RESPOND** (RS.MA, RS.AN, RS.CO, RS.MI) | SecOps/SOC; Strategy, Integration, and Governance; affected technical disciplines | [Incident response readiness](/en-us/security/zero-trust/security-operations-incident-response-readiness), [incident response playbooks](/en-us/security/zero-trust/security-operations-incident-response-playbooks) |
| **RECOVER** (RC.RP, RC.CO) | Business Management and Operations; Infrastructure Security; Data Security; SecOps/SOC; Security Posture Management | [Minimize business damage from security incidents](/en-us/security/zero-trust/security-adoption-scenario-minimize-impact), [Infrastructure Security](/en-us/security/zero-trust/security-adoption-discipline-infrastructure), [Using SAF effectively](/en-us/security/zero-trust/security-adoption-journey) |

## Use Profiles and Tiers with SAF

Use this operating flow to turn a CSF assessment into coordinated work:

1. **Set scope and business context.** Identify the business operations, assets, dependencies, risk owners, and decision authority in scope.
2. **Create or update the Current Profile.** Record applicable CSF outcomes and the evidence that describes the current state.
3. **Define a risk-informed Target Profile.** Select and prioritize outcomes based on mission, threats, legal and contractual obligations, dependencies, and risk tolerance.
4. **Use Tiers as governance context.** Discuss how repeatable, integrated, and adaptive cybersecurity risk-management practices need to be for the scope. Don't use Tiers as a pass/fail score.
5. **Map gaps to SAF.** Connect each material gap to a business scenario, security discipline, technology, accountable role, and responsible roles.
6. **Choose architecture and implementation changes.** Use reference architectures, technical solutions, and product guidance to design the required people, process, and technology changes.
7. **Execute and measure.** Track implementation, control effectiveness, business impact, exceptions, and residual risk.
8. **Reassess and improve.** Update Profiles, architecture, operations, and roadmaps as business priorities, technologies, threats, and evidence change.

## Avoid common mapping errors

- Don't convert every CSF outcome directly into a product feature. Many outcomes depend on governance, architecture, operating processes, and human decisions.
- Don't map every Function to every discipline without identifying the primary work and role actions. Broad applicability is different from primary ownership.
- Don't treat a Target Profile as a fixed end state. Review it when business context or risk changes.
- Don't treat Tiers as maturity certifications or use them to rank organizations without context.
- Don't use framework alignment as a substitute for measuring security effectiveness and residual risk.