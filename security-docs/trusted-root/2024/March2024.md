---
layout: Conceptual
title: March 2024 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2024/march2024
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: tahminaahmad
author: tahmad2
description: This document provides details about the changes made in March 2024 to the root store.
ms.date: 2024-03-20T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: ec5a45a1-7fce-3be4-1c67-ea8406170c53
document_version_independent_id: ec5a45a1-7fce-3be4-1c67-ea8406170c53
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2024/March2024.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2024/march2024
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2024/March2024.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 1801ec30-7b1e-081e-000d-aed57811de6b
---

# March 2024 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, March 26, 2023, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Secom // SECOM RSA Root CA 2023 // 4E004413485C145D9FDE64ADB16756E8F26AAC8A
2. Secom // SECOM Document Signing RSA Root CA 2023 // FDD93B294972BA743A0C2E6ABCFA10050652A047
3. Microsec // E-Szigno TLS Root CA 2023 // 6F9AD5D5DFE82CEBBE3707EE4F4F52582941D1FE
4. Buypass // Buypass Class 3 Root CA G2 HT // 2F7F1FC907B84E71EACC5695E186A144136E595A
5. QuoVadis, DigiCert // QuoVadis Client RSA 4096 Root G4 // 1068BFBEA253BAE0E6E03F34E8C2F1CE2D764B57
6. QuoVadis, DigiCert // QuoVadis SMIME ECC P384 Root G4 // 5B27E1E3C91FD30E6E6EE66EDFED12F5BCDF9236
7. QuoVadis, DigiCert // QuoVadis SMIME RSA 4096 Root G4 // C9B8DBF79C9A3D54B7E46EE63D72F9435E32BFA6
8. QuoVadis, DigiCert // QuoVadis TLS ECC P384 Root G4 // B6BF372A3689B35699F09913DA011D73A6E10FCE
9. QuoVadis, DigiCert // QuoVadis TLS RSA 4096 Root G4 // 20AFEA8DCB031F0684DF8FFD2598C8B7967FCD3C
10. CCA India // CCA India 2022 SPL // 9152D077FEF058914009BB4C0E42A710A38238AF

**Certificate Transparency Log Monitor (CTLM) policy** The Certificate Transparency Log Monitor (CTLM) policy is now included in the monthly Windows CTL. It's a list of publicly trusted logging servers that is for validating certificate transparency on Windows. The list of logging servers is expected to change over time as they're retired or replaced, and this list reflects the CT logging servers that Microsoft trusts. In the upcoming Windows release, users are able to opt in to certificate transparency validation, which will check for the presence of two Signed Certificate Timestamps (SCTs) from different logging servers in the CTLM. This functionality is currently being tested with event logging only to ensure it's reliable before individual applications can opt in to enforcement.

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus