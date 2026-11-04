---
layout: Conceptual
title: Visibility, automation, and orchestration Zero Trust integration overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/integrate/visibility-automation-orchestration
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Independent software vendors (ISVs) can integrate their solutions with Microsoft Sentinel to help customers adopt a Zero Trust model and keep their organizations secure.
ms.date: 2025-02-21T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- zerotrust-partner
locale: en-us
document_id: a74cf02b-8d0e-514a-a02e-a6f24c781de5
document_version_independent_id: 4a31c3a5-da5e-fef6-f087-64f96f603fa9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/integrate/visibility-automation-orchestration.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/integrate/visibility-automation-orchestration
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/integrate/visibility-automation-orchestration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: fac39e91-18fd-f473-5452-3a0fccfc6ab9
---

# Visibility, automation, and orchestration Zero Trust integration overview | Microsoft Learn

![](../media/icon-visibility-automation-orchestration-medium.png)

Organizations today have to contend with an increasingly complex threat landscape. Assuming breach is a key principle of Zero Trust. To assume breach effectively, have a threat detection approach with visibility across the entire estate and the level of depth that security teams need to drill down into individual threats.

Visibility, automation, and orchestration integrations are about building robust solutions for monitoring security signals. They're key to ensuring the ongoing security of an environment by detecting suspicious behavior and enabling proactive hunting for threats. They allow customers to scan for unexpected behavior and access and proactively search for bad actors already in the network.

This guidance is for software providers and technology partners who want to enhance their visibility, automation, and orchestration security solutions by integrating with Microsoft products.

## Visibility, automation, and orchestration Zero Trust integration guide

This integration guide includes instructions for integrating with [Microsoft Sentinel](/en-us/azure/sentinel). Microsoft Sentinel is Microsoft’s cloud-native Security Information and Event Management (SIEM) service. Independent software vendors (ISVs) can integrate with Microsoft Sentinel. This integration enables new use-cases for customers by providing data connectors, analytics rules, interactive workbooks, and automation playbooks that deliver end-to-end product, domain, and industry vertical value for customers.

### Microsoft Sentinel

Microsoft’s approach to threat protection is to combine both Security Information and Event Management (SIEM) and Extended Detection and Response (XDR) into an integrated experience, with Microsoft Sentinel, Microsoft Defender XDR, and Microsoft Defender for Cloud. This approach gives organizations the best of both worlds: end-to-end threat visibility across all of your resources; correlated, prioritized alerts based on the deep understanding Microsoft have of specific resources and AI that stitches that signal together; and coordinated action across the organization.

Microsoft Sentinel, Microsoft’s cloud-native SIEM, provides a bird’s eye view across your entire digital estate. It provides intelligent security analytics across all users, devices, applications, and infrastructure, both on-premises and in multiple clouds. It then cross-correlates and detects threats using machine learning, and streamlines investigations with AI and powerful hunting tools.

Microsoft Sentinel has many integrations with partner solutions, including other security solutions, clouds, threat intelligence vendors, and more. ISVs can integrate with Microsoft Sentinel to enable new use-cases for customers with data connectors, analytics rules, interactive workbooks, and automation playbooks to deliver end-to-end product or domain or industry vertical value for customers.

The following guidance helps you create solutions that integrate with Microsoft Sentinel.

**What you can build**: [Integration Opportunities Guide for Microsoft Sentinel](https://azure.microsoft.com/resources/integration-opportunities-with-microsoft-sentinel-december-2021/)

Partners can engage with Microsoft Sentinel in several key scenarios to deliver mutual customer value. This article outlines these scenario opportunities and technical integrations by describing how to decide what integrations to build, how to get started, how to deliver to Microsoft Sentinel customers, and finally how to promote Microsoft Sentinel Integrations.

![Illustration of the categories of integration opportunities. The opportunities are as follows. Collecting data. Monitoring and detecting with visibility, intelligence, analytics, and hunting. Investigating incidents. Finally, responding with automation.](../media/integrate/visibility-automation-orchestration/integration-opportunities.png)

**How to build it**: [Integration Components for Microsoft Sentinel](https://github.com/Azure/Azure-Sentinel/wiki#get-started)

Once you identified the scenarios you want to support with your solution, create a list of artifacts to implement. This resource contains a list of all the artifacts that you can build and guidance on how to build them. It's available as part of the Threat Hunters program, which is Microsoft Sentinel's community of content contributors inclusive of both partners and the community.

**How to package it**: [Guide to Building Microsoft Sentinel Solutions](https://github.com/Azure/Azure-Sentinel/tree/master/Solutions#readme)

After you created a solution, you must publish it. This guide provides an overview of Microsoft Sentinel Solutions and how to build and publish a solution for Microsoft Sentinel.

Microsoft Sentinel Solutions allows partners to deliver combined product, domain, or vertical value via solutions in Microsoft Sentinel and be able to productize investments. It supports discoverability, deployment, and enablement of scenarios in Microsoft Sentinel. It's powered by [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/) and the [Microsoft Partner Center](/en-us/partner-center/overview).

![Value propositions of packaged Microsoft Sentinel Solutions. For customers, they provide discovery of new value, easy deployment, and enablement. For Partners they build combined value, productize investments, and expand customer reach with marketplace offerings.](../media/integrate/visibility-automation-orchestration/package-solutions.png)