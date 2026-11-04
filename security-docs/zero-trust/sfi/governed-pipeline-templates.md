---
layout: Conceptual
title: Govern CI/CD Pipeline Templates in Azure DevOps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/governed-pipeline-templates
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how governed Azure DevOps pipeline templates standardize security checks, automate compliance, and support centrally managed CI/CD workflows.
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2026-09-24T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1028
ai-usage: ai-assisted
locale: en-us
document_id: f796dbd7-a29f-8206-9161-9a8026d980ec
document_version_independent_id: f796dbd7-a29f-8206-9161-9a8026d980ec
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/governed-pipeline-templates.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/governed-pipeline-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/governed-pipeline-templates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5bd2b3fa-c186-4b92-a3c8-09f22a249d37
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7eba7926-b7b2-4a7a-bf89-e6ac53b3e7f6
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c636fafe-8605-d970-3626-55b8c0bdb7ff
---

# Govern CI/CD Pipeline Templates in Azure DevOps | Microsoft Learn

**Pillar name: Protect engineering systems**

**Practice name: Standardize CI/CD Pipelines with Governed Templates**

Modern software delivery pipelines are foundational to how organizations build, test, and ship software. However, without strong governance, these pipelines can introduce security, compliance, and operational risks. To address this challenge, Microsoft standardized more than 75,000 Azure DevOps pipelines using governed pipeline templates, helping ensure a secure, compliant, and scalable continuous integration/continuous delivery (CI/CD) experience across the enterprise.

## Context and problem

The need for governed pipeline templates emerged from a combination of regulatory pressure and internal engineering complexity. Executive Order 14028 mandated stronger cybersecurity practices, including the creation of Software Bills of Materials (SBOMs) for every software build. While critical for transparency, implementing SBOM generation across thousands of pipelines proved operationally challenging. Software pipelines are automated workflows that enable software to be built, tested, and deployed consistently. Governed pipeline templates provide standardized, predefined steps that enforce engineering best practices such as credential and virus scanning, static code analysis, and SBOM generation at scale.

At Microsoft, several systemic issues compounded the problem:

- **Lack of standardization:** Azure DevOps pipelines were highly flexible, leading to inconsistent implementations of security and compliance controls.
- **Fragmented best practices:** No single authoritative model for CI/CD pipelines existed, causing teams to reinvent processes independently.
- **Security gaps:** Variability in implementation increased the likelihood of vulnerabilities and made them harder to detect.
- **Manual compliance updates:** New regulatory or security requirements mandated that individual teams update pipelines manually, creating delay and inconsistency.
- **Operational inefficiency:** Distributed pipeline ownership across thousands of engineers introduced toil, errors, and inefficiencies.

Together, these challenges made it difficult to achieve the necessary balance of speed, security, and compliance that was expected of Microsoft for software delivery.

## Solution

Microsoft addressed these challenges by developing and deploying governed CI/CD pipeline templates. These templates are predefined, centrally managed frameworks that enforce security, compliance, and engineering best practices across all pipelines.

Key attributes of the solution include:

- **Central governance with local flexibility:** Core templates enforce Microsoft-wide requirements while allowing teams to extend them for specific use cases.
- **Automated compliance enforcement:** The pipeline embeds requirements such as SBOM generation, code signing, and pull request validation.
- **Unified pipeline model:** Templates support a wide range of workloads, including desktop applications, web services, microservices, and machine learning pipelines.
- **Secure-by-default posture:** Templates enforce the use of secure infrastructure and automatically inject required security tooling such as static analysis.

These templates operate through Microsoft’s hub-and-spoke model, where centrally managed **common templates** define required controls, and **spoke templates** enable team-level customization without compromising governance.

## Guidance

Organizations seeking to adopt governed pipeline templates can follow several practical principles derived from Microsoft’s implementation:

Organizations typically implement governed pipeline templates by defining centrally managed frameworks, requiring pipelines to extend approved baselines, integrating security and compliance tooling into those controls, and continuously monitoring adoption and policy coverage. This model helps teams inherit required controls by default while still allowing limited customization for workload-specific needs.

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| **Standardize pipelines across teams** | Define centrally managed YAML Ain’t Markup Language (YAML) templates for common build, validation, and release workflows. Require engineering teams to use approved templates for new pipelines and version those templates so updates can roll out in a controlled way. | [Use YAML templates in pipelines for reusable and secure processes](/en-us/azure/devops/pipelines/process/templates) |
| **Constrain execution paths and enforce approved structure** | Use centrally managed *extends* templates to define the outer structure of pipelines and restrict unapproved tasks or execution paths. Use *includes* templates for reusable building blocks, but keep enforcement in the base template. | [Templates for security](/en-us/azure/devops/pipelines/security/templates) |
| **Enforce security tooling in build pipelines** | Integrate static analysis, infrastructure-as-code scanning, dependency analysis, and malware detection into governed templates so that every build runs the same core security checks. Use deterministic configurations to reduce drift across environments. | [Configure the Microsoft Security DevOps Azure DevOps extension](/en-us/azure/defender-for-cloud/configure-azure-devops-extension)[Scan your connected GitHub repository or Azure DevOps project](/en-us/azure/defender-for-cloud/iac-vulnerabilities) |
| **Govern Azure DevOps and GitHub consistently** | Connect Azure DevOps and GitHub environments to a central security console so security teams can review posture, code findings, secrets exposure, and infrastructure-as-code issues across platforms by using a consistent model. | [Overview of Microsoft Defender for Cloud DevOps security](/en-us/azure/defender-for-cloud/defender-for-devops-introduction)[Connect Azure DevOps environments to Defender for Cloud](/en-us/azure/defender-for-cloud/quickstart-onboard-devops)[Support and prerequisites: DevOps security](/en-us/azure/defender-for-cloud/devops-support) |
| **Enforce gated deployments and approvals** | Apply approvals and checks on environments, service connections, secure files, and other protected resources so pipeline authors can't bypass deployment controls in YAML. Use these gates for branch control, manual approvals, and other predeployment validation steps. | [Define approvals and checks](/en-us/azure/devops/pipelines/process/approvals)[Control deployments with gates and approvals](/en-us/azure/devops/pipelines/release/deploy-using-approvals) |
| **Generate and use SBOM evidence** | Embed SBOM generation into governed templates and use the resulting evidence to identify package exposure, track dependency usage, and support software supply chain transparency requirements. | [Query software bill of materials (SBOM)](/en-us/azure/defender-for-cloud/query-software-bill-of-materials)[Attach a signed SBOM to a container image](/en-us/azure/security/container-secure-supply-chain/articles/attach-sbom)[Secure supply chain](/en-us/windows/security/book/security-foundation-secure-supply-chain) |
| **Maintain governance visibility and adoption** | Measure how many pipelines use approved templates, track the security checks they inherit, and review exceptions regularly so central governance remains effective as engineering teams and tooling evolve. | [Overview of Microsoft Defender for Cloud DevOps security](/en-us/azure/defender-for-cloud/defender-for-devops-introduction)[Make your Azure DevOps secure](/en-us/azure/devops/organizations/security/security-overview) |

## Benefits

Adopting governed pipeline templates provides several measurable advantages, including:

- **Improved security posture:** Built-in security checks and standardized controls reduce vulnerabilities across the software supply chain.
- **Regulatory compliance at scale:** Automated enforcement of requirements such as SBOM generation ensures consistent compliance.
- **Operational efficiency:** Eliminates redundant work across teams and reduces engineering toil.
- **Faster onboarding:** New teams can rapidly establish compliant pipelines by using prebuilt templates.
- **Centralized update capability:** You can roll out changes to policies or tooling across all pipelines simultaneously.
- **Consistency and reliability:** Standardized pipelines reduce variability and improve troubleshooting and maintenance.

## Trade-offs

While powerful, governed pipeline templates introduce some trade-offs that organizations must consider, including:

- **Reduced flexibility:** Strict governance can limit customization for specialized scenarios.
- **Performance overhead:** Additional compliance and security checks might extend pipeline execution time.
- **Initial investment:** Designing templates, tooling, and governance processes requires upfront effort.
- **Change management complexity:** You must carefully manage updates to central templates to avoid disrupting dependent pipelines.

Microsoft continues to address these trade-offs by optimizing performance and exploring automation, including AI-driven enhancements.

## Key success factors

Microsoft’s experience highlights several critical success factors:

- **Strong central ownership:** A dedicated team to manage templates and enforce governance.
- **Clear separation of concerns:** Core templates define mandatory controls, while extension layers enable flexibility.
- **Tooling integration:** Seamless integration of security and compliance tools into pipelines.
- **Scalable rollout strategy:** Deployment completed in phases (two quarters), enabling rapid enterprise-wide adoption.
- **Continuous monitoring and feedback loops:** Regular audits ensure adherence and identify improvement opportunities.
- **Alignment with strategic initiatives:** Integration with SFI ensured executive support and alignment with broader security goals.
- **Measurable adoption and control coverage:** Track the percentage of pipelines using governed templates and the percentage inheriting required security and compliance checks.

## Summary

Governed pipeline templates represent a foundational capability for securing modern software engineering at scale. By standardizing CI/CD pipelines, embedding security and compliance controls, and enabling centralized governance with controlled flexibility, Microsoft has significantly improved its software supply chain resilience.

This approach demonstrates how organizations can shift from fragmented, team-specific pipeline implementations to a unified, secure-by-default model—ensuring that speed, security, and compliance are not competing priorities but integrated outcomes.