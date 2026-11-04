---
layout: Conceptual
title: Apply Zero Trust principles to discontinue legacy network security technology | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-networking-legacy
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: duau
author: duongau
description: Learn how to apply Zero Trust principles to discontinue legacy network security technology.
ms.date: 2024-06-17T00:00:00.0000000Z
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
document_id: 16cc908e-4764-1429-e8a8-0a549342cc84
document_version_independent_id: 16cc908e-4764-1429-e8a8-0a549342cc84
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-networking-legacy.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-networking-legacy
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-networking-legacy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/d4cf20b3-3e54-4ed9-8b09-370a52eee81b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9ecc2643-be13-4271-a1f4-87114737d63a
platformId: 5d72a35e-35f7-f42b-305e-660dc059163f
---

# Apply Zero Trust principles to discontinue legacy network security technology | Microsoft Learn

This article provides guidance to applying the [principles of Zero Trust](zero-trust-overview) for discontinuing legacy network security technology in Azure environments. Here are the Zero Trust principles.

| Zero Trust principle | Definition |
| --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses.  Improve defenses for your Azure environment by removing or upgrading your legacy network services for higher levels of security. |

This article is a part of a [series of articles](azure-networking-overview) that demonstrate how to apply the principles of Zero Trust to Azure networking.

The Azure networking areas to review to discontinue the use of legacy network security technologies are:

- Networking foundation services
- Load balancing and content delivery services
- Hybrid connectivity services

The transition away from using legacy network security technologies can prevent an attacker from accessing environments or moving across them to inflict widespread damage (the **Assume breach** Zero Trust principle).

## Reference architecture

The following diagram shows the reference architecture for this Zero Trust guidance for discontinuing legacy network security technology for components in your Azure environment.

[![Diagram showing the reference architecture for discontinuing legacy network security technology with Azure networking components.](media/azure-networking/azure-networking-legacy-reference-architecture.svg)](media/azure-networking/azure-networking-legacy-reference-architecture.svg#lightbox)

This reference architecture includes:

- Azure IaaS workloads running on Azure virtual machines.
- Azure services.
- A security virtual network (VNet) that contains an Azure VPN Gateway and Azure Application Gateway.
- An Internet edge VNet that contains an Azure Load Balancer.
- Azure Front Door on the edge of the Azure environment.

## What's in this article?

You apply Zero Trust principles across the reference architecture, from users and admins on the Internet or your on-premises network to and within your Azure environment. The following table list the key tasks for discontinuing legacy network security technology across this architecture for the **Assume breach** Zero Trust principle.

| Step | Task |
| --- | --- |
| 1 | Review your network foundations services. |
| 2 | Review your content delivery and load balancing services. |
| 3 | Review your hybrid connectivity services. |

## Step 1: Review your network foundations services

Your review of network foundation services includes:

- Moving from the Basic Public IP SKU to the Standard Public IP SKU.
- Ensuring that virtual machine IP addresses are using explicit outbound access.

This diagram shows the components for updating Azure network foundation services in the reference architecture.

[![Diagram showing the components for updating Azure network foundation services.](media/azure-networking/azure-networking-legacy-step-1.svg)](media/azure-networking/azure-networking-legacy-step-1.svg#lightbox)

### Basic Public IP SKU

IP addresses (public and private) are part of IP services in Azure that enable communication among private and public resources. Public IPs are linked to services like VNet gateways, application gateways, and others that need outbound connectivity to the Internet. Private IPs enable communication between Azure resources internally.

The Basic Public IP SKU is seen as legacy today and has more limitations than Standard Public IP SKU. One of the major limitations for Zero Trust for the Basic Public IP SKU is that the use of network security groups isn't required but recommended, while it's mandatory with the Standard Public IP SKU.

Another important feature for the Standard Public IP SKU is the ability to select a Routing Preference, such as routing through the Microsoft global network. This feature secures traffic within the Microsoft backbone network whenever possible and outbound traffic exits as close to the service or end-user as possible.

For more information, see [Azure Virtual Network IP Services](/en-us/azure/virtual-network/ip-services/ip-services-overview).

Note

The Basic Public IP SKU will be retired in [September 2025](https://azure.microsoft.com/updates/upgrade-to-standard-sku-public-ip-addresses-in-azure-by-30-september-2025-basic-sku-will-be-retired/).

### Default outbound access

By default, Azure provides outbound access to the Internet. Connectivity from the resources is granted by default with the system routes and by the default outbound rules for the network security groups in place. In other words, if no explicit outbound connectivity method is configured, Azure configures a default outbound access IP address. However, without explicit outbound access, certain security risks arise.

Microsoft recommends that you do not leave a virtual machine IP address open to Internet traffic. There's no control over the default outbound IP access and IP addresses, along with their dependencies, can change. For virtual machines equipped with multiple network interface cards (NICs), it isn't recommended to allow all NIC IP addresses to have Internet outbound access. Instead, you should restrict access only to the necessary NICs.

Microsoft recommends that you set up explicit outbound access with one of the following options:

- [Azure NAT Gateway](/en-us/azure/nat-gateway/nat-overview)

    For the maximum source network address translation (SNAT) ports, Microsoft recommends Azure NAT Gateway for outbound connectivity.
- Standard SKU [Azure Load Balancers](/en-us/azure/load-balancer/load-balancer-overview)

    This requires a load balancing rule to program SNAT, which may not be as efficient as an Azure NAT Gateway.
- Restricted use of public IP addresses

    Assigning a direct public IP address to a virtual machine should be done only for testing or development environments because of scalability and security considerations.

## Step 2: Review your content delivery and load balancing services

Azure has many application delivery services that help you send and distribute traffic to your web applications. Sometimes a new version or tier of the service improves the experience and provides the latest updates. You can use the migration tool within each of the application delivery services to easily switch to the newest version of the service and benefit from new and enhanced features.

Your review of content delivery and load balancing services includes:

- Migrating your Azure Front Door tier from the Classic tier to the Premium or Standard tiers.
- Migrating your Azure Application Gateways to WAF\_v2.
- Migrating to Standard SKU [Azure Load Balancer](/en-us/azure/load-balancer/load-balancer-overview).

This diagram shows the components for updating Azure content delivery and load balancing services.

[![Diagram showing the components for updating Azure content delivery and load balancing services.](media/azure-networking/azure-networking-legacy-step-2.svg)](media/azure-networking/azure-networking-legacy-step-2.svg#lightbox)

### Azure Front Door

[Azure Front Door](/en-us/azure/frontdoor/front-door-overview) has three different tiers: Premium, Standard, and Classic. Standard and Premium tiers combine features from Azure Front Door Classic tier, [Azure Content Delivery Network](/en-us/azure/cdn/cdn-overview), and [Azure Web Application Firewall (WAF)](/en-us/azure/web-application-firewall/overview) into one service.

Microsoft recommends migrating your classic Azure Front Door profiles to the Premium or Standard tiers to enjoy these new features and updates. The Premium tier focuses on improved security features such as private connectivity to your backend services, Microsoft managed WAF rules, and bot protection for your web applications.

In addition to the improved features, Azure Front Door Premium includes security reports that are built into the service at no extra cost. These reports help you analyze the WAF security rules and see what kind of attacks your web applications could face. The security report also lets you examine metrics by different dimensions, which help you understand where traffic comes from and a breakdown of top events by criteria.

The Azure Front Door Premium tier provides the most robust Internet security measures between clients and web applications.

### Azure Application Gateway

[Azure Application Gateways](/en-us/azure/application-gateway/overview-v2) have two SKU types, v1 and v2, and a WAF version that can be applied to either SKU. Microsoft recommends migrating your Azure Application Gateway to the WAF\_v2 SKU to benefit from performance upgrades and new features such as autoscaling, custom WAF rules, and support for [Azure Private Link](/en-us/azure/private-link/private-link-overview).

Custom WAF rules allow you to specify conditions to evaluate every request that goes through the Azure Application Gateway. These rules have higher priority than the rules in the managed rule sets and can be customized to suit the needs of your application and security requirements. The custom WAF rules also can limit access to your web applications by country or regions by matching an IP address to a country code.

The other benefit of migrating to WAFv2 is that you can connect to your Azure Application Gateway through the Azure Private Link service when accessing from another VNet or a different subscription. This feature lets you block public access to the Azure Application Gateway while allowing only users and devices access through a private endpoint. With Azure Private Link connectivity, you must approve each private endpoint connection, which ensures that only the right entity can access. For more information about the differences between v1 and v2 SKU, see [Azure Application Gateway v2](/en-us/azure/application-gateway/overview-v2).

### Azure Load Balancer

With the [planned retirement of the Basic Public IP SKU in September 2025](https://azure.microsoft.com/updates/upgrade-to-standard-sku-public-ip-addresses-in-azure-by-30-september-2025-basic-sku-will-be-retired/), you need to upgrade services that use Basic Public IP SKU IP addresses. Microsoft recommends migrating your current Basic SKU Azure Load Balancers to Standard SKU Azure Load Balancers to implement security measures not included with the Basic SKU.

With the Standard SKU Azure Load Balancer, you're secure by default. All inbound Internet traffic to the public load balancer is blocked unless allowed by the rules of the applied network security group. This default behavior prevents accidentally allowing Internet traffic to your virtual machines or services before you're ready and ensures that you're in control of the traffic that can access your resources.

Standard SKU Azure Load Balancer uses Azure Private Link to create private endpoint connections, which is useful in cases where you want to allow private access to your resources behind a load balancer, but you want users to access it from their environment.

## Step 3: Review your hybrid connectivity services

Review of your hybrid connectivity services includes the use of the new generation of SKUs for [Azure VPN Gateway](/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways).

This diagram shows the components for updating Azure hybrid connectivity services in the reference architecture.

[![Diagram showing the components for updating Azure hybrid connectivity services.](media/azure-networking/azure-networking-legacy-step-3.svg)](media/azure-networking/azure-networking-legacy-step-3.svg#lightbox)

The most effective way to connect hybrid networks in Azure currently is with the new generation SKUs for Azure VPN Gateway. While you might continue to employ classic VPN gateways, these are outdated and less reliable and efficient. Classic VPN gateways support a maximum of 10 Internet Protocol Security (IPsec) tunnels, whereas the newer Azure VPN Gateway SKUs can scale up to 100 tunnels.

The newer SKUs operate on a newer driver model and incorporate the latest security software updates. The older driver models were based on outdated Microsoft technologies that aren't suitable for modern workloads. The newer driver models not only offer superior performance and hardware, but also provide enhanced resilience. The [AZ set of SKUs](/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways#gwsku) of VPN gateways can be positioned in availability zones and support active-active connections with multiple public IP addresses, which enhances resilience and offers improved options for disaster recovery.

Additionally, for dynamic routing needs, classic VPN gateways couldn’t run Border Gateway Protocol (BGP), only used IKEv1, and didn't support dynamic routing. In summary, classic SKU VPN gateways are designed for smaller workloads, low bandwidth, and static connections.

Classic VPN gateways also have limitations in the security and functionality of their IPsec tunnels. They only support Policy-Based mode with IKEv1 protocol and a limited set of encryptions and hashing algorithms that are more susceptible to breaches. Microsoft recommends that you transition to the new SKUs that offer a broader range of options for Phase 1 and Phase 2 protocols. A key advantage is that route-based VPN Gateways can use both IKEv1 and IKEv2 main mode, providing greater implementation flexibility and more robust encryption and hashing algorithms.

If you require higher security than the default encryption values, route-based VPN Gateways allow for the customization of Phase 1 and Phase 2 parameters to select specific ciphers and key lengths. Stronger encryption groups include Group 14 (2048-bit), Group 24 (2048-bit MODP Group), or ECP (elliptic curve groups) 256 bit or 384 bit (Group 19 and Group 20, respectively). Additionally, you can specify which prefix ranges are permitted to send encrypted traffic using the Traffic Selector setting to further safeguard the tunnel negotiation from unauthorized traffic.

For more information, see [Azure VPN Gateway cryptography](/en-us/azure/vpn-gateway/vpn-gateway-about-compliance-crypto#cryptographic-requirements).

Azure VPN Gateway SKUs facilitate Point-to-Site (P2S) VPN connections to utilize both IPsec protocols based on the IKEv2 standard and VPN protocols based on SSL/TLS, such as OpenVPN and Secure Socket Tunneling Protocol (SSTP). This support provides users with various implementation methods and enables them to connect to Azure using different device operating systems. Azure VPN Gateway SKUs also offer many client authentication options, including certificate authentication, Microsoft Entra ID authentication, and Active Directory Domain Services (AD DS) authentication.

Note

Classic IPSec gateways will be retired on [August 31, 2024](https://azure.microsoft.com/updates/five-azure-classic-networking-services-will-be-retired-on-31-august-2024/).

## Recommended training

- [Configure and manage virtual networks for Azure administrators](/en-us/training/paths/azure-administrator-manage-virtual-networks/)
- [Secure and isolate access to Azure resources by using network security groups and service endpoints](/en-us/training/modules/secure-and-isolate-with-nsg-and-service-endpoints/)
- [Introduction to Azure Front Door](/en-us/training/modules/intro-to-azure-front-door/)
- [Introduction to Azure Application Gateway](/en-us/training/modules/intro-to-azure-application-gateway/)
- [Introduction to Azure Web Application Firewall](/en-us/training/modules/introduction-azure-web-application-firewall/)
- [Introduction to Azure Private Link](/en-us/training/modules/introduction-azure-private-link/)
- [Connect your on-premises network to Azure with VPN Gateway](/en-us/training/modules/connect-on-premises-network-with-vpn-gateway/)