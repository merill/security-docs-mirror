---
layout: Conceptual
title: How do I apply Zero Trust principles to Azure IaaS? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-infrastructure-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: An overview of how to apply Zero Trust principles to Azure IaaS components and infrastructure.
ms.date: 2025-05-20T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- msftsolution-azureiaas
- msftsolution-overview
- zerotrust-solution
- zerotrust-azure
locale: en-us
document_id: a3d9644a-42d6-3ab5-5e03-bd7d1e1df424
document_version_independent_id: a3d9644a-42d6-3ab5-5e03-bd7d1e1df424
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-infrastructure-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-infrastructure-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-infrastructure-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/20ed8455-bc18-4537-87a4-83784e7b2a39
- https://authoring-docs-microsoft.poolparty.biz/devrel/2ed91286-6cf7-4b83-810d-75d0ee3b09dd
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9a7f703b-30bb-4d62-9eb4-97213f571849
- https://authoring-docs-microsoft.poolparty.biz/devrel/6735bd7e-4f7b-457d-b58c-29e6f0198677
platformId: 222dc238-b48d-ba4d-3512-405ed08ad59e
---

# How do I apply Zero Trust principles to Azure IaaS? | Microsoft Learn

**Summary:** To apply Zero Trust principles to Azure IaaS components and infrastructure, you must first understand the common reference architecture and the components of Azure storage, virtual machines, and spoke and hub virtual networks.

This series of articles help you apply the principles of Zero Trust to your workloads in Microsoft Azure IaaS based on a multi-disciplinary approach to applying the Zero Trust principles. Zero Trust is a security strategy. It isn't a product or a service, but an approach in designing and implementing the following set of security principles:

- Verify explicitly
- Use least privileged access
- Assume breach

Implementing the Zero Trust mindset to "assume breach, never trust, always verify" requires changes to cloud infrastructure, deployment strategy, and implementation.

These initial series of five articles (including this introduction) show you how to apply Zero Trust approach to a common IT business scenario based on infrastructure services. The work is broken into units that can be configured together as follows:

- [Azure storage](azure-infrastructure-storage)
- [Virtual machines](azure-infrastructure-virtual-machines)
- [Spoke virtual networks (VNets) for virtual machine-based workloads](azure-infrastructure-iaas)
- [Hub VNets to support access to many workloads in Azure](azure-infrastructure-networking)

For more information, see [Apply Zero Trust principles to Azure Virtual Desktop](azure-infrastructure-avd).

Note

Additional articles will be added to this series in the future, including how organizations can apply a Zero Trust approach to applications, networking, data, and DevOps services based on real IT business environments.

Important

This Zero Trust guidance describes how to use and configure several security solutions and features available on Azure for a reference architecture. Several other resources also provide security guidance for these solutions and features, including:

- [Microsoft Cloud Security Benchmark](/en-us/security/benchmark/azure/introduction)
- [Microsoft Cloud Security Baseline](/en-us/security/benchmark/azure/security-baselines-overview)

To describe how to apply a Zero Trust approach, this guidance targets a common pattern used in production by many organizations: a virtual-machine-based application hosted in a virtual network (and IaaS application). This is a common pattern for organizations migrating on-premises applications to Azure, which is sometimes referred to as "lift-and-shift." The reference architecture includes all components necessary to support this application, including storage services and a hub virtual network.

The reference architecture reflects a common deployment pattern in production environments. It isn't based on the enterprise-scale landing zones recommended in the Cloud Adoption Framework (CAF), although many of the best practices in CAF are included in the reference architecture, such as using a dedicated virtual network to host components that broker access to the application (hub virtual network).

If you're interested in learning about the guidance recommended in the Cloud Adoption Framework Azure landing zones, see these resources:

- [Get started with the Cloud Adoption Framework](/en-us/azure/cloud-adoption-framework/get-started/index)
- [What is an Azure landing zone?](/en-us/azure/cloud-adoption-framework/ready/landing-zone/index)

## Reference architecture

The following figure shows the reference architecture for this Zero Trust guidance.

[![Diagram of the reference architecture for applying Zero Trust to Azure IaaS that contains different types of users, common applications running on virtual machines, PaaS services, and storage.](media/azure-infra-overview/azure-infra-overview-reference-architecture-1.svg)](media/azure-infra-overview/azure-infra-overview-reference-architecture-1.svg#lightbox)

This architecture contains:

- Multiple IaaS components and elements, including different types of users and IT consumers accessing the app from different sites. such as Azure, the internet, on-premises, and branch offices.
- A common three-tier application containing a front end tier, application tier, and data tier. All tiers run on virtual machines within a virtual network named SPOKE. Access to the app is protected by another virtual network named HUB that contains additional security services.
- Some of the most used PaaS services on Azure that support IaaS applications, including role-based access control (RBAC) and Microsoft Entra ID, which contribute to the Zero Trust security approach.
- Storage Blobs and Storage Files that provide object storage for the applications and files shared by users.

This series of articles walk through the recommendations for implementing Zero Trust for the reference architecture by addressing each of these larger pieces hosted in Azure, as shown here.

[![Diagram of the reference architecture for applying Zero Trust to Azure IaaS that shows the grouped components for storage, virtual machines, and spoke and hub virtual networks.](media/azure-infra-overview/azure-infra-overview.svg)](media/azure-infra-overview/azure-infra-overview.svg#lightbox)

The diagram outlines the larger areas of the architecture that are addressed by each article in this series:

1. [Azure Storage Services](azure-infrastructure-storage)
2. [Virtual machines](azure-infrastructure-virtual-machines)
3. [Spoke VNets](azure-infrastructure-iaas)
4. [Hub VNets](azure-infrastructure-networking)

It’s important to note that the guidance in this series of articles is more specific for this type of architecture than the guidance provided in the Cloud Adoption Framework and Azure landing zone architectures. If you applied the guidance in either of these resources, be sure to also review this series of articles for additional recommendations.

## Understanding Azure components

The reference architecture diagram provides a topological view of the environment. It’s also valuable to see logically how each of the components can be organized within the Azure environment. The following diagram provides a way to organize your subscriptions and resource groups. Your Azure subscriptions might be organized differently.

[![Diagram of the logical architecture for applying Zero Trust to Azure IaaS showing subscriptions, Microsoft Defender for Cloud and Azure Monitor, and resource groups within a Microsoft Entra ID tenant.](media/azure-infra-overview/azure-infra-overview-subscription-architecture-3.svg)](media/azure-infra-overview/azure-infra-overview-subscription-architecture-3.svg#lightbox)

In this diagram, the Azure infrastructure is contained within a Microsoft Entra ID tenant. The following table describes the different sections shown in the diagram.

- Azure subscriptions

    You can distribute the resources in more than one subscription, where each subscription might hold different roles, such as network subscription, or security subscription. This is described in the Cloud Adoption Framework and Azure Landing Zone documentation previously referenced. The different subscriptions can also hold different environments, such as production, development, and tests environments. It depends on how you want to separate your environment and the number of resources you'll have in each. One or more subscriptions can be managed together using a Management Group. This gives you the ability to apply permissions with role based access control (RBAC) and Azure policies to a group of subscriptions instead of setting up each subscription individually.
- Microsoft Defender for Cloud and Azure Monitor

    For each Azure subscription, a set of Azure Monitor solutions and Defender for Cloud is available. If you manage these subscriptions through a Management Group, you can consolidate in a single portal for Azure Monitor and Defender for Cloud functionality. For example, Secure Score, provided by Defender for Cloud, are consolidated for all your subscriptions, using a Management Group as the scope.
- Storage resource group (1)

    The storage account is contained in a dedicated resource group. You can isolate each storage account in a different resource group for more granular permission control. Azure storage services are contained within a dedicated storage account. You can have one storage account for each type of storage workload, for example an Object Storage (also called Blob storage) and Azure Files. This provides more granular access control and can improve performance.
- Virtual machines resource group (2)

    Virtual machines are contained in one resource group. You can also have each virtual machine type for workload tiers such as front end, application, and data in different resource groups to further isolate access control.
- Spoke (3) and hub (4) virtual network resource groups in separate subscriptions

    The network and other resources for each of the VNets in the reference architecture are isolated within dedicated resource groups for spoke and hub VNets. This organization works well when responsibility for these live on different teams. Another option is to organize these components by putting all network resources in one resource group and security resources in another. It depends on how your organization is set up to manage these resources.

## Threat Protection with Microsoft Defender for Cloud

**Microsoft Defender for Cloud** is an extended detection and response (XDR) solution that automatically collects, correlates, and analyzes signal, threat, and alert data from across your environment. Defender for Cloud is intended to be used together with Microsoft Defender XDR to provide a greater breadth of correlated protection of your environment, as shown in the following diagram.

[![Diagram of the logical architecture of Microsoft Defender for Cloud and Microsoft Defender XDR that provides threat protection for Azure IaaS components.](media/azure-infra-overview/azure-infra-overview-threat-protection.svg)](media/azure-infra-overview/azure-infra-overview-threat-protection.svg#lightbox)

In the diagram:

- Defender for Cloud is enabled for a management group that includes multiple Azure subscriptions.
- Microsoft Defender XDR is enabled for Microsoft 365 apps and data, SaaS apps that are integrated with Microsoft Entra ID, and on-premises Active Directory Domain Services (AD DS) servers.

For more information about configuring management groups and enabling Defender for Cloud, see:

- [Organize subscriptions into management groups and assign roles to users](/en-us/azure/defender-for-cloud/management-groups-roles)
- [Enable Defender for Cloud on all subscriptions in a management group](/en-us/azure/defender-for-cloud/onboard-management-group)

## Security solutions in this series of articles

Zero Trust involves applying multiple disciplines of security and information protection together. In this series of articles, this multi-discipline approach is applied to each of the units of work for infrastructure components as follows:

**[Apply Zero Trust principles to Azure storage](azure-infrastructure-storage)**

1. Protect data in all three modes: data at rest, data in transit, and data in use
2. Verify users and control access to storage data with the least privileges
3. Logically separate or segregate critical data with network controls
4. Use Defender for Storage for automated threat detection and protection

**[Apply Zero Trust principles to virtual machines in Azure](azure-infrastructure-virtual-machines)**

1. Configure logical isolation for virtual machines
2. Leverage Role Based Access Control (RBAC)
3. Secure virtual machine boot components
4. Enable customer-managed keys and double encryption
5. Control the applications installed on virtual machines
6. Configure secure access
7. Set up secure maintenance of virtual machines
8. Enable advanced threat detection and protection

**[Apply Zero Trust principles to a spoke VNet in Azure](azure-infrastructure-iaas)**

1. Leverage Microsoft Entra RBAC or set up custom roles for networking resources
2. Isolate infrastructure into its own resource group
3. Create a network security group for each subnet
4. Create an application security group for each virtual machine role
5. Secure traffic and resources within the virtual network
6. Secure access to the virtual network and application
7. Enable advanced threat detection and protection

**[Apply Zero Trust principles to a hub VNet in Azure](azure-infrastructure-networking)**

1. Secure Azure Firewall Premium
2. Deploy Azure DDoS Protection Standard
3. Configure network gateway routing to the firewall
4. Configure threat protection

## Technical illustrations

These illustrations are replicas of the reference illustrations in these articles. Download and customize these for your own organization and customers. Replace the Contoso logo with your own.

| Item | Description |
| --- | --- |
| [![thumbnail picture 1](media/thumb-zero-trust-iaas-contoso.png)](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx)[Download Visio](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS** Use these illustrations with these articles:  - [Overview](azure-infrastructure-overview) - [Azure storage](azure-infrastructure-storage) - [Virtual machines](azure-infrastructure-virtual-machines) - [Azure spoke virtual networks](azure-infrastructure-iaas) - [Azure hub virtual networks](azure-infrastructure-networking) |
| [![thumbnail picture 2](media/thumb-zero-trust-iaas-contoso-poster.png)](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx)[Download Visio](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS — One page poster** A one-page overview of the process for [applying the principles of Zero Trust to Azure IaaS environments](azure-infrastructure-overview). |

For additional technical illustrations, see [Zero Trust illustrations for IT architects and implementers](zero-trust-tech-illus).

## Recommended training for Zero Trust

The following are the recommended training modules for Zero Trust.

### Azure management and governance

| Training | [Describe Azure management and governance](/en-us/training/paths/describe-azure-management-governance/) |
| --- | --- |
| ![](media/describe-azure-management-governance-resized.png) | The Microsoft Azure Fundamentals training is composed of three learning paths: Microsoft Azure Fundamentals: Describe cloud concepts, Describe Azure architecture and services, and Describe Azure management and governance. Microsoft Azure Fundamentals: Describe Azure management and governance is the third learning path in Microsoft Azure Fundamentals. This learning path explores the management and governance resources available to help you manage your cloud and on-premises resources. This learning path helps prepare you for [Exam AZ-900: Microsoft Azure Fundamentals.](/en-us/certifications/exams/az-900) |

### Configure Azure Policy

| Training | [Configure Azure Policy](/en-us/training/modules/configure-azure-policy/) |
| --- | --- |
| ![](media/azure-policy-configure.png) | Learn how to configure Azure Policy to implement compliance requirements. In this module, you learn how to: - Create management groups to target policies and spending budgets.<br>- Implement Azure Policy with policy and initiative definitions.<br>- Scope Azure policies, and determine compliance. |

### Manage security operation

| Training | [Manage Security operation](/en-us/training/paths/manage-security-operation/) |
| --- | --- |
| ![](media/operation-manage-security-resized.png) | Once you have deployed and secured your Azure environment, learn to monitor, operate, and continuously improve the security of your solutions. This learning path helps prepare you for [Exam AZ-500: Microsoft Azure Security Technologies](/en-us/certifications/exams/az-500). |

### Configure storage security

| Training | [Configure Storage security](/en-us/training/modules/configure-storage-security/) |
| --- | --- |
| ![](media/storage-security-configure.png) | Learn how to configure common Azure Storage security features like storage access signatures.In this module, you learn how to:- Configure a shared access signature (SAS), including the uniform resource identifier (URI) and SAS parameters.<br>- Configure Azure Storage encryption.<br>- Implement customer-managed keys.<br>- Recommend opportunities to improve Azure Storage security. |

### Configure Azure Firewall

| Training | [Configure Azure Firewall](/en-us/training/modules/configure-azure-firewall/) |
| --- | --- |
| ![](media/azure-firewall-configure.png) | You will learn how to configure the Azure Firewall including firewall rules.After completing this module, you will be able to:- Determine when to use Azure Firewall.<br>- Implement Azure Firewall including firewall rules. |

For more training on security in Azure, see these resources in the Microsoft catalog:[Security in Azure | Microsoft Learn](/en-us/training/browse/?subjects=security&amp;products=azure)