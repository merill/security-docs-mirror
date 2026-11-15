---
layout: Conceptual
title: Security roles and responsibilities in SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-roles
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Understand the role model, accountabilities, and responsibilities that support security adoption in the Microsoft Security Adoption Framework (SAF).
ms.topic: article
ms.service: security
ms.date: 2026-11-04T00:00:00.0000000Z
locale: en-us
document_id: 969fdb10-9d59-c8a8-4070-a0ef01b4b801
document_version_independent_id: 969fdb10-9d59-c8a8-4070-a0ef01b4b801
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-roles.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-roles
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-roles.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
platformId: ad26ab66-89ed-a555-947b-a3c232e7ea4f
---

# Security roles and responsibilities in SAF | Microsoft Learn

Adopting security through the Microsoft Security Adoption Framework (SAF) is a strategic transformation that affects the entire organization and requires clear ownership and coordination across business, security, and technology teams. It's not a single technology deployment or a one-time project.

This article defines the role model and responsibilities used to plan, implement, and sustain security modernization at scale.

## Why roles matter in adoption

Zero Trust shifts security from a perimeter-based model to one that continuously verifies users, devices, applications, data, and more. This shift affects business processes, user experiences, IT operations, and risk management.

Without clear roles and responsibilities:

- Security initiatives stall or fragment.
- Technology teams optimize locally instead of aligning to business and security priorities.
- Leaders lack visibility into security modernization progress and outcomes.

Defining role ownership helps translate Zero Trust strategy into coordinated action and measurable security improvements across the organization.

## Security is everyone's job

Security is fundamentally a human discipline that manages risk from human threat actors. While automation and AI play important roles, people remain central to security outcomes.

- Security is an intrinsic part of every business area. It has fiduciary and risk implications, affects business capabilities and execution, and touches all technologies.
- Security is everyone's job. From the board of directors to technical engineering and operations teams, nontechnical teams such as finance and legal, and information workers/frontline workers.
- For effective security risk management, every person must understand security in the context of their role, and actively support security objectives.
- Since anyone in the organization can create or amplify security risk, everyone must apply security principles in their daily actions and decisions.

The Open Group [Security Roles and Glossary Standard](https://publications.opengroup.org/s252) anchors this approach:

> 
> Security accountabilities and responsibilities must be delegated across the organization.

This diagram illustrates that delegation model:

[![Illustration of how to delegate security accountability and responsibility through an organization](media/adoption-role-delegation.png)](media/adoption-role-delegation.png#lightbox)

### Security is a team sport

Managing security risk effectively requires accountability and collaboration:

- Collaboration between accountable and responsible parties is critical.
- Making good security decisions requires a healthy relationship. Accountable decision-makers and security experts must be able to share ideas safely and challenge assumptions.

With these tenets in mind, security risk should be managed in a similar way to financial and legal risk. Each role has policies and education/training that guide their daily decisions, rather than assigning responsibility and even blame to security teams only.

[![Illustration of how accountable and responsible parties should collaborate](media/adoption-role-collaboration.png)](media/adoption-role-collaboration.png#lightbox)

## Role definition outcomes

Clearly defined roles help the organization manage security as a business risk rather than treating it only as a technical problem. Different groups contribute different expertise, decision authority, and operational capabilities needed to understand and manage that risk.

When roles are clearly defined, aligned, and connected:

- Leadership sets business priorities, risk appetite, decision rights, and accountability.
- Business leaders identify critical outcomes, assets, processes, and acceptable tradeoffs.
- Risk and security-adjacent disciplines connect security risk with regulatory, privacy, financial, legal, fraud, data, AI, and other enterprise risks.
- Architecture and technical leadership translate business and security requirements into scalable technology decisions.
- Development, engineering, and operations build and sustain protections while balancing security with reliability, usability, cost, and business agility.
- Security strategy, integration, and governance identify systemic risk and coordinate improvements across the organization.
- Security operations detect where threats are materializing and limit the business impact of successful attacks.
- Cross-functional disciplines help manage the financial, legal, workforce, contractual, and reputational consequences of security decisions and incidents.

Together, these roles allow the organization to make informed decisions about security risk, implement those decisions consistently, and understand whether risk is being effectively managed over time.

## Roles and terminology

Role terminology and definitions are based on the [Open Group Security Roles and Glossary Standard](https://publications.opengroup.org/s252).

This updated SAF role list and diagram shows the current role groupings:

[![Illustration of security roles in the Microsoft Security Adoption Framework](media/adoption-role-list.png)](media/adoption-role-list.png#lightbox)

Current role groups:

- Organizational Leadership and Governance
- Business Management and Operations
- Security-Adjacent Disciplines
- Cross-Functional Disciplines
- Technical Leadership
- Architecture
- Application and Product Development
- Security Strategy, Integration, and Governance
- Technical Engineering and Operations
- Security Operations (SecOps/SOC)

### Role terminology glossary

The following terms are based on the [Zero Trust Roles and Glossary Standard from The Open Group](https://publications.opengroup.org/s252) (published as the *Security Roles and Glossary Standard*):

- **Discipline**: A security domain of practice that combines people, process, architecture, operations, and technology.
- **Role**: A set of job functions assigned to one or more people.
- **Job function**: A specific set of tasks performed to achieve a security outcome.
- **Role specialization**: How broad or narrow a role is, based on the depth and scope of assigned tasks.
- **Accountability**: Ownership of outcomes and impacts from decisions and actions.
- **Responsibility**: Obligation to perform tasks competently and provide sound guidance.
- **Security responsibility**: Responsibility focused on managing security risk and outcomes.
- **Technology responsibility**: Responsibility focused on designing, implementing, and operating technology that supports security outcomes.

## Role responsibilities

### Organizational leadership and governance

**Purpose**: Establish organizational direction, priorities, and governance, including decision rights and accountabilities. Executive leadership establishes Zero Trust as an organizational priority and creates the conditions for long-term success.

**Accountabilities include**:

- Sponsoring Zero Trust as a business and risk-management strategy.
- Aligning security objectives with business goals, regulatory obligations, and risk tolerance.
- Providing sustained funding, staffing, and organizational support.
- Establishing governance models and accountability structures.
- Holding leaders responsible for measurable security outcomes.

**Business risk value**: Organizational leadership makes security risk an explicit part of business decision-making. It helps the organization prioritize investment, establish risk ownership, make informed tradeoffs, and avoid unmanaged security risk becoming an unexpected source of business disruption, financial loss, regulatory exposure, or reputational damage.

### Business management and operations

**Purpose**: Embed Zero Trust into day-to-day business execution. Business leaders and operational managers ensure that Zero Trust supports productivity, customer trust, and operational resilience.

**Accountabilities include**:

- Integrating Zero Trust requirements into business processes and workflows.
- Balancing security controls with user experience and operational efficiency.
- Identifying critical business assets, processes, and data to prioritize protection.
- Supporting change adoption across teams and functions.
- Measuring business impact of security decisions.

**Business risk value**: Integrating security into business operations helps protect the processes, assets, data, and capabilities the organization depends on while preserving productivity and customer value. Business leaders are positioned to make informed tradeoffs between security risk and business objectives because they understand the operational consequences of those decisions.

### Security-adjacent disciplines

**Purpose**: Security-adjacent disciplines such as Chief Security Officer (CSO), Chief Risk Officer (CRO), Chief Privacy Officer (CPO), Data Officer / Data Governance, AI Governance, Organizational Compliance and Audit, and Anti-Fraud align security strategy with enterprise risk, compliance, and privacy objectives.

These roles connect Zero Trust to broader enterprise risk management and assurance functions.

**Accountabilities include**:

- Translating Zero Trust principles into risk, compliance, and privacy requirements.
- Ensuring alignment with regulatory, legal, privacy, and other industry obligations.
- Validating controls through audit, assessment, and assurance activities.
- Advising leadership on risk tradeoffs and residual risk.
- Coordinating across security, compliance, and governance domains.

**Business risk value**: These disciplines help the organization understand security risk alongside related business risks such as regulatory, privacy, fraud, data, and AI risk. Their involvement helps leaders make informed risk decisions, demonstrate compliance and assurance where required, and understand residual risk that remains after controls are applied. Good security can make compliance easier to achieve, demonstrate, and sustain, but security does not automatically satisfy compliance obligations.

### Cross-functional disciplines

**Purpose**: Non-technical disciplines such as legal, finance, PR, and communications align Zero Trust adoption across nontechnical business support functions. Zero Trust impacts contracts, budgets, communications, and external trust.

**Accountabilities include**:

- Legal: supporting data protection, contracts, regulatory interpretation, and incident management processes.
- Finance: funding models, cost governance, investment prioritization, and security risk quantification.
- Communications and PR: internal and external messaging during incidents or changes.
- HR and people teams: policy enforcement, training alignment, and workforce engagement.

**Business risk value**: These disciplines help manage business consequences that extend beyond security technology, including contractual exposure, financial loss, workforce impacts, legal obligations, and reputational damage. Their involvement helps the organization prepare for and manage the broader business impact of security decisions and incidents.

### Technical leadership

**Purpose**: Translate strategy into executable technical direction. Technical leaders bridge business intent and engineering execution.

**Accountabilities include**:

- Defining strategic requirements aligned to Zero Trust outcomes, and approving strategic roadmaps and strategy.
- Ensuring coordination on Zero Trust approaches across domains and engineering teams.
- Advising business stakeholders on tradeoff decisions between security, performance, and usability.
- Ensuring consistency across identity, endpoint, application, data, and infrastructure domains.
- Supporting modernization of legacy systems.

**Business risk value**: Strong technical leadership translates business and security priorities into coordinated technology decisions. This reduces risk created by fragmented architectures, inconsistent implementation, legacy technology, and local optimization, while helping the organization balance security with reliability, usability, cost, and business agility.

### Architecture

**Purpose**: Design scalable, coherent solutions that align to Zero Trust principles. Security and enterprise architects collaboratively define enterprise-wide architecture and solutions.

**Accountabilities and responsibilities include**:

- Defining target-state Zero Trust architectures.
- Aligning platforms, services, and workloads to Zero Trust principles and concepts.
- Identifying architectural gaps, dependencies, and integration points.
- Providing design guidance and reference patterns.
- Ensuring solutions scale with business and technology change.

**Business risk value**: Architecture helps prevent security risk from accumulating through inconsistent designs, unmanaged dependencies, and technology fragmentation. Coherent architecture enables the organization to make deliberate risk tradeoffs and build technology environments that can adapt safely as business requirements, threats, and technologies change.

### Application and product development

**Purpose**: Build Zero Trust into applications and services by design. Development teams play a critical role in enforcing Zero Trust at the application layer.

**Accountabilities include**:

- Designing applications that verify explicitly and enforce least privilege.
- Integrating identity, access control, and data protection into applications.
- Supporting secure APIs, service-to-service access, and workload identities.
- Partnering with security teams to reduce risk without harming velocity.
- Addressing security early in the development lifecycle.
- Using secure workstations and CI/CD systems.

**Business risk value**: Building security into applications and products reduces the likelihood that vulnerabilities, excessive access, insecure dependencies, or development practices create business exposure later. Addressing these risks during design and development can reduce remediation cost and disruption while helping protect customers, data, services, and business operations.

### Security strategy, integration, and governance

**Purpose**: Security strategy roles such as security education, insider risk, posture, and compliance management help shape long-term security behavior and maturity. These roles focus on people, policy, and sustained security effectiveness.

**Responsibilities include**:

- Defining security strategy, standards, and roadmaps.
- Managing insider risk and user-related threats.
- Driving security awareness, education, and culture.
- Monitoring security posture and driving improvements.
- Overseeing security compliance and policy enforcement.
- Measuring maturity and progress against Zero Trust objectives.

**Business risk value**: These functions help the organization identify systemic security risk, establish consistent expectations, prioritize improvements, and monitor whether risk is changing over time. They connect security strategy and governance to business priorities so leaders can make informed decisions about where risk should be reduced, transferred, avoided, or explicitly accepted by the appropriate accountable decision-maker.

### Technical engineering and operations

**Purpose**: Implement and operate Zero Trust controls. Engineering and operations teams turn designs into functioning systems.

**Responsibilities include**:

- Deploying security controls across identity, devices, applications, data, and infrastructure.
- Integrating security into operational workflows and platforms.
- Managing change, testing, and rollout to minimize disruption.
- Maintaining system reliability, availability, and performance.
- Continuously improving controls based on feedback and telemetry.

**Business risk value**: Engineering and operations convert security requirements into reliable protections across the technology estate. Consistent implementation and operation reduce exposure created by configuration drift, control gaps, unmanaged change, and operational failures while balancing security with availability, performance, and business continuity.

### Security operations (SecOps / SOC)

**Purpose**: Apply an asset-centric Zero Trust approach to threat detection and response. Security operations teams respond to attacks that evade preventative controls.

**Responsibilities include**:

- Monitoring telemetry and signals across users, devices, and workloads.
- Detecting threats, policy violations, and anomalous behavior.
- Responding to incidents and coordinating containment and recovery.
- Feeding operational insights back into policies, architecture, and automation.
- Measuring effectiveness through detection, response, and impact metrics.

**Business risk value**: Security operations limit the business impact of attacks that bypass preventive controls by detecting, containing, and helping the organization recover from threats quickly. Operational insights also help the organization understand where risk is materializing and improve controls, architecture, and processes to reduce future likelihood and impact.