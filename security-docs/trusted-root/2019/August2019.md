---
layout: Conceptual
title: August 2019 Deployment Notice (27/August) - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2019/august2019
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: kasirota
author: kasirota
description: This document provides details about the changes made in August 2019 to the root store.
ms.date: 2019-08-02T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: 4f8efacf-e488-20cd-90be-259c2e0c3d6b
document_version_independent_id: d4f00bcc-d0d4-3da6-5222-83ac0b161118
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2019/August2019.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2019/august2019
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2019/August2019.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e0ffb20c-01c6-407b-a9bd-29111652a1dc
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/3904bce4-d817-48cf-85fd-b6146fca83b7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 65865f16-925b-73b9-9419-9fbd71482324
---

# August 2019 Deployment Notice (27/August) - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, August 27th, 2019, Microsoft will release a planned update to the Microsoft Trusted Root Certificate Program.

This release will **disable** the following roots :

1. E-ME SSI (RCA) \ C9321DE6B5A82666CF6971A18A56F2D3A8675602
2. Correo Uruguayo - Root CA \ F9DD19266B2043F1FE4B3DCB0190AFF11F31A69D
3. Skaitmeninio sertifikavimo centras, Lithuania (23E8) \ 23E833233E7D0CC92B7C4279AC19C2F474D604CA
4. Skaitmeninio sertifikavimo centras, Lithuania (3E84) \ 3E84D3BCC544C0F6FA19435C851F3F2FCBA8E814
5. Sectigo (UTN Hardware) \ 0483ED3399AC3608058722EDBC5E4600E3BEF9D7
6. Certinomis \ 2E14DAEC28F0FA1E8E389A4EABEB26C00AD383C3
7. CertEurope \ FA0882595F9CA6A11ECCBEAF65C764C0CCC311D0
8. Certipost E-Trust Primary TOP Root CA \ 0560A2C738FF98D1172A94FE45FB8A47D665371E
9. SwissSign Gold Root CA – G3 \ 0B7199A1C7F3ADDF7BA7EAB8EB574AE80D60DDDE
10. SwissSign Platinum Root CA – G3 \ A1E7C600AA4170E5B74BC94F9B9703EDC261B4B9
11. S-Trust Universal Root CA \ 1B3D1114EA7A0F9558544195BF6B2582AB40CE9A
12. TC TrustCenter Class 3 CA II \ 8025EFF46E70C8D472246584FE403B8A8D6ADBF5
13. ComSign Advanced Security CA \ 80BF3DE9A41D768D194B293C85632CDBC8EA8CF7
14. GeoTrust Global CA 2 \ A9E9780814375888F20519B06D2B0D2B6016907D
15. DigiCert Global Root \ 97817950D81C9670CC34D809CF794431367EF474

This release will **NotBefore** the following roots:

1. Australian Defence Organisation (ADO) Certificate Authority 02 \ 84429D9FE2E73A0DC8AA0AE0A902F2749933FE02
2. IGC/A AC racine Etat francais \ 1AC92F09EA89E28B126DFAC51E3AF7EA9095A3EE
3. Secrétariat Général de la Défense Nationale \ 60D68974B5C2659E8A0FC1887C88D246691B182C
4. Halcom Root CA \ 535B001672ABBF7B6CC25405AE4D24FE033FD1CC
5. Swisscom Root CA 2 \ 77474FC630E40F4C47643F84BAB8C6954A8A41EC
6. LuxTrust Global Root CA \ C93C34EA90D9130C0F03004B98BD8B3570915611
7. SSC GDL CA Root A \ 0C2009A4A88D8B4202185250540CC42BDFB5B089
8. PersonalID Trustworthy RootCA 2011 \ 4394CE3126FF1A224CDD4DEEB4F4EC1DA368EF6A
9. ESIGNIT.ORG \ 9F8DE799CF8764ED2466990564041B194919EDE8
10. Signet Root CA \ B2BD9031AA6D0E14F4C57FD548258F37B1FB39E4
11. TÜRKTRUST Elektronik Sertifika Hizmet Sağlayıcısı H5 \ C418F64D46D1DF003D2730137243A91211C675FB
12. Athex Root CA \ DB2B7B434DFB7FC1CB5926EC5D9521FE350FF279
13. Digidentity BV \ F138A330A4EA986BEB520BB11035876EFB9D7F1C

This release will **NotBefore the code signing EKU** for the following roots:

1. Staat der Nederlanden Root CA - G2 \ 59AF82799186C7B47507CBCF035746EB04DDB716
2. "Japan Certification Services, Inc. SecureSign RootCA11" \ 3BC49F48F8F373A09C1EBDF85BB1C365C7D811B3
3. TeliaSonera Root CA v1 \ 4313BB96F1D5869BC14E6A92F6CFF63469878237
4. Carillon Information Security Inc. \ A69E0336C4E59023FF653C71F928EB73F21C00F0
5. AffirmTrust Premium ECC \ B8236B002F1D16865301556C11A437CAEBFFC3BB
6. AffirmTrust Premium \ D8A6332CE0036FB185F6634F7D6A066526322827
7. AffirmTrust Commercial \ F9B5B632455F9CBEEC575F80DCE96E2CC7B278B7
8. AffirmTrust Networking \ 293621028B20ED02F566C532D1D6ED909F45002F

This release will **remove** the following roots:

1. ePKI Root Certification Authority - G2 \ 81AC5DE150D1B8DE5D3E0E266A136B737862D322

This release will **add** the following roots:

1. TrustFactory Client Root Certificate Authority \ F90CC7521EAB33F228EAA835E4E50292E31D281E
2. TrustFactory SSL Root Certificate Authority \ D11478E8E5FB62540593D22C51570D014EAC76D8

This release will **modify the EV OIDs** for the following root:

1. HiPKI Root CA - G1 \ 6A92E4A8EE1bEC964537E3295749CD96E3E5D260

Note

- Windows 10 allows us to stop trusting roots or EKU's using the "NotBefore" or "Disable" properties, both of which allow us to remove certain capabilities of the root certificate without complete removal. These features are not available on versions prior to Windows 10. Earlier versions of Windows will be unaffected by this change.
- The NotBefore and Disable dates are set for the first day of the release month. This means that all certificates issued after August 1st will be affected.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload