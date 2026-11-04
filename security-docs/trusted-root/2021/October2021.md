---
layout: Conceptual
title: October 2021 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2021/october2021
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in October 2021 to the root store.
ms.date: 2022-06-03T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: 128d5fbf-0fa2-0d8e-3abc-3a9c6185d2bb
document_version_independent_id: 128d5fbf-0fa2-0d8e-3abc-3a9c6185d2bb
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2021/October2021.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2021/october2021
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2021/October2021.md
cmProducts: []
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ecbec206-b3b2-4795-8a5b-73d4d69cc0bc
platformId: 664d00ec-e0d3-0778-0280-b70d1070b485
---

# October 2021 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, October 26, 2021, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Government of Finland, Population Register Centres (Vaestorekisterikeskus, VRK) \ DVV Gov. Root CA - G3 RSA \ EAF83D8427897576CDD1B30957773E5F74B9B7CC
2. Government of Finland, Population Register Centres (Vaestorekisterikeskus, VRK) \ DVV Gov. Root CA - G3 ECC \ B2142AA969EB0DDB5CE9024684CD850B69E418E5

This release will **NotBefore the Code Signing EKU** for the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. SECOM Trust Systems CO. LTD. \ Security Communication ECC RootCA1 \ B80E26A9BFD2B23BC0EF46C9BAC7BBF61D0D4141

This release will **NotBefore the Server Authentication EKU** for the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Red Abogacia \ ACA ROOT \ D496592B305707386CC5F3CDB259AE66D7661FCA

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus