---
layout: Conceptual
title: April 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2022/april2022
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: hasokol
author: hasokol-ms
description: This document provides details about the changes made in April 2022 to the root store.
ms.date: 2022-06-03T00:00:00.0000000Z
ms.service: azure-information-protection
ms.topic: release-notes
locale: en-us
document_id: 7fe6be41-45a9-f705-8a3a-dfb69b55e468
document_version_independent_id: 7fe6be41-45a9-f705-8a3a-dfb69b55e468
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2022/April2022.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2022/april2022
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2022/April2022.md
cmProducts: []
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ecbec206-b3b2-4795-8a5b-73d4d69cc0bc
platformId: 40bb8302-532e-9d23-03b8-9153b80d60d0
---

# April 2022 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, April 26, 2022, Microsoft released an update to the Microsoft Trusted Root Certificate Program.

This release will **add** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Cybertrust Japan / JCSI \ SecureSign Root CA14 \ DD50C0F779B3642E74A2B89D9FD340DDBBF0F24F
2. Cybertrust Japan / JCSI \ Cybertrust iTrust Root Certification Authority \ D884EF31B85CDBCB0F95A6F4CD038F8848135D25
3. Cybertrust Japan / JCSI \ SecureSign Root CA15 \ CBBA83C8C15A5DF1F9736FCAD7EF2813064A077D
4. Cybertrust Japan / JCSI \ SecureSign Root CA12 \ 7A221E3DDE1B06AC9EC84770168E3CE5F76B06F4

This release will **add EV SSL Policy OID** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. HARICA \ HARICA TLS RSA Root CA 2021 \ 022D0582FA88CE140C0679DE7F1410E945D7A56D
2. HARICA \ HARICA TLS ECC Root CA 2021 \ BCB0C19DE9989270193857E98DA7B45D6EEE0148

This release will **add EV Code Sign Policy OID** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. HARICA \ HARICA Code Signing RSA Root CA 2021 \ 8DDEB82046B6227C79246A3EAD7B32C3E88FFCAC
2. HARICA \ HARICA Code Signing ECC Root CA 2021 \ E436E537B71342B62E8E00305AD9A3D1D73347E9

This release will **removed NotBefore property** from the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Certinomis / Docapost \ Certinomis - Root CA \ 9D70BB01A5A4A018112EF71C01B932C534E788A8

This release will **add Client Authentication and Secure Email EKU** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Solutions Notarius Inc. \ Notarius Root Certificate Authority \ B1C3AC0977AAF147E5821A87F8DA32226A210693

This release will **add Client Authentication, Code Signing, Document Signing, Time Stamping and Secure Email EKU** to the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. Austrian Society For Data Protection (GlobalTrust) \ GLOBALTRUST 2020 \ D067C11351010CAAD0C76A65373116264F5371A2

Note

- As part of this release, Microsoft also updated the Untrusted CTL time stamp and sequence number. No changes were made to the contents of the Untrusted CTL but this will cause your system to download/refresh the Untrusted CTL. This is a normal update that is sometimes done when the Trusted Root CTL is updated.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus