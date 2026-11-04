---
layout: Conceptual
title: Develop delegated permissions strategy | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/developer-strategy-delegated-permission
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: As a developer, implement the best approach for managing permissions in your application and develop with Zero Trust.
ms.subservice: zero-trust
ms.service: security
ms.topic: concept-article
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: f2f607c6-96c7-fd7c-3747-602629c9cfe4
document_version_independent_id: f2f607c6-96c7-fd7c-3747-602629c9cfe4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/developer-strategy-delegated-permission.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/developer-strategy-delegated-permission
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/developer-strategy-delegated-permission.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
- https://authoring-docs-microsoft.poolparty.biz/devrel/5f286262-a4cb-47f4-92d3-dc24f172492b
- https://authoring-docs-microsoft.poolparty.biz/devrel/1e31b9be-b6e9-4221-a20b-d1460dbd5dfa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
- https://authoring-docs-microsoft.poolparty.biz/devrel/90571f66-8410-4272-8117-79ce87fc2dcc
- https://authoring-docs-microsoft.poolparty.biz/devrel/8d63a4c4-4889-43b4-a98e-8e50dbfdb083
platformId: 3582341e-e63a-3774-9b69-4c95ba7bc22d
---

# Develop delegated permissions strategy | Microsoft Learn

This article helps you, as a developer, to implement the best approach for managing permissions in your application and [develop using Zero Trust principles](overview). As described in [Acquire authorization to access resources](acquire-application-authorization-to-access-resources), *delegated permissions* are used with delegated access to allow an application to act on behalf of a user, accessing only what the user can access. To access any data associated with the permission, use *Application permissions* with direct access to allow an application. Only administrators and owners of [service principals](/en-us/entra/identity-platform/how-applications-are-added#what-are-service-principals-and-where-do-they-come-from) can consent to application permissions.

The permission and consent models refer primarily to an application. The permission and consent process has no control over what a user can do. It controls what actions the application is allowed to perform.

Reference the following Venn diagram. With delegated permissions, there's an intersection between what the user is allowed to do and what the application is allowed to do. That intersection is the effective permission by which the application is bound. Anytime you use a delegated permission, effective permissions bound it.

[!\[Venn diagram shows effective permissions as intersection of app permissions and user capabilities.\](../media/develop/developer-strategy-delegated-permission/diagram-effective-permissions-inline.png)
 "Venn diagram description: Left circle text: Apps are granted consent for the app's range of operation. Right circle text: Users have permissions for operations managed by their organization. Intersection of circles text: Effective permissions: intersection of app permissions and user capabilities."](../media/develop/developer-strategy-delegated-permission/diagram-effective-permissions-expanded.png#lightbox)

For example, your application that has users in front of the app gets permission to update every user's profile in the tenant. That doesn't mean that anyone running your application can update anyone else's profile. If the admin decides to grant your application `User.ReadWrite.All`, then they believe that your application is doing the right things when updating any users profile. Your app might log the changes and properly safeguard the information. The admin makes a value judgment about the application, not about the user.

## Least privilege approach

APIs can be complex. Simple APIs might not have many operations. Complex APIs like Microsoft Graph encapsulate many requests that an application might want to use. Just because the application has the right to read doesn't mean it should have the right to update. For example, Microsoft Graph has thousands of APIs. Just because you have permission to read the user's profile, there's no reason why you should also have permission to delete all their OneDrive files.

As a developer, you should:

- know which APIs the app calls.
- understand the API documentation and what permissions the API requires.
- use the least possible permission to accomplish your tasks.

APIs often provide access to organization data stores and attract the attention of bad actors who want to access that data.

Evaluate the permissions you request to ensure that you seek the absolute least privileged set to get the job done. Avoid requesting higher privilege permissions. Instead, carefully work through the large number of permissions that APIs like Microsoft Graph provide. Locate and use the minimum permissions to address your needs. If you don't write code to update the user's profile, you don't request it for your application. If you only access users and groups, you don't request access to other information in the directory. You don't request permission to manage user email if you don't write code that accesses user email.

In Zero Trust application development:

- Define your application's intention and what it needs.
- Ensure that bad actors can't compromise and use your app in a way that you didn't intend.
- Make requests for approval in which you define your requirements (for example, read the user's mail).

## User and tenant administrator roles in permission and consent

People who can approve of your requests fall into two categories: admins who can always consent to permission requests and regular users who aren't admins. However, the tenant admins have the final say in their tenant regarding which permissions require admin consent and to which permissions a user can consent.

When an API designer requires admin consent for a permission, that permission always requires admin consent. A tenant admin can't overrule that and require only user consent.

When an API designer defines permissions that require user consent, the tenant admin can overrule the API designer's user consent suggestions. The tenant admins can do that with a *big switch* in the tenant: everything requires admin consent. They can overrule user consent in a more granular way with [permission and consent management](/en-us/entra/identity/enterprise-apps/configure-user-consent). For example, they might allow users to consent to user consent requests from [verified publishers](developer-strategy-authorization-best-practices#become-a-verified-publisher) but not from other publishers. In another example, they might allow `User.Read` to sign in the user and read their profile but require admin consent to apps that ask permission to mail or to files.

API designers make their suggestions but tenant admins have the final say. Therefore, as a developer, you don't always know when your app requires admin consent. It's nice to plan and design around that. Remember, when you make a token request, it could be denied for any reason. In your code, you need to gracefully handle not getting a token because tenant admins in which your customers or users who run your application decide when permissions require admin consent.

## Example using JavaScript MSAL

For the authentication in this example, you use our JavaScript Microsoft Authentication Library (MSAL) to sign in the user in a single page application (SPA) where all the app logic executes from the browser.

From the related [Quickstart article](/en-us/entra/identity-platform/index-spa), you can [download](/en-us/entra/identity-platform/quickstart-single-page-app-javascript-sign-in#clone-or-download-the-sample-application) and run a code sample. It demonstrates how a JavaScript single-page application (SPA) can sign in users and call Microsoft Graph with the authorization code flow with Proof Key for Code Exchange (PKCE). The code sample shows how to get an access token to call the Microsoft Graph API or any web API.

As shown in the following example code, you instantiate a public client because an application that runs entirely in the browser must be a public client. The user can get their hands on the internals of your application when the code is in the browser.

```javascript
// Create the main myMSALObj instance
// configuration parameters are located at authConfig.js
const myMSALObj = new msal.PublicClientApplication(msalConfig);
```

Then you use our MSAL library. In MSAL JavaScript, there's a specific API to sign in. There are two APIs that utilize specific capabilities within the browser. One is to sign in with a pop-up experience; the other one is to sign in with a browser redirect experience.

As shown in the following code example, the sign-in pop-up handles the authentication that the user needs to perform by calling the `signIn` function.

```javascript
function signIn() {

    /**
     * You can pass a custom request object. This overrides the initial configuration. For more information, visit:
     * https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-browser/docs/request-response-object.md#request
     */

    myMSALObj.loginPopup(loginRequest)
        .then(handleResponse)
        .catch(error => {
            console.error(error);
        });
}
```

Your app can get information about the user, such as their display name or user ID. Next, your app needs authorization to read the full profile of the user from Microsoft Graph by following a pattern that you use throughout our MSAL libraries.

As shown in the following example code, your app attempts to get the authorization by calling `AcquireTokenSilent`. If Microsoft Entra ID can issue the token without interacting with the user, then `AcquireTokenSilent` returns the token that your app needs to access Microsoft Graph on behalf of the user.

```javascript
function getTokenPopup(request) {

    /**
     * See here for more info on account retrieval: 
     * https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-common/docs/Accounts.md
     */
    request.account = myMSALObj.getAccountByUsername(username);
    
    return myMSALObj.`AcquireTokenSilent`(request)
        .catch(error => {
            console.warn("silent token acquisition fails. acquiring token using popup");
            if (error instanceof msal.InteractionRequiredAuthError) {
                // fallback to interaction when silent call fails
                return myMSALObj.`AcquireTokenPopup`(request)
                    .then(tokenResponse => {
                        console.log(tokenResponse);
                        return tokenResponse;
                    }).catch(error => {
                        console.error(error);
                    });
            } else {
                console.warn(error);
            }
    });
}
```

However, often Microsoft Entra ID can't issue the token without interacting with the user (for example, the user changed their password or doesn't grant consent). Therefore, `AcquireTokenSilent` sends an error back to the application that requires user interaction. When you're your app receives the error, you fall back to call `AcquireTokenPopup`.

At that point, Microsoft Entra ID has a conversation with the user so they can authenticate the user and authorize your app to act on the user's behalf (for example, do an MFA, provide their password, grant consent). Then your app gets the token it needs to move forward.

A primary step in an enterprise's journey to Zero Trust is to adopt stronger authentication methods instead of just a user ID and password. The preceding example code fully enables an enterprise to move to the stronger authentication method that the enterprise chooses. For example, multifactor authentication, fully passwordless with a FIDO2 key, Microsoft Authenticator.