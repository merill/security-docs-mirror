---
layout: Conceptual
title: Developer Security Stories with Azure DevOps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/developer-security-stories
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: v-cjwoodling
author: cjwoodling6
description: This approach improves shared accountability, enables earlier remediation, and reinforces Secure by Design principles across the product lifecycle.
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2026-09-25T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1028
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
ai-usage: ai-generated
locale: en-us
document_id: 8a687d57-d866-d1ad-ffc8-c4b46b529ea1
document_version_independent_id: 8a687d57-d866-d1ad-ffc8-c4b46b529ea1
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/developer-security-stories.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/developer-security-stories
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/developer-security-stories.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/5bd2b3fa-c186-4b92-a3c8-09f22a249d37
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7eba7926-b7b2-4a7a-bf89-e6ac53b3e7f6
platformId: 1f4ff507-c24e-badc-47f0-1d246da0cb51
---

# Developer Security Stories with Azure DevOps | Microsoft Learn

**Pillar name: Protect engineering systems** **Practice name: Tracking security work as backlog items**

As engineering teams accelerate delivery through continuous development, security requirements often become fragmented across tools, reports, and specialized teams. Microsoft addresses this challenge by translating critical security requirements into developer security stories that integrate directly into standard engineering workflows. By embedding security into the Azure DevOps backlog alongside feature work, organizations can operationalize Secure by Design principles, improve accountability, and ensure that security is delivered with the same rigor and visibility as core product functionality.

## Context and problem

As organizations adopt continuous delivery and rapidly evolve their products, security requirements increasingly originate from multiple sources. This includes threat modeling, UX reviews, compliance systems, red teams, code scanning, and live security incidents. When these requirements are tracked outside normal engineering workflows, they're often delayed, inconsistently implemented, or deprioritized in favor of feature delivery.

Common challenges organizations face include:

- Security requirements documented in reports or tools that are disconnected from engineering backlogs
- Threat modeling outputs that don't translate into actionable, prioritized engineering work
- Inconsistent interpretation of mitigations across teams, leading to uneven security posture
- Security ownership concentrated in specialized teams rather than shared across engineering
- Late discovery of design‑level security gaps that are costly to remediate after release
- Difficulty maintaining Secure by Design intent as products evolve through continuous releases

In each of these cases, security requirements that remain outside the backlog are less likely to be implemented consistently, verified in code, or prioritized with the same discipline as feature and reliability work.

## Solution

Microsoft addresses this challenge by translating significant security requirements into **developer security stories** that the team tracks as first-class Azure DevOps work items alongside feature and reliability work. Under this practice, developers can implement, test, and close meaningful security requirements through normal engineering workflows.

Microsoft’s approach includes:

- Defining security stories with clear acceptance criteria, engineering ownership, and evidence of completion
- Translating threat modeling outputs, design review findings, compliance issues, and operational security signals into actionable work items
- Tracking security work in the same backlog, sprint, and release process used for other engineering commitments
- Using engineering controls such as pull requests, branch policies, and validation checks to reinforce completion criteria
- Using security tooling to generate findings, but requiring tracked engineering work when durable design, code, configuration, or identity changes are needed

By centralizing security requirements as developer security stories, organizations embed Secure by Design into everyday engineering decisions without creating a separate security delivery process.

## Guidance

Organizations that translate security requirements into developer stories often encounter similar implementation needs. The following use cases show how developer security stories can help translate security expectations into normal engineering work.

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| Teams don't implement threat modeling outputs consistently | Use threat modeling outputs to create security stories that identify the threat scenario, affected component, mitigation, validation method, and engineering owner. Preserve traceability between the threat model and the resulting work item so teams can confirm that mitigations were implemented, not merely documented. Review and update threat-derived stories when architecture or attack surface changes significantly. | [Microsoft Threat Modeling Tool overview](/en-us/azure/security/develop/threat-modeling-tool)[Getting started with the Threat Modeling Tool](/en-us/azure/security/develop/threat-modeling-tool-getting-started)[Architecture strategies for securing a development lifecycle](/en-us/azure/well-architected/security/secure-development-lifecycle) |
| Teams track security requirements outside the DevOps backlog | Track security stories in the same Azure DevOps backlog used for feature work. Use common work item types, tags, ownership fields, and dashboards so product, engineering, and security teams can review security debt together. Define a standard security story template with risk, mitigation, acceptance criteria, and evidence of completion. | [Manage work items effectively](/en-us/azure/devops/boards/backlogs/manage-work-items)[Update work items with templates in Azure Boards](/en-us/azure/devops/boards/backlogs/work-item-template)[Create and manage your backlog](/en-us/azure/devops/boards/backlogs/create-your-backlog) |
| Teams need to durably remediate code, dependency, or secret findings | Enable GitHub Advanced Security for Azure DevOps so you can review and triage code scanning, dependency scanning, and secret scanning findings. Convert recurring, high-severity, or design-affecting findings into developer security stories instead of treating them as a separate queue. Treat exposed secrets as compromised, replace them, and track the structural fix required to prevent recurrence. | [Configure GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/configure-github-advanced-security-features)[Set up code scanning for GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-code-scanning)[Set up dependency scanning for GitHub Advanced Security](/en-us/azure/devops/repos/security/github-advanced-security-dependency-scanning)[Set up secret scanning for GitHub Advanced Security](/en-us/azure/devops/repos/security/github-advanced-security-secret-scanning) |
| Teams discover infrastructure as code and pipeline weaknesses late | Scan infrastructure as code templates and CI/CD configurations before deployment. Create security stories for issues that require design, permission, or pipeline changes. Use posture management findings to identify broad misconfigurations across repositories, pipelines, service connections, and build environments. Prioritize fixes that reduce blast radius, such as restricted service connections, read-only defaults, and stronger branch protection. | [Configure the Microsoft Security DevOps Azure DevOps extension](/en-us/azure/defender-for-cloud/configure-azure-devops-extension)[Scan for misconfigurations in Infrastructure as Code](/en-us/azure/defender-for-cloud/iac-vulnerabilities)[Overview of Microsoft Defender for Cloud DevOps security](/en-us/azure/defender-for-cloud/defender-for-devops-introduction)[DevOps environment posture management overview](/en-us/azure/defender-for-cloud/concept-devops-environment-posture-management-overview) |
| Applications or pipelines rely on embedded secrets or broad identities | Create security stories that replace hard-coded credentials, long-lived secrets, and broadly privileged service principals with managed identities, workload identities, or Azure Key Vault-backed retrieval patterns. Follow least-privilege principles when assigning access to applications, service principals, and pipeline identities. Treat secret-based authentication as a temporary exception rather than the default model. | [Workload identities overview](/en-us/entra/workload-id/workload-identities-overview)[Securing managed identities in Microsoft Entra ID](/en-us/entra/architecture/service-accounts-managed-identities)[Managed identity best practice recommendations](/en-us/entra/identity/managed-identities-azure-resources/managed-identity-best-practice-recommendations)[Azure Key Vault developer's guide](/en-us/azure/key-vault/general/developers-guide)[Best practices for protecting secrets](/en-us/azure/security/fundamentals/secrets-best-practices) |
| Teams need stronger completion controls for security work | Use pull requests, branch policies, linked work item checks, build validation, and comment resolution to make security story completion measurable. Protect important branches so security-sensitive changes can't bypass normal engineering review. Use dashboards and security overviews to track open findings, coverage, and remediation progress. | [Git branch policies and settings](/en-us/azure/devops/repos/git/branch-policies)[Branch policies overview](/en-us/azure/devops/repos/git/branch-policies-overview)[Security overview on GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-security-overview)[Secure your Azure Pipelines](/en-us/azure/devops/pipelines/security/secrets) |

## Outcomes

### Benefits

- Plan and deliver security requirements with the same rigor as feature work.
- Use threat modeling and design reviews to produce measurable engineering outcomes rather than static documentation.
- Distribute security ownership across engineering teams, reinforcing shared responsibility.
- Identify and address design‑level security gaps earlier, reducing downstream remediation cost.
- Maintain Secure by Design intent despite continuous iteration and release.
- Embed security into standard engineering workflows, improving process consistency, accountability, and operational rigor across teams.

### Trade-offs

- Requires upfront effort to standardize security story templates and workflows.
- Increases backlog volume, requiring disciplined prioritization and triage.
- Demands closer collaboration between security, UX, and engineering roles.
- Might surface design‑level security work earlier than teams are accustomed to planning.

## Key success factors

Successful implementation depends on consistent execution and leadership support:

- Percentage of threat modeling outputs converted into developer security stories
- Time from security requirement identification to story creation and assignment
- SLA adherence for security story remediation
- Coverage of security stories across services and critical attack surfaces
- Evidence that security stories are reviewed and prioritized alongside feature work

## Summary

As products scale and release continuously, organizations can't rely on static security reviews or isolated security teams. By integrating security requirements as developer security stories within standard engineering workflows, teams can translate threat modeling, UX security insights, and compliance signals into actionable engineering work. This approach improves shared accountability, enables earlier remediation, and reinforces Secure by Design principles across the product lifecycle.