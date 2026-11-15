---
layout: Conceptual
title: Shift DevOps to DevSecOps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-development-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Integrate security into DevOps practices to reduce software and delivery-pipeline risk while maintaining development velocity.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 0fd4e742-40fe-098e-5e90-4b889e5caf63
document_version_independent_id: 0fd4e742-40fe-098e-5e90-4b889e5caf63
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-development-security.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-development-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-development-security.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: dacce49b-c4d8-1698-7627-455fa93f2e05
---

# Shift DevOps to DevSecOps | Microsoft Learn

Use DevSecOps to operationalize the [Development Security discipline](security-adoption-discipline-development). DevSecOps integrates security into development and operations so that teams can manage software risk while delivering reliable capabilities at the speed the business needs.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**. It focuses on the operating-model and process changes needed to make security part of normal engineering work.

DevSecOps is not a separate security framework, a final gate, or a maturity stage that begins after DevOps is complete. It is the security dimension of modern software delivery.

## Security risk in modern development environments

Modern development creates powerful paths from an idea to production. Source repositories, developer endpoints, build systems, automation, service identities, artifacts, dependencies, and cloud platforms can all influence what reaches a production environment.

Attackers target these paths because compromise can provide access to:

- Proprietary source code and intellectual property.
- Developer, workload, and service identities.
- Credentials, secrets, and production data.
- Build artifacts and deployment configurations.
- Customer or partner environments through software supply-chain compromise.

Security risk can enter through several related areas:

| Risk area | Examples | Potential impact |
| --- | --- | --- |
| **Application design and implementation** | Insecure authorization, improper input validation, weak cryptography, unsafe handling of data, or flaws in business logic | Unauthorized access, data exposure, manipulation of business processes, or persistent compromise |
| **Development infrastructure and automation** | Compromised developer endpoints, repositories, pipelines, build agents, infrastructure-as-code templates, or service identities | Malicious changes to code or configuration, stolen credentials, tampered artifacts, or unauthorized deployment |
| **Software supply chain** | Vulnerable or malicious packages, container images, tools, extensions, or platform services | Compromise of organizational workloads or downstream customers and partners |
| **Operations** | Weak configuration, inadequate monitoring, delayed patching, or incomplete recovery plans | Longer exposure, greater damage, and slower restoration of business services |

Protect both the software and the systems used to create, deliver, and operate it.

## Shift security earlier, then validate continuously

Shifting left means bringing security into development decisions early enough to change the outcome, rather than discovering problems after design and implementation are complete.

Integrate appropriate security practices into:

- Ideation and planning.
- Architecture and design.
- Development and testing.
- Build and release.
- Deployment and operations.

Early integration reduces the cost and disruption of fixing security issues while giving teams more options for addressing risk. Use proven practices such as the [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl/practices), and include governance, risk, privacy, safety, and compliance requirements during planning rather than treating them as a final release gate.

Shifting left does not eliminate the need to validate later. Assume that people, automation, and controls can fail. Recheck important requirements before release, monitor the workload in production, and feed operational lessons back into design and engineering. This combination of early action and continuous validation provides defense in depth.

## Set minimum production viability in the secure definition of done

Use **minimum production viability** as the release quality gate within the team's **secure definition of done**. It is the minimum set of development, security, and operations requirements that a workload needs for production use. A minimum viable product is not production-ready based on functionality alone.

Before each production release, verify all three dimensions:

| Requirement | Minimum outcome for production use |
| --- | --- |
| **Development** | The software meets the required business and user needs. |
| **Security** | The software meets the security, safety, privacy, and compliance requirements appropriate to its risk. |
| **Operations** | The software meets the quality, performance, reliability, supportability, monitoring, and recovery requirements for production use. |

Treat these dimensions as concurrent inputs to one release decision, not as a sequence from Development to DevOps to DevSecOps. Keep security present from ideation through production operations.

Tailor the rigor to the workload's business impact, exposure, and regulatory obligations. Improve or sustain the required outcomes with each release.

[![DevSecOps lifecycle showing that minimum production viability combines development, security, and operations requirements at the first production release and improves continuously afterward.](media/develop-security-agile.png)](media/develop-security-agile.png#lightbox)

## Integrate security into engineering workflows

Security is most effective when it uses the same mechanisms as other engineering work. Avoid a separate process that forces product and engineering teams to discover, translate, and maintain duplicate requirements.

Map the path from idea to production and ongoing operations. Identify:

- The people and teams who make product, architecture, risk, release, and operational decisions.
- The repositories, branches, tools, identities, environments, and automation involved.
- The events that trigger builds, tests, approvals, deployments, and rollbacks.
- The security activities required at each stage.
- The path for resolving design flaws, vulnerabilities, dependency issues, and incidents.

Then integrate security into normal workflows:

- Track security requirements and defects in the same backlog and work-management systems used for other engineering work.
- Use the same prioritization language for security and nonsecurity defects so teams can make informed tradeoffs.
- Include security expertise in architecture and design decisions.
- Protect high-impact branches and release actions with appropriate review and approval.
- Document the code-to-production path so teams can see where changes are validated and who can authorize them.
- Use blameless postmortems to capture security lessons and improve the system rather than assigning blame.

## Automate repeatable security work

Automation helps teams apply controls consistently and reduces the effort required to follow secure practices.

Use automation to:

- Apply policy and configuration checks.
- Scan code, dependencies, secrets, infrastructure as code, and deployment configurations.
- Generate and preserve provenance information and software bills of materials where appropriate.
- Enforce branch, build, artifact, and release protections.
- Use short-lived federated identities instead of long-lived pipeline secrets where possible.
- Create repeatable, secure environments and deployment patterns.
- Feed security findings into the team's normal remediation workflow.

Use automation to help engineers act, not flood them with low-quality findings. Tune tools, assign remediation responsibilities and service levels, and provide access to security expertise when teams need help interpreting results.

Platform foundations such as [Azure landing zones](/en-us/azure/cloud-adoption-framework/ready/landing-zone/design-area/platform-automation-devops) can provide reusable patterns for governance, security, and deployment automation. Use platform engineering and paved paths to make the secure approach the easiest practical approach.

## Apply rigor based on business risk

Not every workload requires identical controls. Use a risk-based baseline that accounts for:

- Business criticality and potential financial impact.
- Customer, partner, safety, or regulatory consequences.
- Data sensitivity and privilege.
- Exposure to external users and untrusted input.
- The ability to affect other systems or downstream customers.
- The expected lifetime and support model of the software.

Establish a standard baseline for production software, stronger assurance for high-impact workloads, and a governed exception process for temporary prototypes or urgent business needs. For an exception, record the unmet requirement, business rationale, compensating controls, expiration date, and remediation plan. Only a person with delegated authority may approve the exception and accept the residual risk.

## Assign accountability, responsibilities, and decision authority

DevSecOps changes how development, security, and operations teams work together. Product and engineering teams are accountable for the functionality, security, reliability, and operational outcomes of the software they deliver. Security specialists have distinct responsibilities: define and interpret security requirements, advise and enable teams, challenge risk decisions, and provide expertise and reusable patterns.

Assign decision authority separately from delivery responsibilities. Only a person with delegated authority may approve an exception or accept residual risk. Escalate decisions that exceed the team's authority.

Leaders can support this model by:

- Setting shared goals for functionality, security, reliability, and delivery.
- Making business urgency and likely security impact visible to the whole team.
- Ensuring no single function wins every tradeoff by default.
- Funding security as part of the product and engineering plan rather than as an external afterthought.
- Expecting continuous improvement instead of immediate perfection.
- Modeling respect for the expertise and constraints of other disciplines.

Teams need time to develop skills and shared practices. Make the change easier to adopt by explaining why it matters, providing practical training and automation, and improving incrementally based on experience.

## Manage friction deliberately

Every control adds some cost or delay. The goal is not to eliminate friction but to put the right friction in the right place.

- **Healthy friction** prompts useful review, threat modeling, testing, or approval at a point where the decision can reduce meaningful risk.
- **Unhealthy friction** delays delivery without proportional risk reduction, produces excessive false positives, or requires teams to repeat work across disconnected processes.

Measure the effect of controls on both risk and engineering flow. Remove steps that provide little value, improve noisy tools, automate repeatable checks, and preserve deliberate human review for consequential decisions.

Modernize incrementally. Prioritize the highest-risk gaps and the foundational practices that make later improvements easier. Keep delivery moving while changing how software is built and secured.

## Expected outcomes

Organizations that integrate security into DevOps can:

- Reduce the likelihood that design and implementation flaws reach production.
- Reduce compromise of developer environments, repositories, pipelines, and automation.
- Improve software supply-chain integrity.
- Detect and remediate security issues earlier and more consistently.
- Improve resilience and recovery when failures or attacks occur.
- Sustain delivery velocity without allowing security risk to grow unchecked.