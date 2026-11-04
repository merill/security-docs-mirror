---
layout: Conceptual
title: Make it hard for ransomware attacks to happen to your organization | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/ransomware/protect-against-ransomware-phase3
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: pauloliveria
author: poliveria
manager: orspodek
ms.service: security
ms.subservice: ''
ms.date: 2024-10-16T00:00:00.0000000Z
ms.topic: concept-article
ms.collection:
- msftsolution-ransomware
ms.custom: cx-rw
description: How to stop ransomware attacks by making it hard for a cybercriminal to get into your environment. Use ransomware prevention to reduce your risks.
locale: en-us
document_id: 7506236f-4e29-d613-341c-db487e4984cc
document_version_independent_id: 7506236f-4e29-d613-341c-db487e4984cc
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/ransomware/protect-against-ransomware-phase3.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: ransomware/protect-against-ransomware-phase3
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/ransomware/protect-against-ransomware-phase3.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: e92fdba2-e6c4-9a60-12ad-79abf0ee8fe3
---

# Make it hard for ransomware attacks to happen to your organization | Microsoft Learn

In this phase, you make the threat actors work *harder* to access your on-premises or cloud systems by gradually removing risks at the points of entry.

While many of these changes will be familiar and easy to implement, **it's extremely important that your work on this part of the strategy not slow your progress on the other critically important parts!**

Here are the links to review the three-part ransomware prevention plan:

- [Have a recovery plan](protect-against-ransomware-phase1)
- [Limit the harm done](protect-against-ransomware-phase2)
- [Make it hard to get in](protect-against-ransomware-phase3)

## Remote access

Getting access to your organization's intranet through a remote access connection is an attack vector for ransomware threat actors.

Once an on-premises user account is compromised, a threat actor can leverage an intranet to gather intelligence, elevate privileges, and install ransomware. The Colonial Pipeline cyberattack in 2021 is an example.

### Program and project member accountabilities for remote access

This table describes the overall protection of your remote access solution from ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| CISO or CIO |  | Executive sponsorship |
| Program lead on the [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Infrastructure/Network Team |  | Drive results and cross-team collaboration |
|  | IT and [Security](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) Architects | Prioritize component integration into architectures |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Identity Team | Configure Microsoft Entra ID and conditional access policies |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Operations | Implement changes to environment |
|  | Workload Owners | Assist with RBAC permissions for app publishing |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |
|  | User Education Team | Update any guidance on workflow changes and perform education and change management |

### Implementation checklist for remote access

Apply these best practices to protect your remote access infrastructure from ransomware threat actors.

| Done | Task | Description |
| --- | --- | --- |
|  | Maintain software and appliance updates. Avoid missing or neglecting manufacturer protections (security updates, supported status). | Threat actors use well-known vulnerabilities that have not yet been patched as attack vectors. |
|  | Configure Microsoft Entra ID for existing remote access by including enforcing [Zero Trust](https://www.microsoft.com/security/business/zero-trust) user and device validation with Conditional Access. | Zero Trust provides multiple levels of securing access to your organization. |
|  | Configure security for existing third-party VPN solutions (Cisco [AnyConnect](/en-us/azure/active-directory/saas-apps/cisco-anyconnect), Palo Alto Networks [GlobalProtect](/en-us/azure/active-directory/saas-apps/palo-alto-networks-globalprotect-tutorial) & [Captive Portal](/en-us/azure/active-directory/saas-apps/paloaltonetworks-captiveportal-tutorial), Fortinet [FortiGate SSL VPN](/en-us/azure/active-directory/saas-apps/fortigate-ssl-vpn-tutorial), Citrix [NetScaler](/en-us/azure/active-directory/saas-apps/citrix-netscaler-tutorial), [Zscaler Private Access (ZPA)](/en-us/azure/active-directory/saas-apps/zscalerprivateaccess-tutorial), and [more](/en-us/azure/active-directory/saas-apps/tutorial-list)). | Take advantage of the built-in security of your remote access solution. |
|  | Deploy [Azure Point-to-Site (P2S) VPN](/en-us/azure/vpn-gateway/openvpn-azure-ad-tenant#enable-authentication) to provide remote access. | Take advantage of integration with Microsoft Entra ID and your existing Azure subscriptions. |
|  | Publish on-premises web apps with [Microsoft Entra application proxy](/en-us/azure/active-directory/manage-apps/application-proxy-integrate-with-remote-desktop-services). | Apps published with Microsoft Entra application proxy do not need a remote access connection. |
|  | Secure access to Azure resources with [Azure Bastion](/en-us/azure/bastion/bastion-overview). | Securely and seamlessly connect to your Azure virtual machines over SSL. |
|  | Audit and monitor to find and fix deviations from baseline and potential attacks (see [Detection and Response](protect-against-ransomware-phase2#ransomware-detection-and-response)). | Reduce risk from ransomware activities that probe baseline security features and settings. |

## Email and collaboration

Implement best practices for email and collaboration solutions to make it more difficult for threat actors to abuse them, while letting your workers access external content easily and safely.

Threat actors frequently enter the environment by introducing malicious content disguised within authorized collaboration tools such as email and file sharing and convincing users to run the content. Microsoft has invested in enhanced mitigations that vastly increase protection against these attack vectors.

### Program and project member accountabilities for email and collaboration

This table describes the overall protection of your email and collaboration solutions from ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| CISO, CIO, or Identity Director |  | Executive sponsorship |
| Program lead from the [Security Architecture](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) team |  | Drive results and cross-team collaboration |
|  | IT Architects | Prioritize component integration into architectures |
|  | Cloud Productivity or End User Team | Enable Defender for Office 365, Azure Site Recovery, and AMSI |
|  | [Security Architecture](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) / [Infrastructure + Endpoint](/en-us/azure/cloud-adoption-framework/organize/cloud-security-infrastructure-endpoint) | Configuration assistance |
|  | User Education Team | Update guidance on workflow changes |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |

### Implementation checklist for email and collaboration

Apply these best practices to protect your email and collaboration solutions from ransomware threat actors

| Done | Task | Description |
| --- | --- | --- |
|  | Enable [AMSI for Office VBA](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/). | Detect Office macro attacks with endpoint tools like [Defender for Endpoint](/en-us/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). |
|  | Implement Advanced Email security using [Defender for Office 365](/en-us/microsoft-365/security/office-365-security/office-365-atp) or a similar solution. | Email is a common entry point for threat actors. |
|  | [Deploy attack surface reduction (Azure Site Recovery) rules](/en-us/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-deployment) to block common attack techniques including:  - Endpoint abuse such as credential theft, ransomware activity, and suspicious use of PsExec and WMI.  - Weaponized Office document activity such as advanced macro activity, executable content, process creation, and process injection initiated by Office applications. **Note:** Deploy these rules in audit mode first, then assess any negative impact, and then deploy them in block mode. | Azure Site Recovery provides additional layers of protect specifically targeted at mitigating common attack methods. |
|  | Audit and monitor to find and fix deviations from baseline and potential attacks (see [Detection and Response](protect-against-ransomware-phase2#ransomware-detection-and-response)). | Reduces risk from ransomware activities that probe baseline security features and settings. |

## Endpoints

Implement relevant security features and rigorously follow software maintenance best practices for endpoints (devices) and applications, prioritizing applications and server/client operating systems directly exposed to Internet traffic and content.

Internet-exposed endpoints are a common entry vector that provides threat actors access to the organization's assets. Prioritize blocking common OS and application vulnerabilities with preventive controls to slow or stop them from performing the next stages.

### Program and project member accountabilities for endpoints

This table describes the overall protection of your endpoints from ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| Business leadership accountable for business impact of both downtime and attack damage |  | Executive sponsorship (maintenance) |
| [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Operations or CIO |  | Executive sponsorship (others) |
| Program lead from the [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Infrastructure Team |  | Drive results and cross-team collaboration |
|  | IT and [Security](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) Architects | Prioritize component integration into architectures |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Operations | Implement changes to environment |
|  | Cloud Productivity or End User Team | Enable attack surface reduction |
|  | Workload/App Owners | Identify maintenance windows for changes |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |

### Implementation checklist for endpoints

Apply these best practices to all Windows, Linux, macOS, Android, iOS, and other endpoints.

| Done | Task | Description |
| --- | --- | --- |
|  | Block known threats with [attack surface reduction](/en-us/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-deployment) rules, [tamper protection](/en-us/microsoft-365/security/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection), and [block at first sight](/en-us/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus). | Don't let lack of use of these built-in security features be the reason an attacker entered your organization. |
|  | Apply [Security Baselines](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines) to harden internet-facing Windows servers and clients and Office applications. | Protect your organization with the minimum level of security and build from there. |
|  | Maintain your software so that it is:  - Updated: Rapidly deploy critical security updates for operating systems, browsers, & email clients  - Supported: Upgrade operating systems and software for versions supported by your vendors. | Attackers are counting on you missing or neglecting manufacturer updates and upgrades. |
|  | Isolate, disable, or retire insecure systems and protocols, including [unsupported operating systems](/en-us/lifecycle/) and [legacy protocols](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/retire-those-old-legacy-protocols/ba-p/259396). | Attackers use known vulnerabilities of legacy devices, systems, and protocols as entry points into your organization. |
|  | Block unexpected traffic with host-based firewall and network defenses. | Some malware attacks rely on unsolicited inbound traffic to hosts as a way of making a connection for an attack. |
|  | Audit and monitor to find and fix deviations from baseline and potential attacks (see [Detection and Response](protect-against-ransomware-phase2#ransomware-detection-and-response)). | Reduces risk from ransomware activities that probe baseline security features and settings. |

## Accounts

Just as antique skeleton keys won’t protect a house against a modern-day burglar, passwords cannot protect accounts against common attacks we see today. While multifactor authentication (MFA) was once a burdensome extra step, passwordless authentication improves the sign-in experience using biometric approaches that don’t require your users to remember or type a password. Additionally, a [Zero Trust](https://www.microsoft.com/security/business/zero-trust) infrastructure stores information about trusted devices, which reduce prompting for annoying out-of-band MFA actions.

Starting with high-privilege administrator accounts, rigorously follow these best practices for account security including using passwordless or MFA.

### Program and project member accountabilities for accounts

This table describes the overall protection of your accounts from ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| CISO, CIO, or Identity Director |  | Executive sponsorship |
| Program lead from [Identity and Key Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-identity-keys) or [Security Architecture](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) teams |  | Drive results and cross-team collaboration |
|  | IT and [Security](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) Architects | Prioritize component integration into architectures |
|  | [Identity and Key Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-identity-keys) or [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Operations | Implement configuration changes |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |
|  | User Education Team | Update password or sign-in guidance and perform education and change management |

### Implementation checklist for accounts

Apply these best practices to protect your accounts from ransomware attackers.

| Done | Task | Description |
| --- | --- | --- |
|  | Enforce strong MFA or passwordless sign-in for all users. Start with administrator and [priority](/en-us/microsoft-365/admin/setup/priority-accounts) accounts using one or more of:  - Passwordless authentication with [Windows Hello](/en-us/windows/security/identity-protection/hello-for-business/hello-identity-verification) or the [Microsoft Authenticator app](/en-us/azure/active-directory/authentication/howto-authentication-phone-sign-in).  - [Multifactor authentication](/en-us/azure/active-directory/authentication/howto-mfa-userstates).  - A third-party MFA solution. | Make it harder for an attacker to perform a credential compromise by just determining a user account password. |
|  | Increase password security:  - For Microsoft Entra accounts, use [Microsoft Entra Password Protection](/en-us/azure/active-directory/authentication/concept-password-ban-bad) to detect and block known weak passwords and additional weak terms that are specific to your organization.  - For on-premises Active Directory Domain Services (AD DS) accounts, [Extend Microsoft Entra Password Protection](/en-us/azure/active-directory/authentication/concept-password-ban-bad-on-premises) to AD DS accounts. | Ensure that attackers can't determine common passwords or passwords based on your organization name. |
|  | Audit and monitor to find and fix deviations from baseline and potential attacks (see [Detection and Response](protect-against-ransomware-phase2#ransomware-detection-and-response)). | Reduces risk from ransomware activities that probe baseline security features and settings. |

### Implementation results and timelines

Try to achieve these results within 30 days:

- 100% of employees are actively using MFA
- 100% deployment of higher password security

## Additional ransomware resources

Key information from Microsoft:

- [Moonstone Sleet emerges as new North Korean threat actor with new bag of tricks](https://www.microsoft.com/security/blog/2024/05/28/moonstone-sleet-emerges-as-new-north-korean-threat-actor-with-new-bag-of-tricks), Microsoft Blog, May 2024
- [Human-operated ransomware](human-operated-ransomware)
- [Rapidly protect against ransomware and extortion](protect-against-ransomware)
- [2023 Microsoft Digital Defense Report](https://www.microsoft.com/security/security-insider/microsoft-digital-defense-report-2023) (see pages 17-26)
- [Ransomware: A pervasive and ongoing threat](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) threat analytics report in the Microsoft Defender portal
- Microsoft Incident Response team (formerly DART) ransomware [approach](/en-us/security/ransomware/incident-response-playbook-dart-ransomware-approach) and [case study](dart-ransomware-case-study)

Microsoft 365:

- [Deploy ransomware protection for your Microsoft 365 tenant](/en-us/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Maximize Ransomware Resiliency with Azure and Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Recover from a ransomware attack](/en-us/microsoft-365/security/office-365-security/recover-from-ransomware)
- [Malware and ransomware protection](/en-us/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Protect your Windows 10 PC from ransomware](https://support.microsoft.com/windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [Handling ransomware in SharePoint Online](/en-us/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Threat analytics reports for ransomware](https://security.microsoft.com/threatanalytics3?page_size=30&amp;filters=tags%3DRansomware&amp;ordering=-lastUpdatedOn&amp;fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) in the Microsoft Defender portal

Microsoft Defender XDR:

- [Find ransomware with advanced hunting](/en-us/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure:

- [Azure Defenses for Ransomware Attack](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Maximize Ransomware Resiliency with Azure and Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Backup and restore plan to protect against ransomware](/en-us/azure/security/fundamentals/backup-plan-to-protect-against-ransomware)
- [Help protect from ransomware with Microsoft Azure Backup](https://www.youtube.com/watch?v=VhLOr2_1MCg) (26 minute video)
- [Recovering from systemic identity compromise](/en-us/azure/security/fundamentals/recover-from-identity-compromise)
- [Advanced multistage attack detection in Microsoft Sentinel](/en-us/azure/sentinel/fusion#ransomware)
- [Fusion Detection for Ransomware in Microsoft Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps:

- [Create anomaly detection policies in Defender for Cloud Apps](/en-us/cloud-app-security/anomaly-detection-policy)

Microsoft Security team blog posts:

- [3 steps to prevent and recover from ransomware (September 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [A guide to combatting human-operated ransomware: Part 1 (September 2021)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

    Key steps on how Microsoft's Detection and Response Team (DART) conducts ransomware incident investigations.
- [A guide to combatting human-operated ransomware: Part 2 (September 2021)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

    Recommendations and best practices.
- [Becoming resilient by understanding cybersecurity risks: Part 4—navigating current threats (May 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

    See the **Ransomware** section.
- [Human-operated ransomware attacks: A preventable disaster (March 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

    Includes attack chain analyses of actual attacks.
- [Ransomware response—to pay or not to pay? (December 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro responds to ransomware attack with transparency (December 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)