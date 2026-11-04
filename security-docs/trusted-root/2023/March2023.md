---
layout: Conceptual
title: March 2023 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2023/march2023
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in March 2023 to the root store.
ms.date: 2023-11-08T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: b22d2572-b7f9-62cf-eab1-5bf7af1836c5
document_version_independent_id: b22d2572-b7f9-62cf-eab1-5bf7af1836c5
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2023/March2023.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2023/march2023
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2023/March2023.md
cmProducts: []
platformId: 0560956a-f0ed-ec1d-2048-2047e549586b
---

# March 2023 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, March 28, 2023, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **Add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint): 1.

This release will **Add EV SSL** from the following roots (CA \ Root Certificate \ SHA-1 Thumbprint): 1.

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus