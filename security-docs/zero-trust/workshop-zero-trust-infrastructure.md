---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Infrastructure | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-infrastructure
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the Infrastructure pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: b1820328-8f20-bf36-707f-43963622d83f
document_version_independent_id: b1820328-8f20-bf36-707f-43963622d83f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-infrastructure.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-infrastructure
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-infrastructure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/64b65f6c-101f-411a-9b83-9f577fab52d0
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/1a667fd1-8145-4b11-af0f-9f5de205a6e5
platformId: ee2a94db-2d4a-a7b9-e779-8fd8ba1ba683
---

# Microsoft Zero Trust Workshop - Infrastructure | Microsoft Learn

Infrastructure provides the compute, platform, storage, database, API, and management services that host applications and business workloads. The Infrastructure workshop pillar helps organizations reduce implicit trust by continuously assessing, hardening, protecting, and monitoring infrastructure across cloud, multicloud, hybrid, and on-premises environments.

The Infrastructure workshop pillar helps organizations identify security gaps and create a prioritized implementation roadmap for infrastructure governance, posture management, workload protection, vulnerability remediation, and security operations.

The Infrastructure workshop pillar corresponds to the Infrastructure technology defined in the [Microsoft Security Adoption Framework (SAF)](deploy/overview).

## Why focus on infrastructure?

Infrastructure misconfigurations, excessive administrative access, unpatched vulnerabilities, exposed services, and gaps in runtime monitoring can create paths to critical resources. The Infrastructure Workshop applies the Zero Trust principles of verify explicitly, use least privilege, and assume breach throughout the infrastructure lifecycle.

The expected output is an actionable backlog of infrastructure projects prioritized into First, Then, and Next based on organizational risk, dependencies, implementation effort, user impact, coverage, and readiness.

## Infrastructure implementation areas

| **Area** | **Details** |
| --- | --- |
| **Define infrastructure security strategy, ownership, and governance** | Align infrastructure security objectives with business and compliance requirements. Define accountable owners, operating responsibilities, governance rules, notification paths, reporting, and continuous-improvement processes across cloud and hybrid environments. |
| **Establish cloud security posture management** | Continuously assess resources for misconfigurations, policy violations, exposure, attack paths, and coverage gaps. Use security standards, governance rules, secure score, and risk-based recommendations to prioritize remediation across Azure, AWS, Google Cloud, and hybrid resources where applicable. |
| **Manage compliance and security policies** | Identify applicable regulatory and organizational requirements, assign standards, create policies where needed, monitor findings, and track remediation. Use policy and compliance reporting to detect configuration drift and demonstrate progress. |
| **Protect servers and virtual machines** | Plan and deploy workload protection for cloud and hybrid servers. Enable appropriate endpoint protection, vulnerability assessment, file-integrity monitoring, agentless capabilities, just-in-time access, and ongoing health and coverage monitoring. |
| **Protect containers and Kubernetes environments** | Secure clusters, nodes, registries, images, and running containers across supported environments. Apply posture standards, vulnerability scanning, runtime sensors, policy controls, binary-drift monitoring, attack-path analysis, and incident response. |
| **Protect storage services** | Assess storage coverage and configuration, enable appropriate threat protection, malware scanning, and sensitive-data discovery, and monitor security recommendations and attack paths. Integrate alerts with remediation and response workflows. |
| **Protect database services** | Assess database posture and vulnerabilities across supported platforms. Apply workload protection, data-sensitivity context, multicloud or hybrid connectors, attack-path analysis, and monitored remediation and response processes. |
| **Protect APIs and application platform services** | Assess and protect APIs and platform services such as App Service, Key Vault, and resource-management control planes. Track onboarding and coverage, test API security where applicable, remediate recommendations, and monitor threats and attack paths. |
| **Control administrative access** | Enforce least privilege through role-based access control, scoped assignments, privileged access processes, and just-in-time access. Coordinate identity and infrastructure controls so administrative access is approved, time-bound where appropriate, and monitored. |
| **Harden configurations and remediate vulnerabilities** | Define and enforce security baselines for compute, containers, storage, databases, APIs, and platform services. Prioritize vulnerabilities and configuration findings by risk, validate exceptions, and use automated remediation where it is safe and appropriate. |
| **Manage multicloud and hybrid coverage** | Identify dependencies and connect supported cloud and on-premises resources using appropriate connectors and Azure Arc capabilities. Verify resource coverage, sensor and agent health, data flow, permissions, and lifecycle processes. |
| **Monitor workloads and respond to threats** | Establish real-time monitoring, alert triage, suppression governance, investigation, and response for infrastructure threats. Define response strategies and playbooks, test them regularly, and automate repeatable actions where appropriate. |
| **Integrate infrastructure signals into security operations** | Export posture findings, compliance results, vulnerabilities, runtime alerts, and resource-health signals to centralized security operations and SIEM or SOAR platforms. Correlate infrastructure information with identity, device, network, application, and data signals to support investigation and response. |

These areas summarize the Infrastructure workshop pillar. Use the detailed Infrastructure project guidance to review individual projects and implementation considerations.

## How to use the Infrastructure Workshop

Use the web-based Workshop with infrastructure, cloud platform, security architecture, engineering, compliance, application, identity, network, and security operations stakeholders. For each relevant project:

- Review the project objective and applicability to your environment.
- Record the current status, notes, decisions, owners, and known dependencies.
- Consider licensing, implementation effort, user impact, technical prerequisites, coverage, and cross-pillar dependencies.
- Prioritize the project into First, Then, or Next and incorporate it into the implementation roadmap.

[Open the Zero Trust Workshop](https://aka.ms/ztworkshop) and select the Infrastructure pillar.

[Review the detailed Infrastructure project guidance](https://microsoft.github.io/zerotrustassessment/docs/category/infrastructure) for project-level information.

## Assess your infrastructure posture

The Microsoft Zero Trust Assessment can provide programmatically generated findings for supported infrastructure configurations and activity data. Assessment results can help identify technical gaps and inform Workshop discussions, but the Assessment is complementary and is not required to conduct the Infrastructure Workshop. It does not evaluate every Infrastructure Workshop project.

[Learn about the Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview) or [get started with an assessment](/en-us/security/zero-trust/assessment/get-started).

## Who should participate?

- Cloud platform, infrastructure, and solution architecture teams.
- Security architecture, cloud security posture management, security operations, and incident response teams.
- Server, container, storage, database, API, application platform, network, and identity teams.
- Governance, risk, compliance, finance, service management, and business or workload owners.