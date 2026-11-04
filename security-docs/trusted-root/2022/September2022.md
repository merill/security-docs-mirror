---
layout: Conceptual
title: September 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2022/september2022
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in September 2022 to the root store.
ms.date: 2022-09-29T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: a40b5d6c-317e-2fc5-278d-d0506ccd0665
document_version_independent_id: a40b5d6c-317e-2fc5-278d-d0506ccd0665
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2022/September2022.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2022/september2022
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2022/September2022.md
cmProducts: []
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ecbec206-b3b2-4795-8a5b-73d4d69cc0bc
platformId: 42d8ac4e-bb34-70f4-e474-89376e1094b5
---

# September 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, September 27, 2022, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **Add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Entrust \ Entrust Code Signing Root Certification Authority - CSBR1 \ 897424053a4a887ac098380291034d885c8714b9
2. E-Tugra \ E-Tugra Global Root CA RSA v3 \ E9A85D2214521C5BAA0AB4BE246A238AC9BAE2A9
3. E-Tugra \ E-Tugra Global Root CA ECC v3 \ 8A2FAF5753B1B0E6A104EC5B6A69716DF61CE284
4. Carillon Information Security Inc. \ Carillon PKI Services G2 Root CA 1 \ EB9237B72076F8CC8BC13E7046F2FCABC18199D3
5. Firmaprofesional, S.A. \ Autoridad de Certificacion Firmaprofesional CIF A62634068 \ 0BBEC2272249CB39AADB355C53E38CAE78FFB6FE

This release will **Modify** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Microsec Ltd. \ e-Szigno Root CA 2017 \ 89D483034F9E9A48805F7237D4A9A6EFCB7C1FD1

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus