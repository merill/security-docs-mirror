---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Data | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-data
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about the Data pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-05-31T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 60dba2d8-5492-91e5-fbee-c592437df8b2
---

# Microsoft Zero Trust Workshop - Data | Microsoft Learn

In a Zero Trust framework, data is a critical security boundary. Protecting infrastructure or identities alone isn't sufficient—organizations must understand what data they have, where it resides, how sensitive it is, and how it's accessed and used. The Data pillar focuses on discovering, classifying, protecting, and governing data to reduce risk, enforce least privilege, and monitor for inappropriate use.

Data pillar workshop guidance focuses on understanding the data estate, defining classification and protection policies, enforcing controls on data usage and sharing, and monitoring for data risks across users, endpoints, and applications.

## Workshop implementation

The Data workshop covers the implementation areas summarized in the table.

| **Area** | **Details** |
| --- | --- |
| **Discover and classify sensitive data** | Identify and inventory sensitive data across locations such as Microsoft 365, endpoints, and other connected data sources.Use built-in and trainable classifiers (including exact data match and fingerprinting) to detect sensitive information based on content and patterns. |
| **Define and standardize a data classification taxonomy** | Establish a sensitivity labeling taxonomy (for example, internal, confidential, and highly confidential) aligned with business requirements. Ensure labeling definitions are clear, enforceable, and consistently applied across workloads. |
| **Gain visibility into data usage and activity** | Understand how data is accessed, used, and shared across the organization. Use activity monitoring and data exploration tools to assess current behaviors and identify risks before enforcing policies. |
| **Apply labels and enforce data protection policies** | Implement sensitivity labels (manual and automatic) to protect data through encryption, access restrictions, and usage controls. Apply protection consistently across data at rest, in motion, and in use. |
| -**Enforce data access and usage controls** | Apply policy-based controls that govern how protected data can be accessed and used based on identity, device, location, and session context. Use conditional access for apps, session controls, and app-based protections to enforce Zero Trust access decisions for data. |
| **Monitor and control data sharing and collaboration** | Track and control external and internal sharing of sensitive data. Implement policies to govern collaboration with partners and external users, and enforce restrictions on risky sharing behaviors across services such as SharePoint, OneDrive, and Teams. |
| **Protect data across endpoints and devices** | Extend data protection policies to endpoints by integrating labeling and DLP with device and application controls. Ensure sensitive data remains protected when accessed, copied, or moved across managed and unmanaged devices. |
| **Manage insider risk and sensitive data exposure** | Detect and respond to risky user activities involving data, such as exfiltration, misuse, or unusual access patterns. Correlate signals across data, identity, and endpoints, and apply enhanced protections to high-value data assets. |
| **Manage data governance and administrative control** | Apply role-based access control (RBAC) and administrative segmentation for data protection, labeling, and compliance roles. Ensure separation of duties so that only authorized personnel can define, manage, and operate data security policies. |
| **Integrate data signals into security operations (SecOps)** | Use data-related alerts, DLP events, and insider risk signals as part of broader security monitoring and incident response. Correlate data activity with identity and device signals to detect, investigate, and respond to threats. |

## Assess data posture

The Zero Trust Assessment tool can assess your data configuration against a range of security best practices. [Learn more](/en-us/security/zero-trust/assessment/overview).