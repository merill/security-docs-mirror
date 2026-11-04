---
layout: Conceptual
title: Securing source code with GitHub Advanced Security | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-source-code-github-advanced-security
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: v-cjwoodling
author: cjwoodling6
description: Securing source code with GitHub Advanced Security is an effective way to reduce software supply chain risk, limit credential exposure, and improve remediation speed across engineering systems.
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
document_id: 73f67c27-9180-2a13-9b5a-f6190e94b61e
document_version_independent_id: 73f67c27-9180-2a13-9b5a-f6190e94b61e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-source-code-github-advanced-security.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-source-code-github-advanced-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-source-code-github-advanced-security.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9bdc1705-9b40-49d6-8377-caa0b71fda66
- https://authoring-docs-microsoft.poolparty.biz/devrel/5bd2b3fa-c186-4b92-a3c8-09f22a249d37
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/686ed158-d915-41e9-9760-efa46ba88f6d
- https://authoring-docs-microsoft.poolparty.biz/devrel/7eba7926-b7b2-4a7a-bf89-e6ac53b3e7f6
platformId: 24ce6ca4-b395-6b38-9d34-598d90aebd4c
---

# Securing source code with GitHub Advanced Security | Microsoft Learn

**Pillar name: Protecting engineering systems** **Practice name: Shift security left in the development lifecycle**

Securing source code with GitHub Advanced Security is part of the protect engineering systems pillar of the Secure Future Initiative (SFI), which focuses on reducing risk across the software development lifecycle by hardening engineering environments, strengthening supply chain controls, and embedding security directly into developer workflows. This pattern helps organizations identify vulnerable code, exposed secrets, and risky dependencies earlier so they can reduce and prevent technical security debt and remediate issues before they reach production.

## Context and problem

Modern software repositories often contain several of the risks attackers most commonly exploit, including vulnerable code, insecure open-source dependencies, and exposed credentials committed to source control. In large engineering environments, these issues often extend across shared libraries, build pipelines, and downstream applications, increasing both exposure and remediation cost.

Traditional approaches that scan codebases for such issues late in the development cycle or rely on manual review are no longer enough. Organizations need repository-level protections that surface and block risk earlier, at the point where developers write, review, and merge code.

## Solution

To address these challenges, Microsoft expanded adoption of GitHub Advanced Security across GitHub and Azure DevOps repositories. The goal was to embed security controls directly into developer workflows so code, dependencies, and secrets could be evaluated continuously during the development process rather than periodically. For customers implementing this pattern with Microsoft products, the most practical starting point is to enable GitHub Advanced Security for Azure DevOps in Azure Repos, prioritize critical repositories, and phase adoption of code scanning, dependency scanning, and secret protection capabilities with the right level of policy enforcement for each repository.

Microsoft uses the full set of GitHub Advanced Security capabilities embed continuous security control evaluation through:

- Code scanning with CodeQL to detect vulnerabilities in custom code and surface findings during pull request review.
- Dependency scanning and alerting to identify vulnerable open-source components and support faster remediation.
- Secret scanning and push protection to detect exposed credentials and block secrets before they are committed.
- Developer-integrated workflows that support secure-by-design and secure-by-default engineering practices.

This implementation helped Microsoft shift repository security earlier in the lifecycle, reduce exposure from known vulnerabilities and leaked secrets, and create more consistent security expectations across engineering systems. This illustrates an important implementation pattern for customers that starts with broad repository visibility, uses default protections where possible, moves to advanced configurations where needed, and uses policy and reporting features to sustain coverage over time.

## Guidance

Organizations can adopt a similar pattern to secure source code by using the following actionable practices:

| **Use case** | **Recommended action** | **Resources** |
| --- | --- | --- |
| Initial rollout | Start by enabling GitHub Advanced Security for Azure DevOps in Azure Repos, validating permissions and prerequisites, and prioritizing critical repositories. Use default code scanning for quick adoption, then move to advanced setup for multibranch scanning, custom build steps, or self-hosted agent scenarios. | [Configure GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/configure-github-advanced-security-features) |
| Code scanning | Enable code scanning across production repositories and critical shared components. Use custom CodeQL queries where needed to address organization-specific risks, and use troubleshooting guidance to resolve build and analysis issues in compiled-language or customized pipeline environments. | [Set up code scanning for GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-code-scanning)[Use custom queries with GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-code-scanning-queries) |
| Dependency management | Inventory direct and transitive dependencies across supported ecosystems, run dependency scanning after restore or build steps, and prioritize remediation based on severity, exploitability, and business context. Use automated update workflows where possible to reduce time to patch. | [Set up dependency scanning for GitHub Advanced Security](/en-us/azure/devops/repos/security/github-advanced-security-dependency-scanning)[Troubleshoot dependency scanning for GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-dependency-scanning-troubleshoot) |
| Secret protection | Enable historical and real-time secret scanning across code repositories and use push protection to block new exposures. Treat exposed credentials as compromised, revoke and replace them promptly, and review supported secret patterns and detection behavior to improve triage and coverage. | [Set up secret scanning for GitHub Advanced Security](/en-us/azure/devops/repos/security/github-advanced-security-secret-scanning)[Troubleshoot secret scanning for GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-secret-scanning-troubleshoot) |
| Branch protection and merge gates | Use branch policies to require pull requests, reviewers, build validation, linked work items, comment resolution, and status checks on critical branches so unresolved findings and unreviewed changes don't flow into protected branches. | [Git branch policies and settings](/en-us/azure/devops/repos/git/branch-policies)[Customize and extend pull request workflows with pull request status](/en-us/azure/devops/repos/git/pull-request-status)[Configure a branch policy for an external service](/en-us/azure/devops/repos/git/pr-status-policy) |
| Secretless modernization | Replace embedded secrets with managed identities where supported, or use workload identity federation for application or service-principal authentication. Use secret scanning findings as a trigger to reduce long-lived credentials in code, pipelines, and automation workflows. | [Secretless authentication in Azure](/en-us/entra/identity/managed-identities-azure-resources/secretless-authentication)[Managed identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/overview)[Connect to Azure with an Azure Resource Manager service connection](/en-us/azure/devops/pipelines/library/connect-to-azure)[Migrate applications away from secret-based authentication](/en-us/entra/identity/enterprise-apps/migrate-applications-from-secrets) |
| Program measurement and coverage | Use organization-level security reporting to monitor enablement status, alert volume, severity trends, and coverage gaps across repositories. Review coverage regularly to identify repositories that aren't scanned or are missing one or more protections. | [Security overview on GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-security-overview)[Manage Advanced Security permissions for GitHub Advanced Security for Azure DevOps](/en-us/azure/devops/repos/security/github-advanced-security-permissions) |
| Enforce repository-level protections | Configure settings and policies for all repositories in a project, for individual repositories, and for branches of repositories. | [Set Git repository settings and policies](/en-us/azure/devops/repos/git/repository-settings?tabs=browser) |

## Outcomes

### Benefits

- Reduced exposure across source code repositories and engineering systems.
- Earlier detection of vulnerabilities, leaked secrets, and dependency risk.
- Faster remediation through integrated alerts and automated update workflows.
- More consistent security baselines across repositories, teams, and development environments.

### Trade‑offs

- Repository onboarding and policy tuning can require significant upfront effort.
- Developers need training and support to interpret findings and remediate them effectively.
- Dependency updates and remediation gates can introduce workflow friction if not phased in carefully.

## Key success factors

- Percentage of critical repositories onboarded to GitHub Advanced Security for Azure DevOps.
- Percentage of repositories covered by code scanning, dependency scanning, and secret scanning.
- Percentage of high-severity findings resolved before release.
- Mean time to remediate dependency and code scanning alerts.
- Number of secrets blocked, revoked, or replaced before they can be exploited.
- Coverage of branch protections and merge policies for critical repositories.

## Summary

Securing source code with GitHub Advanced Security is an effective way to reduce software supply chain risk, limit credential exposure, and improve remediation speed across engineering systems. Organizations can use this pattern to embed security earlier in the development lifecycle and strengthen the baseline protections that protect modern applications.