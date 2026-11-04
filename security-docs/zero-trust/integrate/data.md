---
layout: Conceptual
title: Zero Trust integration for Data overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/integrate/data
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Independent software vendors (ISVs) can integrate their solutions with Microsoft Purview Information Protection SDK to help customers adopt a Zero Trust model and keep their organizations secure.
ms.date: 2025-02-21T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: integration
ms.collection:
- zerotrust-partner
locale: en-us
document_id: d698abc3-94b2-2ebf-a0a7-3ca972fb892f
document_version_independent_id: cbf22cad-28ae-edf0-1d65-7af47e67c642
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/integrate/data.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/integrate/data
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/integrate/data.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
platformId: 1a04b904-9fd9-9834-b18d-af26185ef129
---

# Zero Trust integration for Data overview | Microsoft Learn

![](../media/icon-data-medium.png)

Keeping data protected is a central objective of a Zero Trust strategy. Where possible, data should remain safe even if it leaves the devices, apps, infrastructure, and networks the organization controls. To ensure protection and that data access is restricted to authorized users, data should be inventoried, classified, labeled, and, where appropriate, encrypted.

Zero Trust data solutions help customers classify and label data based on assessed risk, and ensure that the data management is following the organization's compliance requirements.

This guidance is for software providers and technology partners who want to enhance their data security solutions by integrating with Microsoft products.

## Zero Trust integration for Data guide

This integration guide includes instructions for integrating with the Microsoft Purview Information Protection SDK, which is the unification of Microsoft's classification, labeling, and protection services.

Independent software vendors (ISVs) can integrate with the Microsoft Purview Information Protection (MIP) SDK to build solutions that help customers understand and protect data, prevent data loss, and govern data storage and access.

![Image with the four ways ISVs can integrate with the MIP SDK. The four categories are: know your data, protect your data, prevent data loss, and govern your data.](../media/integrate/data/microsoft-information-protection-capabilities.png)

### Microsoft Purview Information Protection SDK

The Microsoft Purview Information Protection solution is the unification of Microsoft's classification, labeling, and protection services. Third parties can use the MIP SDK to integrate with applications, using a standard, consistent data labeling schema and protection service.

ISVs can use the [Microsoft Purview Information Protection SDK](/en-us/information-protection/develop/overview) to help customers understand their data landscape, apply flexible protection actions, detect risky behavior to prevent data loss, and maintain data compliance through automatic actions. For example:

- Applying labels automatically to documents based on content
- Enforcing protection and controls based on labels
- Automatically classifying and protecting data coming out of apps to prevent data theft

The [Microsoft Purview Information Protection SDK - API concepts](/en-us/information-protection/develop/concept-apis-use-cases) page includes more examples of how you can integrate with the MIP SDK.

### Getting started with the SDK

We include the following guidance to help you on the journey to integrating your solutions with Microsoft Entra ID.

[Microsoft Purview Information Protection SDK](/en-us/information-protection/develop/overview#microsoft-information-protection-sdk) This document describes common use cases for the MIP SDK, including how to get started using the SDK and building integrations. The MIP SDK exposes the labeling and protection services from Microsoft 365 Security and Microsoft Purview compliance portal to non-Microsoft applications and services. Partners can use the SDK to build solutions with native support for applying labels and protection to files as well as reasoning over MIP-encrypted information and which actions should be taken when specific labels are detected.

https://aka.ms/mipsdksamples This resource contains sample implementations showing the use of the MIP SDK in code. For example, the [.NET File Quickstart](/en-us/samples/azure-samples/mipsdk-dotnet-file-quickstart/mipsdk-file-dotnet-quickstart/) demonstrates labeling and reading labels on files.