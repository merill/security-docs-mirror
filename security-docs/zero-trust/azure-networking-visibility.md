---
layout: Conceptual
title: Apply Zero Trust principles to gain visibility into network traffic | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-networking-visibility
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: duau
author: duongau
description: Learn how to apply Zero Trust principles to gain visibility into network traffic.
ms.date: 2024-06-12T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.reviewer: adtork, maroja, maalgeba
ms.topic: reference-architecture
ms.collection:
- msftsolution-azureiaas
- msftsolution-scenario
- zerotrust-solution
- zerotrust-azure
locale: en-us
document_id: 6336f205-982d-9e73-4063-56e59fa843f0
document_version_independent_id: 6336f205-982d-9e73-4063-56e59fa843f0
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-networking-visibility.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-networking-visibility
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-networking-visibility.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/85ee13c4-5d0b-41b0-895d-b7e834668123
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/7e79a0d4-3b49-4899-aac2-fbdd26ca15a8
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 17737f85-64b8-eb0a-437d-2f4114591f7b
---

# Apply Zero Trust principles to gain visibility into network traffic | Microsoft Learn

This article provides guidance for applying the [principles of Zero Trust](zero-trust-overview) for segmenting networks in Azure environments. Here are the Zero Trust principles.

| Zero Trust principle | Definition |
| --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses.  This principle is met by using analytics to get visibility into the network traffic in your Azure infrastructure. |

This article is a part of a [series of articles](azure-networking-overview) that demonstrate how to apply the principles of Zero Trust to Azure networking.

The types of network traffic covered in this article are:

- Centralized
- East-west traffic, which is traffic flows between your Azure virtual networks (VNets) and your Azure services and on-premises network
- North-south, which are traffic flows between your Azure environment and the Internet

## Reference architecture

The following diagram shows the reference architecture for this Zero Trust guidance for traffic inspection between on-premises and Azure VNets, between Azure VNets and Azure services, and between your Azure environment and the Internet.

[![Diagram showing the reference architecture and east-west and north-south traffic flows.](media/azure-networking/azure-networking-visibility-reference-architecture.svg)](media/azure-networking/azure-networking-visibility-reference-architecture.svg#lightbox)

This reference architecture includes:

- Azure IaaS workloads running on Azure virtual machines.
- Azure services.
- An Internet edge VNet that contains [Azure DDoS Protection](/en-us/azure/ddos-protection/ddos-protection-overview), an [Azure Firewall](/en-us/azure/firewall/overview), and an [Azure Web Application Firewall](/en-us/azure/web-application-firewall/overview) (WAF).
- Arrows showing east-west and north-south traffic flows.

## What’s in this article?

Zero Trust principles are applied across the reference architecture. The following table describes the recommendations for ensuring the visibility of network traffic across this architecture for the **Assume breach** Zero Trust principle.

| Step | Task |
| --- | --- |
| 1 | Implement a centralized traffic inspection point. |
| 2 | Implement east-west traffic inspection. |
| 3 | Implement north-south traffic inspection. |

## Step 1: Implement a centralized traffic inspection point

Centralized traffic inspection gives you the ability to control and visualize the traffic going in and out of your network. [Hub and spoke VNets](/en-us/azure/architecture/networking/architecture/hub-spoke) and [Azure Virtual WAN](/en-us/azure/virtual-wan/virtual-wan-about) are the two most common network topologies in Azure. They have different capabilities and features in how they connect networks. In both designs, the hub VNet is the central network and is used to split workloads into applications and workloads from the hub VNet to spoke VNets. The centralized inspection includes traffic that flows north-south, east-west, or both.

### Hub and spoke topology

One of the characteristics of a hub and spoke model is that the VNets are all managed by you. A customer-hub managed VNet serves as a shared VNet to which other spoke VNets connect. This centralized VNet is typically used:

- To establish hybrid connectivity to on-premises networks.
- For traffic inspection and segmentation using Azure Firewall or third-party network virtual appliances (NVAs).
- To centralize application delivery service inspection such as [Azure Application Gateway](/en-us/azure/application-gateway/overview) with WAF.

In this topology, you place an Azure Firewall or an NVA in the hub VNet and configure [user defined routes](/en-us/azure/virtual-network/virtual-networks-udr-overview) (UDRs) to direct traffic from spoke VNets and from your on-premises network to the hub VNet. The Azure Firewall or NVA can also serve as a route engine to route traffic between spoke virtual networks. One of the most important features of a customer-managed VNet hub and spoke model is the granular control of traffic using UDRs and the ability to manually modify routing, segmentation, and propagation of those routes.

### Azure Virtual WAN

Azure Virtual WAN is an Azure-managed hub VNet that contains Route Service instances under the hood that oversee propagating routes from and to all the branches and all the spokes. It effectively enables any-to-any connectivity.

One of the large differences with a managed VNet (called managed virtual hub) is that granularity of routing control is abstracted for the users. Some of the key benefits include:

- Simplified route management using native any-to-any connectivity. If you need traffic isolation, you can manually configure custom route tables or static routes within the default route table.
- Only Virtual Network Gateways, Azure Firewall, and approved NVAs or software-defined WAN (SD-WAN) devices can be deployed within the hub. Centralized services such as DNS and Application Gateways need to be on regular spoke VNets. Spokes need to be attached to the virtual hubs using VNet peering.

Managed VNets are best suited for:

- Large scale deployments across regions that need transit connectivity providing traffic inspection to and from any location.
- More than 30 branches sites or over 100 Internet Protocol security (IPsec) tunnels.

Some of the best features of Virtual WAN are the scalability routing infrastructure and interconnectivity. Examples of scalability include throughput of 50 Gbps per hub and 1,000 branch sites. To further scale, multiple virtual hubs can be interconnected to create a larger Virtual WAN mesh network. Another benefit of Virtual WAN is the ability to simplify the routing for traffic inspection by injecting prefixes with the click of a button.

Each design carries its own advantages and disadvantages. The appropriate choice should be determined based on anticipated future growth and management overhead requirements.

## Step 2: Implement east-west traffic inspection

East-west traffic flows include VNet-to-VNet and VNet-to-on-premises. To inspect traffic between east-west, you can deploy an Azure Firewall or an NVA in the hub virtual network. This requires UDRs to direct private traffic to the Azure Firewall or NVA for inspection. Within the same VNet you can utilize network security groups for access control, but if you need deeper control with inspection you can use a local firewall or a centralized firewall in the hub virtual network with the use of UDRs.

With Azure Virtual WAN, you can have the Azure Firewall or an NVA inside the virtual hub for centralized routing. You can utilize [Azure Firewall Manager](/en-us/azure/firewall-manager/overview) or routing intent to inspect all private traffic. If you want to customize inspection, you can have the Azure Firewall or NVA in the virtual hub to inspect desired traffic. The easiest way to direct traffic in a Virtual WAN environment is to enable routing intent for private traffic. This feature pushes private address prefixes (RFC 1918) to all spokes connected to the hub. Any traffic destined to a private IP address will be directed to the virtual hub for inspection.

Each method has its own advantages and disadvantages. The advantage of using routing intent is simplification of UDR management, however you can’t customize inspection per connection. The advantage of not using routing intent or Firewall Manager is that you can customize inspection. The disadvantage is that you can’t do inter-region traffic inspection.

The following diagram shows east-west traffic inside the Azure environment.

[![Diagram showing the reference architecture with east-west traffic inside the Azure environment.](media/azure-networking/azure-networking-visibility-east-west.svg)](media/azure-networking/azure-networking-visibility-east-west.svg#lightbox)

For visibility into your network traffic within Azure, Microsoft recommends the implementation of an Azure Firewall or an NVA in your VNet. Azure Firewall can inspect both network layer and application layer traffic. Furthermore, Azure Firewall provides extra features such as Intrusion Detection and Prevention System (IDPS), Transport Layer Security (TLS) inspection, URL filtering, and Web Categories filtering.

The inclusion of Azure Firewall or an NVA in your Azure network is crucial for adhering to the **Assume breach** Zero Trust principle for networking. Given that breaches can transpire whenever data traverses a network, it's essential to understand and control what traffic is permitted to reach its destination. Azure Firewall, UDRs, and network security groups play a crucial role in enabling a secure traffic model by permitting or denying traffic across workloads.

To see more details about your VNet traffic flows, you can enable [VNet flow logs](/en-us/azure/network-watcher/vnet-flow-logs-overview) or [NSG flow logs](/en-us/azure/network-watcher/nsg-flow-logs-overview). Flow log data is stored in an Azure Storage account where you can access and export it to a visualization tool, such as [Azure Traffic Analytics](/en-us/azure/network-watcher/traffic-analytics). With Azure Traffic Analytics, you can find unknown or unwanted traffic, monitor the traffic level and bandwidth usage, or filter for specific traffic to understand your application behavior.

## Step 3: Implement north-south traffic inspection

North-south traffic typically includes traffic between private networks and the Internet. To inspect north-south traffic in a hub and spoke topology, you can utilize UDRs to direct the traffic to an Azure Firewall instance or an NVA. For dynamic advertisement, you can use an [Azure Route Server](/en-us/azure/route-server/overview) with an NVA that supports BGP to direct all Internet-bound traffic from VNets to the NVA.

In Azure Virtual WAN, to direct north-south traffic from the VNets to the Azure Firewall or NVA supported in virtual hub, you can use these common scenarios:

- Use an NVA or Azure Firewall in the [virtual hub that is controlled with Routing-Intent](/en-us/azure/virtual-wan/how-to-routing-policies) or with Azure Firewall Manager to direct north-south traffic.
- If your NVA isn’t supported inside the virtual hub, you can deploy it in a spoke VNet and direct the traffic with UDRs for inspection. The same applies to Azure Firewall. Alternatively, you can also BGP peer an NVA in a spoke with the virtual hub to advertise a default route (0.0.0.0/0).

The following diagram shows north-south traffic between an Azure environment and the Internet.

[![Diagram showing the reference architecture and north-south traffic between the Azure environment and the Internet.](media/azure-networking/azure-networking-visibility-north-south.svg)](media/azure-networking/azure-networking-visibility-north-south.svg#lightbox)

Azure provides the following networking services designed to offer visibility into the network traffic entering and exiting your Azure environment.

### Azure DDoS Protection

Azure DDoS Protection can be enabled on any VNet that has public IP resources to monitor and mitigate possible Distributed Denial of Service (DDoS) attacks. This mitigation process involves analyzing the traffic utilization against predefined thresholds in the DDoS policy, followed by logging this information for further examination. To be better prepared for future incidents, Azure DDoS Protections offers the ability to [conduct simulations](/en-us/azure/ddos-protection/test-through-simulations) against your public IP addresses and services, providing valuable insights into your application’s resilience and response during a DDoS attack.

### Azure Firewall

Azure Firewall provides a collection of tools to monitor, audit, and analyze network traffic.

- Logs and metrics

    Azure Firewall collects detailed logs by integrating with Azure Log Analytics workspaces. You can use Kusto Query Language (KQL) queries to extract extra information on major categories of rules, such as application and networking rules. You can also retrieve logs that are resource-specific that expand on schemas and structures from the networking level to threat intelligence and IDPS logs. For more information, see [Azure Firewall structured logs](/en-us/azure/firewall/firewall-structured-logs).
- Workbooks

    Azure Firewall provides workbooks that present data collected using graphs of activity over time. This tool also helps you visualize multiple Azure Firewall resources by combining them into a unified interface. For more information, see [Using Azure Firewall Workbooks](/en-us/azure/firewall/firewall-workbook).
- Policy analytics

    Azure Firewall Policy Analytics provides an overview of the policies you implemented and based on the policy insights, rule analytics, and traffic flow analytics, it tunes and modifies the implemented policies to adjust to traffic patterns and threats. For more information, see [Azure Firewall Policy Analytics](/en-us/azure/firewall/policy-analytics).

These capabilities ensure that Azure Firewall remains a robust solution for securing network traffic by providing administrators with the tools needed for effective network management.

### Application Gateway

Application Gateway provides important capabilities to monitor, audit, and analyze traffic for security purposes. By enabling log analytics and using either predefined or custom KQL queries, you can view [HTTP error codes](/en-us/azure/application-gateway/application-gateway-diagnostics#error-code-information), including those in the 4xx and 5xx ranges that are critical for identifying issues.

Application Gateway’s access logs also provide critical insights into key security-related parameters such as client IP addresses, request URIs, HTTP version, and SSL/TLS-specific configuration values such as protocols, TLS cipher suites, and when SSL encryption is enabled.

### Azure Front Door

[Azure Front Door](/en-us/azure/frontdoor/front-door-overview) employs Anycast TCP to route traffic to the nearest datacenter point of presence (PoP). Like a conventional load balancer, you can place an Azure Firewall or NVA in the Azure Front Door back-end pool, also known as its origin. The only requirement is that the IP address in the origin is public.

Once you configure Azure Front Door to receive requests, it generates traffic reports to show how the Azure Front Door profile is behaving. When you use the Azure Front Door Premium tier, security reports are also available to show matches to WAF rules, including Open Worldwide Application Security Project (OWASP) rules, bot protection rules, and custom rules.

### Azure WAF

Azure WAF is an additional security feature that inspects layer 7 traffic and can be activated for both Application Gateway and Azure Front Door with certain tiers. This provides an extra layer of security for traffic not originating within Azure. You can configure the WAF in both prevention and detection modes using OWASP core rule definitions.

### Monitoring tools

For comprehensive monitoring of north-south traffic flows, you can use tools such as NSG flow logs, Azure Traffic Analytics, and VNet flow logs to enhance visibility into the network.

## Recommended training

- [Configure and manage virtual networks for Azure administrators](/en-us/training/paths/azure-administrator-manage-virtual-networks/)
- [Introduction to Azure Web Application Firewall](/en-us/training/modules/introduction-azure-web-application-firewall/)
- [Introduction to Azure Virtual WAN](/en-us/training/modules/introduction-azure-virtual-wan/)
- [Introduction to Azure Front Door](/en-us/training/modules/intro-to-azure-front-door/)
- [Introduction to Azure Application Gateway](/en-us/training/modules/intro-to-azure-application-gateway/)