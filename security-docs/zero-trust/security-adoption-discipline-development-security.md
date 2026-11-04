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
description: Learn why we need to integrate security to DevOps modernization.
ms.date: 2026-05-24T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: dacce49b-c4d8-1698-7627-455fa93f2e05
---

# Shift DevOps to DevSecOps | Microsoft Learn

As you create or modernize a [Development Security discipline](security-adoption-discipline-development), this article outlines how integrating security into development practices enables the shift from developer operations (DevOps) to developer-security-operations (DevSecOps), and helps secure application delivery.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)** and extends the Development Security discipline with implementation-oriented DevSecOps adoption guidance.

Modern organizations rely on rapid software development to deliver innovation, respond to changing business requirements, and maintain competitive advantage. DevOps enables this agility through continuous integration and delivery. However, increased speed also introduces new security risks.

Continuous release cycles reduce the time between design decisions and production deployment, increasing the likelihood that weaknesses are introduced into production environments, including:

- Application design weaknesses
- Vulnerable dependencies
- Configuration errors
- Infrastructure automation flaws
- Poor secrets management or hygiene.

## DevOps risk

Modern DevOps environments expand the attack surface across development, pipeline, and production systems. DevOps tools such as source code repositories, pipelines, and automation systems are high-value targets for attackers.

If malicious code is introduced early, it might pass through existing security checks and reach production systems.

Common attack objectives include:

- Injecting malicious code into build artifacts.
- Compromising developer identities or service accounts.
- Accessing or exfiltrating production data.

Attackers often target custom applications and development environments to gain access to:

- Sensitive organizational or customer data.
- Proprietary business logic and intellectual property.
- Production infrastructure through compromised development systems.
- Downstream customers through software supply chain compromise.

Potential security risks are summarized in the following diagram:

[![Diagram illustrates DevOps environments and security threats.](media/develop/secure-devops-environments/diagram-enterprise-devops-overview-inline.png)](media/develop/secure-devops-environments/diagram-enterprise-devops-overview-expanded.png#lightbox)

### Application and development risk

Application workloads can be compromised through weaknesses introduced during development or through compromise of the infrastructure used to build and deploy them.

| **Risk** | **Target** | **Potential outcome** |
| --- | --- | --- |
| **App design/implementation** | Security issues introduced during design or development may expose workloads to attack techniques such as:- Improper input validation- Insecure authentication or authorization logic- Weak or improperly implemented cryptography- Exposure of sensitive data through application logic | These weaknesses might allow attackers to:- Access or manipulate application data- Execute unauthorized operations- Maintain persistent access through implanted logic flaws. |
| **Dev infrastructure/automation** | Attacks might target:- Source code repos- Build pipelines- Deployment automation- Infrastructure-as-code (IaC) templates- Develop endpoints or service identities | Compromise might allow attackers to:- Insert malicious code into build artifacts- Modify deployment configurations- Maintain persistent access through implanted logic flaw- Obtain credentials or secrets used in production environments. |
| **Dev software supply chain** | Applications commonly rely on:- Third‑party libraries- Open‑source packages- Container images- Platform services | Vulnerabilities or malicious code introduced through these dependencies might affect:- Organizational production workloads- Customer or partner environments |

Integrating security into development processes reduces the likelihood that these risks propagate into production release.

## Shifting left

Shift left is a security engineering approach that integrates security earlier in the development lifecycle.

Instead of validating security late in the process, organizations embed it into:

- Envisioning
- Design
- Development
- Operations

This reduces remediation cost and risk exposure.

To support this approach, organizations should"

- Use structured best practices such as the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl/practices) early in the process, rather than late when issues become expensive and difficult to fix.
- To sustain this approach, integrate governance, risk, and compliance (GRC) into development strategy.

## What is DevSecOps?

DevSecOps delivers on the Shift Left approach by extending DevOps and embedding security into every stage of the software development lifecycle - from idea inception through design, development, and operations.

- In traditional development approaches, security validation was often performed as a final quality gate before release. This created delays, increased remediation cost, and allowed vulnerabilities to persist until late in the lifecycle.
- DevSecOps shifts security earlier and embeds it continuously into development and operational processes.
- DevSecOps reduces friction between development, operations, and security teams, aligning them around shared goals of innovation speed, reliability, and security resilience, and enabling teams to address the most important issues early and continuously.
- DevSecOps integrates security into:

    - Architectural design
    - Application implementation
    - Infrastructure automation
    - Deployment and operational processes

### Benefits

DevSecOps enables development, security, and operations teams to:

- Identify and remediate issues earlier in the lifecycle.
- Reduce exposure in production.
- Maintain delivery speed while managing risk.

Security becomes part of how software is built and delivered, rather than a control applied after delivery.

[![Graphic showing how development, security, and operations fit together](media/development-security-operations.png)](media/development-security-operations.png#lightbox)

## Secure innovation lifecycle

Innovation typically progresses through two lifecycle stages:

| **Stage** | **Details** |
| --- | --- |
| **Idea incubation** | A capability is designed, implemented, and validated for initial production use. It begins with a new idea |
| **Initial release** | A **first production release** meets the minimum product criteria for safe product use.- **Development**: Functionality meets the minimum business requirements.- **Security**: Capabilities meet the regulatory compliance, security, and safety requirements for production use.- **Operations:** Functionality meets the minimum quality, performance, and supportability requirements to be a production system. |

After initial release, development becomes iterative as workloads evolve with:

- Changing risk tolerance
- Application requirements and maturity
- Regulatory obligations
- Threat conditions

[![Diagram showing how DevSecOps keeps the development cycle agile and continuously improving](media/develop-security-agile.png)](media/develop-security-agile.png#lightbox)

## Integrate security into development

Traditional development approaches validate security late in the lifecycle, as a final gate before release after design and implementation are complete. In modern development environments, delaying validation increases:

- Vulnerability complexity
- Remediation cost
- Operational delays and disruption
- Increased risk exposure to active exploitation

DevSecOps integrates security continuously throughout development and operations, to address issues earlier, reduce risk, and improve consistency.

### Key practices

Security must be embedded into existing development processes to be effective, scalable, and sustainable. It should be integrated directly into how apps are designed, built, deployed, and operated, not implemented in a separate or parallel workflow. We recommend:

- Mapping end-to-end workflows from idea through development, deployment, and ongoing operations.
- Defining clear roles, tools, and responsibilities for security at each stage of the lifecycle.
- Establishing consistent remediation paths for vulnerabilities, defects, and design issues.

Tailor security practices based on workload risk. Business-critical applications require greater rigor, while lower-risk scenarios can follow streamlined approaches.

At a minimum, ensure that you:

- Identify the stages, people, and technologies involved in your development lifecycle.
- Define how security activities integrate into each stage, rather than treating them as separate checkpoints.
- Establish processes for handling both major changes and routine fixes throughout the lifecycle.

## Automate security into development and deployment

Automation is essential to enforce security consistently and at scale across development and operations.

- Integrate security controls and tooling directly into CI/CD pipelines.
- Automate key activities such as threat modeling, code scanning, validation, and policy enforcement.
- Use Infrastructure as Code (IaC) to enable repeatable, secure deployments.

Platform foundations such as Azure landing zones can support this approach by

Platform foundations such as [Azure landing zones](/en-us/azure/cloud-adoption-framework/ready/landing-zone/design-area/platform-automation-devops) can support this approach by providing standardized patterns for security, governance, and DevOps integration.

## Expected outcomes

Organizations that shift from DevOps to DevSecOps can:

- Reduce the likelihood that vulnerabilities are introduced into production workloads
- Limit the ability of attackers to exploit development infrastructure or automation
- Improve resilience of applications to evolving attack techniques
- Support regulatory and organizational compliance requirements
- Sustain innovation velocity without increasing operational or security risk

## Tips on navigating the journey

Adopting DevSecOps requires organizational and cultural changes.

### Education and culture changes

These are critical early steps. The team you have must develop new skills and adopt new perspectives to understand the DevSecOps model.

Education and culture change takes time, focus, executive sponsorship, and regular follow up to help individuals fully understand and see the value of the change.

Changing cultures and skills drastically can sometimes tap into the professional identity of individuals, creating potential for strong resistance. It's critical to understand and express the why, what, and how of the change for each individual and their situation.

### Change takes time

You can only move as fast as your team can adapt to the implications of doing things in new ways. Teams must do their existing jobs while they transform.

It's critical to carefully prioritize what is most important and to manage expectations of how fast this change can happen.

Focusing on a crawl, walk, run strategy, where the most important and foundational elements come first, serves your organization well.

### Change introduces (temporary) friction

All new technologies, methodologies, and other changes introduce friction and confusion. It's critical to focus on healthy friction that drives critical thinking to reduce risk while avoiding unhealthy friction that slows down processes with limited benefit or risk reduction.

### Limited resources

A challenge that organizations usually face early on is to find talent and skills in both security and application development.

As organizations begin to collaborate more effectively, they might find hidden talent, such as developers with a security mindset or security professionals with a development background.

### Ongoing shifts

Apps are changing fast. In addition to new features, the technical definition and composition of an application is fundamentally changing with the introduction of technologies such as cloud, serverless, and AI.

This shift is changing development practices, application security, and even empowers nondevelopers to create applications.

### Consider an SRE model

Some DevSecOps implementations combine operations and security responsibilities into a **site reliability engineer (SRE)** role.

While such a model can work, it's often an extreme change from existing enterprise culture and practices.

If you're considering an SRE model, we recommend that you start by embedding security into DevOps using practical quick wins and incremental progress outlined in this guidance to ensure you're getting good return on investment (ROI) and meeting immediate needs.

This incrementally adds security responsibilities to your operations and development personnel, which moves teams closer to an SRE end-state.