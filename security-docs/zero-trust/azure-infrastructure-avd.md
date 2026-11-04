---
layout: Conceptual
title: Apply Zero Trust principles to Azure Virtual Desktop | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-infrastructure-avd
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to secure an Azure Virtual Desktop deployment with Zero Trust principles.
ms.date: 2025-05-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: how-to
ms.collection:
- msftsolution-azurepaas
- msftsolution-scenario
- zerotrust-solution
- zerotrust-azure
locale: en-us
document_id: 18791b4c-ec32-3c53-6ed9-21dd2aff67ff
document_version_independent_id: 18791b4c-ec32-3c53-6ed9-21dd2aff67ff
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-infrastructure-avd.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-infrastructure-avd
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-infrastructure-avd.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7814ca69-56be-4667-8a46-86327796c328
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/f15dfcd0-2664-48ba-bb88-f1f86eadbfd1
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 73ce0c8e-c2ec-efa3-7337-279247f8a483
---

# Apply Zero Trust principles to Azure Virtual Desktop | Microsoft Learn

This article provides steps to apply the [principles of Zero Trust](zero-trust-overview) to an Azure Virtual Desktop deployment in the following ways:

| Zero Trust principle | Definition | Met by |
| --- | --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. | Verify the identities and endpoints of Azure Virtual Desktop users and secure access to session hosts. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. | - Confine access to session hosts and their data.<br>- Storage: Protect data in all three modes: data at rest, data in transit, data in use.<br>- Virtual networks (VNets): Specify allowed network traffic flows between hub and spoke VNets with Azure Firewall.<br>- Virtual machines: Use role-based access control (RBAC). |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses. | - Isolate the components of an Azure Virtual Desktop deployment.<br>- Storage: Use Defender for Storage for automated threat detection and protection.<br>- VNets: Prevent traffic flows between workloads with Azure Firewall.<br>- Virtual machines: Use double encryption for end-to-end encryption, enable encryption at host, secure maintenance for virtual machines, and Microsoft Defender for Servers for threat detection.<br>- Azure Virtual Desktop: Use Azure Virtual Desktop security, governance, management, and monitoring features to improve defenses and collect session host analytics. |

For more information about how to apply the principles of Zero Trust across an Azure IaaS environment, see the [Apply Zero Trust principles to Azure IaaS overview](azure-infrastructure-overview).

## Reference architecture

In this article, we use the following reference architecture for Hub and Spoke to demonstrate a commonly deployed environment and how to apply the principles of Zero Trust for Azure Virtual Desktop with users’ access over the Internet. [Azure Virtual WAN](/en-us/azure/virtual-wan/virtual-wan-about) architecture is also supported in addition to private access over a managed network with [RDP Shortpath for Azure Virtual Desktop](/en-us/azure/virtual-desktop/rdp-shortpath?tabs=managed-networks).

[![Diagram of the reference architecture for Azure Virtual Desktop.](media/avd/ref-arch-avd.svg)](media/avd/ref-arch-avd.svg#lightbox)

The Azure environment for Azure Virtual Desktop includes:

| Component | Description |
| --- | --- |
| A | Azure Storage Services for Azure Virtual Desktop user profiles. |
| B | A connectivity hub virtual network (VNet). |
| C | A spoke VNet with Azure Virtual Desktop session host virtual machine-based workloads. |
| D | An Azure Virtual Desktop Control Plane. |
| E | An Azure Virtual Desktop Management Plane. |
| F | Dependent PaaS services including Microsoft Entra ID, Microsoft Defender for Cloud, role-based access control (RBAC), and Azure Monitor. |
| G | Azure Compute Gallery. |

Users or admins that access the Azure environment can originate from the internet, office locations, or on-premises datacenters.

The reference architecture aligns to the architecture described in the [Enterprise-scale landing zone for Azure Virtual Desktop](/en-us/azure/cloud-adoption-framework/scenarios/wvd/enterprise-scale-landing-zone) Cloud Adoption Framework.

## Logical architecture

In this diagram, the Azure infrastructure for an Azure Virtual Desktop deployment is contained within a Microsoft Entra tenant.

[![Diagram of the components of Azure Virtual Desktop in a Microsoft Entra tenant.](media/avd/logical-arch-avd.svg)](media/avd/logical-arch-avd.svg#lightbox)

The elements of the logical architecture are:

- Azure subscription for your Azure Virtual Desktop

    You can distribute the resources in more than one subscription, where each subscription might hold different roles, such as network subscription, or security subscription. This is described in [Cloud Adoption Framework and Azure Landing Zone](/en-us/azure/cloud-adoption-framework/scenarios/wvd/enterprise-scale-landing-zone). The different subscriptions might also hold different environments, such as production, development, and tests environments. It depends on how you want to separate your environment and the number of resources you have in each. One or more subscriptions can be managed together using a Management Group. This gives you the ability to apply permissions with RBAC and Azure policies to a group of subscriptions instead of setting up each subscription individually.
- Azure Virtual Desktop resource group

    An Azure Virtual Desktop resource group isolates Key Vaults, Azure Virtual Desktop service objects and private endpoints.
- Storage resource group

    A storage resource group isolates Azure Files service private endpoints and data sets.
- Session host virtual machines resource group

    A dedicated resource group isolates the virtual machines for their session hosts Virtual Machines, Disk Encryption Set and an Application Security Group.
- Spoke VNet resource group

    A dedicated resource group isolates the spoke VNet resources and a Network Security Group, which networking specialists in your organization can manage.

## What’s in this article?

This article walks through the steps to apply the principles of Zero Trust across the Azure Virtual Desktop reference architecture.

| Step | Task | Zero Trust principle(s) applied |
| --- | --- | --- |
| 1 | Secure your identities with Zero Trust. | Verify explicitly |
| 2 | Secure your endpoints with Zero Trust. | Verify explicitly |
| 3 | Apply Zero Trust principles to Azure Virtual Desktop storage resources. | Verify explicitly  Use least privileged access  Assume breach |
| 4 | Apply Zero Trust principles to hub and spoke Azure Virtual Desktop VNets. | Verify explicitly  Use least privileged access  Assume breach |
| 5 | Apply Zero Trust principles to Azure Virtual Desktop session host. | Verify explicitly  Use least privileged access  Assume breach |
| 6 | Deploy security, governance, and compliance with Azure Virtual Desktop. | Assume breach |
| 7 | Deploy secure management and monitoring to Azure Virtual Desktop. | Assume breach |

## Step 1: Secure your identities with Zero Trust

To apply Zero Trust principles to the identities used in Azure Virtual Desktop:

- Azure Virtual Desktop supports different types of [identities](/en-us/azure/virtual-desktop/prerequisites#supported-identity-scenarios). Use the information in [Securing identity with Zero Trust](deploy/identity) to ensure that your chosen identity types adhere to Zero Trust principles.
- Create a dedicated user account with least privileges to join session hosts to a Microsoft Entra Domain Services or AD DS domain during session host [deployment](/en-us/azure/virtual-desktop/prerequisites#deployment-parameters).

## Step 2: Secure your endpoints with Zero Trust

Endpoints are the devices through which users access the Azure Virtual Desktop environment and session host virtual machines. Use the instructions in the [Endpoint integration overview](integrate/endpoints) and use Microsoft Defender for Endpoint and Microsoft Intune to ensure that your endpoints adhere to your security and compliance requirements.

## Step 3: Apply Zero Trust principles to Azure Virtual Desktop storage resources

Implement the steps in [Apply Zero Trust principles to Storage in Azure](azure-infrastructure-storage) for the storage resources being used in your Azure Virtual Desktop deployment. These steps ensure that you:

- Secure your Azure Virtual Desktop data at rest, in transit, and in use.
- Verify users and control access to storage data with the least privileges.
- Implement private endpoints for storage accounts.
- Logically separate critical data with network controls. Such as separate storage accounts for different host pools and other purposes such as with MSIX app attach file shares.
- Use Defender for Storage for automated threat protection.

Note

In some designs, [Azure NetApp files](/en-us/azure/virtual-desktop/create-fslogix-profile-container) is the storage service of choice for FSLogix profiles for Azure Virtual Desktop via an SMB share. Azure NetApp Files provides built-in security features that include [delegated subnets](/en-us/azure/azure-netapp-files/azure-netapp-files-delegate-subnet) and [security benchmarks](/en-us/security/benchmark/azure/baselines/azure-netapp-files-security-baseline?toc=%2Fazure%2Fazure-netapp-files%2FTOC.json).

## Step 4: Apply Zero Trust principles to hub and spoke Azure Virtual Desktop VNets

A hub VNet is a central point of connectivity for multiple spoke virtual networks. Implement the steps in [Apply Zero Trust principles to a hub virtual network in Azure](azure-infrastructure-networking) for the hub VNet being used to filter outbound traffic from your session hosts.

A spoke VNet isolates the Azure Virtual Desktop workload and contains the session host virtual machines. Implement the steps in [Apply Zero Trust principles to spoke virtual network in Azure](azure-infrastructure-iaas) for the spoke VNet that contains the session host/virtual machines.

Isolate different host pools on separate VNets using [NSG](/en-us/azure/virtual-network/network-security-groups-overview) with the required URL necessary for Azure Virtual Desktop for each subnet. When deploying the private endpoints place them in the appropriate subnet in the VNet based on their role.

Azure Firewall or a network virtual appliance (NVA) firewall can be used to control and restrict outbound traffic Azure Virtual Desktop session hosts. Use the instructions [here](/en-us/azure/firewall/protect-azure-virtual-desktop?tabs=azure) for Azure Firewall to protect session hosts. Force the traffic through the firewall with [User-Defined Routes (UDRs)](/en-us/azure/virtual-network/virtual-networks-udr-overview#user-defined) linked to the host pool subnet. Review the full list of required [Azure Virtual Desktop URLs](/en-us/azure/virtual-desktop/safe-url-list?tabs=azure) to configure your firewall. Azure Firewall provides an Azure Virtual Desktop [FQDN Tag](/en-us/azure/firewall/fqdn-tags#current-fqdn-tags) to simplify this configuration.

## Step 5: Apply Zero Trust principles to Azure Virtual Desktop session hosts

Session hosts are virtual machines that run inside a spoke VNet. Implement the steps in [Apply Zero Trust principles to virtual machines in Azure](azure-infrastructure-virtual-machines) for the virtual machines being created for your session hosts.

[Host pools](/en-us/azure/virtual-desktop/environment-setup#host-pools) should have separated organizational units (OUs) if managed by [group policies](/en-us/windows-server/remote/remote-desktop-services/clients/rdp-files?context=%2Fazure%2Fvirtual-desktop%2Fcontext%2Fcontext) on [Active Directory Domain Services (AD DS)](/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats. You can use Microsoft Defender for Endpoint for session hosts. For more information, see [virtual desktop infrastructure (VDI) devices](/en-us/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-vdi).

## Step 6: Deploy security, governance, and compliance with Azure Virtual Desktop

Azure Virtual Desktop service allows you to use [Azure Private Link](/en-us/azure/virtual-desktop/private-link-overview) to privately connect to your resources by [creating private endpoints](/en-us/azure/virtual-desktop/private-link-setup).

Azure Virtual Desktop has built-in advanced security features to protect session hosts. However, see the following articles to improve the security defenses of your Azure Virtual Desktop environment and session hosts:

- [Azure Virtual Desktop security best practices](/en-us/azure/virtual-desktop/security-guide)
- [Azure security baseline for Azure Virtual Desktop](/en-us/security/benchmark/azure/baselines/azure-virtual-desktop-security-baseline?context=%2Fazure%2Fvirtual-desktop%2Fcontext%2Fcontext)

In addition, see the key design considerations and recommendations for [security, governance, and compliance](/en-us/azure/cloud-adoption-framework/scenarios/wvd/eslz-security-governance-and-compliance) in Azure Virtual Desktop landing zones in accordance with Microsoft's Cloud Adoption Framework.

## Step 7: Deploy secure management and monitoring to Azure Virtual Desktop

Management and continuous monitoring are important to ensure that your Azure Virtual Desktop environment is not engaging in malicious behavior. Use [Azure Virtual Desktop Insights](/en-us/azure/virtual-desktop/insights) to log data and report diagnostic and usage data.

See these additional articles:

- Review recommendations from [Azure Advisor for Azure Virtual Desktop](/en-us/azure/virtual-desktop/azure-advisor-recommendations).
- Use [Microsoft Intune](/en-us/azure/virtual-desktop/management#microsoft-intune) for granular policy management.
- Review and set [RDP Properties](/en-us/azure/virtual-desktop/rdp-properties) for granular settings on a host pool level.

## Recommended training

### Secure an Azure Virtual Desktop deployment

| Training | [Secure an Azure Virtual Desktop deployment](/en-us/training/modules/m365-wvd-security/) |
| --- | --- |
| ![](media/secure-avd-deployment.svg) | Learn about the Microsoft security capabilities that help keep your applications and data secure in your Microsoft Azure Virtual Desktop deployment. |

### Protect your Azure Virtual Desktop deployment by using Azure

| Training | [Protect your Azure Virtual Desktop deployment by using Azure](/en-us/training/modules/protect-virtual-desktop-deployment-azure-firewall/) |
| --- | --- |
| ![](media/protect-virtual-desktop-deployment-azure-firewall.svg) | Deploy Azure Firewall, route all network traffic through Azure Firewall, and configure rules. Route the outbound network traffic from the Azure Virtual Desktop host pool to the service through Azure Firewall. |

### Manage access and security for Azure Virtual Desktop

| Training | [Manage access and security for Azure Virtual Desktop](/en-us/training/paths/manage-access-security/) |
| --- | --- |
| ![](media/manage-access-and-security.svg) | Learn how to plan and implement Azure roles for Azure Virtual Desktop and implement Conditional Access policies for remote connections. This learning path aligns with exam AZ-140: Configuring and Operating Microsoft Azure Virtual Desktop. |

### Design for user identities and profiles

| Training | [Design for user identities and profiles](/en-us/training/modules/design-user-identities-profiles/) |
| --- | --- |
| ![](media/3-design-for-user-identities-and-profiles.svg) | Your users require access to those applications both on-premises and in the cloud. You use the Remote Desktop client for Windows Desktop to access Windows apps and desktops remotely from a different Windows device. |

For more training on security in Azure, see these resources in the Microsoft catalog:[Security in Azure](/en-us/training/browse/?subjects=security&amp;products=azure)