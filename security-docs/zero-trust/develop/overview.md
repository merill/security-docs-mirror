---
layout: Conceptual
title: Develop using Zero Trust principles | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: As a developer, learn how to implement the guiding principles of Zero Trust so that you can improve your application security.
ms.date: 2025-02-24T00:00:00.0000000Z
ms.subservice: zero-trust
ms.topic: best-practice
ms.service: security
ms.collection:
- zerotrust-dev
locale: en-us
document_id: cce249e3-4c0b-40eb-549c-9da9fd9ab8a0
document_version_independent_id: 6c167d1e-ad8e-35c3-f2e9-46143053212c
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 64714f1c-25c8-1b2c-7de4-e0ea5bbdf98c
---

# Develop using Zero Trust principles | Microsoft Learn

This article helps you, as a developer, to understand the guiding principles of Zero Trust so that you can improve your application security. You play a key role in organizational security. Applications and their developers can no longer assume that the network perimeter is secure. Compromised applications can affect the entire organization.

Organizations are deploying new security models that adapt to complex modern environments and embrace the mobile workforce. New models protect people, devices, applications, and data wherever they're located. Organizations are striving to achieve [Zero Trust](../zero-trust-overview), a security strategy and approach for designing and implementing applications that follow these guiding principles:

- Verify explicitly
- Use least privilege access
- Assume breach

Instead of believing everything behind the corporate firewall is safe, the Zero Trust model assumes breach and verifies each request as though it originated from an uncontrolled network. Regardless of where the request originates or what resource it accesses, the Zero Trust model requires us to *never trust, always verify*.

Understand that Zero Trust isn't a replacement for security fundamentals. With work originating from anywhere on any device, design your applications to incorporate Zero Trust principles throughout your development cycle.

## Why develop with a Zero Trust perspective?

- We see a rise in the level of sophistication of cybersecurity attacks.
- The *work from anywhere* workforce redefined the security perimeter. Data is being accessed outside the corporate network and shared with external collaborators such as partners and vendors.
- Corporate applications and data are moving from on-premises to hybrid and cloud environments. Traditional network controls can no longer be relied on for security. Controls need to move to where the data resides on devices and inside apps.

The development guidance in this section helps you to increase security, reduce the blast radius of a security incident, and swiftly recover with Microsoft technology.

## Developer guidance overview

- [What do we mean by Zero Trust compliance?](identity-zero-trust-compliance) provides an overview of application security from a developer's perspective to address the guiding principles of Zero Trust.
- Use [Zero Trust identity and access management development best practices](identity-iam-development-best-practices) in your application development lifecycle to create secure applications.
- [Standards-based development methodologies](identity-standards-based-development-methodologies) provides an overview of supported standards and their benefits.
- [Developer and administrator responsibilities for application registration, authorization, and access](identity-developer-administrator-responsibilities) helps you to better collaborate with your IT Pros.

## Permissions and access

- [Build apps that secure identity through permissions and consent](identity) provides an overview of permissions and access best practices.
- [Integrate applications with Microsoft Entra ID and the Microsoft identity platform](integrate-apps-microsoft-identity-platform) helps developers to build and integrate apps that IT pros can secure in the enterprise.
- [Register applications](app-registration) introduces developers to the application registration process and its requirements. It helps them to ensure that apps satisfy Zero Trust principles of use least privileged access and assume breach.
- [Supported identity and account types for single- and multitenant apps](identity-supported-account-types) explains how you can choose if your app allows only users from your Microsoft Entra tenant, any Microsoft Entra tenant, or users with personal Microsoft accounts.
- [Authenticate users for Zero Trust](user-authentication) helps developers to learn best practices for authenticating application users in Zero Trust application development. It describes how to enhance application security with the Zero Trust principles of least privilege and verify explicitly.
- [Acquire authorization to access resources](acquire-application-authorization-to-access-resources) helps you to understand how to best ensure Zero Trust when acquiring resource access permissions for your application.
- [Develop delegated permissions strategy](developer-strategy-delegated-permission) helps you to implement the best approach for managing permissions in your application and develop with Zero Trust principles.
- [Develop application permissions strategy](developer-strategy-application-permissions) helps you to decide upon your application permissions approach to credential management.
- [Request permissions that require administrative consent](permissions-require-admin-consent) describes the permission and consent experience when application permissions require administrative consent.
- [Reduce overprivileged permissions and apps](overprivileged-permissions) helps you to limit privilege to manage access and improve security.
- [Provide application identity credentials when there's no user](identity-non-user-applications) explains Managed Identities for Azure resources best practices for services (nonuser applications).
- [Manage tokens for Zero Trust](token-management) helps developers to build security into applications with ID tokens, access tokens, and security tokens that they can receive from the Microsoft identity platform.
- [Customize tokens](zero-trust-token-customization) describes the information that you can receive in Microsoft Entra tokens and how you can customize tokens.
- [Secure applications with Continuous Access Evaluation](secure-with-cae) helps developers to improve application security with Continuous Access Evaluation. Learn how to [ensure Zero Trust support](overview) in your apps that receive authorization to access resources when they acquire access tokens from Microsoft Entra ID.
- [Configure group claims and app roles in tokens](configure-tokens-group-claims-app-roles) shows you how to configure your apps with app role definitions and assign security groups.
- [API Protection](protect-api) describes best practices for protecting your API through registration, defining permissions and consent, and enforcing access to achieve your Zero Trust goals.
- [Example of API protected by Microsoft identity consent framework](protected-api-example) helps you to design least privilege application permissions strategies for the best user experience.
- [Call an API from another API](api-calls-api) helps you to ensure Zero Trust when you have one API that needs to call another API. You learn how to securely develop your application when it's working on behalf of a user.
- [Authorization best practices](developer-strategy-authorization-best-practices) helps you to implement the best authorization, permission, and consent models for your applications.

## Zero Trust DevSecOps

- [Secure DevOps environments for Zero Trust](secure-devops-environments-zero-trust) describes best practices for securing your DevOps environments.
- [Secure the DevOps platform environment](secure-devops-platform-environment-zero-trust) helps you to implement Zero Trust principles in your DevOps platform environment and highlights best practices for secret and certificate management.
- [Secure the developer environment](secure-dev-environment-zero-trust) helps you to implement Zero Trust principles in your development environments with best practices for least privilege, branch security, and trusting tools, extensions, and integrations.
- [Embed Zero Trust security into your developer workflow](embed-zero-trust-dev-workflow) helps you to innovate quickly and securely.

## More Zero Trust documentation

Reference the following Zero Trust content based on documentation set or roles in your organization.

### Documentation set

Follow this table for the best Zero Trust documentation sets for your needs.

| Documentation set | Helps you... | Roles |
| --- | --- | --- |
| [Adoption framework](../adopt/zero-trust-adoption-overview) for phase and step guidance for key business solutions and outcomes | Apply Zero Trust protections from the C-suite to the IT implementation. | Security architects, IT teams, and project managers |
| [Concepts and deployment objectives](../deploy/overview) for general deployment guidance for technology areas | Apply Zero Trust protections aligned with technology areas. | IT teams and security staff |
| [Zero Trust for small businesses](../guidance-smb-partner) | Apply Zero Trust principles to small business customers. | Customers and partners working with Microsoft 365 for business |
| [Zero Trust Rapid Modernization Plan (RaMP)](../zero-trust-ramp-overview) for project management guidance and checklists for easy wins | Quickly implement key layers of Zero Trust protection. | Security architects and IT implementers |
| [Zero Trust deployment plan with Microsoft 365](/en-us/microsoft-365/security/microsoft-365-zero-trust?bc=%2fsecurity%2fzero-trust%2fbreadcrumb%2ftoc.json&amp;toc=%2fsecurity%2fzero-trust%2ftoc.json) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to your Microsoft 365 tenant. | IT teams and security staff |
| [Zero Trust for Microsoft Copilots](../copilots/apply-zero-trust-copilots-overview) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to Microsoft Copilots. | IT teams and security staff |
| [Zero Trust for Azure services](../azure-infrastructure-overview) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to Azure workloads and services. | IT teams and security staff |
| [Partner integration with Zero Trust](../integrate/overview) for design guidance for technology areas and specializations | Apply Zero Trust protections to partner Microsoft cloud solutions. | Partner developers, IT teams, and security staff |

### Your role

Follow this table for the best documentation sets for your role in your organization.

| Role | Documentation set | Helps you... |
| --- | --- | --- |
| Security architect  IT project manager  IT implementer | [Adoption framework](../adopt/zero-trust-adoption-overview) for phase and step guidance for key business solutions and outcomes | Apply Zero Trust protections from the C-suite to the IT implementation. |
| Member of an IT or security team | [Concepts and deployment objectives](../deploy/overview) for general deployment guidance for technology areas | Apply Zero Trust protections aligned with technology areas. |
| Customer or partner for Microsoft 365 for business | [Zero Trust for small businesses](../guidance-smb-partner) | Apply Zero Trust principles to small business customers. |
| Security architect  IT implementer | [Zero Trust Rapid Modernization Plan (RaMP)](../zero-trust-ramp-overview) for project management guidance and checklists for easy wins | Quickly implement key layers of Zero Trust protection. |
| Member of an IT or security team for Microsoft 365 | [Zero Trust deployment plan with Microsoft 365](/en-us/microsoft-365/security/microsoft-365-zero-trust?bc=%2fsecurity%2fzero-trust%2fbreadcrumb%2ftoc.json&amp;toc=%2fsecurity%2fzero-trust%2ftoc.json) for stepped and detailed design and deployment guidance for Microsoft 365 | Apply Zero Trust protections to your Microsoft 365 tenant. |
| Member of an IT or security team for Microsoft Copilots | [Zero Trust for Microsoft Copilots](../copilots/apply-zero-trust-copilots-overview) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to Microsoft Copilots. |
| Member of an IT or security team for Azure services | [Zero Trust for Azure services](../azure-infrastructure-overview) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to Azure workloads and services. |
| Partner developer or member of an IT or security team | [Partner integration with Zero Trust](../integrate/overview) for design guidance for technology areas and specializations | Apply Zero Trust protections to partner Microsoft cloud solutions. |