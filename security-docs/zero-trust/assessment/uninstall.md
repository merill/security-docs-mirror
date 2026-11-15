---
layout: Conceptual
title: Remove the Zero Trust Assessment | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/uninstall
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Remove Zero Trust Assessment packages and safely retire output files, diagnostic packages, dependency caches, and dedicated application access.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: 07ec327d-976f-ee7a-c2db-943e4a46550e
document_version_independent_id: 07ec327d-976f-ee7a-c2db-943e4a46550e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/uninstall.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/uninstall
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/uninstall.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: b3b30f1c-0361-121d-44c2-7fe12d1ec987
---

# Remove the Zero Trust Assessment | Microsoft Learn

Remove Zero Trust Assessment packages and data when you no longer need them. Keep cleanup scoped to the assessment resources you intend to retire, without removing shared modules or access used by other tools. Before cleanup, identify the affected packages and outputs, and review your retention requirements.

## Prerequisites

- Identification of the assessment packages, output directories, and manually created diagnostic packages you intend to remove.
- Your organization's retention requirements for reports, exports, and logs.

## Remove assessment packages

Close assessment sessions before removing the packages they use.

1. Close the PowerShell sessions running the assessment.
2. Remove installed assessment versions:

    ```powershell
    Uninstall-PSResource ZeroTrustAssessment -Version '*'
    ```
3. If the legacy `ZeroTrustAssessmentv2` package is installed, remove it separately with `Uninstall-PSResource ZeroTrustAssessmentv2 -Version '*'`.
4. Review the isolated [dependency cache](get-started#bundled-powershell-modules) separately from the package. Don't remove it while any assessment session is using it.

For a routine stable package update instead of removal, see [Install the PowerShell modules](get-started#install-the-powershell-modules).

## Clean up resources

Package removal and data/access cleanup are separate tasks. Review each location before deleting anything.

1. Delete only the assessment output directories and manually created diagnostic packages you intend to remove. Reports and exports can contain sensitive tenant information.
2. Review the [extended PSFramework log location](troubleshooting#logs-and-diagnostic-files) under your retention policy. Those logs are outside the assessment output directory and can include other PSFramework-using tools.
3. If retiring a dedicated app registration, review and remove its grants and resource-role assignments before deleting it. Don't delete a shared Microsoft Graph PowerShell application or revoke shared consent without assessing the impact on other tools.