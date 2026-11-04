---
layout: Conceptual
title: September 2021 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2021/september2021
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in September 2021 to the root store.
ms.date: 2022-06-03T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: f60c2ef9-b3c9-cf87-6cda-aafff678bb47
document_version_independent_id: f60c2ef9-b3c9-cf87-6cda-aafff678bb47
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2021/September2021.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2021/september2021
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2021/September2021.md
cmProducts: []
platformId: 2202ab2c-0709-7487-f472-7c704857353b
---

# September 2021 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, September 28, 2021, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **add Client Authentication EKU** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Internet Security Research Group(ISRG) \ ISRG Root X1 \ CABD2A79A1076A31F21D253635CB039D4329A5E8
2. Internet Security Research Group(ISRG) \ ISRG Root X2 \ BDB1B93CD5978D45C6261455F8DB95C75AD153AF

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus