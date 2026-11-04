---
layout: Conceptual
title: Call an API from another API | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/api-calls-api
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Ensure Zero Trust when you have one API that needs to call another API and securely develop your application when it's working on behalf of a user.
ms.subservice: zero-trust
ms.topic: concept-article
ms.service: security
ms.date: 2025-04-18T00:00:00.0000000Z
ms.collection:
- zerotrust-dev
ms.custom:
- template-concept
- sfi-image-nochange
locale: en-us
document_id: 8f7a9ae1-adea-19d4-bdf3-2177f9d581c4
document_version_independent_id: 8f7a9ae1-adea-19d4-bdf3-2177f9d581c4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/api-calls-api.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/api-calls-api
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/api-calls-api.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: d59ae56f-ee71-6ab6-1324-5ea809f0a4d9
---

# Call an API from another API | Microsoft Learn

How do you, as a developer, [ensure Zero Trust](overview) when you have one API that needs to call another API? In this article, you learn how to securely develop your application when it's working on behalf of a user.

When a user drives an app's UI, the app might use a delegated permission so that the API knows which user on whose behalf the app is working. It inspects the subject (`sub`) claim or object ID (`oid`) and tenant ID (`tid`) claims in the access token that the app provides when calling the API. The API doesn't rely on the untrusted app, which is just a call coming from somewhere on the network. Instead, it validates the token to ensure that the API only works on behalf of the app user that Microsoft Entra ID verified.

When one API (we refer to it as the *Original API*) calls another, it's vital that the API that we're calling (we refer to it as the *Downstream API*) follows the validation process. The Downstream API can't rely on an untrusted network source. It must get the user identity from a properly validated access token.

If the Downstream API doesn't follow the proper validation process, the Downstream API must rely on the Original API to provide the identity of the user in another way. The Downstream API might incorrectly use an application permission to perform the operation. Then the Original API then becomes the sole authority over which users can achieve which results against the Downstream API. The Original API can intentionally (or unintentionally) allow a user to accomplish a task that the user can't otherwise accomplish. For example, one user can change the details of another user or read and update documents that the user doesn't have permission to access. Improper validation can cause serious security issues.

For better security, the Original API acquires a [delegated permission](developer-strategy-delegated-permission) access token to provide to the Downstream API when the Original API makes the call. Let's walk through how this works.

1. **Client App acquires access token to call Original API.** The Client Application acquires a delegated permission access token to the Original API. The delegated permission access token allows it to work on behalf of the user to call the Original API that requires authorization.
2. **Client App gives access token to Original API.** The Client App gives the access token to the Original API. The Original API fully validates and inspects the access token to determine the identity of the Client App's user.
3. **Original API performs token validation and enforcement.** After the Client App gives the access token to the Original API, the Original API performs token validation and enforcement. If all is good, the API proceeds and services the request for the Client App.
4. **Original API can't use access token to call Downstream API.** The Original API wants to call a Downstream API. However, the Original API can't use the access token to call the Downstream API.
5. **Original API goes back to Microsoft Entra ID.** The Original API needs to go back to Microsoft Entra ID. It needs an access token to call the Downstream API on behalf of the user. The Original API provides the token that the Original API received from the Client App and the Original API's client credentials.
6. **Microsoft Entra ID performs checks.** Microsoft Entra ID checks for things like consent or conditional access enforcement. You might have to go back to your calling client and provide a reason for not being able to get the token. You would typically use a [claims challenge](/en-us/entra/identity-platform/claims-challenge) process to go back to the calling application with information regarding consent not being received (such as being related to conditional access policies). If everything is okay, Microsoft Entra ID issues an access token to the Original API to call the Downstream API on behalf of the user.
7. **Original API has user context with On-Behalf-Of flow.** The [On-Behalf-Of flow](/en-us/entra/identity-platform/v2-oauth2-on-behalf-of-flow) (OBO) process allows an API to continue to have the user context as it calls Downstream API.
8. **Original API calls Downstream API.** Call the Downstream API. The token that the Downstream API receives has the proper audience (aud) claim that indicates the Downstream API. The token includes the scopes for granted consent and the original app user identity. The Downstream API can properly implement effective permissions to ensure that the identified user has permission to accomplish the requested task. You want to use the on behalf of flow to acquire tokens for an API to call another API to make sure that user context passes to all Downstream APIs.

## Best option: Original API performs On-Behalf-Of flow

The best option is for the Original API to perform On-Behalf-Of flow (OBO). If the Downstream API receives the correct token, it can correctly respond. When an API is acting on behalf of a user and needs to call another API, the API must use OBO to acquire a delegated permission access token to call the Downstream API on behalf of the user. APIs should never use application permissions to call Downstream APIs when the API is acting on behalf of a user.