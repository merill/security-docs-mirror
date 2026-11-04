---
layout: Conceptual
title: Securing privileged access accounts - Privileged access | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/privileged-access-workstations/privileged-access-accounts
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: None
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Securing accounts is only one part of the privileged access story
ms.service: security
ms.subservice: privileged-access
ms.topic: best-practice
ms.date: 2021-01-20T00:00:00.0000000Z
ms.reviewer: mas
locale: en-us
document_id: c6700160-def6-9773-4183-38e13e6c0a5e
document_version_independent_id: c6700160-def6-9773-4183-38e13e6c0a5e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/privileged-access-workstations/privileged-access-accounts.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: privileged-access-workstations/privileged-access-accounts
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/privileged-access-workstations/privileged-access-accounts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/079cf7bf-da09-4bd3-ab74-bd5a5da031d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b606cead-f1a2-4925-9a71-5fbd7a0d9b81
platformId: b2479275-634e-c14a-9d9e-c693f5c6112d
---

# Securing privileged access accounts - Privileged access | Microsoft Learn

Account security is a critical component of [securing privileged access](overview). Zero Trust end-to-end security for sessions requires strongly establishing that the account being used in the session is actually under the control of the human owner and not an attacker impersonating them.

Strong account security starts with secure provisioning and full lifecycle management through to deprovisioning, and each session must establish strong assurances that the account isn't currently compromised based on all available data including historical behavior patterns, available threat intelligence, and usage in the current session.

## Account security

This guidance defines three security levels for account security that you can use for assets with different sensitivity levels:

![Protecting accounts end to end](media/privileged-access-accounts/end-to-end-protecting-accounts.png)

These levels establish clear and implementable security profiles appropriate for each sensitivity level that you can assign roles to and scale out rapidly. All of these account security levels are designed to maintain or improve productivity for people by limiting or eliminating interruption to user and admin workflows.

## Planning account security

This guidance outlines the technical controls required to meet each level. Implementation guidance is in the [privileged access roadmap](security-rapid-modernization-plan).

### Account security controls

Achieving security for the interfaces requires a combination of technical controls that both protect the accounts and provide signals to be used in a Zero Trust policy decision (see Securing Interfaces for policy configuration reference).

The controls used in these profiles include:

- Multifactor authentication - providing diverse sources of proof that the (designed to be as easy as possible for users, but difficult for an adversary to mimic).
- Account risk - Threat and Anomaly Monitoring - using UEBA and Threat intelligence to identify risky scenarios
- Custom monitoring - For more sensitive accounts, explicitly defining allowed/accepted behaviors/patterns allows early detection of anomalous activity. This control is not suitable for general purpose accounts in enterprise as these accounts need flexibility for their roles.

The combination of controls also enables you to improve both security and usability - for example a user who stays within their normal pattern (using the same device in same location day after day) does not need to be prompted for outside MFA every time they authenticate.

![Comparing each account tier and cost benefit](media/privileged-access-accounts/compare-account-controls-by-level.png)

### Enterprise security accounts

The security controls for enterprise accounts are designed to create a secure baseline for all users and provide a secure foundation for specialized and privileged security:

- Enforce strong multifactor authentication (MFA) - Ensure that the user is authenticated with strong MFA provided by an enterprise-managed identity system (detailed in the diagram below). For more information about multifactor authentication, see [Azure security best practice 6](/en-us/azure/cloud-adoption-framework/security/security-top-10#6-technology-require-passwordless-or-multifactor-authentication-mfa).

    Note

    While your organization may choose to use an existing weaker form of MFA during a transition period, attackers are increasingly evading the weaker MFA protections, so all new investment into MFA should be on the strongest forms.
- Enforce account/session risk - ensure that the account is not able to authenticate unless it is at a low (or medium?) risk level. See Interface Security Levels for details on conditional enterprise account security.
- Monitor and respond to alerts - Security operations should integrate account security alerts and get sufficient training on how these protocols and systems work to ensure they are able to rapidly comprehend what an alert means and react accordingly.

    - Enable [Microsoft Entra ID Protection](/en-us/azure/active-directory/identity-protection/overview-identity-protection)
    - [Investigate risk Microsoft Entra ID Protection](/en-us/azure/active-directory/identity-protection/howto-identity-protection-investigate-risk)
    - [Troubleshoot/Investigate Conditional Access Sign-in failures](/en-us/azure/active-directory/conditional-access/troubleshoot-conditional-access)

The following diagram provides a comparison to different forms of MFA and passwordless authentication. Each option in box **Best** is both high security and high usability. Each has different hardware requirements so you may want to mix and match which ones apply to different roles or individuals. All Microsoft passwordless solutions are recognized by Conditional Access as multifactor authentication because they require combining something you have with either biometrics, something you know, or both.

![Comparison of authentication methods good, better, best](media/privileged-access-accounts/compare-authentication-methods.png)

Note

For more information on why SMS and other phone based authentication is limited, see the blog post [It's Time to Hang Up on Phone Transports for Authentication](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/it-s-time-to-hang-up-on-phone-transports-for-authentication/ba-p/1751752).

### Specialized accounts

Specialized accounts provide a higher protection level that's suitable for sensitive users. Because of their higher business impact, specialized accounts warrant additional monitoring and prioritization during security alerts, incident investigations, and threat hunting.

Specialized security builds on the strong MFA in enterprise security by identifying the most sensitive accounts and ensuring alerts and response processes are prioritized:

1. Identify Sensitive Accounts - See specialized security level guidance for identifying these accounts.
2. Tag specialized Accounts - Ensure each sensitive account is tagged
    1. [Configure Microsoft Sentinel Watchlists](/en-us/azure/sentinel/watchlists) to identify these sensitive accounts
    2. [Configure Priority account protection in Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385) and designate specialized and privileged accounts as priority accounts -
3. Update Security Operations processes to give these alerts the highest priority
4. Set up Governance - Update or create governance process to ensure that
    1. All new roles to are evaluated for specialized or privileged classifications as they are created or changed
    2. All new accounts are tagged as they are created
    3. Continuous or periodic out of band checks to ensure that roles and accounts didn't get missed by normal governance processes.

### Privileged accounts

Privileged accounts have the highest level of protection because they represent a significant or material potential impact on the organization's operations if compromised.

Privileged accounts always include IT Admins with access to most or all enterprise systems, including most or all business critical systems. Other accounts with a high business impact may also warrant this additional level of protection. For more information about which roles and accounts should be protected at what level, see the article [Privileged Security](privileged-access-security-levels).

In addition to specialized security, privileged account security increases both:

- Prevention - add controls to restrict the usage of these accounts to the designated devices, workstations, and intermediaries.
- Response - closely monitor these accounts for anomalous activity and rapidly investigate and remediate the risk.

## Configuring privileged account security

Follow the guidance in the [Security rapid modernization plan](security-rapid-modernization-plan) to both increase the security of your privileged accounts and decrease your cost to manage.