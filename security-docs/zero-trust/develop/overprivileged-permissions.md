---
layout: Conceptual
title: Reduce overprivileged permissions and apps | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/overprivileged-permissions
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn why applications shouldn't request more permissions than they need (overprivileged) and how to limit privilege to manage access and improve security.
ms.subservice: zero-trust
ms.topic: best-practice
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: ebda1aa0-c246-6a85-83eb-dcc266ce94e4
document_version_independent_id: ebda1aa0-c246-6a85-83eb-dcc266ce94e4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/overprivileged-permissions.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/overprivileged-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/overprivileged-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
platformId: eaf5ba06-547a-600a-8fda-3e9a2f073011
---

# Reduce overprivileged permissions and apps | Microsoft Learn

As a developer aiming to design and implement applications that follow the [guiding principles of Zero Trust](overview), you want to [increase application security with least privilege](/en-us/entra/identity-platform/secure-least-privileged-access). It's imperative that you reduce the attack surface of your application and the effect of a security breach.

In this article, you learn why applications shouldn't request more permissions than they need. You learn the term *overprivilege*. You discover recommendations and best practices to limit privilege in your applications, manage access, and improve security.

## What is overprivilege?

[Overprivilege](/en-us/entra/identity-platform/secure-least-privileged-access#overprivileged-applications) occurs when an application requests or receives more permissions than it needs for it to properly function. Improve your understanding of overprivilege with examples of unused and reducible permissions in the remainder of this article.

## Unused permissions

For this unused key example, imagine that there are three locked doors (blue, yellow, and green) as shown in the following diagram.

[![Diagram shows three doors with corresponding keys to illustrate unused permissions.](../media/develop/overprivileged-permissions/diagram-unused-key-inline.png)](../media/develop/overprivileged-permissions/diagram-unused-key-expanded.png#lightbox)

Your assets are behind the doors. You have three keys (blue, yellow, and green) that allow you to open its corresponding door. For example, the blue key can open the blue door. When you only need access to the yellow door, you only carry the yellow key.

To best protect your assets, you only carry the keys you need when you need them and keep unused keys in a safe location.

## Reducible permissions

The reducible keys example is more complicated than the unused key example to which we now add two special keys as shown in the following diagram.

[![Diagram shows three doors with corresponding keys to illustrate reducible permissions.](../media/develop/overprivileged-permissions/diagram-reducible-key-inline.png)](../media/develop/overprivileged-permissions/diagram-reducible-key-expanded.png#lightbox)

The first black key is a pass key that can open all the doors. The second black key can open the yellow and the green doors. When you only need access to the yellow and the green doors, you only carry the second black key. You keep your pass key in a safe location with the redundant green key.

With the Microsoft identity platform, the keys are access permissions. Your resources and you, the key holder, are applications. If you understand the risk of carrying unnecessary keys, you're aware of the risk of your applications having unnecessary permissions.

## Permission gap and risk

How can doors and keys help to understand how overprivilege occurs? Why might your application have the right permissions to perform a task, but still be overprivileged? Let's look at the permission gap that might cause the discrepancy in the following diagram.

[![Diagram shows Permissions and Time for Granted Permissions and Permissions Used.](../media/develop/overprivileged-permissions/diagram-permission-gap-inline.png)](../media/develop/overprivileged-permissions/diagram-permission-gap-expanded.png#lightbox)

The X axis represents **Time** and the Y axis represents **Permissions**. At the start of the measured **Time**, you request and receive permission for your application. As the business grows and changes over time, you add new permissions to support your needs and the slope of **Granted Permissions** increases. The **Permissions Used** might be lower than **Granted Permissions** when you forget to remove unnecessary permissions (for example, if the application doesn't break) resulting in a **Permission Gap**.

Here are interesting observations in the Microsoft identity platform.

- We have more than 4,000 APIs in Microsoft Graph.
- More than 200 Microsoft Graph permissions are available on Microsoft identity platform.
- Developers have access to a wide range of data and can apply granularity to permissions that their apps request.
- In our investigations, we found that apps fully utilize only 10% of permissions for their scenarios.

Think carefully about permissions your app requires. Beware of the permission gap and regularly check your application permissions.

## Security compromised for overprivileged

Let's dive deeper into the risks that result from permission gaps with an example. This compromising scenario comprises two roles: IT admin and developer.

- IT admin: Jeff is a tenant admin who ensures that applications in Microsoft Entra ID are trustworthy and secure. Part of Jeff's job is to grant consent to permissions that app developers require.
- Developer: Kelly is an app developer who uses Microsoft identity platform and owns apps. Kelly's job is to ensure that applications have the right permissions to perform required tasks.

The following common overprivilege security compromise scenario typically has four stages.

[![Diagram shows four stages of a security compromise scenario.](../media/develop/overprivileged-permissions/diagram-permission-scenario-inline.png)](../media/develop/overprivileged-permissions/diagram-permission-scenario-expanded.png#lightbox)

1. The developer starts configuring the application and adding required permissions.
2. The IT admin reviews required permissions and grants consent.
3. The bad actor starts cracking user credentials and successfully hacks the user identity.
4. If the user owns multiple applications, they're also overprivileged. The bad actor can quickly use the token of the granted permission to retrieve sensitive data.

## Overprivileged applications

An entity is overprivileged when it asks for or receives more permissions than it needs. The definition of *overprivileged application* in Microsoft identity platform is *any application with unused or reducible permissions*.

Let's use Microsoft Graph as part of the Microsoft identity platform in a real-world example to better understand unused permission and reducible permission.

[![Diagram shows example of unused and reducible permissions.](../media/develop/overprivileged-permissions/diagram-overprivileged-types-inline.png)](../media/develop/overprivileged-permissions/diagram-overprivileged-types-expanded.png#lightbox)

Unused permission occurs when your application receives permissions that aren't necessary for the desired tasks. For example, you're building a calendar app. Your calendar app requests and receives `Files.ReadWrite.All` permission. Your app doesn't integrate with any files' APIs. Therefore, your application has an unused `Files.ReadWrite.All` permission.

Reducible permission is more difficult to discover. It occurs when your application receives few permissions but has a lower privileged alternative that would provide sufficient access for required tasks. In the calendar app example, your app requests and receives `Files.ReadWrite.All` permission. However, it only needs to read files from the signed-in user's OneDrive and never needs to create new files or modify existing ones. In this case, your application only partially utilizes `Files.ReadWrite.All` so you need to downgrade to `Files.Read.All`.

## Recommendations for reducing overprivileged scenarios

Security is a journey, not a destination. There are three distinct phases in the security lifecycle:

- Prevention
- Auditing
- Remediation

The following diagram illustrates recommendations for reducing overprivileged scenarios.

[![Diagram shows recommendations to prevent, audit, and remediate overprivileged scenarios.](../media/develop/overprivileged-permissions/diagram-reduce-overprivileged-recommendations-inline.png)](../media/develop/overprivileged-permissions/diagram-reduce-overprivileged-recommendations-expanded.png#lightbox)

- **Prevent**: When you build an application, fully understand required permissions for the API calls that your application needs to make. Only request what's necessary to enable your scenario. Microsoft Graph documentation has clear references for least privilege permissions to most privileged permission for all endpoints. Be mindful of overprivileged scenarios as you determine which permissions you need.
- **Audit**: You and IT admins should regularly review existing applications' previously granted privileges.
- **Remediate**: If you or IT admins notice an overprivileged application in the ecosystem, stop requesting tokens for the overprivileged permission. IT admins should revoke granted consents. This step usually requires a code change.

## Best practices for maintaining least privilege permission

Two major incentives for maintaining least privilege permission with your applications are driving application adoption and stopping the spread.

[![Diagram illustrates Drive Adoption and Stop the Spread.](../media/develop/overprivileged-permissions/diagram-least-privilege-best-practices-inline.png)](../media/develop/overprivileged-permissions/diagram-least-privilege-best-practices-expanded.png#lightbox)

- **Drive adoption by building a trustworthy app for customers that avoids excessive permission requests.** Limit your application permissions to only what it needs to complete its task. This practice reduces the potential blast radius of attacks and increases customer adoption of your apps. Apply more scrutiny when reviewing permissions that applications request and deciding whether to grant app permissions.
- **Stop the spread by ensuring bad actors are unable to use excessive privileges to gain further access.** When you create an app that asks for unnecessary permissions, it's least likely to receive approval or denied altogether. The best way to control damage is to prevent bad actors from gaining elevated privilege that increases the scope of the compromise. For example, if your application only has `User.ReadBasic.All` to read user basic information, then your OneDrive, Outlook, Teams, and any confidential data are safe if an app is compromised.