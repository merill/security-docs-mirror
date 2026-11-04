---
layout: Conceptual
title: August 2024 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2024/august-2024
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: tahminaahmad
author: tahmad2
description: This document provides details about the changes made in August 2024 to the root store.
ms.date: 2024-07-09T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: 7ef06d76-1bb8-cff6-b229-48de29f4df53
document_version_independent_id: 7ef06d76-1bb8-cff6-b229-48de29f4df53
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2024/august-2024.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2024/august-2024
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2024/august-2024.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 0494e6be-2131-15cd-9e8c-5f91eceb0853
---

# August 2024 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, August 27, 2024, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will NotBefore the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

- e-commerce monitoring GmbH // GLOBALTRUST 2020 // D067C11351010CAAD0C76A65373116264F5371A2

**Certificate Transparency Log Monitor (CTLM) policy** The Certificate Transparency Log Monitor (CTLM) policy is now included in the monthly Windows CTL. It's a list of publicly trusted logging servers that is for validating certificate transparency on Windows. The list of logging servers is expected to change over time as they're retired or replaced, and this list reflects the CT logging servers that Microsoft trusts. In the upcoming Windows release, users are able to opt in to certificate transparency validation, which will check for the presence of two Signed Certificate Timestamps (SCTs) from different logging servers in the CTLM. This functionality is currently being tested with event logging only to ensure it's reliable before individual applications can opt in to enforcement.

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus