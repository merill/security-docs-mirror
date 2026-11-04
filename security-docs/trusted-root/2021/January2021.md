---
layout: Conceptual
title: January 2021 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2021/january2021
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: kasirota
author: kasirota
description: This document provides details about the changes made in January 2021 to the root store.
ms.date: 2021-01-20T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: ddbe70ea-721c-1c46-a131-094d9fe8096a
document_version_independent_id: 8013a635-4d81-9951-1cf6-5430031c84c4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2021/January2021.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2021/january2021
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2021/January2021.md
cmProducts: []
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ecbec206-b3b2-4795-8a5b-73d4d69cc0bc
platformId: 3d4748c1-5908-451f-d708-3c875112c45c
---

# January 2021 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, January 26, 2021, Microsoft will release an update to the Microsoft Trusted Root Certificate Program.

This release will **add** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Telia Company \ Telia Root CA v2 \ B999CDD173508AC44705089C8C88FBBEA02B40CD

This release will **add the Code Signing** to the following roots:

1. Atos \ Atos TrustedRoot 2011 \ 2BB1F53E550C1DC5F1D4E6B76A464B550602AC21

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus