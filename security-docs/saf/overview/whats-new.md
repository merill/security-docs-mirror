---
layout: Conceptual
title: What's new in Microsoft security guidance | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/overview/whats-new
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Discover significant customer-visible updates across Microsoft security guidance, including Zero Trust, SAF, AI security, security disciplines, standards, best practices, and applicable SFI lessons.
ms.date: 2026-11-13T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: whats-new
locale: en-us
document_id: 5652bd00-8984-27a4-0287-f59232170013
document_version_independent_id: 5652bd00-8984-27a4-0287-f59232170013
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/overview/whats-new.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/overview/whats-new
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/overview/whats-new.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 966354a2-9e4b-2660-bb07-70a38958acca
---

# What's new in Microsoft security guidance | Microsoft Learn

Use this page to discover significant customer-visible updates across the Microsoft Security Guidance Center and find guidance that can help you improve strategy, architecture, implementation plans, engineering, and security operations.

Microsoft's [Secure Future Initiative (SFI)](../../zero-trust/sfi/secure-future-initiative-overview) is Microsoft's internal security transformation program. The [Microsoft Security Adoption Framework (SAF)](../../zero-trust/security-adoption-model) is customer-facing guidance informed by applicable SFI lessons, Zero Trust principles, and security best practices.

## November 2026

### Accelerate and measure Zero Trust

- The [Microsoft Zero Trust Workshop](../../zero-trust/workshop-zero-trust-overview) provides a web-based planning experience across eight Workshop pillars, including DevSecOps. It helps business, security, and technology stakeholders turn current-state discussions, technical findings, risks, and dependencies into a prioritized implementation roadmap.
- The [Zero Trust Assessment](../../zero-trust/assessment/overview) is a complementary source of programmatically generated findings for supported configurations. Use its results when evidence from the environment can improve prioritization. The Workshop covers eight pillars; the current Assessment evaluates seven and doesn't include a DevSecOps assessment.

### Plan security adoption and architecture

- The [Microsoft Security Adoption Framework (SAF)](../../zero-trust/security-adoption-model) more clearly connects business priorities and risk to business scenarios, security disciplines, technologies, and technical solutions. This structure helps organizations move from desired security outcomes to coordinated security work and implementation.
- The [Microsoft Cybersecurity Reference Architectures (MCRA)](../../zero-trust/microsoft-reference-architecture) and [SAF technology guidance](../../zero-trust/deploy/overview) make architecture and implementation routes easier to discover and connect durable security concepts with the technologies that implement them.

### Secure AI adoption

- The [AI security transformation themes in SAF](../scenarios/ai-security/overview) connect emerging AI security priorities to durable practices: strengthen security foundations, use agents and automation to increase defensive speed and scale, and apply appropriate controls to AI agents and agentic systems.
- The [AI security Workshop pillar](../../zero-trust/workshop-zero-trust-ai-security) helps teams organize planning across identities, data, applications, infrastructure, agents, and operations and turn the work into a prioritized roadmap.

### Use standards and framework mappings

- The [security standards and frameworks hub](../../zero-trust/security-standards-and-frameworks) provides a discovery path from external frameworks and models into relevant SAF and Microsoft guidance without treating a framework as a product deployment plan.
- Updated mappings cover the [NIST Cybersecurity Framework 2.0](../framework-mappings/nist-cybersecurity-framework), [CIS Controls and Benchmarks](../framework-mappings/cis-controls-benchmarks), [The Open Group Zero Trust](../framework-mappings/open-group-zero-trust), [CISA Zero Trust Maturity Model](../../zero-trust/cisa-zero-trust-maturity-model-intro), and [DoD Zero Trust Strategy](../../zero-trust/dod-zero-trust-strategy-intro). The mappings connect desired outcomes to SAF disciplines, technologies, and implementation guidance while preserving each framework's scope.

### Strengthen security operations and development security

- The [SAF SecOps discipline](../../zero-trust/security-adoption-discipline-security-operations) and [SecOps Workshop pillar](../../zero-trust/workshop-zero-trust-security-operations) provide clearer routes from operating-model decisions to telemetry, detection, investigation, response, threat hunting, automation, and continuous improvement.
- The [SAF Development Security discipline](../../zero-trust/security-adoption-discipline-development-security) and [DevSecOps Workshop pillar](../../zero-trust/workshop-zero-trust-devsecops) connect secure engineering governance with identities, repositories, dependencies, pipelines, software supply chains, deployments, and operational feedback.

### Apply Microsoft security best practices

- The [Microsoft security best practices overview](../../zero-trust/security-best-practices-overview) brings together practical guidance across strategy, governance, architecture, implementation, and operations. Use these patterns as implementation input and adapt them to your organization's risks, architecture, regulatory obligations, capabilities, and resources.

## Secure Future Initiative progress and lessons for customers

The [Secure Future Initiative (SFI)](../../zero-trust/sfi/secure-future-initiative-overview) is a multiyear Microsoft security transformation program focused on improving how Microsoft designs, builds, tests, and operates products, services, and infrastructure.

SFI combines changes across culture, governance, engineering, and operations. It applies **Secure by Design**, **Secure by Default**, and **Secure Operations**, together with Zero Trust principles, across six engineering pillars. The updates and lessons below preserve the customer-relevant content from the former separate SFI What's New feed.

### Track ongoing progress

The latest SFI progress report was published in July 2026. It describes continued progress across the six SFI engineering pillars and highlights how Microsoft is adapting its security approach as threats, technologies, and AI capabilities evolve.

The July 2026 report describes three broad areas of progress:

- **Secure foundations:** Strengthen identity, tenant, network, engineering, inventory, and telemetry foundations and continuously validate their effectiveness.
- **Proactive defense:** Detect and mitigate threats earlier by combining threat intelligence, security research, automation, AI, centralized telemetry, and faster response.
- **Future-ready security:** Prepare security architecture and engineering for changes such as AI agents, post-quantum cryptography, confidential computing, and evolving attacker capabilities.

Across these areas, Microsoft's experience reinforces a consistent lesson: effective security depends on reinforcing controls across identities, applications, data, infrastructure, networks, engineering systems, and operations rather than isolated security controls.

For detailed status, metrics, and objective-level progress, see the [July 2026 SFI progress report](https://www.microsoft.com/en-us/trust-center/security/secure-future-initiative/sfi-progress-report-july-2026). Earlier reports are also available:

- [November 2025 SFI progress report](https://www.microsoft.com/en-us/trust-center/security/secure-future-initiative/sfi-progress-report-november-2025)
- [April 2025 SFI progress report](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/sfi-april-2025-progress-report.pdf)
- [September 2024 SFI progress report](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/SFI_September_2024_progress_report.pdf)

### Security in the age of AI

AI changes both the threat landscape and the speed of security work, but it doesn't replace fundamental security practices.

Attackers can use AI to accelerate vulnerability discovery, identify attack paths, and scale operations. Defenders can use the same advances to identify weaknesses earlier, improve detection, accelerate investigations, and respond at machine speed where appropriate.

This shift increases the importance of strong security foundations. Identity controls, asset inventory, secure architecture, telemetry, segmentation, secure engineering, and operational discipline provide the context and control points that AI-enabled defense depends on.

Organizations should also reconsider the boundary between manual and automated security work. Agents, automation, tools, and people can each perform the work they're best suited to perform. Automation and agents can perform suitable repeatable analysis, investigation, and response at greater speed and scale, while people continue to provide judgment, expertise, oversight, and accountability where required.

These changes connect to the [AI security transformation themes in SAF](../scenarios/ai-security/overview): strengthening security foundations, using agents and automation to increase defensive speed and scale, and applying appropriate security controls to AI agents and agentic systems.

### Secure foundations

The latest SFI work reinforces that security foundations must operate as a system of reinforcing controls.

#### Identity and secrets

Microsoft continues to strengthen identity as a primary security control plane. SFI work includes phishing-resistant multifactor authentication, hardware protection for cryptographic keys, standardized identity libraries, reduction of long-lived credentials, stronger token validation, and preparation for post-quantum cryptography.

A key lesson is that identity protection includes more than users. Workload identities, applications, credentials, certificates, tokens, and cryptographic keys all require controlled lifecycles and appropriate protection.

#### Tenants and isolation

Microsoft continues to reduce risk from unused tenants, applications, persistent privileges, unmanaged access paths, and other resources that can create lateral-movement opportunities.

SFI emphasizes lifecycle governance from creation through retirement, secure defaults, least privilege, separation between production and nonproduction environments, and continuous removal of unnecessary access and resources.

#### Networks and infrastructure

SFI network improvements combine accurate asset inventory, identity-aware access, segmentation, secure configuration, and removal of unnecessary public exposure.

Segmentation is part of a broader containment strategy. Identity, application, tenant, network, and infrastructure boundaries work together to restrict lateral movement and reduce blast radius when one control is bypassed.

#### Engineering systems

Microsoft continues to move secure engineering from optional guidance and reactive remediation toward governed development environments, standardized pipelines, secure deployment controls, software supply-chain protection, and security checks that operate throughout the development lifecycle.

These practices help make secure engineering repeatable and easier to adopt consistently across large engineering organizations.

### Continuously validate security

Security foundations remain effective only when organizations can determine whether controls are still operating as intended.

SFI investments in comprehensive inventory, standardized telemetry, centralized security data, enforced baselines, and detection of configuration drift illustrate the importance of continuous validation rather than relying only on periodic assessment.

Continuous visibility helps security teams identify changes, detect gaps, investigate incidents, validate security controls, and prioritize remediation based on current conditions.

This creates a feedback loop between security operations, security posture, architecture, engineering, and governance. Operational evidence can identify systemic weaknesses, and those findings can drive improvements to architectures, engineering practices, policies, and controls.

### Proactive defense

SFI continues to expand Microsoft's ability to find and address security weaknesses before attackers can exploit them. This work includes:

- AI-assisted vulnerability discovery and validation.
- Threat intelligence and proactive threat hunting.
- Behavioral and baseline-driven detection.
- Centralized security telemetry for investigation and hunting.
- Faster vulnerability mitigation and remediation.
- Greater automation of suitable detection, investigation, and response activities.
- Increased transparency about vulnerabilities and security incidents.

The goal isn't simply to add AI to existing manual processes. Organizations should redesign suitable security workflows so that agents, automation, tools, and people can work together to increase speed, consistency, and scale while preserving appropriate oversight and accountability.

### Future-ready security

Security architecture must also prepare for changes in technologies and threats.

Recent SFI work includes preparation for post-quantum cryptography, increased use of hardware-backed protections and confidential computing, security controls for AI agents, improvements to platform integrity, and continued modernization of legacy authentication and cryptographic systems.

These investments illustrate a broader principle: organizations should identify security dependencies that are difficult or slow to change and begin modernization before emerging threats or technology transitions make those changes urgent.

### Progress across the SFI engineering pillars

SFI continues to organize engineering execution around six pillars:

| SFI engineering pillar | Current focus |
| --- | --- |
| **Protect identities and secrets** | Strengthen identity systems, credentials, cryptographic keys, authentication, workload identities, and preparation for post-quantum cryptography. |
| **Protect tenants and isolate systems** | Govern tenant and application lifecycles, enforce least privilege, reduce persistent access, and prevent lateral movement across security boundaries. |
| **Protect networks** | Maintain accurate inventory, reduce public exposure, strengthen segmentation, and apply secure network controls consistently. |
| **Protect engineering systems** | Protect source code, development environments, build and release pipelines, software supply chains, and deployment processes. |
| **Monitor and detect cyberthreats** | Improve inventory, telemetry, log retention, centralized investigation data, behavioral detection, and threat hunting. |
| **Accelerate response and remediation** | Reduce time to mitigation, improve vulnerability transparency, automate suitable response activities, and strengthen customer communication during security incidents. |

SFI pillars represent how Microsoft organizes and prioritizes its own security transformation. They aren't intended to replace Zero Trust, SAF, NIST CSF, or an organization's existing security governance model. For current objective-level status and metrics, use the latest SFI progress report as the authoritative source.

### Apply lessons from SFI

Organizations should use SFI as a source of Microsoft implementation experience rather than as a blueprint that must be reproduced exactly.

Several lessons apply broadly:

- **Strengthen foundations first.** Identity, inventory, architecture, telemetry, secure engineering, segmentation, and operational controls reinforce one another.
- **Design security into systems and processes.** Move important controls earlier into architecture, engineering, deployment, and lifecycle management instead of relying primarily on later detection and remediation.
- **Use secure defaults and paved paths.** Make secure practices easier to adopt consistently while allowing exceptions to be explicitly understood and governed.
- **Continuously validate controls.** Detect configuration drift, missing telemetry, unmanaged assets, excessive privilege, and other gaps as operating conditions change.
- **Connect operations back to improvement.** Use incidents, threat intelligence, hunting, posture findings, and attack simulation to improve architecture, engineering, governance, and controls.
- **Use AI and automation where they improve security outcomes.** Automate suitable repeatable work while preserving human judgment, expertise, oversight, and accountability where required.
- **Prepare for transitions before they become emergencies.** Long-running changes such as cryptographic modernization, identity modernization, and removal of legacy systems require sustained planning and investment.

Explore implementation patterns for [phishing-resistant multifactor authentication](../../zero-trust/sfi/phishing-resistant-mfa), the [Safe Secrets Standard](../../zero-trust/sfi/safe-secrets-standard), [software supply-chain protection](../../zero-trust/sfi/protect-software-supply-chain), and [security log retention standards](../../zero-trust/sfi/security-log-retention-standards).

Use [How Microsoft Secure Future Initiative (SFI) informs SAF](../foundations/sfi/saf-mapping) and [Apply lessons from SFI](../../zero-trust/sfi/secure-future-initiative-adoption) to translate applicable lessons into sustained outcomes based on your organization's business priorities, risks, roles, technologies, and implementation needs.