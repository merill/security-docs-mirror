---
layout: Conceptual
title: Integrate SaaS apps for Zero Trust with Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/integrate-saas-apps
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: macapara
author: mjcaparas
description: Learn how to integrate SaaS apps for Zero Trust with Microsoft 365.
ms.date: 2024-04-18T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: solution-overview
ms.collection:
- m365solution-saas
- m365solution-overview
- m365solution-zero-trust
- zerotrust-solution
- highpri
locale: en-us
document_id: 87bc2ee3-48b0-f4bb-90e9-8784249e99f9
document_version_independent_id: 87bc2ee3-48b0-f4bb-90e9-8784249e99f9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/integrate-saas-apps.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/integrate-saas-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/integrate-saas-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e69816a-aaaa-474e-a36f-3ec7790fadc3
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/ae012320-d2b3-47d8-abdc-898a64d069a9
platformId: cfabae44-e141-0420-66d3-2c76b2ed4ec3
---

# Integrate SaaS apps for Zero Trust with Microsoft 365 | Microsoft Learn

The widespread increase in cloud adoption is transforming how organizations achieve business outcomes. This shift highlights the reliance on cloud-based apps resulting in higher demand for services such as Software as a Service (SaaS), Platform as a Service (PaaS), Infrastructure as a Service (IaaS), and cloud-based app development platforms. SaaS apps play a key role in ensuring that applications and resources are available and accessible from any device with an Internet connection.

While a multicloud environment can help reduce operational costs and improve scalability, the large amount of sensitive data and the flexibility it affords organizations can potentially pose a security risk. Deliberate steps must be taken to ensure that apps hosted in the cloud and their data are protected.

To ensure that access and productivity are secure, implementation of SaaS apps must align with the Zero Trust security model, which is based on these guiding principles.

| Zero Trust principle | Definition | Met by... |
| --- | --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. | Registering your SaaS apps and using Microsoft Entra Conditional Access policies. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. | Using Microsoft Purview Information Protection. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses. | Using Microsoft Defender for Cloud Apps. |

This documentation solution helps you apply Zero Trust principles using Microsoft 365 to help manage your digital estate of cloud apps, with a focus on SaaS apps.

The following diagram shows the relationships between your third-party cloud apps, Microsoft Entra ID, Defender for Cloud Apps, and Microsoft Purview Information Protection to apply these principles.

[![Diagram of the relationships between your third-party cloud apps, Microsoft Entra ID, Microsoft Defender for Cloud Apps, and Microsoft Purview Information Protection.](media/saas-apps-products.svg)](media/saas-apps-products.svg#lightbox)

The diagram shows:

- Examples of third-party cloud apps that include SaaS apps and your custom PaaS apps.
- The role of Microsoft Entra ID to include these apps in the scope of your strong authentication and other Conditional Access policies. For more information, see [Integrating all your apps with Microsoft Entra ID](/en-us/azure/active-directory/fundamentals/five-steps-to-full-application-integration-with-azure-ad).
- The role of Microsoft Defender for Cloud Apps in discovering the cloud apps that your organization uses. You can approve apps, apply session controls, and discover sensitive data. For newly discovered enterprise cloud apps that support federation, you can add them to Microsoft Entra ID to enforce strong authentication and other policies.
- The role of Microsoft Purview Information Protection to protect cloud app data and prevent data loss in conjunction with Microsoft Defender for Cloud apps.

## Implementing the layers of protection for SaaS apps

This diagram shows the units of work for deploying Zero Trust capabilities across your Microsoft 365 tenant, highlighting the specific steps for integrating and protecting your SaaS apps.

[![Diagram of the Microsoft 365 Zero Trust deployment stack with the specific steps for SaaS app integration and protection highlighted.](media/zero-trust-m365-saas-steps.svg)](media/zero-trust-m365-saas-steps.svg#lightbox)

| Step | Description |
| --- | --- |
| 1. [Add SaaS apps to Microsoft Entra ID](add-saas-apps) | Add applications to Microsoft Entra ID so that authorized users can securely access it. Many types of applications can be registered with Microsoft Entra ID. |
| 2. [Create Microsoft Defender for Cloud Apps policies](create-policies) | Ensure that policies are in place so that only authorized users and specific conditions are met before users are able to access resources. |
| 3. [Deploy information protection for SaaS apps](deploy-information-protection-saas) | Ensure that the proprietary and sensitive business data for your SaaS apps is protected. |

For guidance on licensing, see [Microsoft 365 guidance for security & compliance](/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

For more information about applying Zero Trust protections across Microsoft 365, see the [Microsoft 365 Zero Trust deployment plan](/en-us/microsoft-365/security/microsoft-365-zero-trust).