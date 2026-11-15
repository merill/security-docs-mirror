---
layout: Conceptual
title: Run and Resume a Zero Trust Assessment | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/run-assessment
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Run the Zero Trust Assessment across selected pillars and tests, configure output and timeouts, and resume processing an existing export.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: 2826abfa-591c-7483-7bd0-d127c6bd1ebe
document_version_independent_id: 2826abfa-591c-7483-7bd0-d127c6bd1ebe
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/run-assessment.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/run-assessment
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/run-assessment.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: a850f37d-ca1f-fad6-c761-6a5847c57552
---

# Run and Resume a Zero Trust Assessment | Microsoft Learn

Run all Zero Trust Assessment pillars or select a pillar and specific test IDs. You can also reuse an existing export to rerun assessment and report processing without collecting a fresh tenant snapshot. Before starting, connect to the services and choose a protected output directory.

The options and defaults in the following section describe the development source. Check your installed version's help when using a published package.

## Prerequisites

- Completion of [Connect to assessment services](connect-services), with the service connections available in the same PowerShell session.
- A protected output directory with sufficient disk space.
- Azure read access and subscription tags for Infrastructure scope, if applicable.

## Run a fresh assessment

`Invoke-ZtAssessment` uses the connected tenant; it doesn't take a tenant parameter. Choose the output path and scope before running the command.

Warning

A non-resume run against a nonempty output directory prompts to delete its contents. In a detected continuous integration (CI) environment, the current implementation cleans the directory automatically. Don't point `-Path` at a directory containing unrelated files.

1. Choose a new output directory. The default is `.\ZeroTrustReport`, relative to your current directory.
2. Run one of these alternatives:

    - To assess all seven current pillars, use:

        ```powershell
        Invoke-ZtAssessment
        ```
    - To assess only Devices and use a custom path, use:

        ```powershell
        Invoke-ZtAssessment -Path C:\MyAssessment01 -Pillar Devices
        ```
3. Follow the progress dashboard and review [diagnostic files](troubleshooting#logs-and-diagnostic-files) when you need to distinguish active work from a failure.

Runtime varies with tenant size, service response times, throttling, and selected tests. `-NoBrowser` disables both the progress dashboard server and automatic opening of the final report.

`All` includes Identity, Devices, Network, Data, Infrastructure, security operations (SecOps), and AI. The `-Preview` switch isn't required for these pillars. It enables preview-only features when present and is separate from [installing a prerelease package](get-started#install-the-powershell-modules).

## Reuse an existing export

Use `-Resume` only when you intend to reuse the existing tenant snapshot and database, not collect current tenant data.

1. Preserve the existing output directory, exports, and database.
2. Use the original pillar, or an individual pillar if the original export used `All`. A single-pillar export can't be resumed as `All` or as a different pillar.
3. Keep the necessary service connections available and rerun against the original path:

    ```powershell
    Invoke-ZtAssessment -Path C:\MyAssessment01 -Pillar Devices -Resume
    ```

Resume skips export and database rebuild, but reruns assessment and report processing. It isn't a fresh collection or a guarantee of fully offline execution.

## Infrastructure scope

Infrastructure findings use Microsoft Defender for Cloud recommendations. Prepare the intended subscriptions before assessing this pillar.

1. Arrange Reader access, or equivalent read permissions, on each intended subscription/resource scope.
2. Tag the intended accessible Azure subscriptions with `ZeroTrustAssessment:Infrastructure`.
3. Run the Infrastructure pillar or `All`, then review any skipped checks.

Only accessible subscriptions with the required tag are included. No matching tagged subscriptions produces a skip, not a passed assessment.

## Invoke-ZtAssessment parameters

Use this table to select run options. Explicit command-line values override supported configuration-file settings. Not every parameter is a configuration-file setting.

| Parameter | Behavior |
| --- | --- |
| **`-Path <string>`** | Output folder; defaults to `.\ZeroTrustReport` relative to the current directory. |
| **`-Pillar <string>`** | `All` by default, or `Identity`, `Devices`, `Network`, `Data`, `Infrastructure`, `SecOps`, or `AI`. |
| **`-Preview`** | Enable preview-only features when present. Not needed for the seven current pillars. |
| **`-Resume`** | Reuse exports and database at `-Path`; use the original pillar or a subset of an `All` export. |
| **`-Tests <id[,id...]>`** | Exact test IDs, without wildcards. Otherwise, run the selected pillar's tests. |
| **`-Days <1-30>`** | Sign-in log lookback; defaults to 30 days. |
| **`-MaximumSignInLogQueryTime <minutes>`** | Sign-in collection time budget; defaults to 60. `0` removes the time limit, but the export size limit still applies. |
| **`-NoBrowser`** | Don't start the progress dashboard server or open the final report. |
| **`-ShowLog`** | Show a high-level console log summary. |
| **`-ExportLog`** | Create a PSFramework support package under `<Path>\log` near the end of the run. Per-run diagnostic files don't require this switch. |
| **`-ConfigurationFile <path>`** | JSON configuration for supported settings. Explicit command-line values take precedence. |
| **`-DisableTelemetry`** | Disable the assessment telemetry event. See [data handling and telemetry](get-started#protect-assessment-data). |
| **`-Timeout <timespan>`** | Overall wait for tests; defaults to 24 hours. Accepts values such as `12h` or `3d`. |
| **`-TestTimeout <minutes/timespan>`** | Per-test timeout; defaults to 60 minutes. `0` disables it. The default measures idle time since activity, not total elapsed time. Interruption of external and remoting operations is best effort. |
| **`-ExportThrottleLimit <n>`**, **`-TestThrottleLimit <n>`** | Parallel export collectors and tests, respectively; default to 5 each. |

For the complete interface, use `Get-Help Invoke-ZtAssessment -Full` and review the [command source](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/public/Invoke-ZtAssessment.ps1). For configuration persistence and large-tenant settings, see [Configure and tune assessments](configure-assessment).