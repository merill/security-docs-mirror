---
layout: Conceptual
title: August 2020 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/trusted-root/2020/august2020
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: kasirota
author: kasirota
description: This document provides details about the changes made in August 2020 to the root store.
ms.date: 2020-08-18T00:00:00.0000000Z
ms.service: security
ms.topic: release-notes
locale: en-us
document_id: c69cce54-8ce4-c30c-1ec7-02087dad7962
document_version_independent_id: 33ff34a5-229a-b01b-178e-bc32da7bbfdf
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/trusted-root/2020/august2020.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: trusted-root/2020/august2020
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/trusted-root/2020/august2020.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e0ffb20c-01c6-407b-a9bd-29111652a1dc
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/3904bce4-d817-48cf-85fd-b6146fca83b7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 6e7ca797-dd0f-de5b-f833-bdc3f247c8d5
---

# August 2020 Deployment Notice - Microsoft Trusted Root Program | Microsoft Learn

On Tuesday, August 25th, 2020, Microsoft will release a planned update to the Microsoft Trusted Root Certificate Program.

This release will **NotBefore** the following roots (CA \ Root Certificate \ SHA-1 Thumbprint):

1. China Financial Certification Authority (CFCA) \ China Financial CA \ EABDA240440ABBD694930A01D09764C6C2D77966
2. LuxTrust \ LuxTrust Global Root 2 \ 1E0E56190AD18B2598B20444FF668A0417995F3F

This release will **NotBefore the Code Signing EKU** to the following roots:

1. China Financial Certification Authority (CFCA) \ CFCA EV ROOT \ E2B8294B5584AB6B58C290466CAC3FB8398F8483
2. Chunghwa Telecom \ Chunghwa Telecom Co., Ltd. - ePKI Root Certification Authority \ 67650DF17E8E7E5B8240A4F4564BCFE23D69C6F0
3. Chunghwa Telecom \ ePKI Root Certification Authority - G2 \ D99B104298594763F0B9A927B79269CB47DD158B
4. DigiCert \ Symantec Enterprise Mobile Root for Microsoft \ 92B46C76E13054E104F230517E6E504D43AB10B5
5. Government of Brazil, Instituto Nacional de Tecnologia da Informação (ITI) \ Autoridade Certificadora Raiz Brasileira v2 \ A9822E6C6933C63C148C2DCAA44A5CF1AAD2C42E
6. Government of India, Ministry of Communications & Information Technology, Controller of Certifying Authorities (CCA) \ CCA India 2015 SPL \ 3BC6DCE00307BD676041EBD85970C62F8FDA5109
7. Izenpe S.A. \ Izenpe.com \ 30779E9315022E94856A3FF8BCF815B082F9AEFD
8. Korea Information Security Agency (KISA) \ KISA RootCA 1 \ 027268293E5F5D17AAA4B3C3E6361E1F92575EAA
9. NetLock Ltd. \ NetLock Minositett Kozjegyzoi (Class QA) Tanusitvanykiado \ 016897E1A0B8F2C3B134665C20A727B7A158E28F
10. SI-TRUST \ SI-TRUST Root \ 3A4979B40FA841488200B582FBEEB63AAB9919AE

This release will **Disallow the OCSP EKU** to the following roots:

1. Chunghwa \ Telecom Chunghwa Telecom Co., Ltd. - ePKI Root Certification Authority \ 67650DF17E8E7E5B8240A4F4564BCFE23D69C6F0
2. DigiCert \ Baltimore CyberTrust Root \ D4DE20D05E66FC53FE1A50882C78DB2852CAE474
3. Government of Spain, Dirección General de la Policía ? Ministerio del Interior ? España. AC R \ AIZ DNIE \ B38FECEC0B148AA686C3D00F01ECC8848E8085EB
4. Korea Information Security Agency (KISA) \ KISA RootCA 1 \ 027268293E5F5D17AAA4B3C3E6361E1F92575EAA
5. SI-TRUST \ SI-TRUST Root \ 3A4979B40FA841488200B582FBEEB63AAB9919AE

This release will **NotBefore the EFS EKU** to the following roots:

1. Austrian Society for Data Protection (Arge Daten) (GlobalTrust) \ GLOBALTRUST \ 342CD9D3062DA48C346965297F081EBC2EF68FDC
2. China Financial Certification Authority (CFCA) \ CFCA EV ROOT \ E2B8294B5584AB6B58C290466CAC3FB8398F8483
3. Chunghwa Telecom \ Chunghwa Telecom Co., Ltd. - ePKI Root Certification Authority \ 67650DF17E8E7E5B8240A4F4564BCFE23D69C6F0
4. Chunghwa Telecom \ ePKI Root Certification Authority - G2 \ D99B104298594763F0B9A927B79269CB47DD158B
5. Entrust \ AffirmTrust Premium \ D8A6332CE0036FB185F6634F7D6A066526322827
6. Entrust \ AffirmTrust Commercial \ F9B5B632455F9CBEEC575F80DCE96E2CC7B278B7
7. Entrust \ Entrust Root Certification Authority \ B31EB1B740E36C8402DADC37D44DF5D4674952F9
8. Entrust \ AffirmTrust Premium ECC \ B8236B002F1D16865301556C11A437CAEBFFC3BB
9. Entrust \ Entrust.net Certification Authority (2048) \ 503006091D97D4F5AE39F7CBE7927D7D652D3431
10. Entrust \ Entrust Root Certification Authority - G2 \ 8CF427FD790C3AD166068DE81E57EFBB932272D4
11. Entrust \ AffirmTrust Networking \ 293621028B20ED02F566C532D1D6ED909F45002F
12. Global Digital Cybersecurity Authority Co., Ltd. (Formerly Guang Dong Certificate Authority (GDCA)) \ GDCA TrustAUTH R5 ROOT \ 0F36385B811A25C39B314E83CAE9346670CC74B4
13. Government of Brazil, Instituto Nacional de Tecnologia da Informação (ITI) \ Autoridade Certificadora Raiz Brasileira v2 \ A9822E6C6933C63C148C2DCAA44A5CF1AAD2C42E
14. Government of India, Ministry of Communications & Information Technology, Controller of Certifying Authorities (CCA) CCA India 2015 SPL \ 3BC6DCE00307BD676041EBD85970C62F8FDA5109
15. Government of India, Ministry of Communications & Information Technology, Controller of Certifying Authorities (CCA) CCA India 2014 \ A2B86B5A68D92819D9CE5DD6D7969A4968E11991
16. IdenTrust Services, LLC \ IdenTrust Public Sector Root CA 1 \ BA29416077983FF4F3EFF231053B2EEA6D4D45FD
17. IdenTrust Services, LLC \ DST Root CA X3 \ DAC9024F54D8F6DF94935FB1732638CA6AD77C13
18. OISTE \ OISTE WISeKey Global Root GC CA \ E011845E34DEBE8881B99CF61626D1961FC3B931
19. SI-TRUST \ SI-TRUST Root \ 3A4979B40FA841488200B582FBEEB63AAB9919AE

This release will **NotBefore the IP Security EKUs** to the following roots:

1. Austrian Society for Data Protection (Arge Daten) (GlobalTrust) \ GLOBALTRUST \ 342CD9D3062DA48C346965297F081EBC2EF68FDC
2. China Financial Certification Authority (CFCA) \ CFCA EV ROOT \ E2B8294B5584AB6B58C290466CAC3FB8398F8483
3. Chunghwa Telecom \ Chunghwa Telecom Co., Ltd. - ePKI Root Certification Authority \ 67650DF17E8E7E5B8240A4F4564BCFE23D69C6F0
4. Entrust \ AffirmTrust Premium \ D8A6332CE0036FB185F6634F7D6A066526322827
5. Entrust \ AffirmTrust Commercial \ F9B5B632455F9CBEEC575F80DCE96E2CC7B278B7
6. Entrust \ Entrust Root Certification Authority \ B31EB1B740E36C8402DADC37D44DF5D4674952F9
7. Entrust \ AffirmTrust Premium ECC \ B8236B002F1D16865301556C11A437CAEBFFC3BB
8. Entrust \ Entrust.net Certification Authority (2048) \ 503006091D97D4F5AE39F7CBE7927D7D652D3431
9. Entrust \ Entrust Root Certification Authority - G2 \ 8CF427FD790C3AD166068DE81E57EFBB932272D4
10. Entrust \ AffirmTrust Networking \ 293621028B20ED02F566C532D1D6ED909F45002F
11. Government of Brazil, Instituto Nacional de Tecnologia da Informação (ITI) \ Autoridade Certificadora Raiz Brasileira v2 \ A9822E6C6933C63C148C2DCAA44A5CF1AAD2C42E
12. Izenpe S.A. \ Izenpe.com \ 30779E9315022E94856A3FF8BCF815B082F9AEFD

This release will **add** to the following roots:

1. Government of Brazil, Instituto Nacional de Tecnologia da Informação (ITI) \ Autoridade Certificadora Raiz Brasileira v10 \ 6C155ED7271A904A0DC040F0C857FF53BF6DB290

Note

- Windows 10 allows us to stop trusting roots or EKU's using the "NotBefore" or "Disable" properties, both of which allow us to remove certain capabilities of the root certificate without complete removal. These features are not available on versions prior to Windows 10. Earlier versions of Windows will be unaffected by this change.
- The NotBefore and Disable dates are set for the first day of the release month.
- The update package will be available for download and testing at: https://aka.ms/CTLDownload
- Signatures on the Certificate Trust Lists (CTLs) for the Microsoft Trusted Root Program changed from dual-signed (SHA-1/SHA-2) to SHA-2 only. No customer action required. For more information, please visit: https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus