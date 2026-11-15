---
layout: Conceptual
title: Get Started with the Zero Trust Assessment | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/get-started
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jayrusso
author: HULKsmashGithub
description: Prepare your assessment host, install the PowerShell module, connect to your tenant, and run your first Zero Trust Assessment.
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.date: 2026-11-11T00:00:00.0000000Z
ms.reviewer: joflore
ms.custom: sfi-ga-nochange, msecd-doc-authoring-1032
ai-usage: ai-assisted
locale: en-us
document_id: 66a16d0a-172c-ccba-255d-be8c6873115f
document_version_independent_id: 66a16d0a-172c-ccba-255d-be8c6873115f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/get-started.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/get-started
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/get-started.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: c9e5a8ad-c78f-d0e2-a9cf-5c91a99d6727
---

# Get Started with the Zero Trust Assessment | Microsoft Learn

Install the Zero Trust Assessment PowerShell module, connect to your tenant's services, and run an assessment to review your security configuration.

Before you begin, prepare a supported PowerShell host and arrange access to the services you want to assess. See Prerequisites for the full requirements.

These instructions describe the development source. Published packages can have different requirements and capabilities.

## Prerequisites

- Access to the tenant and services you want to assess, including the [permissions and roles](permissions). Initial consent and runtime access are separate requirements.
- PowerShell 7.6 or later for the current development dependency set. The pinned ExchangeOnlineManagement 3.10.1 uses .NET 10 and requires PowerShell 7.6+. Older packages can differ. See [Exchange module prerequisites](/en-us/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) and [Install PowerShell on Windows](/en-us/powershell/scripting/install/installing-powershell-on-windows). Windows PowerShell 5.1 isn't the assessment host.
- Windows for full service coverage. SharePoint Online and Azure Information Protection (AIP) use Windows PowerShell compatibility sessions. On other platforms, these services are unavailable and their related tests are skipped.
- The [Microsoft Visual C++ Redistributable (x64)](/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version) for the native DuckDB dependency on Windows.
- A clean PowerShell process, preferably on a dedicated Windows virtual machine (VM), before importing other modules.
- Applicable service subscriptions and licenses. Missing services, licenses, or data access can produce skipped checks, not evidence that the tenant meets a recommendation.
- A protected output directory with sufficient disk space. Use a new directory for each fresh assessment.

## Protect assessment data

Decide how to protect local assessment data and whether to send assessment telemetry before you run the module.

1. Limit access to the output directory. Reports, exports, and diagnostics can contain tenant configuration and personal information. Remove them when no longer needed. Importing Workshop JSON or sharing diagnostics is a separate action you control.
2. Review the telemetry behavior. Telemetry is enabled by default; use `Invoke-ZtAssessment -DisableTelemetry` to disable the assessment telemetry event.

The telemetry event's only tenant-specific custom property is the tenant ID. It also includes a name, timestamp, instrumentation key, and fixed anonymized IP address and operating system (OS) tags. Assessment results aren't included. Network services can process standard connection metadata, such as the source IP address. See the [telemetry implementation](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/private/Send-ZtAppInsightsTelemetry.ps1).

## Install the PowerShell modules

Install a published package in a clean process so that unrelated modules don't load conflicting assemblies first.

1. Open a fresh PowerShell 7 process, preferably with `pwsh -NoProfile`.
2. Install the stable assessment package for your user:

    ```powershell
    Install-PSResource -Name ZeroTrustAssessment -Scope CurrentUser
    ```
3. Review repository trust prompts before accepting them. Let the assessment initialize its dependencies when imported or first used.

To opt into a prerelease package instead, use:

```powershell
Install-PSResource -Name ZeroTrustAssessment -Prerelease -Scope CurrentUser
```

Installing a prerelease selects a package version. The assessment's `-Preview` switch enables preview-only features when present; it isn't required for the seven current pillars. Neither option means every repository change has been published.

To update an existing stable installation, run `Update-PSResource -Name ZeroTrustAssessment`, then start a fresh PowerShell process. You don't need to remove unrelated modules to update the assessment.

### Bundled PowerShell modules

The [development module manifest](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/ZeroTrustAssessment.psd1) pins these versions. They describe the source snapshot, not necessarily the latest stable Gallery package.

| Module | Required version | Service | Platform |
| --- | --- | --- | --- |
| **`PSFramework`** | `1.14.457` | Logging, configuration, and runspaces. | All. |
| **`Microsoft.Graph.Authentication`** | `2.40.0` | Microsoft Graph. | All. |
| **`Microsoft.Graph.Beta.Teams`** | `2.40.0` | Teams beta APIs. | All. |
| **`Az.Accounts`** | `5.5.3` | Azure. | All. |
| **`ExchangeOnlineManagement`** | `3.10.1` | Exchange Online and Security & Compliance. | All, where supported by the service. |
| **`Microsoft.Online.SharePoint.PowerShell`** | `16.0.27612.12000` | SharePoint Online. | Windows. |
| **`AipService`** | `3.1.0.0` | Azure Information Protection. | Windows. |

The [dependency initializer](https://github.com/microsoft/zerotrustassessment/blob/6a304637fc53846fd55182d495b6a2980f30b434/src/powershell/Initialize-Dependencies.ps1) resolves these versions into `%APPDATA%\ZeroTrustAssessment\Modules` on Windows or `~/.cache/ZeroTrustAssessment/Modules` on macOS/Linux. It prepends that cache to `$env:PSModulePath`. Don't substitute arbitrary dependency versions.

### Use a clean assessment host

A dedicated Windows VM with PowerShell 7, the Visual C++ Redistributable, and the assessment's dependencies minimizes assembly conflicts.

An installed module isn't automatically a conflict. Profiles, automatic imports, or earlier commands can load incompatible assemblies into the same process. Removing or reimporting a module doesn't reliably unload those assemblies. Retry in a fresh `pwsh -NoProfile` process rather than uninstalling shared modules.

## Connect to Microsoft Graph and Microsoft Azure

The connector establishes separate connections to Microsoft Graph, Azure, Exchange Online, Security & Compliance, SharePoint Online, and AIP.

1. Arrange the [interactive user access](permissions#interactive-user-access) for the services you intend to assess. Activate eligible roles through Microsoft Entra Privileged Identity Management before connecting.
2. Connect to the intended tenant. Replace the example domain with your tenant's verified domain:

    ```powershell
    Connect-ZtAssessment -Tenant contoso.onmicrosoft.com
    ```
3. Complete the service prompts and review each connection status. Cached sessions and single sign-on can reduce prompts; there's no guaranteed prompt count. Reconnect after changing access.

For service selection, connection options, and certificate-based unattended access, see [Connect to assessment services](connect-services).

### Sign in to Microsoft Graph

Use the assessment account's runtime roles, preferably Global Reader, after an authorized administrator arranges consent. Consent doesn't assign runtime roles. New scopes can require consent again; see [Permissions and roles](permissions).

### Sign in to Microsoft Azure

Use an account with Reader access, or equivalent read permissions, at the intended subscription/resource scopes. Select the intended tenant and subscription if prompted. Azure access is separate from Microsoft Entra ID directory roles. Skipping Azure limits Infrastructure, Network, and security operations (SecOps) coverage as well as log export checks.

## Run the assessment

Run the assessment in the same PowerShell session after checking the service connections. The assessment doesn't apply tenant remediation.

Warning

A fresh, non-resume run against a nonempty output directory prompts to delete its contents. In a detected continuous integration (CI) environment, the current implementation cleans it automatically. Use a dedicated new directory, never a folder containing unrelated files.

1. Choose a working directory where the default `.\ZeroTrustReport` output folder is new. For a custom path or a selected pillar, see [Run and resume assessments](run-assessment).
2. Run the assessment:

    ```powershell
    Invoke-ZtAssessment
    ```
3. Follow the progress dashboard and review warnings or errors. Runtime varies with tenant size, service response times, throttling, and selected tests. Use the [diagnostic files](troubleshooting#logs-and-diagnostic-files) to distinguish active work from a failure.

## Review assessment results

The redesigned report opens by default at `.\ZeroTrustReport\ZeroTrustAssessmentReport.html`. Review all seven pillars, including skipped checks and errors, before drawing conclusions. See [Review results and import into Workshop](review-results).

## Turn assessment results into action

Use the **Risk**, **Status**, and recommended remediation for each result to build a prioritized improvement backlog. Assign each item to the team that owns the affected technology, and track the security outcome rather than treating assessment completion as the end of the work.

### Identity, endpoint, network, and data owners

Use the assessment tabs to continue into the corresponding implementation guidance:

- **Identity:**[Implement Zero Trust for identity](../deploy/identity).
- **Devices:**[Implement Zero Trust for endpoints](../deploy/endpoints).
- **Network:**[Implement Zero Trust for networks](../deploy/networks).
- **Data:**[Implement Zero Trust for data](../deploy/data).

### Security leaders and architects

Use these paths to coordinate remediation across teams and connect findings to the broader security program:

- [Prioritize remediation with security posture management](../security-adoption-discipline-posture).
- [Organize security improvements with the Microsoft Security Adoption Framework](../security-adoption-model).
- [Map findings to security standards and frameworks](../security-standards-and-frameworks).
- [Plan integrated security capabilities with MCRA](../microsoft-reference-architecture).

## Remove the Zero Trust Assessment module

When you no longer need the module or its data, follow [Remove the assessment](uninstall). Remove only the outputs and diagnostic packages you intend to delete; extended PSFramework logs are stored separately.

## FAQs

These links preserve access to procedures that now have dedicated articles.

### Export troubleshooting logs

Capture diagnostics in the same PowerShell session and review them before sharing. See [Capture a support package](troubleshooting#capture-a-support-package).

### Viewing logs during test execution

For per-run progress logs, collector and test details, and extended PSFramework logs, see [Logs and diagnostic files](troubleshooting#logs-and-diagnostic-files).

### Uninstall previous versions

For current and legacy package cleanup, see [Remove assessment packages](uninstall#remove-assessment-packages). For a routine stable update, use the installation guidance.

### Could not load file or assembly Microsoft.Graph.Authentication

Start with a clean process and the assessment's pinned dependencies, not blanket removal of shared modules. See [Resolve Graph assembly conflicts](troubleshooting#resolve-graph-assembly-conflicts).

### How can I know what the script does?

Review the source, progress dashboard, and [assessment diagnostics](troubleshooting#inspect-assessment-activity).

### Why did I get the exception error, "The type initializer for 'DuckDB.NET.Data.DuckDBConnectionStringBuilder' threw an exception."?

Inspect the inner exception before choosing a remedy. See [Resolve DuckDB initialization errors](troubleshooting#resolve-duckdb-initialization-errors).

### How do I get support?

The assessment has community help, not official Microsoft product support. See [Report an issue or provide feedback](troubleshooting#report-an-issue-or-provide-feedback).