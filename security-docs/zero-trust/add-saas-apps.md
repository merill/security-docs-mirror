---
layout: Conceptual
title: Add SaaS apps to Microsoft Entra ID and to the scope of policies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/add-saas-apps
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: macapara
author: mjcaparas
description: Learn steps to add SaaS apps to Microsoft Entra ID and to the scope of identity and device policies.
ms.date: 2024-04-18T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- m365solution-saas
- m365solution-scenario
- m365solution-zero-trust
- zerotrust-solution
- highpri
locale: en-us
document_id: 1a933d7f-5dcb-42c5-f8fd-3d20c790dec3
document_version_independent_id: 1a933d7f-5dcb-42c5-f8fd-3d20c790dec3
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/add-saas-apps.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/add-saas-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/add-saas-apps.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: fb59aad6-a87e-93ba-0777-2088ef6d532d
---

# Add SaaS apps to Microsoft Entra ID and to the scope of policies | Microsoft Learn

Microsoft Entra ID is Microsoft's cloud-based identity and access management service. Microsoft Entra ID provides secure authentication and authorization solutions so that customers, partners, and employees can access the applications they need. Microsoft Entra ID, [Conditional Access](/en-us/azure/active-directory/conditional-access/overview), [multifactor authentication](/en-us/azure/active-directory/authentication/concept-mfa-howitworks), [single-sign on (SSO)](/en-us/azure/active-directory/hybrid/how-to-connect-sso), and [automatic user provisioning](/en-us/azure/active-directory/app-provisioning/user-provisioning) make identity and access management easy and secure.

Integrate your SaaS apps into Microsoft Entra ID so that you can monitor and configure access for them. Microsoft Entra ID has an application gallery, which is a collection of SaaS apps that have been preintegrated with Microsoft Entra ID. You can also add your own custom apps. For more information, see [Five steps for integrating all your apps with Microsoft Entra ID](/en-us/entra/fundamentals/five-steps-to-full-application-integration).

After adding apps to Microsoft Entra ID, you can configure how apps are accessed and subject to specific conditions by including them in the scope of your [Zero Trust identity and device access policies](/en-us/microsoft-365/security/office-365-security/zero-trust-identity-device-access-policies-overview).

If you already have Microsoft Defender for Cloud Apps deployed, you can discover SaaS apps that are being used in your organization. For more information, see [Step 2 of this solution](create-policies) and [Discover and manage shadow IT in your network](/en-us/defender-cloud-apps/tutorial-shadow-it).

## Adding apps in Microsoft Entra ID

Adding apps in Microsoft Entra ID helps you leverage the services it provides including:

- Application authentication and authorization.
- User authentication and authorization.
- SSO using federation or passwords.
- User provisioning and synchronization.
- Role-based access control that uses Microsoft Entra to define application roles and perform role-based authorization checks in an application.
- OAuth authorization services, which are used by Microsoft 365 and other Microsoft applications to authorize access to APIs and resources.
- Application publishing and proxy to publish an application from your private network to the internet.
- Directory schema extension attributes to store additional data in Microsoft Entra ID.

There are several ways you can add apps in Microsoft Entra ID. The easiest way to start managing apps is to use the application gallery. You also have the option of adding custom apps. This section guides you through both ways.

### Add apps from the application gallery

Microsoft Entra ID has an application gallery that contains a collection of SaaS apps that have been preintegrated with Microsoft Entra ID. Just sign into the Microsoft Entra admin center and choose the applications from specific cloud platforms, featured applications, or search for the application that you want to use.

For more information, see [Add an enterprise application](/en-us/azure/active-directory/manage-apps/add-application-portal#add-an-enterprise-application) and [Overview of the Microsoft Entra application gallery](/en-us/azure/active-directory/manage-apps/overview-application-gallery).

### Adding custom apps in Microsoft Entra app gallery

You can develop your own custom cloud apps and register them in Microsoft Entra ID. Registering them with Microsoft Entra ID lets you leverage the security features provided by your Microsoft 365 tenant. In the Microsoft Entra admin center, you can register your application in **App Registrations**, or you can register it using the **Create your own application** link when adding a new application in **Enterprise applications**.

For more information, see [What is application management in Microsoft Entra ID?](/en-us/entra/identity/enterprise-apps/what-is-application-management) and [Request to publish your application in the Microsoft Entra application gallery](/en-us/azure/active-directory/manage-apps/v2-howto-app-gallery-listing).

## Add apps to the scope of your Zero Trust identity and device access policies

Conditional Access policies allow you to assign controls to specific applications, actions, or authentication context. You can define conditions such as what device type can access a resource, user risk levels, trusted locations, and other conditions such as strong authentication. For example, multifactor authentication (MFA) helps safeguard access to data and applications with additional security by requiring a second form of verification.

After adding apps in Microsoft Entra ID, you'll need to add them to the scope of your Zero Trust identity and device access policies.

### Updating common policies

The following diagram shows the Zero Trust identity and device access policies for SaaS and PaaS apps, highlighting the set of common Conditional Access policies whose scopes must be modified to include your SaaS apps.

[![Diagram of the Zero Trust identity and device access policies for SaaS apps with highlighted policies whose scopes must be modified.](media/zero-trust-identity-device-access-policies-saas-apps.svg)](media/zero-trust-identity-device-access-policies-saas-apps.svg#lightbox)

For each policy to update, make sure that your apps and their dependent services are included in the assignment of cloud apps.

This table lists the policies that need to be reviewed with links to each policy in the set of [common identity and device access policies](/en-us/microsoft-365/security/office-365-security/microsoft-365-policies-configurations).

| Protection level | Policies | Description |
| --- | --- | --- |
| **Starting point** | [Require MFA when sign-in risk is *medium* or *high*](/en-us/microsoft-365/security/office-365-security/identity-access-policies#require-mfa-based-on-sign-in-risk) | Ensure that your cloud apps and dependent services are included in the list of apps. |
|  | [Block clients that don't support modern authentication](/en-us/microsoft-365/security/office-365-security/identity-access-policies#block-clients-that-dont-support-multi-factor) | Include your apps and dependent services in the assignment of cloud apps. |
|  | [High risk users must change password](/en-us/microsoft-365/security/office-365-security/identity-access-policies#high-risk-users-must-change-password) | Forces app users to change their password when signing in if high-risk activity is detected for their account. |
|  | [Apply APP data protection policies](/en-us/microsoft-365/security/office-365-security/identity-access-policies#apply-app-data-protection-policies) | Ensure that your cloud apps and dependent services are included in the list of apps. Update the policy for each platform (iOS, Android, Windows). |
| **Enterprise** | [Require MFA when sign-in risk is *low*, *medium*, or *high*](/en-us/microsoft-365/security/office-365-security/identity-access-policies#require-mfa-based-on-sign-in-risk) | Ensure that your cloud apps and dependent services are included in the list of apps. |
|  | [Require compliant PCs *and* mobile devices](/en-us/microsoft-365/security/office-365-security/identity-access-policies#require-compliant-pcs-and-mobile-devices) | Ensure that your cloud apps and dependent services are included in the list of apps. |
| **Specialized security** | [*Always* require MFA](/en-us/microsoft-365/security/office-365-security/identity-access-policies#require-mfa-based-on-sign-in-risk) | Regardless of user identity, your organization uses MFA. |

For more information, see [Recommended Microsoft Defender for Cloud Apps policies for SaaS apps](/en-us/microsoft-365/security/office-365-security/mcas-saas-access-policies).