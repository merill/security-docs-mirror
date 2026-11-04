---
layout: Conceptual
title: Zero Trust integration with Networks overview | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/integrate/networks
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Independent software vendors (ISVs) integrate their solutions with Azure Firewall Manager to help customers adopt a Zero Trust model and keep their organizations secure.
ms.date: 2025-02-21T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.collection:
- zerotrust-partner
locale: en-us
document_id: c470c8f5-0ac5-6f1b-e4e7-f2a5abb87109
document_version_independent_id: bc0054ef-8967-66c6-4bec-0819d7bb2d62
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/integrate/networks.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/integrate/networks
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/integrate/networks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e8fdebed-2921-4997-a75a-fa863723a535
- https://authoring-docs-microsoft.poolparty.biz/devrel/29bdf9a9-815a-40ec-b62b-fd9e5b6d9428
- https://authoring-docs-microsoft.poolparty.biz/devrel/f98c9a19-e481-4f15-8047-76b641e6ed57
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/cf1e63a8-325f-42be-b60c-d84a95a42b1f
- https://authoring-docs-microsoft.poolparty.biz/devrel/fe6fa0bc-4e6f-4083-9ca9-3576e60f223c
- https://authoring-docs-microsoft.poolparty.biz/devrel/f5685781-a4fd-40f1-8126-59abde4643bf
platformId: d1723612-93dd-f2a2-5e38-50641e3bdbc6
---

# Zero Trust integration with Networks overview | Microsoft Learn

![](../media/icon-networks-medium.png)

Traditional enterprise networks are designed to provide users access to applications and data hosted in company operated data centers with strong perimeter security. However, the modern workplace increasingly uses services and data outside the corporate firewall. Apps and services moved to the cloud. Users need to access them from various work and personal devices.

Network solutions are an important piece of Zero Trust. They verify that the ingress and egress at the edge of the network is allowable and inspect traffic for malicious content. They support least privilege access and the principle of "assume breach" by allowing organizations to segment networks and only connect users to the segment of the network they need access to.

## Zero Trust integration with Networks guidance

Independent Software Vendor (ISV) partners integrate with Microsoft's network solutions and bring their own security expertise to enhance the products.

In this article, we discuss our Network integration partners so customers can use familiar, best-in-breed, non-Microsoft security as a service (SECaaS) offerings to protect Internet access for their users. For more information about becoming an ISV partner, see [Microsoft 365 Networking Partner Program](/en-us/microsoft-365/enterprise/microsoft-365-networking-partner-program).

### Gateway Load Balancer

Gateway Load Balancer is a product in the Azure Load Balancer portfolio catered for high performance and high availability scenarios with non-Microsoft Network Virtual Appliances (NVAs). It enables you to easily deploy, scale, and manage NVAs.

### Virtual WAN

Virtual WAN is a networking service that brings many networking, security, and routing functionalities together to provide a single operational interface. It provides a hub and spoke architecture with scale and performance built in for branches (VPN/SD-WAN devices), users (Azure VPN/OpenVPN/IKEv2 clients), ExpressRoute circuits, and virtual networks. It enables a global transit network architecture, where the cloud hosted network *hub* enables transitive connectivity between endpoints that might be distributed across different types of *spokes*.

### Azure Web Application Firewall

Azure Web Application Firewall (WAF) provides centralized protection of your web applications from common exploits and vulnerabilities. WAF can be deployed with Azure Application Gateway, Azure Front Door, and Azure Content Delivery Network (CDN) service from Microsoft. WAF on Azure CDN is currently under public preview.

### DDOS Protection

Azure DDoS Protection, combined with application design best practices, provides enhanced DDoS mitigation features to defend against DDoS attacks. Automatic tuning helps protect your specific Azure resources in a virtual network. Protection is simple to enable on any new or existing virtual network, and it requires no application or resource changes.

### Azure Firewall Manager

[Azure Firewall Manager](/en-us/azure/firewall-manager/overview) is a security management service that provides central security policy and route management for cloud-based security perimeters.

Security partner providers [integrated with Azure Firewall Manager](/en-us/azure/firewall-manager/trusted-security-partners) so customers can use familiar, best-in-breed, non-Microsoft security as a service (SECaaS) offerings to protect Internet access for their users. Customers can secure a hub with a supported security partner and route and filter Internet traffic from Virtual Networks (VNets) or branch locations within a region. Hubs can be deployed in multiple Azure regions to get connectivity and security anywhere across the globe, using the security partner’s offering for Internet/SaaS application traffic and Azure Firewall for private traffic in the secured hubs.

The supported security partners are Zscaler, Check Point, and iboss.

![Architectural network diagram illustrating ZScaler, Check Point, and iboss solutions with a bi-directional connection to a secured vHub. The vHub is in the same vNet as a hub VNET hosted in another Azure region. The vHub is also connected to the company headquarters with a virtual WAN and by a VPN to end user devices. The hub VNET is connected by a VPN to a data center.](../media/integrate/networks/firewall-security-partners.png)

If your solution connects with Microsoft 365, you can use the guidance from the [Microsoft 365 Networking Partner Program](/en-us/microsoft-365/enterprise/microsoft-365-networking-partner-program) to ensure that your solution follows [Microsoft 365 network connectivity principles](/en-us/microsoft-365/enterprise/microsoft-365-network-connectivity-principles). The purpose of this program is to facilitate great customer experience with Microsoft 365 through easy discovery of validated partner solutions that consistently demonstrate alignment to key principles for optimal Microsoft 365 connectivity in customer deployments.