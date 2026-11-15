---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Data | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-data
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the Data pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 57fa04b7-7bdf-d1cb-5bd1-bbc0b90a51f2
document_version_independent_id: 57fa04b7-7bdf-d1cb-5bd1-bbc0b90a51f2
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-data.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-data
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-data.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/64b65f6c-101f-411a-9b83-9f577fab52d0
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/1a667fd1-8145-4b11-af0f-9f5de205a6e5
platformId: 60dba2d8-5492-91e5-fbee-c592437df8b2
---

# Microsoft Zero Trust Workshop - Data | Microsoft Learn

Data is the asset that attackers ultimately target, so in a Zero Trust model protection must travel with the data itself. Every access decision should account for what the data is, how sensitive it is, where it resides, and who or what is requesting it.

The Data workshop pillar helps organizations assess their current data security posture, identify gaps, and create a prioritized implementation roadmap for discovering, classifying, protecting, and governing data across Microsoft 365, endpoints, and other connected data sources.

The Data workshop pillar corresponds to the Data technology defined in the [Microsoft Security Adoption Framework (SAF)](deploy/overview).

## Why focus on data?

Protecting infrastructure or identities alone isn't sufficient. Strong data security controls reduce the risk of oversharing, data loss, insider misuse, and regulatory exposure. The Data Workshop applies the Zero Trust principles of verify explicitly, use least privilege, and assume breach to structured and unstructured data wherever it is stored, shared, or used.

The expected output is an actionable backlog of data security projects prioritized into First, Then, and Next based on business and regulatory risk, data sensitivity, dependencies, implementation effort, user impact, and readiness.

## Data implementation areas

| **Area** | **Details** |
| --- | --- |
| **Discover and inventory sensitive data** | Identify and inventory sensitive data across Microsoft 365, endpoints, and other connected data sources. Use built-in sensitive information types, trainable classifiers, exact data match, and document fingerprinting to detect sensitive content based on its content and patterns. |
| **Define data governance and regulatory requirements** | Identify the legal, regulatory, contractual, and industry obligations that apply to your data. Use these requirements to inform classification, protection, retention, and monitoring decisions, and assign clear ownership for data governance. |
| **Define a data classification taxonomy** | Establish a sensitivity label taxonomy, such as General, Confidential, and Highly Confidential, aligned with business and regulatory requirements. Reuse an existing or default taxonomy where appropriate, and ensure label definitions are clear, enforceable, and consistently applied across workloads. |
| **Classify and label sensitive data** | Apply sensitivity labels through a combination of manual labeling, label recommendations, and automatic labeling. Identify scenarios suited to automatic classification, and phase in enforcement as classification accuracy and user readiness improve. |
| **Gain visibility into data usage and activity** | Understand how data is accessed, used, and shared across the organization. Use activity monitoring and data exploration tools to assess current behaviors and identify risks before enforcing policies. |
| **Identify and protect critical data assets** | Identify the organization's most critical and highly sensitive data assets, and plan protections proportionate to their value and risk. Apply encryption, access restrictions, and usage controls, and evaluate special cryptographic requirements such as Bring Your Own Key (BYOK) and Double Key Encryption (DKE) where required. |
| **Prevent data loss** | Deploy data loss prevention (DLP) policies across Microsoft 365 services, endpoints, and other supported locations, using simulation mode before enforcement where appropriate. Establish processes to triage, investigate, and tune DLP alerts and incidents on an ongoing basis. |
| **Govern data sharing and collaboration** | Document approved cross-boundary sharing scenarios, including sharing with external partners and customers. Monitor and restrict risky internal and external sharing across services such as SharePoint, OneDrive, and Teams, and review sharing activity on an ongoing basis. |
| **Enforce data access and permission controls** | Implement a SharePoint permission strategy that reduces oversharing and applies least privilege to sites and content. Use Conditional Access, session controls, app protection policies, and minimum standards for trusted devices and accounts to govern how protected data can be accessed and used. |
| **Protect data on endpoints and devices** | Extend sensitivity labeling and DLP to endpoints, and integrate them with device and application controls. Ensure sensitive data remains protected when it is accessed, copied, or moved across managed and unmanaged devices. |
| **Manage insider risk** | Implement insider risk management policies to detect and respond to risky activities involving data, such as exfiltration, misuse, or unusual access patterns. Correlate signals across data, identity, and endpoints, and apply stronger protections to users and data that present elevated risk. |
| **Secure data security administration** | Apply role-based access control (RBAC) and privileged access management for DLP, information protection, and insider risk administrators. Segment administration using administrative units, and maintain separation of duties so that only authorized personnel can define, manage, and operate data security policies. |
| **Integrate data signals into security operations** | Use DLP alerts, insider risk signals, and data-related activity as part of broader security monitoring, SIEM workflows, and incident response. Correlate data activity with identity and device signals to detect, investigate, and respond to threats. |

These areas summarize the Data workshop pillar. Use the detailed Data project guidance to review individual projects and implementation considerations.

## How to use the Data Workshop

Use the web-based Workshop with information protection, compliance, security, collaboration platform, endpoint, legal, and security operations stakeholders. For each relevant project:

- Review the project objective and applicability to your environment.
- Record the current status, notes, decisions, owners, and known dependencies.
- Consider licensing, implementation effort, user impact, technical prerequisites, and cross-pillar dependencies.
- Prioritize the project into First, Then, or Next and incorporate it into the implementation roadmap.

[Open the Zero Trust Workshop](https://aka.ms/ztworkshop) and select the Data pillar.

[Review the detailed Data project guidance](https://microsoft.github.io/zerotrustassessment/docs/category/data) for project-level information.

## Assess your data posture

The Microsoft Zero Trust Assessment can provide programmatically generated findings for supported data security configuration in your tenant. Assessment results can help identify technical gaps and inform Workshop discussions, but the Assessment is complementary and is not required to conduct the Data Workshop. It does not evaluate every Data Workshop project.

[Learn about the Zero Trust Assessment](/en-us/security/zero-trust/assessment/overview) or [get started with an assessment](/en-us/security/zero-trust/assessment/get-started).

## Who should participate?

- Information protection, data governance, and compliance teams.
- Security architecture, security operations, insider risk, and incident response teams.
- Microsoft 365 collaboration, messaging, endpoint, identity, and cloud platform teams.
- Legal, privacy, risk, HR, data owners, and business stakeholders.