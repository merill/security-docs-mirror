---
layout: Conceptual
title: Secure your foundations | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/scenarios/ai-security/security-foundations
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Use Microsoft security guidance to reduce exposure, prioritize risk, and strengthen the identities, data, applications, infrastructure, networks, endpoints, and other security foundations that AI depends on.
ms.date: 2026-11-17T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 58187395-9971-98b2-9886-4142d2ed6b05
---

# Secure your foundations | Microsoft Learn

AI applications and agents depend on the same identities, data, applications, infrastructure, networks, endpoints, development practices, and operations as the rest of the enterprise.

Attackers can use AI to find weaknesses in these foundations more quickly, exploit them at greater speed and scale, and increase their potential impact. AI adoption also introduces new identities, data flows, applications, agents, tools, connectors, and dependencies that organizations must understand and protect.

Securing your foundations does not mean delaying AI until every control is mature. It means continuously identifying and reducing enterprise weaknesses and dependencies that AI can amplify while AI adoption continues.

Organizations must reduce exposure to known attacks, make informed risk decisions, protect critical assets and data, and continuously improve the controls on which AI depends. Security teams, agents, and automation also need shared signals, context, workflows, and controls to detect threats, respond effectively, and recover quickly.

This work starts with knowing what the organization has, understanding business impact and exposure, applying [Zero Trust principles](/en-us/security/zero-trust/zero-trust-overview), and making steady, measurable progress.

## What good looks like

- The organization has reliable visibility into AI applications, agents, identities, data sources, connectors, tools, models, infrastructure, dependencies, and accountable owners.
- Critical assets and sensitive data are classified by business impact, tagged where appropriate, and protected accordingly.
- Human, workload, and agent identities use strong authentication, least privilege, lifecycle governance, and protected credentials.
- Development and platform teams use approved patterns for designing, building, testing, deploying, operating, and recovering AI applications, agents, APIs, models, tools, and dependencies.
- Security teams can measure exposure, vulnerabilities, configuration, control coverage, and response readiness for business-critical systems and services.
- Leaders have clearly defined risk ownership, decision rights, exception paths, funding, and measures of progress.
- Teams use posture findings, incidents, near misses, threat intelligence, assessment results, and operational evidence to continuously improve architecture, controls, and operations.

Strengthening security foundations requires coordinated changes across strategy, governance, people, processes, and technology. Microsoft provides guidance and technology to help organizations prioritize this work, plan improvements, and implement and operate the controls that reduce risk.

## Plan and organize

Planning and organizing foundational security starts with clearly understanding the business outcomes and risks that matter to your organization. Identify the goals for AI adoption, the critical business assets and data those goals depend on, the weaknesses that could cause material business impact, and the roles accountable for managing those risks.

Use the [Microsoft Security Adoption Framework (SAF)](/en-us/security/zero-trust/security-adoption-model) to translate business outcomes and risks into coordinated security work:

- **Start with the most relevant business scenarios.** Use [Adopt and secure AI and data](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) to define the business and security outcomes for AI adoption and [Strengthen security posture and compliance](/en-us/security/zero-trust/security-adoption-scenario-improve-posture) to establish continuous risk reduction, measurable improvement, and support for applicable compliance requirements.
- **Organize, plan, and continuously improve the security work.** Use the [Security Integration and Governance (SIG) discipline](/en-us/security/zero-trust/security-adoption-discipline-strategy) to identify the highest-priority security outcomes, clarify ownership and decision rights, and coordinate work across teams. Use the [technical strategy disciplines](/en-us/security/zero-trust/security-adoption-discipline-overview) to plan end-to-end security outcomes across the required capabilities. Apply [SAF technology guidance](/en-us/security/zero-trust/security-adoption-model) across identities, data, applications, AI, endpoints, infrastructure, and networks, and use [Security Posture Management](/en-us/security/zero-trust/security-adoption-discipline-posture) to monitor exposure and control effectiveness, prioritize improvements, and continuously adapt implementation as the environment and risk change.

The result should be a prioritized security roadmap with clear business and security outcomes, accountable decision owners, end-to-end security requirements, and measurable improvements across the technologies on which AI depends.

## Implement and operate

Put the prioritized roadmap into action by implementing and operating security capabilities across identities, data, applications, AI, endpoints, infrastructure, networks, development practices, and security operations. Use Microsoft security products and implementation guidance together with architecture, operating processes, and accountable ownership to implement and sustain these protections.

The following five activities provide a practical path for strengthening security foundations as organizations adopt AI and agentic capabilities.

### Establish your security baseline

Start by understanding your current security posture, business-critical assets, and the areas where improvement can reduce the most material risk. Use assessments, posture management, architecture reviews, and operational findings to identify gaps and translate the prioritized roadmap into implementation work.

Use findings from the [Microsoft Zero Trust Workshop for AI security](/en-us/security/zero-trust/workshop-zero-trust-ai-security), the [Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview), [Microsoft Security Exposure Management](/en-us/security-exposure-management/), and other architecture reviews and assessments to inform the baseline.

Connect findings to the critical assets, sensitive data, business processes, and dependencies they affect. Prioritize improvements based on business impact and security risk, assign accountable decision owners, and track the work through implementation.

### Discover and prioritize security exposure

Continuously discover your organization's assets, identities, data, applications, AI systems, agents, and dependencies. Assess the vulnerabilities, misconfigurations, attack paths, and other exposures that could affect them.

Use [Microsoft Security Exposure Management](/en-us/security-exposure-management/) to understand how individual weaknesses combine into meaningful attack paths and where remediation can reduce the most risk. Prioritize findings by using threat context, exploitability, business impact, critical dependencies, and the relationships among assets and controls.

Use [Microsoft Perception](https://www.microsoft.com/security/business/microsoft-perception-agentic-system) agents and playbooks, where applicable, to help prioritize exposure, coordinate suitable remediation work, and verify progress. Automate repeatable work through defined playbooks and guardrails while people remain responsible for priorities, risk decisions, exceptions, approval of high-impact actions, and accountability.

Where supported, use compensating controls and temporary protections to reduce reachable attack paths or limit exploitation while teams complete patching, privilege reduction, configuration changes, or architectural improvements. Temporary protection should reduce immediate exposure, not replace permanent remediation.

For AI, maintain visibility into approved, experimental, custom-built, embedded, and unsanctioned applications and agents. Follow [Discover AI apps and data](/en-us/security/security-for-ai/discover) and use relevant Microsoft security posture capabilities to identify AI usage, data exposure, cloud risks, and control gaps.

### Protect your foundations and AI

Strengthen the security foundations that business applications, cloud services, AI systems, and agents depend on. Apply protections across identities, devices, data, applications, development, infrastructure, networks, and threat protection based on business impact, exposure, and risk.

Follow [Prepare for AI security](/en-us/security/security-for-ai/prepare) and [Protect AI apps and data](/en-us/security/security-for-ai/protect) to apply AI-specific protections alongside existing security controls. Protect prompts and context, grounding data, outputs, connected data sources, agent identities and permissions, tools, connectors, and other data flows from oversharing, misuse, manipulation, and unauthorized access.

Follow [Prepare your organization for AI security](/en-us/security/security-for-ai/prepare) and [Protect AI applications and data](/en-us/security/security-for-ai/protect) to apply AI-specific protections alongside established security controls.

Protect:

- Human, workload, and agent identities and credentials.
- Prompts, context, memory, grounding data, outputs, and connected data sources.
- Applications, models, APIs, tools, connectors, plugins, and agent-to-agent interactions.
- Development environments, software dependencies, build and deployment pipelines, runtimes, and platforms.
- Endpoints, infrastructure, networks, browsers, cloud services, and external dependencies.

Apply the Zero Trust principles of **verify explicitly**, **use least privilege**, and **assume compromise (assume breach)** as AI systems and agents introduce new identities, permissions, data flows, models, tools, memory, connectors, and autonomous actions.

Apply least privilege to agent identities, data access, connected tools, and actions. Protect credentials and secrets, maintain accurate production inventories, and integrate threat modeling and software supply-chain o design, development, testing, deployment, and change management.

Use data classification, access controls, data loss prevention, monitoring, and other safeguards to reduce oversharing, unauthorized access, manipulation, and leakage through prompts, grounding data, outputs, connected data sources, and agent actions.

Use Microsoft security products and approved implementation patterns to automate and enforce these protections where practical. Maintain defined paths for exceptions and explicit risk acceptance when standard controls can't be applied.

### Integrate security operations (SecOps/SOC)

Integrate security operations (SecOps) to bring signals, threat intelligence, exposure context, detection, investigation, response, and recovery together. This integration reduces gaps, handoffs, and slowdowns across security processes.

[Integrated Security Operations Center (ISOC)](https://www.microsoft.com/security/business/solutions/integrated-security-operations-center) in Microsoft Defender brings XDR and SIEM capabilities, threat intelligence, automation, and AI together in the Microsoft Defender portal. Shared signals, context, and workflows help security teams and agents detect, investigate, prioritize, and respond to threats across the environment.

This integrated approach connects pre-breach exposure reduction with post-breach detection, investigation, response, and recovery.

Use integrated security operations to:

- Bring together signals from Microsoft and non-Microsoft environments.
- Correlate activity across identities, endpoints, applications, data, cloud infrastructure, networks, and AI systems.
- Give practitioners, agents, and automation the context needed to investigate and act.
- Connect exposure-management findings to detection, response, remediation, and recovery workflows.
- Feed lessons from incidents and investigations back into architecture, posture management, and security priorities.

With this integration you can use automation, playbooks, and AI agents to replace suitable repetitive manual work and accelerate operations.

### Govern change and improve continuously

Review material changes to business processes, identities, data, applications, AI systems and agents, models, tools, permissions, connectors, infrastructure, and external dependencies. Use appropriate reassessment, testing, approval, documentation, and monitoring when changes affect risk.

Use posture and exposure findings, incidents, near misses, threat intelligence, assessment results, operational evidence, and user feedback to continuously improve architecture, controls, implementation patterns, policies, training, and the prioritized roadmap.

## Measure progress

Use a small set of outcome measures that leaders and practitioners can act on. Example measures include:

- Percentage of AI applications and agents with accountable owners, risk classifications, and documented dependencies.
- Percentage of critical assets and sensitive data paths covered by required identity, data, development, infrastructure, monitoring, response, and recovery controls.
- Time to identify, assign, contain, and remediate high-risk exposure findings.
- Age of unresolved or explicitly accepted exceptions.
- Coverage of strong authentication, least privilege, credential and secret management, secure development, logging, monitoring, and incident response for material AI systems.
- Change in exposure, control effectiveness, and resilience over time, including improvements driven by incidents, exercises, assessments, and operational findings.

## Recommended next steps

Strengthening security foundations is a continuous process. You don't need to start with every activity at once. Choose the actions that best match your current priorities, use the findings from each to inform the others, and update the roadmap as business needs, technology, and threats change.

- **Identify and reduce your most important exposures.** Use [Microsoft Security Exposure Management](/en-us/security-exposure-management/) and [Microsoft Perception](/en-us/security/agentic-security/agentic-security-overview) to help prioritize exposure, coordinate suitable remediation work through governed agents and playbooks, and verify progress while keeping people accountable for consequential decisions.
- **Modernize security operations.** Use the [Security Operations (SecOps/SOC) discipline](/en-us/security/zero-trust/security-adoption-model) guidance in SAF and [Integrated Security Operations Center (ISOC)](https://www.microsoft.com/security/business/solutions/integrated-security-operations-center) to connect exposure reduction with detection, investigation, response, and recovery. Use shared signals, context, automation, playbooks, and AI to help people and agents work together across security operations.
- **Build a prioritized Zero Trust roadmap.** Use the [Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-overview) to bring business, technology, and security stakeholders together, combine business context with technical assessment evidence, and create a prioritized implementation roadmap.
- **Assess your current configuration.** Use the [Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview) to evaluate supported Microsoft 365 and Azure configurations, identify gaps, and add technical evidence to planning and improvement activities.

Use the [Microsoft Security Adoption Framework (SAF)](/en-us/security/zero-trust/security-adoption-model) to connect these activities as part of one security program rather than treating individual assessments, products, or projects as separate efforts. Start with the action that addresses your most important current need, then use what you learn to update the roadmap and guide the next cycle of implementation, operation, measurement, and improvement.