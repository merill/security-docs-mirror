---
layout: Conceptual
title: Adopt secure development planning imperatives | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-development-imperatives
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Plan how to integrate security into development practices across the software lifecycle.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 0bd4c76d-0262-2a63-f297-cae4c0b7b7a8
document_version_independent_id: 0bd4c76d-0262-2a63-f297-cae4c0b7b7a8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-development-imperatives.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-development-imperatives
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-development-imperatives.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 2d660f83-2f0b-766c-83c5-52bf78260aef
---

# Adopt secure development planning imperatives | Microsoft Learn

This article defines the planning imperatives for integrating security into development practices as part of the [Development Security discipline](security-adoption-discipline-development).

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**. Use these imperatives to translate the discipline into planning and release expectations. Use [Shift DevOps to DevSecOps](security-adoption-discipline-development-security) for the operating-model and process changes that put them into practice.

Modern organizations depend on rapid software delivery to innovate and respond to change. Integrate security into development strategy, workflows, and release decisions so that delivery speed does not create unmanaged security or operational risk.

## Outcomes

Use these planning imperatives to:

- Reduce security weaknesses in production workloads.
- Make production-readiness decisions more consistent.
- Reduce unhealthy friction between development, security, and operations.
- Improve the resilience of workloads and delivery infrastructure.
- Sustain delivery velocity while managing security and operational risk.

## Recognize the scope of development security

Plan for more than application code. Include the people, identities, tools, environments, automation, dependencies, and infrastructure used to design, build, deploy, and operate workloads.

Account for:

- Application logic, services, and APIs.
- Infrastructure as code and deployment configurations.
- Source repositories, build systems, and release pipelines.
- Developer environments and service identities.
- Third-party and open-source components.
- Production platforms and operational tooling.

Use the [Development Security discipline](security-adoption-discipline-development) for the full scope and its relationships with other SAF disciplines.

## Account for key risks

Include these risk areas when defining requirements and priorities:

| Risk area | Example impact |
| --- | --- |
| **Application design and implementation** | Unauthorized access, data exposure, or persistent flaws in business logic. |
| **Development infrastructure and automation** | Stolen credentials, unauthorized changes, or tampered build artifacts. |
| **Developer environment** | Compromised identities, source code, tools, or privileged access. |
| **Software supply chain** | Malicious or vulnerable dependencies that affect the organization or downstream customers. |
| **Operations** | Extended exposure or disruption caused by weak configuration, monitoring, patching, or recovery. |

Use these risks to shape design, workflow, assurance, and governance decisions for both the workload and the systems used to deliver it.

## Integrate security into strategy and the lifecycle

Define security, privacy, safety, and compliance requirements alongside business, functional, and operational requirements. Connect them to:

- Product and development strategy.
- Architecture and design.
- Delivery and release workflows.
- Operational support and recovery models.

Use a continuous Security Development Lifecycle (SDL) approach:

- Define requirements while teams still have practical design options.
- Align architecture and implementation with those requirements.
- Integrate security into infrastructure automation and delivery pipelines.
- Validate important requirements throughout delivery and before release.
- Track findings in normal engineering workflows and prioritize remediation by risk.
- Feed vulnerabilities, incidents, and operational lessons back into planning and design.

Product and engineering teams are accountable for the functionality, security, reliability, and operational outcomes of the software they deliver. Development, security, and operations roles have distinct responsibilities. Security specialists define and interpret security requirements, provide expertise and reusable patterns, enable teams with tools and education, challenge risk decisions, and advise authorized decision makers.

## Set minimum production viability in the secure definition of done

Use **minimum production viability** as the release quality gate within the team's **secure definition of done**. It is the minimum set of development, security, and operations requirements that a workload needs for production use. A minimum viable product is not production-ready based on functionality alone.

Before each production release, verify all three dimensions:

| Requirement | Minimum outcome for production use |
| --- | --- |
| **Development** | The software meets the required business and user needs. |
| **Security** | The software meets the security, safety, privacy, and compliance requirements appropriate to its risk. |
| **Operations** | The software meets the quality, performance, reliability, supportability, monitoring, and recovery requirements for production use. |

Treat these dimensions as concurrent inputs to one release decision, not as sequential maturity stages. Tailor the rigor to the workload's business impact, exposure, and regulatory obligations.

Define decision authority and escalation paths explicitly. For an exception, record the unmet requirement, business rationale, compensating controls, expiration date, and remediation plan. Only a person with delegated authority may approve the exception and accept the residual risk.

## Integrate security into development workflows

Use the same planning, backlog, defect, approval, and release mechanisms for security work that teams use for other engineering work.

Integrate security activities into:

- **Design**: Apply secure patterns, threat modeling, and architecture review where risk warrants them.
- **Build**: Validate code, dependencies, secrets, infrastructure as code, and configurations.
- **Delivery**: Protect repositories, branches, pipelines, identities, artifacts, and release actions.
- **Operations**: Monitor, patch, detect, respond, recover, and feed lessons back into engineering.

Manage security findings through the normal defect workflow and release decision process. Block release when an unmet requirement exceeds the risk that an authorized decision maker can accept. Validate continuously instead of relying only on a final checkpoint.

## Apply policy-driven security guardrails

Use policy-driven guardrails to apply requirements consistently without creating unnecessary delivery friction. Include:

- Identity and access requirements.
- Configuration and compliance standards.
- Deployment and release controls.

Integrate guardrails into platform foundations, development workflows, and deployment automation. Automate repeatable checks when practical, tune noisy controls, and preserve human review for consequential decisions.

For a balanced approach to security and delivery speed, review [policy-driven guardrails](/en-us/azure/cloud-adoption-framework/ready/enterprise-scale/dine-guidance).

## Sustain and improve

Update development security practices as workloads, threats, regulations, delivery models, and business priorities change.

- Define shared objectives for functionality, security, reliability, and delivery flow.
- Use metrics that show both risk reduction and the effect of controls on engineering work.
- Prevent any one discipline from dominating tradeoffs by default.
- Review delivery friction and remove steps that add little risk reduction.
- Incorporate security requirements into product planning and resource allocation.
- Refine minimum production viability criteria based on vulnerabilities, incidents, testing, and production telemetry.

Improve incrementally. Prioritize the highest-risk gaps and the foundations that make secure delivery easier to sustain.