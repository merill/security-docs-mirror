---
layout: Conceptual
title: September 2020 Microsoft Trusted Root Program Deployment Notice | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2020/september2020
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: kasirota
author: kasirota
description: This document provides details about the changes made in September 2020 to the root store.
ms.date: 2020-09-29T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: 48de1f2d-5556-3e5f-3145-bdb04dacdf09
document_version_independent_id: fd478561-c303-e9d7-1461-1fca8b26ae77
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2020/September2020.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2020/september2020
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2020/September2020.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e0ffb20c-01c6-407b-a9bd-29111652a1dc
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/3904bce4-d817-48cf-85fd-b6146fca83b7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: cb0b9257-23e8-80b2-2b09-dccce6f1919e
---

# September 2020 Microsoft Trusted Root Program Deployment Notice | Microsoft Learn

On Tuesday, September 29th, 2020, Microsoft will release a planned update to the Microsoft Trusted Root Certificate Program.

This release will **add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Austrian Society For Data Protection (GlobalTrust) \ GLOBALTRUST 2020 \ D067C11351010CAAD0C76A65373116264F5371A2
2. První Certifikační Autorita, A.S. \ I.CA Root CA/ECC 12/2016 \ 1E70283209903C9472C79B2C103E8EBB238BEB62
3. GlobalSign \ GlobalSign Root E46 \ 39B46CD5FE8006EBE22F4ABB0833A0AFDBB9DD84
4. GlobalSign \ GlobalSign Root R46 \ 53A2B04BCA6BD645E6398A8EC40DD2BF77C3A290

Note

- Windows 10 allows us to stop trusting roots or EKU's using the "NotBefore" or "Disable" properties, both of which allow us to remove certain capabilities of the root certificate without complete removal. These features are not available on versions prior to Windows 10. Earlier versions of Windows will be unaffected by this change.
- The NotBefore and Disable dates are set for the first day of the release month.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus