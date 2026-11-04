---
layout: Conceptual
title: Authorization best practices | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/developer-strategy-authorization-best-practices
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: As a developer, implement the best authorization, permission, and consent models for your applications.
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.collection:
- zerotrust-dev
ms.custom:
- template-concept
- sfi-image-nochange
locale: en-us
document_id: 5df82518-d16b-87ca-0b31-22b5a4c190c4
document_version_independent_id: 5df82518-d16b-87ca-0b31-22b5a4c190c4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/developer-strategy-authorization-best-practices.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/developer-strategy-authorization-best-practices
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/developer-strategy-authorization-best-practices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: d59a0ec0-3aa6-2a3b-318a-ce2d0e54f197
---

# Authorization best practices | Microsoft Learn

As you learn to [develop using Zero Trust principles](overview), this article continues from [Acquire authorization to access resources](acquire-application-authorization-to-access-resources), [Develop delegated permissions strategy](developer-strategy-delegated-permission), and [Develop application permissions strategy](developer-strategy-application-permissions). It helps you, as a developer, to implement the best authorization, permission, and consent models for your applications.

You can [implement authorization](/en-us/entra/identity-platform/authorization-basics#implementing-authorization) logic within applications or solutions that require access control. When authorization approaches rely on information about an authenticated entity, an application can evaluate information that is exchanged during authentication (for example, information provided within a [security token](/en-us/entra/identity-platform/security-tokens)). When a security token doesn't contain information, an application can make calls to external resources.

You don't have to embed authorization logic entirely within your application. You can use dedicated authorization services to centralize authorization implementation and management.

## Best practices for permissions

The most widely adopted applications in Microsoft Entra ID follow consent and authorization best practices. Review [Best practices for working with Microsoft Graph](/en-us/graph/best-practices-concept) and [Microsoft Graph permissions reference](/en-us/graph/permissions-reference) to learn how to be thoughtful with your permission requests.

- **Apply [least privilege](/en-us/entra/identity-platform/secure-least-privileged-access).** Only request necessary permissions. Use incremental consent to request granular permissions just in time. Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection.
- **Use the correct [permission type](/en-us/entra/identity-platform/permissions-consent-overview) based on scenarios**. Avoid using both application and delegated permissions in the same app. If you build an interactive application where a signed-in user is present, use *delegated permissions*. If, however, your application runs [without a signed-in user](identity-non-user-applications), such as a background service or daemon, use *application permissions*.
- **Provide [terms of service and privacy statements](/en-us/entra/identity-platform/howto-add-terms-of-service-privacy-statement).** The user consent experience surfaces your terms of service and privacy statement to users to help them know that they can trust your app. They're especially critical for user-facing multitenant apps.

## When to request permission

Some permissions require an administrator to grant consent within a tenant. They can use the admin consent endpoint to grant permissions to an entire tenant. To request permissions or scopes, you can follow these models.

- **Implement dynamic user consent at sign-in or first access token request.** Dynamic user consent doesn't require anything in your app registration. You can define the scopes that you need under certain conditions (for example, when you sign in a user for the first time). After you request that permission and receive consent, you won't need to request permission. However, if you don't receive dynamic user consent at sign-in or first access, then it goes through the permission experience.
- **Request incremental user consent as needed.** With incremental consent combined with dynamic user consent, you don't have to request all of the permissions at any one time. You can request a few permissions. As the user moves to different functionality in your application, you request more consent. This approach can increase the user's comfort level as they incrementally grant permissions to your application. For example, if your application requests OneDrive access, it might arouse suspicion if you also request Calendar access. Instead, later ask the user to add Calendar reminders against their OneDrive.
- **Use the `/.default` scope.** The `/.default` scope effectively mimics the old default experience that looked at what you put in the application registration, figured out what consents you needed, and then asked for all of the consents not yet granted. It doesn't require you to include the permissions that you need in your code because they're in your app registration.

## Become a Verified Publisher

Microsoft customers sometimes describe difficulty in deciding when to allow an application to access the Microsoft identity platform by signing in a user or calling an API. While adopting [Zero Trust principles](../zero-trust-overview), they want:

- Increased visibility and control.
- More proactive and easier reactive decisions.
- Systems that keep data safe and reduce the decision burden.
- Accelerated app adoption for trustworthy developers.
- Restricted consent to apps with low-risk permissions that are publisher verified.

While access to data in APIs like Microsoft Graph allows you to build rich applications, your organization or your customer evaluates the permissions that your app requests along with your app's trustworthiness.

Becoming a [Microsoft Verified Publisher](/en-us/entra/identity-platform/publisher-verification-overview) helps you to give your customers an easier experience in accepting your application requests. When an application comes from a verified publisher, users, IT Pros, and customers know that it comes from someone with whom Microsoft has a business relationship. A blue checkmark appears next to the publisher's name (component #5 in the following **Permissions requested** consent prompt example. Reference the component table at [Microsoft Entra application consent experience](/en-us/entra/identity-platform/application-consent-experience#building-blocks-of-the-consent-prompt)). The user can select the verified publisher from the consent prompt to view more information.

[!\[Screenshot of Permissions requested dialog shows component building blocks as described in linked Microsoft Entra application consent experience article.\](../media/develop/developer-strategy-authorization-best-practices/screenshot-application-permissions-requested-consent-prompt-inline.png)
 "Screenshot of the consent experience Permissions requested dialog."](../media/develop/developer-strategy-authorization-best-practices/screenshot-application-permissions-requested-consent-prompt-expanded.png#lightbox)

When you're a verified publisher, users and IT pros gain trust in your application because you're a verified entity. Publisher verification provides improved branding for your application, and increased transparency, reduced risk, and smoother enterprise adoption for your customers.