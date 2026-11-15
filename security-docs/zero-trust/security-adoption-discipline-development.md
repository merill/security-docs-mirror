---
layout: Conceptual
title: Establish a Development Security discipline | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-development
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Establish a Development Security discipline that reduces software risk while enabling rapid, reliable delivery.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 23acb7da-0b1a-239f-20d5-68494ef33c0b
document_version_independent_id: 23acb7da-0b1a-239f-20d5-68494ef33c0b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-development.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-development
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-development.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f9615260-cb26-532d-5e10-a7715bc70eca
---

# Establish a Development Security discipline | Microsoft Learn

This article helps security and technology teams establish or modernize a Development Security discipline. The discipline helps organizations design, build, integrate, deploy, and operate software securely while maintaining delivery speed and reliability.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**. SAF connects business scenarios, security disciplines, technologies, and implementation guidance so that security work supports business outcomes instead of becoming a collection of isolated controls.

Within SAF, Development Security is a technical strategy discipline. Use [Shift DevOps to DevSecOps](security-adoption-discipline-development-security) for operating-model and process change, [Development security implementation patterns](/en-us/security/saf/disciplines/development/implementation-patterns) for repeatable engineering approaches, and [Adopt secure development planning imperatives](security-adoption-discipline-development-imperatives) for secure-development expectations.

For capability-maturity assessment and planning, use the [DevSecOps Capability Model](/en-us/devops/devsecops/capability-model) with SAF. The capability model helps you assess software security practices. SAF helps you connect improvements to business risk, cross-discipline dependencies, and operating priorities.

## Mission and outcomes

The Development Security discipline reduces organizational risk by ensuring that software developed internally or by partners meets the organization's security requirements throughout its lifecycle.

Software is deeply connected to identities, data, infrastructure, devices, and business processes. A weakness in an application, development environment, dependency, or delivery pipeline can give an attacker a path to broader organizational assets or downstream customers.

Without an effective Development Security discipline, organizations commonly experience:

- Vulnerabilities introduced during design, development, integration, or deployment.
- Application compromise that exposes identities, data, infrastructure, or business processes.
- Supply-chain compromise that affects the organization, its customers, or its partners.
- Emergency fixes, operational disruption, and delayed releases.
- Accumulating technical and security debt that increases future cost and risk.

A mature discipline helps organizations:

- Build security into normal engineering work instead of adding it near release.
- Find and address design and implementation flaws earlier.
- Produce more predictable and secure releases.
- Reduce rework, emergency remediation, and operational disruption.
- Improve security posture with each release instead of adding risk over time.

The goal is to **secure innovation while it happens**.

## Recognize the scope of development security

Development security applies to more than application source code. It includes the people, processes, identities, tools, environments, dependencies, and infrastructure used to create and operate software.

The discipline can apply to:

- Applications, services, and APIs.
- Scripts, automation, and infrastructure as code.
- Web, mobile, desktop, and device software.
- Firmware, operational technology, and Internet of Things solutions.
- AI-enabled applications, agents, models, tools, and connectors.
- Source repositories, developer environments, build systems, and release pipelines.
- Third-party and open-source components used by the software.
- The platforms and infrastructure that host the resulting workloads.

Treating only the application code as in scope leaves important attack paths unaddressed.

## Establish accountability

Product and engineering teams are accountable for the functionality, security, reliability, and operational outcomes of the software they deliver. Security teams have distinct responsibilities: define and interpret security requirements, provide expertise and reusable patterns, enable teams with tools and education, challenge risk decisions, and advise authorized decision makers.

These responsibilities keep security close to the decisions that create risk without expecting every developer or product owner to become a security specialist.

Primary roles commonly include:

- Product owners and technology delivery managers.
- Software developers, including AI developers.
- Software security and application security engineers.
- DevOps and platform engineering leads.
- Software testing and quality managers.
- Supply-chain and dependency security roles.

Key collaborators include:

- Business and technical leaders with delegated authority, who provide sponsorship and make or escalate risk decisions.
- Security architecture roles, who guide secure design and integration.
- Security Strategy, Integration, and Governance roles, who provide policy, education, oversight, and risk coordination.
- Access and identity, data, infrastructure, endpoint, and network teams, who secure the technology dependencies used by development and production workloads.
- Security Operations (SecOps), who monitor applications and their supporting systems and respond to attacks.

Define decision authority and escalation paths explicitly. Specify which decisions product and engineering teams can make, which require escalation, and who may approve exceptions or accept residual risk. Do not treat participation in delivery as authority to accept risk.

## Integrate security into engineering work

Meet product and engineering teams where they work. Integrate security into the tools, processes, and workflows already used to plan, design, build, test, release, and operate software.

This approach is often described as **shifting left**: bringing security into decisions early enough to improve the outcome, when teams still have practical options and fixes usually cost less. Shifting left does not mean saying no earlier. It means adding security context while product and technical decisions are still being made.

Key principles include:

- **Integrate early**: Consider security during ideation and design, not only during testing.
- **Use existing engineering workflows**: Track security work in the same planning, backlog, approval, and defect-management systems used for other engineering work.
- **Make secure practices easier to adopt**: Provide paved paths, reusable components, automation, and practical guidance.
- **Apply rigor based on risk**: Use stronger assurance for software that can create greater business, customer, safety, or regulatory impact.
- **Validate throughout the lifecycle**: Find issues early, verify important controls before release, and monitor the workload in production.
- **Continuously improve**: Use vulnerabilities, incidents, testing, and operational feedback to strengthen both the software and the development process.

Done well, security reduces late surprises and costly rework instead of becoming another source of delivery friction.

## Apply the discipline

Apply Development Security by establishing a consistent approach across the organization:

1. **Define a development security strategy aligned to business risk**: Establish how to design, build, integrate, release, and maintain software to protect critical business functions and manage software risk.
2. **Set minimum production viability in the secure definition of done**: Define one release quality gate that combines the minimum development, security, and operations requirements for production use. Adjust the rigor to the workload's business impact.
3. **Integrate security into engineering processes**: Build security into planning, architecture, design, development, testing, deployment, and operations rather than applying it after development is complete.
4. **Standardize and automate secure practices**: Provide reusable patterns for secure design, coding, dependencies, identities, pipelines, infrastructure, testing, and release decisions.
5. **Protect the development environment and software supply chain**: Secure developer endpoints, repositories, build systems, service identities, dependencies, artifacts, and delivery paths.
6. **Continuously improve**: Use vulnerabilities, incidents, postmortems, testing, and production telemetry to improve priorities, practices, and controls.

## Set minimum production viability in the secure definition of done

Use **minimum production viability** as the release quality gate within the team's **secure definition of done**. It is the minimum set of development, security, and operations requirements that a workload needs for production use. A minimum viable product is not production-ready based on functionality alone.

Before each production release, verify all three dimensions:

| Requirement | Minimum outcome for production use |
| --- | --- |
| **Development** | The software meets the required business and user needs. |
| **Security** | The software meets the security, safety, privacy, and compliance requirements appropriate to its risk. |
| **Operations** | The software meets the quality, performance, reliability, supportability, monitoring, and recovery requirements for production use. |

Treat these dimensions as concurrent inputs to one release decision, not as sequential maturity stages. Keep security present from ideation through production operations.

Tailor the rigor to the workload. A prototype, a customer-facing service, a financial system, and a safety-critical device do not need identical assurance. For an exception, record the unmet requirement, business rationale, compensating controls, expiration date, and remediation plan. Only a person with delegated authority may approve the exception and accept the residual risk.

[![Release quality gate showing that minimum production viability combines development, security, and operations requirements before the first production release and improves continuously afterward.](media/security-adoption-discipline-dev-overview.png)](media/security-adoption-discipline-dev-overview.png#lightbox)

## Use DevSecOps to operationalize the discipline

DevSecOps is a primary way to operationalize Development Security. It integrates security into DevOps practices so that development, security, and operations work together throughout the software lifecycle.

Focus on four connected areas:

- **Secure design**: Use proven design patterns and threat modeling to identify and reduce risk before implementation choices become expensive to change.
- **Secure code and dependencies**: Apply secure coding practices and validate first-party and third-party components.
- **Secure delivery**: Protect repositories, build systems, artifacts, identities, and CI/CD pipelines from compromise and unauthorized change.
- **Secure operations**: Configure, patch, monitor, detect, respond, and recover throughout the workload's operational life.

Use [Shift DevOps to DevSecOps](security-adoption-discipline-development-security) for the process and operating-model changes needed to put this approach into practice.

## Align with other SAF disciplines and technologies

Development Security depends on other SAF disciplines:

- **Access and identity** protects developer, workload, service, and agent identities.
- **Data security** protects the data used, generated, and stored by software.
- **Infrastructure security** protects developer platforms, build systems, hosting environments, and shared services.
- **Security architecture** establishes secure design patterns, trust boundaries, and cross-technology controls.
- **Security Strategy, Integration, and Governance** aligns development practices to business risk, policy, and accountability.
- **Security Operations** detects and responds to attacks against applications, pipelines, and supporting infrastructure.

Development Security also requires controls across identities, endpoints, applications, data, infrastructure, networks, and AI. Use the relevant SAF technology guidance and product documentation for detailed implementation.

[![Development Security relationships with SAF technology areas.](media/security-adoption-discipline-dev-pillars.png)](media/security-adoption-discipline-dev-pillars.png#lightbox)

## Use Microsoft workshops

Microsoft Unified offers expert-led workshops to help organizations modernize Development Security:

- **Architecture and strategy**: The *Security Adoption Framework (SAF) - Architecture Design Session: Infrastructure and Development Security* workshop focuses on Development Security modernization and its relationship with Infrastructure Security.
- **Technology adoption**: Development Security technology workshops help teams plan, implement, and optimize relevant Microsoft capabilities.

[![Development Security technology adoption workshops.](media/security-adoption-discipline-dev-technical.png)](media/security-adoption-discipline-dev-technical.png#lightbox)

## Where to go next

- Use [Development security implementation patterns](/en-us/security/saf/disciplines/development/implementation-patterns) for repeatable engineering approaches.
- Use [Shift DevOps to DevSecOps](security-adoption-discipline-development-security) to integrate security into the development operating model.
- Use [Adopt secure development planning imperatives](security-adoption-discipline-development-imperatives) for secure-development expectations.
- Use the [DevSecOps Capability Model](/en-us/devops/devsecops/capability-model) to assess current maturity and prioritize improvements.
- Use the [Microsoft Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/) for practices that apply across software development approaches and platforms.