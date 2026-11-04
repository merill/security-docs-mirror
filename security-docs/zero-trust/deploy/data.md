---
layout: Conceptual
title: Secure data with Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/deploy/data
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: cabailey
author: cabailey
description: Protecting data is one of the primary responsibilities of security and compliance teams. To ensure protection and that data access is restricted to authorized users, data should be inventoried, classified, labeled, and, where appropriate, encrypted.
ms.date: 2024-04-30T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: best-practice
ms.collection:
- zerotrust-pillar
locale: en-us
document_id: 79343709-0480-e6d0-bf6f-71d36cd24eb3
document_version_independent_id: 05216694-6a9c-6971-419f-ec134a954e58
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/deploy/data.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/deploy/data
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/deploy/data.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fd261790-6583-8473-f5a8-78d81bbf0112
---

# Secure data with Zero Trust | Microsoft Learn

![](../media/icon-data-medium.png)

**Background**

Zero Trust is a security strategy used to design security principles for your organization. Zero Trust helps secure corporate resources by implementing the following security principles:

- **Verify explicitly**. Always authenticate and authorize based on all available data points, including user identity, location, device health, service or workload, data classification, and anomalies.
- **Use least privilege access**. Limit user access with just-in-time (JIT) and just-enough-access (JEA), risk-based adaptive policies, and data protection to help secure both data and productivity.
- **Assume breach**. Minimize the blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses.

Microsoft Purview proposes five core elements for a data defense in depth strategy and a Zero Trust implementation for data:

1. Data classification and labeling If you don't know what sensitive data you have on-premises and in cloud services, you can't adequately protect it. Discover and detect data across your entire organization and classify it by sensitivity level.
2. Information Protection Conditional and least privilege access to sensitive data reduce data security risks. Apply sensitivity-based access control guardrails, rights management and encryption where environmental controls are insufficient. Use information sensitivity markings to increase awareness and security policy compliance.
3. Data Loss Prevention Access control resolves only part of the problem. Checking and controlling risky data activities and movements which might result in a data security or compliance incident allows organizations to prevent oversharing of sensitive data.
4. Insider Risk Management Data access might not always provide the whole story. Minimize risks to data by enabling behavioral detection from a broad array of signals, and acting on potentially malicious and inadvertent activities in your organization that could be precursors to or an indication of a data breach.
5. Data Governance Proactively managing the lifecycle of sensitive data reduces its exposure. Limit the number of copies or propagation of sensitive data and delete data that is no longer needed to minimize data breach risks.

## Data Zero Trust deployment objectives

| We recommend you focus on these initial deployment objectives when implementing an end-to-end Zero Trust framework for data: |
| --- |
| ![List icon with one checkmark.](../media/icon-initial-deployment-small.png) | **I.**Classify and label data.Automatically classify and label data where possible. Apply manually where it isn't.<br><br>**II.**Apply encryption, access control, and content markings. Apply encryption where protection and access control are insufficient.<br><br>**III.**Control access to data.Control access to sensitive data so they're better protected. Ensure that access and usage policy decisions are inclusive of data sensitivity. |
| As you make progress achieving the above objectives, add these additional deployment objectives: |
| ![List icon with two checkmarks.](../media/icon-additional-deployment-small.png) | **IV.**Prevent data leakage.Use DLP policies that are driven by risky signals and data sensitivity.<br><br>**V.**Manage risks. Manage risks that might lead to a data security incident by checking risky security related user activities and data activity patterns that might result in a data security or compliance incident.<br><br>**VI.**Reduce data exposure. Reduce data exposure through data governance and continual data minimization |

## Zero Trust deployment guide for data

This guide will walk you step-by-step through a Zero Trust approach to data protection. Please keep in mind that these items will vary widely depending on the sensitivity of your information and the size and complexity of your organization.

As a precursor to any data security implementation, Microsoft recommends that you create a data classification framework and sensitivity label taxonomy that defines high level categories of data security risk. That taxonomy will be used to simplify everything from data inventory or activity insights, to policy management to investigation prioritization.

For more information, see:

- [Create a well-designed data classification framework](/en-us/compliance/assurance/assurance-create-data-classification-framework)

| ![Checklist icon with one checkmark.](../media/icon-initial-deployment.png) | Initial deployment objectives |
| --- | --- |

### I. Classify, label and discover sensitive data

An information protection strategy needs to encompass your organization's entire digital content.

Classifications and sensitivity labels let you understand where your sensitive data is located, how it moves, and implement appropriate access and usage controls consistent with zero trust principles:

- Use automated classification and labeling to detect sensitive information and scale discovery across your data estate.
- Use manual labeling for documents and containers, and manually curate data sets used in analytics where classification and sensitivity are best established by knowledgeable users.

Follow these steps:

- [Learn about sensitive information types](/en-us/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Learn about trainable classifiers](/en-us/microsoft-365/compliance/classifier-learn-about)
- [Learn about sensitivity labels](/en-us/microsoft-365/compliance/sensitivity-labels)

Once you have configured and tested classification and labeling, scale up data discovery across your data estate.

Follow these steps to extend discovery beyond Microsoft 365 services:

- [Get started with the Microsoft Purview on-premises scanner](/en-us/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Discover and protect sensitive information in SaaS applications](/en-us/defender-cloud-apps/tutorial-dlp)
- [Learn about scans and ingestion in the Microsoft Purview governance portal](/en-us/azure/purview/concept-scans-and-ingestion#scanning)

As you discover, classify and label your data, use those insights to remediate risk and inform your policy management initiatives.

Follow these steps:

- [Get started with Content Explorer](/en-us/microsoft-365/compliance/data-classification-content-explorer)
- [Review labeling activity with Activity Explorer](/en-us/microsoft-365/compliance/data-classification-activity-explorer)
- [Learn about Data Insights](/en-us/azure/purview/concept-insights)

### II. Apply encryption, access control and content markings

Simplify your least privilege implementation by using sensitivity labels to protect your most sensitive data with encryption and access control. Use content markings to enhance user awareness and traceability.

#### Protect document and emails

Microsoft Purview Information Protection enables access and usage control based on sensitivity labels or user defined permissions for documents and emails. It can also optionally apply markings and encrypt information that resides in or flows out to lesser trust environments internal or external to your organization. It provides protection at rest, in motion, and in use for enlightened applications.

Follow these steps:

- [Review encryption options in Microsoft 365](/en-us/microsoft-365/compliance/encryption)
- [Restrict access to content and usage by using sensitivity labels](/en-us/microsoft-365/compliance/encryption-sensitivity-labels)

#### Protect documents in Exchange, SharePoint, and OneDrive

For data stored in Exchange, SharePoint, and OneDrive, automatic classification with sensitivity labels can be deployed via policies to targeted locations to restrict access and manage encryption on authorized egress.

Take this step:

- [Configure auto-labeling policies for SharePoint, OneDrive and Exchange](/en-us/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

### III. Control access to data

Providing access to sensitive data must be controlled so that they're better protected. Ensure that access and usage policy decisions are inclusive of data sensitivity.

#### Control data access and sharing in Teams, Microsoft 365 Groups and SharePoint sites

Use container sensitivity labels to implement conditional access and sharing restrictions to Microsoft Teams, Microsoft 365 Groups or SharePoint sites.

Take this step:

- [Use sensitivity labels with Microsoft Teams, Microsoft 365 Groups, and SharePoint sites](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#how-to-configure-groups-and-site-settings)

#### Control access to data in SaaS applications

Microsoft Defender for Cloud Apps provides additional capabilities for conditional access and to manage sensitive files in Microsoft 365 and third-party environments such as Box or Google Workspace, including:

- Removing permissions to address excessive privilege and prevent data leakage.
- Quarantining files for review.
- Applying labels to sensitive files.

Follow these steps:

- [Integrate Microsoft Purview Information Protection](/en-us/defender-cloud-apps/azip-integration)

Tip

Check out [Integrate SaaS apps for Zero Trust with Microsoft 365](/en-us/security/zero-trust/integrate-saas-apps) to learn how to apply Zero Trust principles to help manage your digital estate of cloud apps.

#### Control access to in IaaS/PaaS storage

Deploy mandatory access control policies to IaaS/PaaS resources that contain sensitive data.

Take this step:

- [Learn about Microsoft Purview DevOps policies](/en-us/azure/purview/concept-policies-devops)

### IV. Prevent data leakage

Controlling access to data is necessary but insufficient in exerting control over data movement and in preventing inadvertent or unauthorized data leakage or loss. That is the role of data loss prevention and insider risk management, which is described in section IV.

Use Microsoft Purview DLP policies to identify, check, and automatically protect sensitive data across:

- Microsoft 365 services such as Teams, Exchange, SharePoint, and OneDrive
- Office applications such as Word, Excel, and PowerPoint
- Windows 10, Windows 11 and macOS (three latest released versions) endpoints
- on-premises file shares and on-premises SharePoint
- non-Microsoft cloud apps.

Follow these steps:

- [Plan for data loss prevention](/en-us/microsoft-365/compliance/dlp-overview-plan-for-dlp)
- [Create, test, and tune DLP policies](/en-us/microsoft-365/compliance/dlp-create-deploy-policy)
- [Learn about the data loss prevention Alerts dashboard](/en-us/microsoft-365/compliance/dlp-alerts-dashboard-learn)
- [Review data activity with Activity Explorer](/en-us/microsoft-365/compliance/data-classification-activity-explorer)

### V. Manage insider risks

Least privilege implementations help minimize known risks, but it's also important to correlate additional security related user behavioral signals, check sensitive data access patterns, and to broad detection, investigation and hunting capabilities.

Take these steps:

- [Learn about Insider Risk Management](/en-us/microsoft-365/compliance/insider-risk-management-solution-overview)
- [Investigate insider risk management activities](/en-us/microsoft-365/compliance/insider-risk-management-activities)

### VI. Delete unnecessary sensitive information

Organizations can reduce their data exposure by managing the lifecycle of their sensitive data.

Remove all privileges where you're able, by deleting the sensitive data itself when it's no longer valuable or permissible for your organization.

Take this step:

- [Deploy data lifecycle management and records management](/en-us/purview/data-governance-solution)

Minimize duplication of sensitive data by favoring in-place sharing and use rather than data transfers.

Take this step:

- [Learn about in-place data sharing with Microsoft Purview](/en-us/azure/purview/concept-data-share)

## Products covered in this guide

[Microsoft Purview](/en-us/purview/purview)

[Microsoft Defender for Cloud Apps](/en-us/defender-cloud-apps/what-is-defender-for-cloud-apps)

For further information or help with implementation, please contact your Customer Success team.

**The Zero Trust deployment guide series**

[![Icon for the introduction](../media/icon-introduction-navbar.png)](https://aka.ms/ZTDeploymentGuideIntroduction)

[![Icon for identity](../media/icon-identity-navbar.png)](https://aka.ms/ZTIdentity)

[![Icon for endpoints](../media/icon-endpoints-navbar.png)](https://aka.ms/ZTDevices)

[![Icon for applications](../media/icon-applications-navbar.png)](https://aka.ms/ZTApplications)

[![Icon for data](../media/icon-data-navbar.png)](https://aka.ms/ZTData)

[![Icon for infrastructure](../media/icon-infrastructure-navbar.png)](https://aka.ms/ZTInfrastructure)

[![Icon for networks](../media/icon-networks-navbar.png)](https://aka.ms/ZTNetwork)

[![Icon for visibility, automation, orchestration](../media/icon-visibility-automation-orchestration-navbar.png)](https://aka.ms/ZTCrossPillars)