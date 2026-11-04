---
layout: Conceptual
title: October 2020 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2020/october2020
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: kasirota
author: kasirota
description: This document provides details about the changes made in october 2020 to the root store.
ms.date: 2020-10-27T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: e958e8ab-e4ce-6202-1b80-58bdda339ce0
document_version_independent_id: bb2ede7c-c939-afbe-f7be-c08bd0fa6ff5
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2020/October2020.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2020/october2020
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2020/October2020.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/65ca8d99-bbc4-4d52-a348-666fc2eb372e
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/46e3e84d-7df1-440c-800c-0ff8f1f8f41c
platformId: c61c8ef1-6698-6fcd-af1f-f5617e1c3926
---

# October 2020 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Thursday, October 27, 2020, Microsoft will release an update to the Microsoft Trusted Root Certificate Program.

This release will **NotBefore the Server Authentication** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. DATEV eG \ CA DATEV BT 02 \ 39410BC2303748066069A72A664DE4C743481296
2. DATEV eG \ CA DATEV INT 02 \ 93F7F48B1261943F6A78210C52E626DFBFBBE260
3. DATEV eG \ CA DATEV STD 02 \ AB9D58C03F54B1DAE3F7C2D4C6C1EC3694559C37

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus