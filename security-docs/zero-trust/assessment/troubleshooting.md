---
layout: Conceptual
title: Troubleshoot the Zero Trust Assessment | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/troubleshooting
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Troubleshoot Zero Trust Assessment connections, dependencies, and reports, locate logs, and collect diagnostics safely for community help.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: troubleshooting-general
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: b8796a9a-04c2-aa48-b4e9-ae2d26327b4f
document_version_independent_id: b8796a9a-04c2-aa48-b4e9-ae2d26327b4f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/troubleshooting.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/troubleshooting
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/troubleshooting.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: a0127248-dcf6-54db-9ef9-315fae2c3fc0
---

# Troubleshoot the Zero Trust Assessment | Microsoft Learn

Investigate Zero Trust Assessment connection failures, skipped checks, slow runs, dependency conflicts, and report problems. Start with the affected stage, then collect diagnostics if the symptom-specific checks don't resolve the issue. Keep the PowerShell session or available diagnostics for your investigation.

Before you begin, gather your assessment and PowerShell versions, run scope, and error summary. See Prerequisites for the information you need.

## Prerequisites

- The assessment PowerShell session, if still available, or its generated diagnostics.
- The assessment and PowerShell versions, selected pillar and test IDs, affected stage, and error summary.

## Troubleshooting checklist

Identify the failure stage before changing permissions, dependencies, or timeouts.

### Identify the affected stage

Identify which assessment stage failed so you can select the relevant diagnostics.

1. Review connection messages and the per-run diagnostic files to identify whether the problem occurs during connection, export, database creation, tests, or report processing.
2. Record the assessment version, PowerShell version, selected pillar and test IDs, and a sanitized error summary.
3. Preserve completed exports and the database if you might use [resume](run-assessment#reuse-an-existing-export).

### Check access and coverage

Use the symptom table to select the next check. A successful Microsoft Graph connection doesn't establish every other service, and a skipped check isn't evidence of a secure configuration.

| Symptom | What to check |
| --- | --- |
| **Graph consent or role validation fails.** | Compare grants with `Get-ZtGraphScope`, activate the required user role or configure app permissions, and reconnect. A new package can require additional consent. |
| **A service fails to connect or tests are skipped.** | Check the service's role, license, platform, and connection message. See [connection guidance](connect-services). |
| **A protection, label, data loss prevention (DLP), or hunting check returns an authorization error.** | Check workload role assignments and data scopes for the command or API, not just Microsoft Entra ID role names. Use the [access tables](permissions). |
| **Infrastructure has no findings.** | Verify Azure read access and [subscription tags](run-assessment#infrastructure-scope). No tagged/accessible subscriptions isn't a passed assessment. |
| **Runtime is long, requests are throttled, or memory pressure increases.** | Inspect collector and test logs. Review lookback, concurrency, caches, and timeouts in [configuration settings](configure-assessment). |
| **A certificate connection fails.** | Check certificate validity/private key, app public-key registration, tenant GUID, consent, and service-principal roles. SharePoint also needs an exportable key in the current connector. |
| **Constrained Language Mode prevents execution.** | Use an approved host/policy that supports the assessment. Don't bypass organizational controls; the advanced override doesn't make restricted operations work. |

## Causes and solutions

Use the following procedures for dependency and report errors. Check the affected version before choosing a workaround.

### Resolve Graph assembly conflicts

For `Could not load file or assembly Microsoft.Graph.Authentication`, start with a clean process instead of removing shared modules.

1. Start a new `pwsh -NoProfile` process.
2. Let the assessment load its pinned dependencies before other cloud modules.
3. Check the [dependency cache and clean-host guidance](get-started#bundled-powershell-modules) if the problem persists.

Another installed module isn't automatically a conflict, but already-loaded assemblies can be incompatible. Removing or reimporting a module doesn't reliably unload assemblies. Avoid blanket removal of shared Graph modules and third-party cleanup scripts as the default remedy.

### Resolve DuckDB initialization errors

The error `The type initializer for 'DuckDB.NET.Data.DuckDBConnectionStringBuilder' threw an exception` can have different underlying causes.

1. Inspect the inner exception. On Windows, a `DllNotFoundException` for `duckdb` can indicate a missing native dependency.
2. If missing, install the [Microsoft Visual C++ Redistributable (x64)](/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version).
3. Retry in a fresh PowerShell session. Don't assume every database error has the same cause.

### Recover from report-rendering errors

Older reports could show `Unexpected Application Error! Invalid array length`. Related reports include [microsoft/zerotrustassessment#1235](https://github.com/microsoft/zerotrustassessment/issues/1235), [microsoft/zerotrustassessment#1272](https://github.com/microsoft/zerotrustassessment/issues/1272), [microsoft/zerotrustassessment#1310](https://github.com/microsoft/zerotrustassessment/issues/1310), and [microsoft/zerotrustassessment#1388](https://github.com/microsoft/zerotrustassessment/issues/1388).

1. Check the issue and [release history](https://github.com/microsoft/zerotrustassessment/releases) for your version. Don't assume a prerelease is always required.
2. If exports and database creation completed, preserve them.
3. After installing an applicable fix, reconnect and use `-Resume` with the original path and pillar to rerun assessment and report processing.
4. Use the classic HTML report if it was generated successfully.

### Inspect assessment activity

Review the [PowerShell source](https://github.com/microsoft/zerotrustassessment/tree/dev/src/powershell), progress dashboard, and per-run logs to understand the assessment's activity. The upstream [advanced troubleshooting guide](https://github.com/microsoft/zerotrustassessment/blob/dev/docs/troubleshooting.md) covers support-package analysis.

## Advanced troubleshooting and data collection

Different diagnostics capture different stages. Choose the location that matches the failure before collecting or sharing data.

### Logs and diagnostic files

`<Path>` is the directory you pass to `Invoke-ZtAssessment -Path`, or `.\ZeroTrustReport` by default. The optional support package, per-run files, and extended PSFramework logs are three separate diagnostic locations.

| Location | Contents and use |
| --- | --- |
| **`<Path>\log\`** | A PSFramework support-package ZIP created by `-ExportLog` near successful completion, containing a `.cliDat` snapshot. It can be absent if the switch wasn't used or the run failed before this stage. |
| **`<Path>\zt-export\logs\<run>\1-export_progress.log`** | Export collector progress and status. Start here for data-collection problems. |
| **`<Path>\zt-export\logs\<run>\2-database_progress.log`** | Database build progress and timings. Resume skips this phase. |
| **`<Path>\zt-export\logs\<run>\3-test_progress.log`** | Assessment execution progress and status. |
| **`<Path>\zt-export\logs\<run>\1-Export\export_<Name>.md`** | Collector status, duration, timestamps, endpoint/type, module version, and diagnostic messages. |
| **`<Path>\zt-export\logs\<run>\2-Tests\<TestID>.md`** | Test title, status, duration, timestamps, module version, and detailed messages, potentially including query text. |
| **`%APPDATA%\PowerShell\PSFramework\Logs\` on Windows** | Extended message logs and XML error records, independent of the output path. Useful for connection/import issues, exceptions, source locations, stack traces, and messages outside individual tests. |

`<run>` uses the timestamp format `yy-MM-dd-HHmmss`. Files appear as their phases execute; a partial or resumed run need not contain every file. Per-run files are generated independently of `-ExportLog`.

Extended PSFramework files include computer/process identifiers and numbered segments, such as `<computer>_<pid>_message_0.log` and `<computer>_<pid>_error_0.xml`. Availability and retention depend on the logging provider configuration.

On Windows, `%APPDATA%` identifies the user's Roaming folder, normally `%USERPROFILE%\AppData\Roaming`. In PowerShell, use `$env:APPDATA`; the equivalent log path is `Join-Path $env:APPDATA 'PowerShell\PSFramework\Logs'`.

The rest of `<Path>\zt-export` is assessment data, not just logs: exported entities, `ztConfig.json`, `db\zt.db`, `ZeroTrustAssessmentReport.json`, and `ZeroTrustWorkshop.json`. These files can help reproduce or resume a run but can contain sensitive tenant data. Deleting `<Path>` doesn't remove separate PSFramework logs.

### Capture a support package

If a run fails before it creates an optional support package, capture diagnostics in the same PowerShell session before closing it.

1. Choose a separate destination for the diagnostic package. It doesn't need to match the assessment output path. Replace the example destination with a folder for your run:

    ```powershell
    New-PSFSupportPackage -Path C:\AssessmentLogs\Run01 -Force
    ```
2. Extract the generated ZIP to access its `.cliDat` file.
3. Review and redact diagnostics before sharing. For importing and investigating the snapshot, see the [advanced log analysis guide](https://github.com/microsoft/zerotrustassessment/blob/dev/docs/troubleshooting.md).

A support package snapshots available session diagnostics, including message and error history and potentially command history or console output. It isn't an automatic archive of all exported tenant files.

Warning

Reports, exports, support packages, and extended logs can contain personal information, tenant identifiers, query values, and configuration details. Never attach them unreviewed to public GitHub issues or upload them to an unapproved tool. Share additional diagnostics only through an approved private channel agreed with the recipient.

### Report an issue or provide feedback

Search or file [GitHub issues](https://github.com/microsoft/zerotrustassessment/issues) or use the [feedback channel](https://aka.ms/zerotrust/feedback). Include the assessment version, PowerShell version, selected pillar and test IDs, affected stage, and a sanitized error summary.

The assessment is a community project, not an official Microsoft product. Community issue reporting isn't a support contract or a guarantee of a response. Read the [support policy](https://github.com/microsoft/zerotrustassessment/blob/dev/SUPPORT.md) before sharing diagnostics.