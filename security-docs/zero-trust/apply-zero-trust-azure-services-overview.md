---
layout: Conceptual
title: How do I apply Zero Trust principles to Azure services? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/apply-zero-trust-azure-services-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: An overview of the set of articles that describe how to apply Zero Trust principles to Microsoft Azure services.
ms.date: 2025-05-06T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- msftsolution-azureiaas
- msftsolution-overview
- zerotrust-solution
- zerotrust-azure
locale: en-us
document_id: 7399e67b-7225-6e1d-96ec-35303d2c8e03
document_version_independent_id: 7399e67b-7225-6e1d-96ec-35303d2c8e03
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/apply-zero-trust-azure-services-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/apply-zero-trust-azure-services-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/apply-zero-trust-azure-services-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: fa11158d-f3ee-460f-e761-b0a6f545912f
---

# How do I apply Zero Trust principles to Azure services? | Microsoft Learn

**Summary:** To apply Zero Trust principles to Azure services, you need to determine the set of infrastructure components required to support your desired workload, and then apply Zero Trust principles to those components.

This series of articles helps you apply the [principles of Zero Trust](zero-trust-overview) to your services in Microsoft Azure using a multi-disciplinary methodology. Zero Trust is a security strategy. It is not a product or a service, but an approach in designing and implementing the following set of security principles:

- Verify explicitly
- Use least privileged access
- Assume breach

Implementing the Zero Trust “never trust, always verify” approach requires changes to cloud infrastructure, deployment strategy, and implementation.

These articles show you how to apply Zero Trust approach to these new or already deployed Azure services:

- [Azure IaaS overview](azure-infrastructure-overview)
    - [Azure storage](azure-infrastructure-storage)
    - [Virtual machines](azure-infrastructure-virtual-machines)
    - [Spoke virtual networks](azure-infrastructure-iaas)
    - [Spoke virtual networks with Azure PaaS services](azure-infrastructure-paas)
    - [Hub virtual networks](azure-infrastructure-networking)
- [Azure Virtual Desktop](azure-infrastructure-avd)
- [Azure Virtual WAN](azure-virtual-wan)
- [IaaS applications in Amazon Web Services](secure-iaas-apps)
- [Microsoft Sentinel and Microsoft Defender XDR](/en-us/security/zero-trust/siem-xdr-overview)

## Content architecture

Here is the content architecture for this set of articles that contain the set of platform and workload articles to apply Zero Trust principles to Azure services.

[![The stack diagram for the set of articles that describe how you apply Zero Trust to Azure services, starting at the bottom of the stack and moving up to the desired workload.](media/apply-zero-trust-azure-services-overview/content-architecture.svg)](media/apply-zero-trust-azure-services-overview/content-architecture.svg#lightbox)

You apply the guidance in the articles in a stack from the bottom up.

| Workload | Platform set of articles (from the bottom up) |
| --- | --- |
| IaaS apps in Amazon Web Services (AWS) | - Cloud identity infrastructure<br>- Microsoft Sentinel and Microsoft Defender XDR |
| Spoke VNet with Azure IaaS services | - Cloud identity infrastructure<br>- Microsoft Sentinel and Microsoft Defender XDR<br>- Hub VNets (traditional) OR Azure Virtual WAN (Microsoft-managed)<br>- Storage |
| Azure Virtual Desktop or virtual machines | - Cloud identity infrastructure<br>- Microsoft Sentinel and Microsoft Defender XDR<br>- Hub VNets (traditional) OR Azure Virtual WAN (Microsoft-managed)<br>- Storage<br>- Spoke VNet with Azure IaaS services |

It’s important to note that the guidance in this series of articles is more specific for this type of architecture than the guidance provided in the [Cloud Adoption Framework](/en-us/azure/cloud-adoption-framework/get-started/index) and [Azure landing zone](/en-us/azure/cloud-adoption-framework/ready/landing-zone/index) architectures. If you have applied the guidance in either of these resources, be sure to also review this series of articles for additional recommendations.

## Additional articles for Azure services

Take a look at these additional articles for applying Zero Trust principles to Azure services:

- For Azure IaaS:
    - [Azure storage](azure-infrastructure-storage)
    - [Virtual machines](azure-infrastructure-virtual-machines)
    - [Spoke virtual networks](azure-infrastructure-iaas)
    - [Hub virtual networks](azure-infrastructure-networking)
- [Azure Virtual Desktop](azure-infrastructure-avd)
- [Azure Virtual WAN](azure-virtual-wan)
- [IaaS applications in Amazon Web Services](secure-iaas-apps)
- [Protect Azure resources from cyberattacks](azure-protect-resources-cyberattacks)
- [Microsoft Sentinel and Microsoft Defender XDR](/en-us/security/zero-trust/siem-xdr-overview)

See these additional articles for applying Zero Trust principles to Azure networking:

- [Encrypt your network traffic](azure-networking-encryption)
- [Segment your network traffic](azure-networking-segmentation)
- [Gain visibility into your network traffic](azure-networking-visibility)
- [Discontinue legacy network security technology](azure-networking-legacy)

## References

Refer to the links below to learn about the various services and technologies mentioned in this article.

- [What is Azure - Microsoft Cloud Services](https://azure.microsoft.com/resources/cloud-computing-dictionary/what-is-azure/)
- [Introduction to Azure security](/en-us/azure/security/fundamentals/overview)
- [Zero Trust implementation guidance](zero-trust-overview)
- [Overview of the Microsoft cloud security benchmark](/en-us/security/benchmark/azure/overview)
- [Security baselines for Azure overview](/en-us/security/benchmark/azure/security-baselines-overview)
- [Building the first layer of defense with Azure security services](/en-us/azure/architecture/solution-ideas/articles/azure-security-build-first-layer-defense)
- [Microsoft Cybersecurity Reference Architectures](microsoft-reference-architecture)

## Additional Zero Trust documentation

Use additional Zero Trust content based on a documentation set or the roles in your organization.

### Documentation set

Follow this table for the best Zero Trust documentation sets for your needs.

| Documentation set | Helps you... | Roles |
| --- | --- | --- |
| [Adoption framework](adopt/zero-trust-adoption-overview) for phase and step guidance for key business solutions and outcomes | Apply Zero Trust protections from the C-suite to the IT implementation. | Security architects, IT teams, and project managers |
| [Assessment and progress tracking resource](/en-us/security/zero-trust/zero-trust-assessment-progress-tracking-resources) | Assess your infrastructure's readiness and track your progress. | Security architects, IT teams, and project managers |
| [Zero Trust partner kit](zero-trust-partner-kit) | Co-branded tracking resources, workshop, and architecture illustrations | Partners and security architects |
| [Concepts and deployment objectives](deploy/overview) for general deployment guidance for technology areas | Apply Zero Trust protections aligned with technology areas. | IT teams and security staff |
| [Zero Trust for small businesses](guidance-smb-partner) | Apply Zero Trust principles to small business customers. | Customers and partners working with Microsoft 365 for business |
| [Zero Trust deployment plan with Microsoft 365](/en-us/microsoft-365/security/microsoft-365-zero-trust?bc=%2fsecurity%2fzero-trust%2fbreadcrumb%2ftoc.json&amp;toc=%2fsecurity%2fzero-trust%2ftoc.json) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to your Microsoft 365 tenant. | IT teams and security staff |
| [Zero Trust for Microsoft Copilots](copilots/apply-zero-trust-copilots-overview) for stepped and detailed design and deployment guidance | Apply Zero Trust protections to Microsoft Copilots. | IT teams and security staff |
| [Partner integration with Zero Trust](integrate/overview) for design guidance for technology areas and specializations | Apply Zero Trust protections to partner Microsoft cloud solutions. | Partner developers, IT teams, and security staff |
| [Develop using Zero Trust principles](develop/overview) for application development design guidance and best practices | Apply Zero Trust protections to your application. | Application developers |