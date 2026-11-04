---
layout: Conceptual
title: RaMP Checklist—Explicitly validate trust for all access requests | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/user-access-productivity-validate-trust
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use the steps in this guidance to deploy explicit validation for all access requests that adheres to Zero Trust principles.
ms.date: 2025-02-24T00:00:00.0000000Z
ms.service: security
ms.topic: overview
ms.subservice: zero-trust
locale: en-us
document_id: 3a4bb5ca-6112-c452-45bf-e580086b4b5f
document_version_independent_id: 3a4bb5ca-6112-c452-45bf-e580086b4b5f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/user-access-productivity-validate-trust.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/user-access-productivity-validate-trust
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/user-access-productivity-validate-trust.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 94e02d1d-652e-b8cf-8ff1-782d67c4c891
---

# RaMP Checklist—Explicitly validate trust for all access requests | Microsoft Learn

This Rapid Modernization Plan (RaMP) checklist helps you establish a security perimeter for cloud applications and mobile devices that uses identity as the control plane and explicitly validates trust for user accounts and devices before allowing access, for both public and private networks.

To be productive, your employees (users) must be able to use:

- Their account credentials to verify their identity.
- Their endpoint (device), such as a PC, tablet, or phone.
- The applications you have provided them to do their jobs.
- A network over which traffic flows between devices and applications, whether they're on-premises or in the cloud.

Each one of these elements is the targets of attackers and must be protected with the "never trust, always verify" central principle of Zero Trust.

This checklist includes using Zero Trust to explicitly validate trust for all access requests for:

- Identities
- Endpoints (devices)
- Apps
- Network

After completing this work, you'll have built out this part of the Zero Trust architecture.

[![A diagram highlighting the identities, endpoints, apps, and network sections of the Zero Trust architecture.](media/user-access-productivity-overview/user-access-productivity-validate-trust-users-devices-apps-network.png)](media/user-access-productivity-overview/user-access-productivity-validate-trust-users-devices-apps-network.png#lightbox)

## Identities

Verify and secure each identity with strong authentication across your entire digital estate with Microsoft Entra ID, a complete identity and access management solution with integrated security that connects hundreds of millions of people to their apps, devices, and data each month.

### Program and project member accountabilities

This table describes the overall protection of your user accounts in terms of a sponsorship-program management-project management hierarchy to determine and drive results.

| Lead | Owner | Accountability |
| --- | --- | --- |
| CISO, CIO, or Director of Identity Security |  | Executive sponsorship |
| Program lead from Identity Security or Identity Architect |  | Drive results and cross-team collaboration |
|  | Security Architect | Advise on configuration and standards |
|  | Identity Security or an Identity Architect | Implement configuration changes |
|  | Identity Admin | Update standards and policy documents |
|  | Security Governance or Identity Admin | Monitor to ensure compliance |
|  | User Education Team | Ensure guidance for users reflects policy updates |

### Deployment objectives

Meet these deployment objectives to protect your privileged identities with Zero Trust.

| Done | Deployment objective | Owner | Documentation |
| --- | --- | --- | --- |
|  | 1. Deploy secured privileged access to protect administrative user accounts. | IT implementer | [Securing privileged access for hybrid and cloud deployments in Microsoft Entra ID](/en-us/entra/identity/role-based-access-control/security-planning) |
|  | 2. Deploy Microsoft Entra Privileged Identity Management (PIM) for a time-bound, just-in-time approval process for the use of privileged user accounts. | IT implementer | [Plan a Privileged Identity Management deployment](/en-us/entra/id-governance/privileged-identity-management/pim-deployment-plan) |

Meet these deployment objectives to protect your user identities with Zero Trust.

| Done | Deployment objective | Owner | Documentation |
| --- | --- | --- | --- |
|  | 1. Enable self-service password reset (SSPR), which gives you credential reset capabilities | IT implementer | [Plan a Microsoft Entra self-service password reset deployment](/en-us/entra/identity/authentication/howto-sspr-deployment) |
|  | 2. Enable multifactor authentication (MFA) and select appropriate methods for MFA | IT implementer | [Plan a Microsoft Entra multifactor authentication deployment](/en-us/entra/identity/authentication/howto-mfa-getstarted) |
|  | 3. Enable combined User Registration for your directory to allow users to register for SSPR and MFA in one step | IT implementer | [Enable combined security information registration in Microsoft Entra ID](/en-us/entra/identity/authentication/howto-registration-mfa-sspr-combined) |
|  | 4. Configure a Conditional Access policy to require MFA registration. | IT implementer | [How To: Configure the Microsoft Entra multifactor authentication registration policy](/en-us/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) |
|  | 5. Enable user and sign-in risk-based policies to protect user access to resources. | IT implementer | [How To: Configure and enable risk policies](/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies) |
|  | 6. Detect and block known weak passwords and their variants and block additional weak terms specific to your organization. | IT implementer | [Eliminate bad passwords using Microsoft Entra Password Protection](/en-us/entra/identity/authentication/concept-password-ban-bad) |
|  | 7. Deploy Microsoft Defender for Identity and review and mitigate any open alerts (in parallel with your security operations). | Security operations team | [Microsoft Defender for Identity](/en-us/defender-for-identity/what-is) |
|  | 8. Deploy passwordless credentials. | IT implementer | [Plan a passwordless authentication deployment in Microsoft Entra ID](/en-us/entra/identity/authentication/howto-authentication-passwordless-deployment) |

You have now built out the **Identities** section of the Zero Trust architecture.

[![A diagram highlighting the Identities section of the Zero Trust architecture.](media/user-access-productivity-overview/user-access-productivity-validate-trust-identities.png)](media/user-access-productivity-overview/user-access-productivity-validate-trust-identities.png#lightbox)

## Endpoints

Ensure compliance and health status before granting access to your endpoints (devices) and gain visibility into how they're accessing the network.

### Program and project member accountabilities

This table describes the overall protection of your endpoints in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Owner | Accountability |
| --- | --- | --- |
| CISO, CIO, or Director of Identity Security |  | Executive sponsorship |
| Program lead from Identity Security or an Identity Architect |  | Drive results and cross-team collaboration |
|  | Security Architect | Advise on configuration and standards |
|  | Identity Security or an Infrastructure Security Architect | Implement configuration changes |
|  | Mobile device management (MDM) Admin | Update standards and policy documents |
|  | Security Governance or MDM Admin | Monitor to ensure compliance |
|  | User Education Team | Ensure guidance for users reflects policy updates |

### Deployment objectives

Meet these deployment objectives to protect your endpoints (devices) with Zero Trust.

| Done | Deployment objective | Owner | Documentation |
| --- | --- | --- | --- |
|  | 1. Register devices with Microsoft Entra ID. | MDM Admin | [Device identities](/en-us/entra/identity/devices/overview) |
|  | 2. Enroll devices and create configuration profiles. | MDM Admin | [Device management overview](/en-us/mem/intune/fundamentals/what-is-device-management) |
|  | 3. Connect Defender for Endpoint to Intune (in parallel with your security operations). | Identity Security Admin | [Configure Microsoft Defender for Endpoint in Intune](/en-us/mem/intune/protect/advanced-threat-protection-configure) |
|  | 4. Monitor device compliance and risk for Conditional Access. | Identity Security Admin | [Use compliance policies to set rules for devices you manage with Intune](/en-us/mem/intune/protect/device-compliance-get-started) |
|  | 5. Implement a Microsoft Purview information protection solution and integrate with Conditional Access policies. | Identity Security Admin | [Use sensitivity labels to protect content](/en-us/purview/sensitivity-labels-teams-groups-sites) |

You have now built out the **Endpoints** section of the Zero Trust architecture.

[![A diagram highlighting the Endpoints section of the Zero Trust architecture.](media/user-access-productivity-overview/user-access-productivity-validate-trust-endpoints.png)](media/user-access-productivity-overview/user-access-productivity-validate-trust-endpoints.png#lightbox)

## Apps

Because apps are used by malicious users to infiltrate your organization, you need to ensure that your apps are using services, such as Microsoft Entra ID and Intune, that provide Zero Trust protection or are hardened against attack.

### Program and project member accountabilities

This table describes a Zero Trust implementation for apps in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Owner | Accountability |
| --- | --- | --- |
| CISO, CIO, or Director of Application Security |  | Executive sponsorship |
| Program lead from Apps Management |  | Drive results and cross-team collaboration |
|  | Identity Architect | Advise on Microsoft Entra configuration for apps  Update authentication standards for on-premises apps |
|  | Developer Architect | Advise on configuration and standards for in-house on-premises and cloud apps |
|  | Network Architect | Implement VPN configuration changes |
|  | Cloud Network Architect | Deploy Microsoft Entra application proxy |
|  | Security Governance | Monitor to ensure compliance |

### Deployment objectives

Meet these deployment objectives to ensure Zero Trust protection for your Microsoft cloud apps, third-party SaaS apps, custom PaaS apps, and on-premises apps.

| Done | Type of app or app usage | Deployment objectives | Owner | Documentation |
| --- | --- | --- | --- | --- |
|  | Third-party SaaS apps and custom PaaS apps that are registered with Microsoft Entra ID | Microsoft Entra app registration uses Microsoft Entra authentication, certification, and app consent policies.  Use Microsoft Entra Conditional Access policies and Intune MAM and Application Protection Policies (APP) policies to allow app usage. | Identity Architect | [Application management in Microsoft Entra ID](/en-us/entra/identity/enterprise-apps/what-is-application-management) |
|  | Cloud apps that are OAuth-enabled and registered in Microsoft Entra ID, Google, and Salesforce | Use app governance in Microsoft Defender for Cloud Apps for app behavior visibility, governance with policy enforcement, and detection and remediation of app-based attacks. | Security Engineer | [Overview](/en-us/defender-cloud-apps/app-governance-manage-app-governance) |
|  | Third-party SaaS apps and custom PaaS apps that are **NOT** registered with Microsoft Entra ID | Register them with Microsoft Entra ID for authentication, certification, and app consent policies.  Use Microsoft Entra Conditional Access policies and Intune MAM and APP policies. | Apps Architect | [Integrating all your apps with Microsoft Entra ID](/en-us/entra/fundamentals/five-steps-to-full-application-integration) |
|  | On-premises users accessing on-premises applications, which include applications running on both on-premises and IaaS-based servers | Ensure that your apps support modern authentication protocols such as OAuth/OIDC and SAML. Contact your application vendor for updates to protect user sign-in. | Identity Architect | See your vendor documentation |
|  | Remote users accessing on-premises applications through a VPN connection | Configure your VPN appliance so that it uses Microsoft Entra ID as its identity provider | Network Architect | See your vendor documentation |
|  | Remote users accessing on-premises **web** applications through a VPN connection | Publish the applications through Microsoft Entra application proxy. Remote users only need to access the individual published application, which is routed to the on-premises web server through an application proxy connector.  Connections take advantage of strong Microsoft Entra authentication and limits users and their devices to accessing a single application at a time. In contrast, the scope of a typical remote access VPN is all locations, protocols, and ports of the entire on-premises network. | Cloud Network Architect | [Remote access to on-premises applications through Microsoft Entra application proxy](/en-us/entra/identity/app-proxy/) |

After completing these deployment objectives, you'll have built out the **Apps** section of the Zero Trust architecture.

[![A diagram highlighting the Apps section of the Zero Trust architecture.](media/user-access-productivity-overview/user-access-productivity-validate-trust-apps.png)](media/user-access-productivity-overview/user-access-productivity-validate-trust-apps.png#lightbox)

## Network

The Zero Trust model assumes breach and verifies each request as though it originated from an uncontrolled network. Although this is a common practice for public networks, it also applies to your organization’s internal networks that are typically firewalled from the public Internet.

To adhere to Zero Trust, your organization must address security vulnerabilities on both public and private networks, whether on-premises or in the cloud, and ensure that you verify explicitly, use least privilege access, and assume breach. Devices, users, and apps aren't to be inherently trusted because they're on your private networks.

### Program and project member accountabilities

This table describes a Zero Trust implementation for public and private networks in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Owner | Accountability |
| --- | --- | --- |
| CISO, CIO, or Director of Network Security |  | Executive sponsorship |
| Program lead from Networking Leadership |  | Drive results and cross-team collaboration |
|  | Security Architect | Advise on encryption and access policy configuration and standards |
|  | Network Architect | Advise on traffic filtering and network architecture changes |
|  | Network Engineers | Design segmentation configuration changes |
|  | Network Implementers | Change networking equipment configuration and update configuration documents |
|  | Networking Governance | Monitor to ensure compliance |

### Deployment objectives

Meet these deployment objectives to ensure Zero Trust protection for your public and private networks, for both on-premises and cloud-based traffic. These objectives can be done in parallel.

| Done | Deployment objective | Owner | Documentation |
| --- | --- | --- | --- |
|  | Require encryption for all traffic connections, including between IaaS components and between on-premises users and apps. | Security Architect | [Azure IaaS components](/en-us/azure/vpn-gateway/vpn-gateway-ipsecikepolicy-rm-powershell)[IPsec for on-premises Windows devices](/en-us/windows/security/threat-protection/windows-firewall/securing-end-to-end-ipsec-connections-by-using-ikev2) |
|  | Limit access to critical data and applications by policy (user or device identity) or traffic filtering. | Security Architect or Network Architect | [Access policies for Defender for Cloud Apps Conditional Access App Control](/en-us/defender-cloud-apps/proxy-intro-aad)[Windows Firewall for Windows devices](/en-us/windows/security/operating-system-security/network-security/windows-firewall/) |
|  | Deploy on-premises network segmentation with ingress and egress traffic controls with micro-perimeters and micro-segmentation. | Network Architect or Network Engineer | See your on-premises network and edge devices documentation. |
|  | Use real-time threat detection for on-premises traffic. | SecOps Analysts | [Windows threat protection](/en-us/windows/security/threat-protection/)[Microsoft Defender for Endpoint](/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint) |
|  | Deploy cloud network segmentation with ingress and egress traffic controls with micro-perimeters and micro-segmentation. | Network Architect or Network Engineer | [Recommendations for networking and connectivity](/en-us/azure/well-architected/security/networking) |
|  | Use real-time threat detection for cloud traffic. | Network Architect or Network Engineer | [Azure Firewall threat intelligence-based filtering](/en-us/azure/firewall/threat-intel)[Azure Firewall Premium network intrusion detection and prevention system (IDPS)](/en-us/azure/firewall/premium-features#idps) |

After completing these deployment objectives, you'll have built out the **Network** section of the Zero Trust architecture.

[![A diagram highlighting the Network section of the Zero Trust architecture.](media/user-access-productivity-overview/user-access-productivity-validate-trust-network.png)](media/user-access-productivity-overview/user-access-productivity-validate-trust-network.png#lightbox)