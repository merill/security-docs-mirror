---
layout: Conceptual
title: Zero Trust integration for Applications overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/integrate/applications
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Independent software vendors (ISVs) can integrate their solutions with Microsoft Defender for Cloud Apps to help customers adopt a Zero Trust model and keep their organizations secure.
ms.date: 2025-02-21T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: integration
ms.collection:
- zerotrust-partner
locale: en-us
document_id: b7062696-d58f-e13d-c766-e89e29ef1d2f
document_version_independent_id: 24dbe085-cc9d-db6e-3b05-448e9ed0cb53
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/integrate/applications.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/integrate/applications
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/integrate/applications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8e3fdb08-a059-4277-98f6-c0e21e940707
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e69816a-aaaa-474e-a36f-3ec7790fadc3
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/88291526-9c74-4f87-878c-de0a82134421
- https://authoring-docs-microsoft.poolparty.biz/devrel/ae012320-d2b3-47d8-abdc-898a64d069a9
platformId: 3cbbe614-e34a-36e0-8e96-c9b502584bac
---

# Zero Trust integration for Applications overview | Microsoft Learn

![](../media/icon-applications-medium.png)

Applications are core productivity tools for employees. In a modern workplace, adoption of cloud based Software as a Service (SaaS) applications creates new challenges for IT. Lack of visibility and control over applications, the way users interact with them, and the data that is exposed through them creates security and compliance risks.

Zero Trust solutions for the applications pillar are about providing visibility and control over app usage data and analytics that identify and combat cyber threats across cloud apps and services.

This guidance is for software providers and technology partners who want to enhance their applications security solutions by integrating with Microsoft products.

## Zero Trust integration with Applications guide

This integration guide includes instructions for integrating with [Microsoft Defender for Cloud Apps)](/en-us/cloud-app-security/). Defender for Cloud Apps is a cloud access security broker (CASB) that operates on multiple clouds. It provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.

![Architectural diagram showing how an organization uses Defender for Cloud Apps features including app connectors, cloud discovery, and proxy access. App connectors connect to protected cloud apps via APIs. Cloud discovery consumes traffic logs and provides configuration scripts. Proxy access sits in between the organization and its protected apps in the cloud.](../media/integrate/applications/microsoft-cloud-app-security-architecture.png)

### Microsoft Defender for Cloud Apps

Independent software vendors (ISVs) can integrate with Defender for Cloud Apps to help organizations discover risky usage or potential exfiltration and protect them from risks surfaced by the use of shadow applications.

The Defender for Cloud Apps API provides programmatic access to Defender for Cloud Apps through [REST API endpoints](/en-us/cloud-app-security/api-introduction). ISVs can use the API to perform read and update operations on Defender for Cloud Apps data and objects at scale. For example:

- Uploading log files for Cloud Discovery
- Generating block scripts
- List activities and alerts
- Dismiss or resolve alerts

This approach allows ISVs to:

- Use Cloud Discovery to map and identify your cloud environment and the cloud apps your organization is using.
- Sanction and unsanction apps in your cloud.
- Easily deploy app connectors that take advantage of provider APIs, for deeper visibility and granular governance of apps that you connect to.
- Use Conditional Access App Control protection to get real-time visibility and control over access and activities within your cloud apps.

To get started, check out the introduction to the [Defender for Cloud Apps REST API](/en-us/cloud-app-security/api-introduction).

### Shadow IT partner integration

Secure Web Gateways (SWG) and Endian Firewall (EFW) solutions can integrate with Defender for Cloud Apps to provide customers with a comprehensive Shadow IT discovery, compliance and security risk assessment of the discovered apps, and integrated Access Control to unsanctioned apps.

The principles of the integration are:

- Deployment-less: The vendor streams traffic logs directly to Defender for Cloud Apps to avoid any agent deployment and maintenance.
- Log enrichment and App correlation: traffic logs are enriched against the Defender for Cloud Apps catalog to map each log record to a known app (associated with a risk profile)
- Defender for Cloud Apps analytics and reporting: Defender for Cloud Apps analyzes and processes the data to provide an overview Shadow IT report
- Risk-based access control: Defender for Cloud Apps syncs back to the vendor the signatures of the app to be blocked in to allow the customer with risk-based app management in Defender for Cloud Apps that consistent vendor access control mechanisms enforce

We recommend performing the following steps before starting to develop the integration:

1. Create a trial Defender for Cloud Apps tenant using [this link](https://www.microsoft.com/en-us/security/business/cloud-apps-defender).
2. Upload a sample traffic log using the manual upload feature.
3. Alternatively, you can use the API-based upload. For detailed instructions, use your trial credentials and [Cloud Discovery API documentation](/en-us/cloud-app-security/api-discovery)
    1. [Generate API token](/en-us/cloud-app-security/api-authentication#generate-a-token)
    2. Log upload –consists of three stages:
        1. [Initiate file upload](/en-us/cloud-app-security/api-discovery-initiate)
        2. [Perform file upload](/en-us/cloud-app-security/api-discovery-perform)
        3. [Finalize file upload](/en-us/cloud-app-security/api-discovery-finalize)
    3. [Generate block script](/en-us/cloud-app-security/api-discovery-script) (that is, extract unsanctioned apps info)

When uploading the log, choose one of the following parser options:

1. If your log format is a standard CEF, W3C, LEEF, select it in the dropdown of existing log formats
2. If not, [configure a custom log parser](/en-us/cloud-app-security/custom-log-parser)