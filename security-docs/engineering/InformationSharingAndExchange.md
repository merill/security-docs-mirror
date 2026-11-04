---
layout: Conceptual
title: Information Sharing and Exchange | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/engineering/informationsharingandexchange
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: laramiller
author: laramillermsft
description: This document provides details of the Information Sharing and Exchange (ISE) offering that enables Microsoft to share and exchange materials related to Microsoft products and services.
ms.date: 2023-11-20T00:00:00.0000000Z
ms.service: security
ms.topic: feature-guide
locale: en-us
document_id: b744576b-955b-fa11-0096-cf9accb285ac
document_version_independent_id: b744576b-955b-fa11-0096-cf9accb285ac
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/engineering/InformationSharingAndExchange.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: engineering/informationsharingandexchange
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/engineering/InformationSharingAndExchange.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2624a017-7337-44fa-9494-a407bb0e59fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/7cf8f81d-2989-4e5d-aa91-5191d10a3323
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a438284e-c3c3-4c36-ab0b-aa7c244b912c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/1cb9c90f-9a3f-4389-8367-0a20c542621f
platformId: 1fb0ecc8-f7fc-3ed8-23a5-b75b284c1af0
---

# Information Sharing and Exchange | Microsoft Learn

The mission of Microsoft’s Government Security Program (GSP) is to build trust through transparency. Since the program’s inception in 2003, Microsoft has provided visibility into our technology and security artifacts, which governments and international organizations can use to help protect themselves and their citizens. The Information Sharing and Exchange offering enables Microsoft to share and exchange materials about security threats, vulnerabilities, anomalous behavior, malware information, and security issues against or related to Microsoft products and services.

This offering brings together groups and resources across the Microsoft environment to help governments protect citizens, infrastructure, and organizations.

## The Information Sharing and Exchange (ISE) offering provides

| Name | Detail |
| --- | --- |
| **Advanced Notice of Security Vulnerabilities** | - 5-day advanced notice of vulnerabilities with release notes and affected software tables<br>- 24-hour advanced notice including exploitability index |
| **Malicious URLs** | - Feed of potentially malicious publicly facing servers and services detected by Bing crawlers<br>- Updated every three hours, 5-day cycle of data |
| **CTIP Botnet Feeds** | - Provided by the Digital Crimes Unit’s (DCU) Cyber Threat Intelligence Program (CTIP)<br>- Botnet data is tailored to the agency (or country code top-level domain in the case of CERTs)<br>- 4 feeds: Infected device, Command & Control, IoT, and Domains<br>- Delivered near real-time, hourly, or daily (deduped) |
| **Clean File Meta Data** | - Clean file hash data often used for allow-listing and forensics<br>- Updated every 3 hours<br>- Covers all Microsoft binaries on the Microsoft download center |
| **Partnership** | - Information exchange through a variety of forums<br>- Access to the Digital Crimes Community (DCU) Portal<br>- Threat intelligence data sharing with the Digital Crimes Unit (DCU)<br>- Direct engagement with engineering groups and other Microsoft teams including the Microsoft Security Response Center (MSRC) and Windows Defender Security Intelligence |

## Data Feeds Delivery

The feeds offered under the ISE authorization reside within several groups including the **Microsoft Security Response Center (MSRC)**, the **Digital Crimes Unit (DCU)**, **Bing**, and **Product Release and Security Services (PRSS)**.

The GSP team provides a **web-based application** that allows GSP agencies to access the ISE data feeds from a single interface. All communications containing sensitive data are encrypted.
![Data Feed delivery](../media/security-gsp/datafeeddelivery.jpg)
## Data Use Descriptions

**Advanced Security Update Notification** The notice package lists all the CVEs (Common Vulnerabilities and Exposures) being addressed in the release. Each CVE contains a set of information including the Vulnerability Description (including metrics), Exploitability Index, and Affected Software.
![Content for each CVE](../media/security-gsp/contentforeachcve.jpg)
**Bing Malicious URLs** The Bing Malicious URL feed contains publicly facing servers or services that have been identified as being potentially malicious. New files are uploaded every three hours; full data sets are generated in 5 days. Many agencies import the JSON files directly into their existing threat intelligence analysis tools.
![Geo map of IPs](../media/security-gsp/bingmurl1.jpg)![Threat types](../media/security-gsp/bingmurl2.jpg)
**Clean File Meta Data (CFMD)**

The Clean File Meta Data (CFMD) feed contains cryptographic signatures (SHA256 hashes) for the files contained within Microsoft products. These are often used in forensic examinations of potentially compromised devices and for allow/disallow file execution in critical systems.
![Clean File Metadata](../media/security-gsp/cleanfilemetadata.jpg)
**CTIP Botnet Feeds: Infected Data Feed**

The DCU provides compromised victim botnet data via the DCU‘s CTIP threat intelligence service Infected device data feed, to enable network protection scenarios for CTIP subscribers, and to help facilitate remediation of the compromised systems with the goal of reducing the number of infected systems on the Internet. Other feeds include the Command and Control (C2), IoT, and Domains lists that are often used to restrict traffic flow to known malware networks via firewalls and protective DNS.
![CTIP data 1](../media/security-gsp/ctip1.jpg)![CTIP data 2](../media/security-gsp/ctip2.jpg)
## Contact Us

Contact your local Microsoft representative to learn more about the Government Security Program.