---
layout: Conceptual
title: October 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2022/october2022
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in October 2022 to the root store.
ms.date: 2022-09-29T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: eaf990fb-52c5-4245-85ad-59ff55c0ea10
document_version_independent_id: eaf990fb-52c5-4245-85ad-59ff55c0ea10
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2022/October2022.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2022/october2022
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2022/October2022.md
cmProducts: []
platformId: 4d4d5d8f-f252-d21d-a8de-a4693b175d73
---

# October 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, October 25, 2022, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **Remove NotBefore Property** from the following root (CA \ Root Certificate \ SHA-1 Thumbprint):

1. A-Trust \ A-Trust-Root-07 \ 1B1815AF925D140EFC5AF9A1AA55EEBB4FFBC561

This release will **Modify** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. E-Tugra \ E-Tugra Global Root CA RSA v3 \ E9A85D2214521C5BAA0AB4BE246A238AC9BAE2A9
2. E-Tugra \ E-Tugra Global Root CA ECC v3 \ 8A2FAF5753B1B0E6A104EC5B6A69716DF61CE284
3. Carillon Information Security Inc. \ Carillon PKI Services G2 Root CA 1 \ EB9237B72076F8CC8BC13E7046F2FCABC18199D3

This release will **Add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Government of India, Ministry of Communications & Information Technology, Controller of Certifying Authorities (CCA) \ CCA India 2022 \ a79e41380bab3ed7f5188d9a5209cefcb3ca6991
2. První certifikační autorita, a.s. \ I.CA Root CA/ECC 05/2022 \ 702723132527203947e0a97829a0731372b03917
3. První certifikační autorita, a.s. \ I.CA TLS Root CA/RSA 05/2022 \ 83e5e5de325414970b263011084456e5faa13ffa
4. První certifikační autorita, a.s. \ I.CA Root CA/RSA 05/2022 \ 461fdd19e71cd4329aadf224dc8c8628cd10fae8

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus