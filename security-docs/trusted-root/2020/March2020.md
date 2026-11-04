---
layout: Conceptual
title: March 2020 Deployment Notice  - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2020/march2020
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: kasirota
author: kasirota
description: This document provides details about the changes made in March 2020 to the root store.
ms.date: 2020-03-18T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: a956ef09-12b5-59d7-bdbb-63808a58db11
document_version_independent_id: 9ec2b684-6b47-19aa-7e58-22a1efd69cf8
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2020/March2020.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2020/march2020
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2020/March2020.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e0ffb20c-01c6-407b-a9bd-29111652a1dc
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/3904bce4-d817-48cf-85fd-b6146fca83b7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: aa25cd64-bb68-b0d7-dc36-2035948be066
---

# March 2020 Deployment Notice  - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, March 24th, 2020, Microsoft will release a planned update to the Microsoft Trusted Root Certificate Program.

This release will **add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Microsoft \ Microsoft EV ECC Root Certificate Authority 2017 \ 6B1937ABFD64E1E40DAF2262A27857C015D6228D
2. Microsoft \ Microsoft EV RSA Root Certificate Authority 2017 \ ADA06E72393CCBE873648CF122A91C35EF4C984D
3. Agence Nationale de Certification Electronique (ANCE) \ TunTrust Root CA \ CFE970840FE0730F9DF60C7F2C4BEE2046349CBB

This release will **remove the NotBefore status** of the following roots:

1. Red Abogacía \ ACA ROOT \ 496592B305707386CC5F3CDB259AE66D7661FCA

This release will **add the code signing EKU** in the following roots:

1. IdenTrust \ IdenTrust Commercial Root CA 1 \ DF717EAA4AD94EC9558499602D48DE5FBCF03A25

Note

- Windows 10 allows us to stop trusting roots or EKU's using the "NotBefore" or "Disable" properties, both of which allow us to remove certain capabilities of the root certificate without complete removal. These features are not available on versions prior to Windows 10. Earlier versions of Windows will be unaffected by this change.
- The NotBefore and Disable dates are set for the first day of the release month. This means that all certificates issued after March 1st will be affected.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus