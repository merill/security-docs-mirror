---
layout: Conceptual
title: August 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2022/august2022
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in August 2022 to the root store.
ms.date: 2022-06-15T00:00:00.0000000Z
ms.service: security
ms.topic: concept-article
locale: en-us
document_id: 12b46346-4f42-c3d9-65e6-2c0a31e03ecc
document_version_independent_id: 12b46346-4f42-c3d9-65e6-2c0a31e03ecc
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2022/August2022.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2022/august2022
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2022/August2022.md
cmProducts: []
platformId: 2dea1c4a-16a8-bdb8-1019-ef104f00024f
---

# August 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, August 23, 2022, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **NotBefore** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. TrustFactory (Pty) Ltd \ TrustFactory SSL Root Certificate Authority \ D11478E8E5FB62540593D22C51570D014EAC76D8

This release will **Disable** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. A-Trust \ A-Trust-Root-05 \ 2E66C9841181C08FB1DFABD4FF8D5CC72BE08F02
2. A-Trust \ A-Trust-nQual-03 \ 4CAEE38931D19AE73B31AA75CA33D621290FA75E
3. China Internet Network Information Center (CNNIC) \ China Internet Network Information Center EV Certificates Root \ 4F99AA93FB2BD13726A1994ACE7FF005F2935D1E
4. China Internet Network Information Center (CNNIC) \ CNNIC Root \ 8BAF4C9B1DF02A92F7DA128EB91BACF498604B6F

This release will **NotBefore Server Authentiation EKU** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. OISTE \ OISTE WISeKey Global Root GA CA \ 5922A1E15AEA163521F898396A4646B0441B0FA9

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus