---
layout: Conceptual
title: Standardize secure development pipelines – Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/standardize-secure-development-pipelines
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Standardize secure development pipelines is part of the protect engineering systems  pillar of the Secure Future Initiative (SFI), focusing on developing governed pipeline templates for implementing centrally managed production pipelines.
ms.date: 2025-08-05T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: design-pattern
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 27cdce43-a058-83a1-8c44-2287db1d2c38
document_version_independent_id: 27cdce43-a058-83a1-8c44-2287db1d2c38
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/standardize-secure-development-pipelines.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/standardize-secure-development-pipelines
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/standardize-secure-development-pipelines.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/5bd2b3fa-c186-4b92-a3c8-09f22a249d37
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7eba7926-b7b2-4a7a-bf89-e6ac53b3e7f6
platformId: 3f1deaa5-61ab-12cd-dfc9-9cff40f2511d
---

# Standardize secure development pipelines – Zero Trust | Microsoft Learn

**Pillar name: Protect engineering systems** **Pattern name: Standardize secure development pipelines**

## Context and problem

CI/CD pipelines are the backbone of modern software delivery. But when left unmanaged, they can also become a blind spot.

For many organizations using tools like Azure DevOps (AzDO), development teams enjoy the flexibility to build and deploy software in ways that fit their unique workflows. But over time, that flexibility can lead to fragmentation. Customers may find that different teams within the same organization implement CI/CD pipelines inconsistently using different security checks, compliance validations, and automation logic. This inconsistency increases the risk of gaps in security, slows down onboarding for new team members, and makes it harder to enforce enterprise-wide standards for responding quickly to emerging threats.

This lack of standardization can make it difficult to:

- Enforce company-wide security or regulatory policies
- Generate Software Bills of Materials (SBOMs) as required by Executive Order 14028
- Apply updates uniformly across thousands of pipelines

The result is a patchwork of practices that slows security adoption, increases compliance risk, and creates unnecessary overhead for engineering teams.

## Solution

To address this challenge at scale, Microsoft developed governed pipeline templates as part of the Secure Future Initiative (SFI). These centrally managed Azure DevOps YAML templates and GitHub actions encode standardized logic, security controls, and compliance requirements—enabling teams to move faster without compromising trust.

Governed pipeline templates serve as secure-by-default blueprints that teams can extend to meet local needs while maintaining a core set of features and enforcement. This approach balances centralized control with developer autonomy.

The templates support a range of workflows, including:

- Pull request (PR) validation
- Official builds
- Release automation
- Services spanning web applications, desktop applications, microservices, and ML models

Microsoft completed the rollout of governed pipeline templates in two quarters. Today, 92% of Microsoft’s commercial cloud production pipelines are centrally managed.

## Guidance

Organizations can adopt a similar pattern using the following actionable practices:

| Use case | Recommended action | Resource |
| --- | --- | --- |
| Leverage built-in tools | - Identify which security, compliance, and productivity tools should be built into every pipeline<br>- Use regulatory needs and SDL policy as a starting point | - [Defender for Cloud DevOps security](/en-us/azure/defender-for-cloud/defender-for-devops-introduction)<br>- [Azure DevOps extension](/en-us/azure/defender-for-cloud/azure-devops-extension) |
| Create a common template | - Build a reusable “extends” YAML template that defines required logic and stages<br>- Limit overrides to prevent accidental policy removal | - [Azure Pipelines](/en-us/azure/devops/pipelines/process/templates)<br>- [Use YAML templates in pipelines for reusable and secure processes](/en-us/azure/devops/pipelines/process/templates) |
| Support local extensions | Allow teams to create spoke templates that add local functionality without modifying the core set of features | [Configure the Microsoft Security DevOps Azure DevOps extension](/en-us/azure/defender-for-cloud/azure-devops-extension) |
| Automate evidence generation | Include SBOMs, test results, security scans, and compliance artifacts in the build process | [ACR - Manage OCI artifacts](/en-us/azure/container-registry/container-registry-manage-artifact) |

## Outcomes

### Benefits

- Speedy onboarding for new teams, who can adopt secure pipelines out of the box
- Reduce the risk of misconfigurations, inconsistent enforcement, or human error
- Increase compliance coverage, including SBOMs and regulatory gates
- Improve visibility into pipeline usage, health, and policy compliance
- Support scalable innovation through continuously evolving central templates
- Simplify support, as the pipeline tooling is maintained and optimized by a dedicated team—freeing engineers to focus on product development

### Trade-offs

- Standardizing pipelines requires significant coordination, change management, and upfront investment
- Teams must migrate custom logic into spoke templates, which can reveal tightly coupled or outdated pipeline designs
- Not every edge case is supported, requiring a balance between flexibility and security—but the long-term gains outweigh initial challenges

## Key success factors

Organizations can track success using the following indicators:

- Percentage of active pipelines using governed templates
- SBOM generation coverage across production builds
- Number of pipelines passing vs. failing compliance gates
- Time to apply new policy or security updates across all pipelines
- Number of support tickets or bugs related to pipeline inconsistency or misconfiguration

## Summary

**Learn how Microsoft is transforming development pipelines into security-first systems, ready for whatever comes next.**