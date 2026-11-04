---
layout: Conceptual
title: Microsoft Secure Future Initiative (SFI) overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Get an overview of Microsoft's Secure Future Initiative (SFI) and best practices cybersecurity.
ms.date: 2026-07-23T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 1045f075-512f-a8dc-f741-bf196d8e938a
document_version_independent_id: 1045f075-512f-a8dc-f741-bf196d8e938a
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/0661002d-4d3e-4257-b5a8-1276befa15d4
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/05df39fb-4203-4146-99d8-5ff1e833520c
platformId: 817e61fb-c12b-8df2-57f2-a9e17ca35c00
---

# Microsoft Secure Future Initiative (SFI) overview | Microsoft Learn

The Secure Future Initiative (SFI) initiative launched in November 2023 as a multiyear effort to increasingly secure the way in which Microsoft designs, builds, tests, and operates its products and services.

For the first year or so after the launch, we shifted to security as a critical priority across Microsoft. We focused on internal security training, and dedicated extensive engineering resources to improve security and mitigate risk across the company.

Over time, SFI efforts continue to evolve as a cross-company initiative in structured waves, keeping pace with shifts in the threat landscape. The ongoing evolution informs security innovation, development, and best practices across Microsoft. It also provides us with ongoing opportunities to work with customers and the broader security industry to strengthen our collective defenses.

## SFI progress reports

We produce periodic SFI progress reports about initiative updates and progress. Reports cover new security capabilities, news from engineering pillars, mapping to the NIST Cybersecurity Framework, and implementation guidance aligned with Zero Trust principles.

- Get a summary of the latest updates and progress over time in [What's new in SFI?](secure-future-initiative-whats-new)
- [Read the latest SFI blog](https://www.microsoft.com/en-us/security/blog/2026/07/10/securing-our-future-july-2026-progress-report-on-microsofts-secure-future-initiative/), and [review the latest SFI report from July 2026](https://www.microsoft.com/trust-center/security/secure-future-initiative/sfi-progress-report-july-2026).
- View earlier reports:

    - [SFI report - November 2025](https://www.microsoft.com/trust-center/security/secure-future-initiative/sfi-progress-report-november-2025).
    - [SFI report - April 2025](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/sfi-april-2025-progress-report.pdf).
    - [SFI report - September 2024](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/SFI_September_2024_progress_report.pdf).

## SFI architecture

SFI architecture design focuses on a set of security principles that are adopted and integrated into Microsoft culture and governance. These security principles are applied to a set of focus areas (engineering pillars) by means of processes, standards, and continuous improvements.

![Diagram summarizing the secure future initiative (SFI).](../media/secure-future-initiative/secure-future-initiative-overview.png)

## Security principles

SFI focuses on these principles.

![Diagram summarizing the secure future initiative (SFI) principles.](../media/secure-future-initiative/secure-future-initiative-security-principles.png)

We use these principles to:

- **Innovate**: Build by-design security features into Microsoft platforms and services.
- **Implement**: Introduce security innovations in Microsoft products with new features, secure defaults, and enforced standards.
- **Guide**: Provide customers with guidance and best practices to deploy, operate, and continuously improve security.

## SFI pillars, Zero Trust, and NIST

The SFI initiative focuses on six prioritized engineering pillars. Multiple objectives align with each pillar. Each objective represents a significant effort to improve security and reduce risk for Microsoft and our customers in a specific pillar area.

The pillars and objectives clearly align to Microsoft's [Zero Trust principles](../zero-trust-overview) and the [National Institute of Standards and Technology (NIST) Cybersecurity Framework](https://www.nist.gov/cyberframework).

## Pillar mapping

The following table shows the pillar mapping. Get more details on NIST function acronyms in the next section.

| **Pillar** | **Zero Trust principle** | **NIST CSF Function** |
| --- | --- | --- |
| **1. Protect identities and secrets** Ensure that only verified and authorized identities can access resources. | **Verify explicitly**: Enforce continuous, context-aware, passwordless authentication (Windows Hello, FIDO2 passkeys, certificate, etc.).**Use least privilege**: Reduce overprivileged identities and enforce privileged identity management/just-in-time access.**Assume breach**: Rotate credentials rapidly and use short-lived tokens to reduce blast radius. | **PR**: Implement controls to secure credentials, secrets, and access.**DE**: Continuously monitor identity activities for anomalies. |
| **2. Protect tenants and isolate systems** Minimize compromise blast radius by ensuring that tenants, environments, and systems are independently isolated and secured, with no implicit trust between them. | **Verify explicitly**: Apply inter-tenant authentication and authorization with explicit approval and logging.**Use least privilege**: Limit access between environments to approved paths only.**Assume breach**: Use tenant isolation as a containment boundary. | **ID**: Discover tenant and production assets.**PR**: Apply isolation, segmentation, and strong boundaries.**DE**: Look for isolation boundary violations or lateral movement. |
| **3. Protect networks** Limit lateral movement and unauthorized access by means of granular network segmentation and identity-aware connectivity. | **Verify explicitly**: Shift from implicit network trust to policy-based, identity-verified connections.**Use least privilege**: Enforce micro-segmentation and just-enough access for workloads and endpoints.**Assume breach**: Treat every network zone as potentially hostile. Isolate high-value assets and enforce strict egress control. | **ID**: Inventory and understand networking assets.**PR**: Apply network security controls (segmentation, encryption, etc.). |
| **4. Protect engineering systems** Secure the entire software development lifecycle (SDLC) and delivery lifecycle by ensuring that code, build systems, and pipelines are tamper-resistant, auditable, and trustworthy. | **Verify explicitly**: Authenticate every action in the SDLC, from code commits to builds, with traceable, signed identities.**Use least privilege**: Restrict developer, agent, and pipeline access based on role and build context.**Assume breach**: Segregate build systems and enforce code signed and reproducible builds to prevent tampering. | **ID**: Understand build/test/deployment systems and dependencies.**PR**: Secure software pipelines, development tooling and artifacts.**GV**: Apply engineering policies, standards, secure design. |
| **5. Monitor and detect threats** Quickly detect, correlate, and prioritize security threats across Microsoft systems by unifying telemetry and analytics. | **Verify explicitly**: Use telemetry-driven, continuous validation of user, device, and workload behavior.**Use least privilege**: Enforce adaptive access control with detection and dynamic conditional access policies.**Assume breach**: Detect anomalies and behavior deviations on the premise that attackers might already have access to resources. | **ID**: Maintain awareness of all monitored systems.**PR**: Ensure protective controls generate telemetry.**DE**: Analyze logs and alerts to identity threats.**RS**: Detect trigger response workflows. |
| **6. Accelerate response and remediation** Minimize the impact and duration of security incidents with automation, coordinated response, and continuous learning. | **Verify explicitly**: Continuously reassess trust in identities, devices, and systems after detection events.**Use least privilege**: Automate token revocation, key rotation, and access removal during response.**Assume breach**: Continuously feed incident learnings into system improvements for rapid containment and ongoing hardening. | **ID**: Understand scope and assets for response. Track changes and revisit baselines after the incident.**RC**: Restore secure operations after incidents. Remediate vulnerabilities and ensure resilience.**RS**: Detect trigger response workflows.**GV**: Apply lessons in governance and standards. |

### NIST functions

The following table summarizes core NIST functions and categories, taken from the [downloadable CSF 2.0 article](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).

| **Function** | **Category** |
| --- | --- |
| **Govern (GV)**Establish policies, procedures, and culture for managing cybersecurity risk, and aligning it with overall business strategy and outcomes of the other NIST functions. | **GV.OC**-Organizational Context**GV.RM**-Risk Management Strategy**GV.RR**-Roles, Responsibilities, and Authorities.**GV.PO**-Policy**GV.OV**-Oversight**GV.SC**-Cybersecurity Supply Chain Risk Management |
| **Identify (ID)**Understand assets, systems, data, and potential threats to build a strong organizational understanding of cyber risk. | **ID.AM**-Asset Management**ID.RA**-Risk Assessment**ID.IM**-Improvement |
| **Protect (PR)**Implement safeguards like access controls, data security, and training to ensure critical services can be delivered. | **PR.AA**-Identity Management, Authentication, and Access Control.**PR.AT**-Awareness and Training**PR.DS**-Data Security.**PR.PS**-Platform Security**PR.IR**-Technology Infrastructure Resilience |
| **Detect (DE)** Develop and implement activities such as continuous monitoring to identify the occurrence of cybersecurity events. | **DE.CM**-Continuous Monitoring**DE.AE**-Adverse Event Analysis |
| **Respond (RS)** Take action regarding a detected incident, including analysis, containment, eradication, and communication. | **RS.MA**-Incident Management**RS.AN**-Incident Analysis**RS.CO**-Incident Response Reporting and Communication.**RS.MI**-Mitigation |
| **Recover (RC)**Restore systems and operations post-incident, emphasizing planning, communication, and improvement to minimize disruption. | **RC.RP**-Incident Recovery Plan Execution**RC.CO**-Incident Recovery Communication |