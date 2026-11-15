---
layout: Conceptual
title: Secure your foundations with SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/scenarios/ai-security/security-foundations
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Translate the secure your foundations theme into durable outcomes and use SAF and Microsoft guidance to reduce AI-era risk across identity, data, posture, and governance.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 50fe4080-a39c-6ca3-f557-fef8a5b81359
document_version_independent_id: 50fe4080-a39c-6ca3-f557-fef8a5b81359
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/scenarios/ai-security/security-foundations.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/scenarios/ai-security/security-foundations
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/scenarios/ai-security/security-foundations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: 58187395-9971-98b2-9886-4142d2ed6b05
---

# Secure your foundations with SAF | Microsoft Learn

**Secure your foundations** is a current AI security transformation theme. The name can evolve, but the underlying work remains necessary: understand what you have, reduce preventable exposure, protect identities and data, secure development and infrastructure, and establish clear governance before AI adoption increases scale and complexity.

This page translates the theme into durable outcomes and execution paths. It does not create a separate implementation framework. Use the Microsoft Security Adoption Framework (SAF) to organize the work and canonical Microsoft guidance to implement it.

## What this theme means

Secure your foundations means improving the security of the environment that AI depends on and connects to. AI applications and agents inherit risk from existing identity, data, application, infrastructure, network, endpoint, and operational weaknesses. They can also amplify those weaknesses through speed, reach, and automation.

**AI changes the threat landscape and the speed of security work, but it does not replace fundamental security practices.** Organizations need to address new AI-specific risks while continuing to strengthen the identity, data, application, development, infrastructure, network, endpoint, and operational practices that protect the enterprise.

The practical objective is to secure now where risk is urgent, prioritize defenses that reduce the greatest business risk, and improve posture to get ready for AI. It also means treating secure AI and data as a continuous responsibility across the lifecycle, not as a one-time deployment gate.

## Durable outcome

The durable outcome is an enterprise foundation that can support AI innovation without accepting unmanaged risk.

Success looks like:

- AI applications, agents, identities, data sources, connectors, and owners are inventoried and governed.
- Critical assets and sensitive data are identified, classified, and protected according to business impact.
- Human, workload, and agent identities use strong authentication, least privilege, and lifecycle governance.
- Security teams can measure exposure, configuration, vulnerability, and control coverage across the estate.
- Development and platform teams use secure patterns for AI applications, agents, APIs, models, tools, and dependencies.
- Business, security, and technology leaders have clear ownership, decision rights, and exception processes.
- Posture and operational signals drive a continuous improvement loop rather than a point-in-time compliance exercise.

## SAF work

### Business scenarios

Use these SAF business scenarios to define scope and expected outcomes:

- [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) - Establish the business and security outcomes for AI adoption.
- [Strengthen posture and compliance](/en-us/security/zero-trust/security-adoption-scenario-improve-posture) - Measure exposure and continuously improve control effectiveness.
- [Protect critical business assets](/en-us/security/zero-trust/security-adoption-scenario-secure-assets) - Focus security work on the assets and data with the greatest business impact.
- [Secure and govern privileged access](/en-us/security/zero-trust/security-adoption-scenario-privileged-access) - Protect administrative and other high-impact control paths that AI systems can depend on or invoke.

### Security disciplines

Coordinate the work across these SAF disciplines:

- [Strategy, integration, and governance](/en-us/security/zero-trust/security-adoption-discipline-strategy) sets priorities, policy, funding, risk acceptance, and outcome measures.
- [Security architecture](/en-us/security/zero-trust/security-adoption-discipline-architecture) defines trust boundaries, control patterns, and end-to-end design across classic and AI systems.
- [Security posture](/en-us/security/zero-trust/security-adoption-discipline-posture) inventories assets and exposure, prioritizes risk, and measures improvement.
- [Access and identities](/en-us/security/zero-trust/security-adoption-discipline-identity-access) governs human, workload, and agent identities and applies least privilege.
- [Data](/en-us/security/zero-trust/security-adoption-discipline-data) discovers, classifies, protects, and governs data used by people, applications, models, and agents.
- [Development](/en-us/security/zero-trust/security-adoption-discipline-development) integrates threat modeling, secure engineering, testing, and release controls into AI delivery.
- [Infrastructure](/en-us/security/zero-trust/security-adoption-discipline-infrastructure) secures hosting, compute, platforms, services, and dependencies.
- [SecOps](/en-us/security/zero-trust/security-adoption-discipline-security-operations) detects active threats and feeds incident learning back into posture and architecture.

### Roles and collaboration

Use [Security roles and responsibilities in SAF](/en-us/security/zero-trust/security-adoption-roles) to assign accountable owners and working relationships.

The foundation depends on collaboration among:

- Organizational leadership and governance to set risk appetite and hold outcome owners accountable.
- Business and AI solution owners to define intended use, criticality, data access, and acceptable behavior.
- Security strategy, architecture, posture, identity, and data teams to define policy and reusable patterns.
- Application and product development teams to build and release AI capabilities securely.
- Technical engineering and operations teams to implement and operate controls across the estate.
- SecOps teams to monitor, investigate, respond, and drive lessons back into prevention.

### Technologies

Apply controls across the complete technology estate:

- [AI](/en-us/security/saf/technologies/ai/overview)
- [Identity](/en-us/security/zero-trust/deploy/identity)
- [Endpoints](/en-us/security/zero-trust/deploy/endpoints)
- [Applications](/en-us/security/zero-trust/deploy/applications)
- [Data](/en-us/security/zero-trust/deploy/data)
- [Infrastructure](/en-us/security/zero-trust/deploy/infrastructure)
- [Network](/en-us/security/zero-trust/deploy/networks)

Do not isolate AI from these dependencies. The secure foundation is the combination of controls across them.

## Implementation and product guidance

Use [Microsoft secure Zero Trust implementation solutions](/en-us/security/zero-trust/implement-overview) to connect the scenarios, disciplines, and technologies to technical implementation. Start with the following canonical guidance:

1. [Build a strong AI security posture](/en-us/security/security-for-ai/posture) to establish the overall approach and priorities.
2. [Prepare for AI security](/en-us/security/security-for-ai/prepare) to strengthen identity, device, data, and threat protection foundations.
3. [Discover AI apps and data](/en-us/security/security-for-ai/discover) to understand the AI estate and associated data paths.
4. [Protect AI apps and data](/en-us/security/security-for-ai/protect) to apply controls to AI usage, applications, and information.
5. [Govern AI for compliance](/en-us/security/security-for-ai/govern) to sustain policy, compliance, and accountable use.
6. [Secure AI with Zero Trust](/en-us/security/saf/technologies/ai/overview) to apply Zero Trust across AI systems and their dependencies.
7. [AI security in the Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security) to align stakeholders and build an implementation plan.
8. [Zero Trust assessment](/en-us/security/zero-trust/assessment/overview) to measure current capabilities and identify improvement priorities.

Use focused implementation guidance where the risk requires it:

- [Secure identity to get ready for AI](/en-us/security/zero-trust/sfi/secure-identity-to-get-ready-for-ai)
- [Least privilege for AI agents](/en-us/security/zero-trust/sfi/least-privilege-for-ai-agents)
- [Safe Secrets Standard](/en-us/security/zero-trust/sfi/safe-secrets-standard)
- [Complete production infrastructure inventory](/en-us/security/zero-trust/sfi/complete-production-infrastructure-inventory)
- [Complete AI threat modeling](/en-us/security/zero-trust/sfi/threat-modeling-ai)
- [Protect the software supply chain](/en-us/security/zero-trust/sfi/protect-software-supply-chain)
- [Use Zero Trust security to prepare for AI companions, including Microsoft Copilots](/en-us/security/zero-trust/copilots/apply-zero-trust-copilots-overview)

Keep detailed configuration steps in their canonical product documentation. Use this theme page to explain the outcome, organize ownership through SAF, and route teams to the right implementation guidance.