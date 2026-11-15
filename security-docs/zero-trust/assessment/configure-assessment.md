---
layout: Conceptual
title: Configure and Tune the Zero Trust Assessment | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/configure-assessment
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Configure Zero Trust Assessment settings, persist changes, and tune concurrency, caches, and timeouts for identified large-tenant bottlenecks.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: 6ca7769b-b03e-468c-c624-9f83c91fbfdf
document_version_independent_id: 6ca7769b-b03e-468c-c624-9f83c91fbfdf
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/configure-assessment.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/configure-assessment
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/configure-assessment.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: bd3001ec-9d99-7883-071a-0852b78d9bc1
---

# Configure and Tune the Zero Trust Assessment | Microsoft Learn

Inspect the Zero Trust Assessment configuration and change settings when you identify a bottleneck. Lower concurrency to reduce memory pressure and throttling. Increasing a timeout doesn't fix missing access.

Start with an imported module and diagnostic files for the bottleneck. The following settings and defaults describe the development source. Check the configuration available in your installed package before changing it.

## Prerequisites

- An [installed assessment module](get-started#install-the-powershell-modules), imported into your PowerShell session.
- The [collector and test diagnostics](troubleshooting#logs-and-diagnostic-files) for the bottleneck you want to investigate.

## Inspect configuration settings

Review current values before deciding what to change.

1. Import the assessment module if it isn't already loaded.
2. Inspect its configuration:

    ```powershell
    Get-PSFConfig -Module ZeroTrustAssessment
    ```
3. Compare the relevant values with the available settings and the affected collector and test diagnostics.

## Change settings for the current session

Set values before invoking the assessment.

1. Select a setting that addresses the identified bottleneck.
2. Set the value. For example, reduce test concurrency in the current session:

    ```powershell
    Set-PSFConfig -Module ZeroTrustAssessment -Name 'ThrottleLimit.Tests' -Value 3
    ```
3. [Run the assessment](run-assessment) and review the affected collector or test diagnostics.

The `-ConfigurationFile` parameter accepts JSON for supported settings. Explicit command-line values override configuration-file values. Not every run parameter is a configuration-file setting.

## Persist a setting

Set the value, then register that configuration entry for future sessions.

1. Set and register the entry. For example:

    ```powershell
    Set-PSFConfig -FullName 'ZeroTrustAssessment.Graph.CacheMaxItems' -Value 10000
    Register-PSFConfig -FullName 'ZeroTrustAssessment.Graph.CacheMaxItems'
    ```
2. Use the configuration inspection command in future sessions to review the registered value.

`Register-PSFConfig` defaults to the current user's settings. `Set-PSFConfig` doesn't have a `-Register` switch.

Duration settings accept standard time spans and PSFramework notation such as `30m`, `2h`, or `2h 30m`. See the [PSFramework documentation](https://psframework.org/) and [assessment configuration definitions](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/scripts/configuration.ps1).

## Available configuration settings

All names in this table use the prefix `ZeroTrustAssessment.`. Defaults describe the development source.

| Setting | Default | Purpose |
| --- | --- | --- |
| **`Export.DependencyWaitLimit`** | `1d` | Maximum wait for another export that a collector depends on. |
| **`Export.SignInLog.MaxSizeBytes`** | `1073741824` (1 GB) | Sign-in export size cap; collection stops at the cap. |
| **`ThrottleLimit.Export`** | `5` | Maximum parallel collectors. |
| **`ThrottleLimit.Tests`** | `5` | Maximum parallel tests. |
| **`Tests.Timeout`** | `1h` | Per-test timeout; `0` disables it. |
| **`Tests.TimeoutType`** | `Idle` | `Idle` measures time since last activity; `Start` measures time since execution began. |
| **`Tests.RetryCount`** | `0` | Reattempts for failed executions. |
| **`Tests.RetryTimeout`** | `$false` | Include timed-out executions in retries. |
| **`Tests.Statistics.MessageCountSoftCap`** | `1024` | Threshold for simplifying stored per-test message objects. |
| **`Azure.DisableCache` / `Graph.DisableCache`** | `$false` | Disable the respective in-memory request cache. |
| **`Azure.CacheMaxItems` / `Graph.CacheMaxItems`** | `50000` | Maximum items in each request cache. |
| **`Azure.CacheLifetime` / `Graph.CacheLifetime`** | `30m` | Expiration of cached entries. |
| **`Logging.Database.IncludeQueryResults`** | `$false` | Include database row values in logs. Leave disabled normally: it increases volume and exposes tenant data. |
| **`Logging.InMemoryLog.MinSize`** | `51200` | Minimum PSFramework in-memory message capacity enforced at import. Larger values consume more memory. |
| **`Debug.KeepWorkflows`** | `$false` | Keep background workflows for debugging instead of normal cleanup. Avoid for routine runs. |
| **`TabExpansion.TestLimit`** | `10` | Maximum test IDs offered by tab completion at a time. |

## Tune a large-tenant run

Review related limits together rather than increasing every value.

1. Inspect collector and test logs to identify slow collection, throttling, timeouts, or memory pressure.
2. Consider lowering both throttle limits and bounding caches.
3. Review sign-in lookback, the collection time budget, the sign-in export size cap, and test and export timeouts together. See [run parameters](run-assessment#invoke-ztassessment-parameters).
4. Review retry settings only for failed or timed-out executions. They don't turn a failed security recommendation into a pass.
5. Leave database row-value logging and retained workflows disabled for routine runs.