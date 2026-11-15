---
layout: Conceptual
title: Integrate security solutions with Microsoft | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/integrate/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Find integration guidance for software providers, independent software vendors, and technology partners building solutions with Microsoft security products.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- zerotrust-partner
locale: en-us
document_id: 22661919-d61c-98c8-0b96-bbbf8ff7afa7
document_version_independent_id: e6d60b39-07ae-9928-5f24-54d56b505c2d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/integrate/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/integrate/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/integrate/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/8b9ae643-2e85-42b8-beb2-eef4bae8c4bc
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e047e27d-b5f3-43a8-b4b0-4f6dca95e7c9
platformId: bced7d89-05a4-947a-c9d5-34ebb89a2833
---

# Integrate security solutions with Microsoft | Microsoft Learn

This guidance is for independent software vendors (ISVs), software providers, and technology partners that build security solutions with Microsoft products and services.

Choose the integration scenario that matches your solution, and then use the linked product documentation for supported APIs, SDKs, prerequisites, and publishing requirements. Product-owned documentation is the source of record for each integration.

These integration paths can help customers apply Zero Trust principles, but they are organized around supported integration opportunities rather than the Security Adoption Framework technology taxonomy.

## Choose an integration scenario

| Integration scenario | Start here |
| --- | --- |
| **Identity and access** | Publish and provision applications with Microsoft Entra ID, or extend authentication for external users. See [Publish your app to the Microsoft Entra application gallery](/en-us/entra/identity/enterprise-apps/publish-app-gallery), [Develop a SCIM endpoint for user provisioning](/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups), and [Custom authentication extensions for Microsoft Entra External ID](/en-us/entra/external-id/customers/concept-custom-extensions). |
| **Endpoint security** | Extend endpoint detection, investigation, and response by using [Microsoft Defender for Endpoint partner opportunities and scenarios](/en-us/defender-endpoint/partner-integration) and the [Defender for Endpoint APIs](/en-us/defender-endpoint/api/apis-intro). |
| **Device management and compliance** | Integrate device, application, and compliance management by [working with Intune in Microsoft Graph](/en-us/graph/api/resources/intune-graph-overview) and [configuring Microsoft Graph API access for Intune](/en-us/intune/developer/configure-graph-api-access). |
| **Applications and SaaS security** | Integrate secure web gateways, firewalls, and other solutions with [Cloud Discovery](/en-us/defender-cloud-apps/set-up-cloud-discovery), or use the [Microsoft Defender for Cloud Apps REST API](/en-us/defender-cloud-apps/api-introduction). |
| **Data protection** | Build applications that classify, label, and protect information by using the [Microsoft Information Protection SDK](/en-us/information-protection/develop/overview). |
| **Cloud and infrastructure security** | Exchange security findings and integrate workflows by using [Microsoft Defender for Cloud partner integrations](/en-us/azure/defender-for-cloud/partner-integrations) and [continuous export](/en-us/azure/defender-for-cloud/continuous-export). |
| **Network security** | Use current Azure network extension points and review Microsoft 365 connectivity requirements. See [Azure Firewall Manager security partner providers](/en-us/azure/firewall-manager/trusted-security-partners), [Gateway Load Balancer](/en-us/azure/load-balancer/gateway-overview), and the [Microsoft 365 Network Provider Program](/en-us/microsoft-365/enterprise/microsoft-365-networking-partner-program) for the program's current status. |
| **Security operations** | Decide what to build, create the required integration content, and package and publish a solution by using the [Microsoft Sentinel solution build and publishing guide](/en-us/azure/sentinel/isv/sentinel-integration-guide). For cross-product security data, see [Microsoft Graph security API partner opportunities](/en-us/graph/security-partner-overview). |
| **Operational technology and IoT security** | Connect SIEM, ticketing, and other partner services by using the [Microsoft Defender for IoT integration guidance](/en-us/azure/defender-for-iot/organizations/integrate-overview). |

## Related guidance

- [Deploy Zero Trust technologies](../deploy/overview) if you're implementing security controls in an organization.
- [Use the Security Adoption Framework](../security-adoption-model) if you're planning security adoption, managing security work, or connecting improvements to business priorities and risk.