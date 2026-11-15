---
layout: Conceptual
title: Development security implementation patterns | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/disciplines/development/implementation-patterns
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Apply repeatable patterns to secure development environments, engineering workflows, and delivery pipelines while maintaining development velocity.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: d85b0d32-fdc8-2a91-cdff-c5cf4828c696
document_version_independent_id: d85b0d32-fdc8-2a91-cdff-c5cf4828c696
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/disciplines/development/implementation-patterns.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/disciplines/development/implementation-patterns
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/disciplines/development/implementation-patterns.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9bdc1705-9b40-49d6-8377-caa0b71fda66
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/686ed158-d915-41e9-9760-efa46ba88f6d
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 4943794e-e7b8-223c-9e08-7504919c62f8
---

# Development security implementation patterns | Microsoft Learn

This article provides practical implementation patterns for the [Development Security discipline](/en-us/security/zero-trust/security-adoption-discipline-development). Use these patterns to integrate security into development environments, engineering workflows, and delivery pipelines while maintaining development velocity.

These patterns are not a replacement for the [Microsoft Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), product documentation, or a workload-specific threat model. They provide a durable SAF-level bridge between development security strategy and technical implementation.

## Use these patterns with the DevSecOps Capability Model

The [DevSecOps Capability Model](/en-us/devops/devsecops/capability-model) and SAF are complementary:

- Use the capability model to assess the maturity of software security practices and identify gaps.
- Use SAF to connect improvements to business risk, cross-discipline dependencies, and operating-model decisions.
- Use these patterns as repeatable approaches for closing the highest-priority gaps.

Apply the patterns based on the risk and maturity of your organization and workloads. You do not need to implement every pattern at once.

## Pattern 1: Secure developer environments and toolchains

**Goal**: Reduce the risk that attackers compromise developer endpoints, identities, tools, extensions, or source-control workflows.

Apply these practices:

- Require phishing-resistant authentication where appropriate and enforce least privilege for developer and DevOps roles.
- Use just-in-time access for privileged development and platform administration.
- Harden and monitor developer endpoints, cloud development environments, and build systems.
- Restrict tools, extensions, packages, and integrations to trusted publishers and approved scopes.
- Protect important branches with review, approval, and policy checks.
- Keep auditable records for privileged actions and code changes.
- Include developer environments and source repositories in threat detection and incident-response planning.

Reference guidance:

- [Secure the developer environment for Zero Trust](/en-us/security/zero-trust/develop/secure-dev-environment-zero-trust)
- [Branch policies in Azure DevOps](/en-us/azure/devops/repos/git/branch-policies)
- [Reviewing the audit log in GitHub Enterprise Cloud](https://docs.github.com/enterprise-cloud@latest/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization)

## Pattern 2: Harden the code-to-production path

**Goal**: Prevent attackers from using repositories, pipelines, artifacts, or deployment automation as a privilege-escalation or software supply-chain path.

Apply these practices:

- Map and document how a change moves from a repository to each deployment environment.
- Record which branches, identities, pipelines, approvals, service connections, and artifacts can affect production.
- Protect pipeline definitions and infrastructure-as-code files as production-impacting code.
- Require independent review and approval for high-risk release actions.
- Make artifacts immutable where practical and preserve provenance from source through deployment.
- Scan code, dependencies, secrets, infrastructure as code, and deployment configurations.
- Generate and retain a software bill of materials when required by risk, customer, or regulatory needs.
- Keep cloud authorization and CI/CD authorization aligned so that a pipeline cannot bypass the intended access model.

A simple code-to-production access table can make hidden deployment paths visible. Include the branch, whether review is required, the target environment, who can approve, and the identity used for deployment. Store this documentation with the code and update it as the workflow changes.

Reference guidance:

- [Secure the DevOps platform environment for Zero Trust](/en-us/security/zero-trust/develop/secure-devops-platform-environment-zero-trust)
- [Secure your Azure Pipelines](/en-us/azure/devops/pipelines/security/overview)
- [Securing your end-to-end supply chain](https://docs.github.com/code-security/supply-chain-security/end-to-end-supply-chain/end-to-end-supply-chain-overview)

## Pattern 3: Use federated workload identity instead of pipeline secrets

**Goal**: Replace static credentials with short-lived, explicitly scoped trust relationships.

Apply these practices:

- Configure OpenID Connect (OIDC) federation between CI/CD platforms and cloud identity providers.
- Scope trust conditions to specific organizations, repositories, branches, environments, and workflows.
- Apply least privilege to service principals and workload identities.
- Separate identities for build, test, and production deployment when their privileges differ.
- Store any remaining secrets in managed secret stores, rotate them, and scan repositories and artifacts for exposure.
- Treat internal repositories as potentially accessible to an attacker who has compromised an identity or endpoint. Do not use repository privacy as a secret-management control.

Reference guidance:

- [Workload identity federation in Microsoft Entra](/en-us/entra/workload-id/workload-identity-federation)
- [Configuring OpenID Connect in Azure for GitHub Actions](https://docs.github.com/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-azure)
- [Azure Key Vault basics](/en-us/azure/key-vault/general/basic-concepts)

## Pattern 4: Validate security throughout the lifecycle

**Goal**: Find issues early, verify important controls before release, and use production feedback to improve future releases.

Apply these practices:

- Use threat modeling and secure design review while the architecture can still change.
- Run code, dependency, secret, configuration, and infrastructure-as-code checks in development and CI/CD.
- Tune tools to reduce false positives and define a clear path for expert help and triage.
- Establish risk-based release criteria for unresolved security findings.
- Revalidate important controls before release instead of assuming earlier checks always succeeded.
- Monitor applications, pipelines, identities, and supporting infrastructure in production.
- Feed vulnerabilities, incidents, penetration tests, postmortems, and operational findings back into design standards and backlog priorities.
- Include security in blameless postmortems so teams can improve systems and processes without discouraging disclosure.

Reference guidance:

- [Embed Zero Trust security into your developer workflow](/en-us/security/zero-trust/develop/embed-zero-trust-dev-workflow)
- [Shift DevOps to DevSecOps](/en-us/security/zero-trust/security-adoption-discipline-development-security)
- [Adopt secure development planning imperatives](/en-us/security/zero-trust/security-adoption-discipline-development-imperatives)

## Pattern 5: Align cloud and CI/CD authorization end to end

**Goal**: Prevent privilege bypass by keeping identity and authorization governance consistent across cloud resources and delivery systems.

Apply these practices:

- Use Microsoft Entra groups as a primary control point for cloud and CI/CD access where supported.
- Prefer group-based assignments over direct user-to-role grants.
- Align CI/CD roles with cloud role-based access control intent. For example, a person who cannot write to production in the cloud should not be able to trigger an unrestricted production deployment through the pipeline.
- Review both direct and indirect privilege paths, including repository administration, pipeline triggers, service connections, environment approvals, artifact replacement, and branch-policy changes.
- Separate routine engineering access from administrative and emergency access.
- Use emergency access only through controlled break-glass paths with logging, approval, and post-use review.
- Include pipeline and repository permissions in recurring access reviews.

Reference guidance:

- [Workload identity federation in Microsoft Entra](/en-us/entra/workload-id/workload-identity-federation)
- [Best practices for Azure RBAC](/en-us/azure/role-based-access-control/best-practices)
- [Default permissions and access for Azure DevOps](/en-us/azure/devops/organizations/security/permissions-access)
- [Managing people's access to your organization with roles in GitHub](https://docs.github.com/organizations/managing-peoples-access-to-your-organization-with-roles)

## Pattern 6: Right-size assurance to business risk

**Goal**: Apply stronger assurance where compromise can cause greater harm without forcing every workload through the same process.

Apply these practices:

- Establish a standard production baseline that applies to all workloads.
- Define additional controls for high-impact workloads based on business criticality, data sensitivity, privilege, external exposure, customer impact, safety, and regulatory obligations.
- Allow streamlined paths for lower-risk work only when the residual risk is understood and owned.
- Treat prototype or urgent-release exceptions as temporary states, not permanent profiles.
- Require every exception to have a named risk owner, compensating controls where practical, an expiration date, and a remediation plan.
- Reassess the workload when its users, data, privileges, exposure, dependencies, or business importance change.
- Use the workload's threat model and operational evidence to adjust the required assurance over time.

This pattern helps teams preserve delivery speed while keeping the level of review and control proportional to the potential impact.