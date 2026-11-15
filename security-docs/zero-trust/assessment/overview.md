---
layout: Conceptual
title: What Is the Zero Trust Assessment? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Use the Zero Trust Assessment to check Microsoft 365 and Azure configuration across seven pillars, review findings, and plan security improvements.
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ms.reviewer: joflore
ai-usage: ai-assisted
locale: en-us
document_id: 6c83bbaa-56db-1823-ab2e-e4c568aaf992
document_version_independent_id: 6c83bbaa-56db-1823-ab2e-e4c568aaf992
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 08b7a66c-3fc0-d7b4-52bb-8faa1001ae6b
---

# What Is the Zero Trust Assessment? | Microsoft Learn

The Zero Trust Assessment is a community PowerShell module that checks your Microsoft 365 tenant and Azure configuration against security recommendations. Use its reports to review findings and plan improvements across seven Zero Trust pillars.

The assessment doesn't apply remediation. It collects configuration data and produces local reports that help you decide what to address.

## Why run this assessment?

Manually comparing tenant configuration with security guidance can be time-consuming. The assessment automates these checks and shows where your configuration aligns with recommendations and where you need to investigate.

The report includes findings, risk and status filters, and supporting guidance. Review skipped checks and errors as well as passed and failed checks: missing access, services, or licenses can leave part of your environment unassessed.

For guidance on interpreting reports, see [Review assessment results](review-results).

[![Screenshot of a synthetic assessment overview with tenant summaries and results across seven pillars.](media/zero-trust-assessment-overview.png)](media/zero-trust-assessment-overview.png#lightbox)

## Supported pillars

The current default run includes all seven pillars. Use the linked guidance and coverage summaries to plan your assessment.

| Pillar | Guidance or coverage |
| --- | --- |
| **Identity** | [Configure Microsoft Entra for increased security](/en-us/entra/fundamentals/configure-security). |
| **Devices** | [Configure Microsoft Intune for increased security](/en-us/intune/intune-service/protect/zero-trust-configure-security). |
| **Network** | [Apply Zero Trust principles to Azure networks](/en-us/azure/networking/security/zero-trust-network-security). |
| **Data** | [Configure Microsoft Purview for increased security](/en-us/purview/configure-security). |
| **Infrastructure** | Infrastructure assessment scope. |
| **Security operations (SecOps)** | Security operations assessment coverage. |
| **AI** | [Configure agent identity security](ai-pillar). |

### Infrastructure

Infrastructure findings use Microsoft Defender for Cloud recommendations. The assessment includes only accessible Azure subscriptions tagged with `ZeroTrustAssessment:Infrastructure`. If no matching subscription exists, the assessment skips rather than passes. See [Infrastructure scope](run-assessment#infrastructure-scope).

### Security operations (SecOps)

The default run includes SecOps. Azure connections support SecOps, Infrastructure, and Network assessments, not just audit and sign-in log export checks. Arrange the relevant [service and resource access](permissions) and review skipped checks or authorization errors before treating the run as complete.

## How the assessment works

The assessment separates service connections, assessment execution, and report review:

1. [Connect to the services](connect-services) you intend to assess. Each service has its own authentication and authorization requirements.
2. [Run the assessment](run-assessment) to collect data and evaluate the selected checks.
3. [Review the local reports](review-results), investigate incomplete coverage, and use the findings to plan improvements. You can also import the generated JSON into Zero Trust Workshop.

Reports, exports, and diagnostics can contain sensitive tenant configuration and personal information. Review [data handling and telemetry](get-started#protect-assessment-data) before running the assessment.

Before connecting, see [Review permissions and roles](permissions) to identify the access requirements for your assessment.

## Source and package versions

These articles cover the [development source](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/doc/readme.md). Published packages can differ. Check the [release history](https://github.com/microsoft/zerotrustassessment/releases) and the help for your installed version before relying on a version-specific dependency, parameter, or permission.

[Release 2.6.0](https://github.com/microsoft/zerotrustassessment/releases/tag/2.6.0) introduced the redesigned report and all seven default pillars. Later source changes include updated dependencies and the `AttackSimulation.Read.All` scope. Installing a prerelease package and using the assessment's `-Preview` switch are separate choices.

## Open source and transparent

Microsoft employees maintain the assessment as a community project. It isn't an official Microsoft product and Microsoft provides it as-is, without support through a Microsoft support program or service.

Review the [PowerShell source](https://github.com/microsoft/zerotrustassessment/tree/dev/src/powershell) and [support policy](https://github.com/microsoft/zerotrustassessment/blob/dev/SUPPORT.md). For community help, see [Report an issue or provide feedback](troubleshooting#report-an-issue-or-provide-feedback).