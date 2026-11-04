---
layout: Conceptual
title: November 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2022/november2022
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in November 2022 to the root store.
ms.date: 2022-11-29T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: 80850606-b244-4be0-6f82-4d4174ca850b
document_version_independent_id: 80850606-b244-4be0-6f82-4d4174ca850b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2022/November2022.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2022/november2022
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2022/November2022.md
cmProducts: []
platformId: cc4e40fb-1ad2-afc2-4286-142e9a7b5f07
---

# November 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, November 29, 2022, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **NotBefore** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. TrustCor \ TrustCor ECA-1 \ 58D1DF9595676B63C0F05B1C174D8B840BC878BD
2. TrustCor \ TrustCor RootCert CA-1 \ FFBDCDE782C8435E3C6F26865CCAA83A455BC30A
3. TrustCor \ TrustCor RootCert CA-2 \ B8BE6DCB56F155B963D412CA4E0634C794B21CC0

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus