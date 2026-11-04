---
layout: Conceptual
title: Developer and administrator responsibilities | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/identity-developer-administrator-responsibilities
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn what IT Pros need from developers and what developers need from them to streamline Zero Trust development workflows.
ms.subservice: zero-trust
ms.topic: best-practice
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 9e88ab37-6ef7-0176-384a-e431e1a9b8fe
document_version_independent_id: 9e88ab37-6ef7-0176-384a-e431e1a9b8fe
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/identity-developer-administrator-responsibilities.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/identity-developer-administrator-responsibilities
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/identity-developer-administrator-responsibilities.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: f673f852-b650-bda1-9ce8-462f4445ada3
---

# Developer and administrator responsibilities | Microsoft Learn

When you create applications in the Microsoft identity platform, work with IT Professionals who have administrator privileges in Microsoft Entra ID to enable your applications to take full advantage of the Microsoft identity platform. Know what your IT Pros need from you and what you need from them to streamline your Zero Trust development workflow.

## Developers and IT Pros must work together

IT organizations increasingly block apps with vulnerabilities. As IT departments embrace a [Zero Trust approach](overview), developers who don't provide applications that follow Zero Trust principles risk not having their apps adopted. Following Zero Trust principles can help ensure that your application is eligible for adoption in a Zero Trust environment.

App developers usually implement, evaluate, and validate aspects of Zero Trust before working with an organization's IT Pros to achieve full compliance and adherence. Developers are responsible for building and integrating apps so that IT Pros can use their tools to further secure the applications. Partner with IT Pros so that you can:

- Minimize the probability of or prevent security compromise.
- Quickly respond to compromise and reduce damage.

The following table summarizes the decisions and tasks required for developer and IT Pro roles to build and deploy secure applications in the Microsoft identity platform. Read on for key details and links to articles to help you plan your secure application development.

**Developer**

- [Register app](/en-us/entra/identity-platform/quickstart-register-app) in Microsoft identity platform.
- Define [supported account types](identity-supported-account-types).
- Determine if app works on behalf of [itself](identity-non-user-applications) or user.
- Define [resources](acquire-application-authorization-to-access-resources) required and how/when to request permission.

**IT Pro Administrator**

- Configure who can register apps in tenant.
- Assign application users, groups, and roles.
- Grant permissions to applications.
- Define policies, including conditional access policy.

## Zero Trust considerations

When entities (individuals, applications, devices) need to access resources in your application, work with IT Pros and consider Zero Trust and security policy enforcement options. Together, decide which access policies to implement and enforce. Microsoft's policy enforcement engine needs to be in touch with threat intelligence, signal processing, and existing policies. Every time an entity needs to access a resource, it goes through the policy enforcement engine.

IT Pros can apply conditional access policies to Security Assertions Markup Language (SAML) apps at authentication. For OAuth 2.0 applications, they can apply policies when an application attempts to access a resource. IT Pros determine which conditional access policies apply to your application (SAML) or the resources that your application accesses (OAuth 2.0).