---
layout: Conceptual
title: Review Zero Trust Assessment Results | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/assessment/review-results
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: anstayk
author: astaykov
description: Review Zero Trust Assessment reports, investigate skipped checks and errors, and import mapped findings into Zero Trust Workshop task notes.
ms.reviewer: joflore
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.date: 2026-11-11T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1032
ai-usage: ai-generated
locale: en-us
document_id: c5c0b897-5c07-5079-c16c-f0f79e315169
document_version_independent_id: c5c0b897-5c07-5079-c16c-f0f79e315169
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/assessment/review-results.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/assessment/review-results
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/assessment/review-results.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 7f866dea-1524-202d-edfd-6ab82336220d
---

# Review Zero Trust Assessment Results | Microsoft Learn

Use Zero Trust Assessment reports to review findings across seven pillars, investigate incomplete coverage, and plan security improvements. You can also import mapped findings into Zero Trust Workshop task notes.

Start with generated reports and authorized access to their output directory. The reports and integration described here reflect the development source. Published packages can differ.

## Prerequisites

- Completion of [Run and resume an assessment](run-assessment), with generated reports available.
- Authorized access to the protected assessment output directory. Reports and exports can contain tenant configuration and personal information.

## Review assessment results

In the following paths, `<Path>` is the output directory you provide to `Invoke-ZtAssessment -Path`, or `.\ZeroTrustReport` by default. The screenshots use [synthetic data from the public demo](https://microsoft.github.io/zerotrustassessment/demo/), not a real tenant.

1. Open a generated report:

    - `<Path>\ZeroTrustAssessmentReport.html` is the redesigned report, opened by default.
    - `<Path>\ZeroTrustAssessmentReport-classic.html` is the classic report.

    If the run used `-NoBrowser`, open the report yourself.
2. Review the **Overview** for tenant summaries and assessment results across Identity, Devices, Network, Data, Infrastructure, security operations (SecOps), and AI.

    [![Screenshot of synthetic tenant counts and assessment results across seven Zero Trust pillars.](media/zero-trust-assessment-overview.png)](media/zero-trust-assessment-overview.png#lightbox)
3. Open a pillar and filter results by risk and status.

    [![Screenshot of Identity assessment results with risk and status filters and synthetic findings.](media/zero-trust-assessment-identity.png)](media/zero-trust-assessment-identity.png#lightbox)
4. Select a result to read its findings and supporting guidance. See the [assessment terminology](glossary) for the documented ratings.

    [![Screenshot of a synthetic failed assessment check with its risk, findings, and evaluation details.](media/zero-trust-assessment-detail.png)](media/zero-trust-assessment-detail.png#lightbox)
5. Check skipped tests and errors, not just passed and failed results. An unavailable service, license, or permission can leave part of the tenant unassessed. Investigate these outcomes with the [access reference](permissions) and [troubleshooting guide](troubleshooting).

The assessment doesn't apply remediation. Use the findings and supporting guidance to plan changes.

## Import results into Zero Trust Workshop

Report generation also creates `<Path>\zt-export\ZeroTrustWorkshop.json`. Import this file to bring mapped findings into Workshop task notes.

1. Locate `ZeroTrustWorkshop.json` in your protected assessment output directory.
2. Open [Zero Trust Workshop](https://aka.ms/ztworkshop) and import that JSON file.
3. Review the imported notes with the following limitations in mind.

### Current limitations

The integration is experimental and generated on a best-effort basis alongside the reports.

- Skipped tests are omitted. Other outcomes are represented in the notes.
- Notes are limited to 1,000 characters per task, including the header.
- A finding longer than 200 characters is compacted to its test title. Excess findings can be omitted, with an indication of how many remain.
- Exported task status is `not-reviewed`. Assessment findings don't automatically mark Workshop tasks complete.