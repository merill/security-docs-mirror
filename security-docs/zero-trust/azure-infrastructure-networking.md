---
layout: Conceptual
title: How do I apply Zero Trust principles to hub virtual networks in Azure? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-infrastructure-networking
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: How to apply Zero Trust principles to a hub virtual network for Azure IaaS workloads.
ms.date: 2024-10-22T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: best-practice
ms.collection:
- msftsolution-azureiaas
- msftsolution-scenario
- zerotrust-solution
- zerotrust-azure
ms.custom: sfi-image-nochange
locale: en-us
document_id: 8f7e220a-9f8b-ee58-30d2-5423c24bb86f
document_version_independent_id: 8f7e220a-9f8b-ee58-30d2-5423c24bb86f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-infrastructure-networking.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-infrastructure-networking
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-infrastructure-networking.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/20ed8455-bc18-4537-87a4-83784e7b2a39
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/85ee13c4-5d0b-41b0-895d-b7e834668123
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9a7f703b-30bb-4d62-9eb4-97213f571849
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/7e79a0d4-3b49-4899-aac2-fbdd26ca15a8
platformId: 928c2578-25bc-78cf-f1ad-57323276fdbf
---

# How do I apply Zero Trust principles to hub virtual networks in Azure? | Microsoft Learn

**Summary:** To apply Zero Trust principles to a hub virtual network in Azure, you must secure Azure Firewall Premium, deploy Azure DDoS Protection Standard, configure network gateway routing to the firewall, and configure threat protection.

The best way to deploy an Azure-based hub virtual network (virtual network) for Zero Trust is to use the Azure Landing Zone materials to deploy a feature-complete hub virtual network, and then tailor it to your specific configuration expectations.

This article provides steps for how to take an existing hub virtual network and ensure you're ready for a Zero Trust methodology. It assumes that you used the ALZ-Bicep [hubNetworking](https://github.com/Azure/ALZ-Bicep/tree/main/infra-as-code/bicep/modules/hubNetworking) module to rapidly deploy a hub virtual network, or deployed some other hub virtual network with similar resources. Using a separate connectivity hub connected to isolated workplace spokes is an anchor pattern in Azure secure networking and helps support the Zero Trust principles.

This article describes how to deploy a hub virtual network for Zero Trust by mapping the [principles of Zero Trust](zero-trust-overview) in the following ways.

| Zero Trust principle | Definition | Met by |
| --- | --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. | Use Azure Firewall with Transport Layer Security (TLS) inspection to verify risk and threats based on all available data. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. | Each spoke virtual network has no access to other spoke VNets unless the traffic gets routed through the firewall. The firewall is set to deny by default, allowing only traffic allowed by specified rules. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses. | In the event of a compromise or breach of one application/workload, it has limited ability to spread due to the Azure Firewall performing traffic inspection and only forwarding allowed traffic. Only resources in the same workload would be exposed to the breach in the same application. |

This article is a part of a series of articles that demonstrate how to apply the principles of Zero Trust across an environment in Azure. This article provides information for configuring a hub virtual network to support an IaaS workload in a spoke Vnet. For more information, see the [Apply Zero Trust principles to Azure IaaS overview](azure-infrastructure-overview).

## Reference architecture

The following diagram shows the reference architecture. The hub virtual network is highlighted in red. For more information about this architecture, see the [Apply Zero Trust principles to Azure IaaS overview](azure-infrastructure-overview).

[![Diagram of the reference architecture for the components of a hub virtual network with Zero Trust principles applied.](media/hub/azure-infra-hub-architecture-1.svg)](media/hub/azure-infra-hub-architecture-1.svg#lightbox)

For this reference architecture, there are many ways you can deploy the resources across the Azure subscription. The reference architecture shows the recommendation of isolating all resources for the hub virtual network within a dedicated resource group. The resources for the spoke virtual network are also shown for comparison. This model works well if different teams are given responsibility for these different areas.

In the diagram, a hub virtual network includes components to support access to other apps and services within the Azure environment. These resources include:

- Azure Firewall Premium
- Azure Bastion
- VPN Gateway
- DDOS Protection, which should also be deployed to spoke virtual networks.

The hub virtual network provides access from these components to an IaaS-based app hosted on virtual machines in a spoke virtual network.

For guidance on organizing for cloud adoption, see [Manage organization alignment](/en-us/azure/cloud-adoption-framework/organize/) in the Cloud Adoption Framework.

The resources that are deployed for the hub virtual network are:

- An Azure virtual network
- Azure Firewall with Azure Firewall policy and a public IP address
- Bastion
- VPN gateway with a public IP address and route table

The following diagram shows the components of a resource group for a hub virtual network in an Azure subscription separate from the subscription for the spoke virtual network. This is one way of organizing these elements within the subscription. Your organization might choose to organize these in a different way.

[![Diagram of the logical architecture for applying Zero Trust to an Azure hub virtual network showing subscriptions, resource groups, and Azure components within a Microsoft Entra ID tenant.](media/hub/azure-infra-hub-subscription-architecture-2.svg)](media/hub/azure-infra-hub-subscription-architecture-2.svg#lightbox)

In the diagram:

- The resources for the hub virtual network are contained within a dedicated resource group. If you're deploying Azure DDoS Plan a part of the resources, you need to include that in the resource group.
- The resources within a spoke virtual network are contained within a separate dedicated resource group.

Depending on your deployment, you might also note that there can be a deployment of an array for Private DNS Zones used for Private Link DNS resolution. These are used to secure PaaS resources with Private Endpoints, which are detailed in a future section. Note that it deploys both a VPN Gateway and an ExpressRoute Gateway. You might not need both, so you can remove whichever one isn't needed for your scenario or turn it off during deployment.

## What's in this article?

This article provides recommendations for securing the components of a hub virtual network for Zero Trust principles. The following table describes the recommendations for securing this architecture.

| Step | Task | Zero Trust principle(s) applied |
| --- | --- | --- |
| 1 | Secure Azure Firewall Premium. | Verify explicitly  Use least privileged access  Assume breach |
| 2 | Deploy Azure DDoS Protection Standard. | Verify explicitly  Use least privileged access  Assume breach |
| 3 | Configure network gateway routing to the firewall. | Verify explicitly  Use least privileged access  Assume breach |
| 4 | Configure threat protection. | Assume breach |

As a part of your deployment, you'll want to make specific selections that aren't the defaults for automated deployments due to their additional costs. Prior to the deployment, you should review the costs.

Operating the connectivity hub as deployed still provides significant value for isolation and inspection. If your organization isn't ready to incur the costs of these advanced features, you can deploy a reduced functionality hub and make these adjustments later.

## Step 1: Secure Azure Firewall Premium

Azure Firewall Premium plays a vital role in helping you secure your Azure infrastructure for Zero Trust.

As a part of the deployment, use Azure Firewall Premium. This requires that you deploy the generated management policy as a premium policy. Changing to Azure Firewall Premium involves recreating the firewall and often the policy as well. As a result, start with Azure Firewall if possible, or be prepared for redeployment activities to replace the existing firewall.

### Why Azure Firewall Premium?

Azure Firewall Premium provides [advanced features](/en-us/azure/firewall/premium-features) for inspecting traffic. The most significant are the following TLS inspection options:

- **Outbound TLS Inspection** protects against malicious traffic that is sent from an internal client to the internet. This helps identify when a client has been breached, and if it's trying to send data outside of your network or establish a connection to a remote computer.
- **East-West TLS Inspection** protects against malicious traffic sent from within Azure to other parts of Azure or to your non-Azure networks. This helps identify attempts for a breach to expand and spread its blast radius.
- **Inbound TLS Inspection** protects resources in Azure from malicious requests that arrive from outside the Azure network. Azure Application Gateway with Web Application Firewall provides this protection.

You should use the Inbound TLS Inspection for resources whenever possible. Azure Application Gateway only provides protection for HTTP and HTTPS traffic. It can't be used for some scenarios, such as those that use SQL or RDP traffic. Other services often have their own threat protection options that could be used to provide *explicit verification* controls for those services. You can review [Security baselines for Azure overview](/en-us/security/benchmark/azure/security-baselines-overview) to understand the threat protection options for these services.

Azure Application Gateway isn't recommended for the hub virtual network. It should instead reside in a spoke virtual network or a dedicated virtual network. For more information, see [Apply Zero Trust principles to spoke virtual network in Azure](azure-infrastructure-iaas) for guidance on the spoke virtual network or [Zero-trust network for web applications](/en-us/azure/architecture/example-scenario/gateway/application-gateway-before-azure-firewall).

These scenarios have specific digital certificate considerations. For more information, see [Azure Firewall Premium certificates](/en-us/azure/firewall/premium-certificates).

Without TLS inspection, Azure Firewall has no visibility in the data that flows in the encrypted TLS tunnel, and so it's less secure.

For example, Azure Virtual Desktop doesn't support [SSL termination](/en-us/azure/virtual-desktop/proxy-server-support#dont-use-ssl-termination-on-the-proxy-server). You should review your specific workloads to understand how to provide TLS inspection.

In addition to the customer defined allow/deny rules, the Azure Firewall is still able to apply [threat intelligence-based filtering](/en-us/azure/firewall/threat-intel). Threat intelligence-based filtering uses known-bad IP addresses and domains to identify traffic that poses a risk. This filtering occurs prior to any other rules, which means even if the access was allowed by your defined rules, Azure Firewall can stop the traffic.

Azure Firewall Premium also has enhanced options for URL filtering and web category filtering, allowing for more fine-tuning for roles.

You can set threat intelligence to notify you with an alert when this traffic occurs, but to allow it through. However for Zero Trust, set it to Deny.

### Configure Azure Firewall Premium for Zero Trust

To configure Azure Firewall Premium to a Zero Trust configuration, make the following changes.

1. Enable Threat Intelligence in Alert and Deny Mode:

    1. Navigate to the Firewall Policy and select **Threat Intelligence**.
    2. In **Threat intelligence mode**, select **Alert and deny**.
    3. Select **Save**.

    [![Screenshot of enabling threat intelligence and Alert and Deny mode.](media/hub/hub-threat-intelligence.png)](media/hub/hub-threat-intelligence.png#lightbox)
2. Enable TLS inspection:

    1. Prepare a certificate to store in a Key Vault, or plan to auto-generate a certificate with a managed identity. You can review these options for [Azure Firewall Premium certificates](/en-us/azure/firewall/premium-certificates) to select the option for your scenario.
    2. Navigate to the Firewall Policy and select **TLS Inspection**.
    3. Select **Enabled**.
    4. Either select a Managed Identity to generate certificates, or select the key vault and certificate.
    5. Then select **Save**.

    [![Screenshot of enabling TLS inspection.](media/hub/hub-tls-inspection.png)](media/hub/hub-tls-inspection.png#lightbox)
3. Enable the Intrusion Detection and Prevention System (IDPS):

    1. Navigate to the Firewall Policy and select **IDPS**.
    2. Select **Alert and deny**.
    3. Then select **Apply**.

    [![Screenshot of enabling IDPS.](media/hub/hub-idps.png)](media/hub/hub-idps.png#lightbox)
4. Next, you'll need to create an application rule for the traffic.

    1. In the Firewall Policy, navigate to **Application Rules**.
    2. Select **Add a rule collection**.
    3. Create an application rule with the source of your Application Gateway subnet, and a destination of the domain name of the web app that is being protected.
    4. Ensure that you enable **TLS inspection**.

    [![Screenshot showing the steps for creating an application rule.](media/applicationruleexample.gif)](media/applicationruleexample.gif#lightbox)

### Additional configuration

After Azure Firewall Premium is configured, you can now perform the following configuration:

- Configure Application Gateways to route traffic to your Azure Firewall by assigning the appropriate route tables and [following this guidance](/en-us/azure/architecture/example-scenario/gateway/application-gateway-before-azure-firewall#hub-and-spoke-example).
- Create alerts for firewall events and metrics by [following these instructions](/en-us/azure/firewall/firewall-diagnostics).
- Deploy the [Azure Firewall Workbook](/en-us/azure/firewall/firewall-workbook) to visualize events.
- Configure URL and [Web category filtering](/en-us/azure/firewall/web-categories), if needed. Because Azure Firewall denies by default, this configuration is needed only if the Azure Firewall needs to grant outbound internet access broadly. You can use this as an additional verification to determine if connections should be allowed.

## Step 2: Deploy Azure DDoS Protection Standard

As a part of the deployment, you'll want to deploy an Azure DDoS Protection Standard Policy. This increases Zero Trust protection provided on the Azure Platform.

Because you can deploy the created policy to existing resources, you can add this protection after the initial deployment without requiring the redeployment of resources.

### Why Azure DDoS Protection Standard?

Azure DDoS Protection Standard has [increased benefits](/en-us/azure/ddos-protection/ddos-protection-overview) over the default DDoS Protection. For Zero Trust, you can have:

- Access to mitigation reports, flow logs, and metrics.
- Application based mitigation policies.
- Access to DDoS rapid response support if a DDoS attack occurs.

Although automatic detection and automatic mitigation are both a part of the DDoS Protection Basic that is enabled by default, these features are only available with DDoS Standard.

### Configure Azure DDoS Protection Standard

Because there are no Zero Trust-specific configurations for DDoS Protection Standard, you can follow the resource specific guides for this solution:

- [Create a DDoS Protection Plan](/en-us/azure/ddos-protection/manage-ddos-protection)
- [Configure Alerting](/en-us/azure/ddos-protection/alerts)
- [Configure Diagnostic Logging](/en-us/azure/ddos-protection/diagnostic-logging)
- [Configure Telemetry](/en-us/azure/ddos-protection/telemetry)

In the current version of Azure DDoS Protection, you must apply Azure DDoS Protection per virtual network. See additional instructions in [DDoS Quickstart](/en-us/azure/ddos-protection/manage-ddos-protection).

In addition, protect the following public IP addresses:

- Azure Firewall public IP addresses
- Azure Bastion public IP addresses
- Azure Network Gateway public IP addresses
- Application Gateway public IP addresses

## Step 3: Configure network gateway routing to the firewall

After deployment, you'll need to configure route tables on various subnets to ensure that traffic between spoke VNets and the on-premises networks are inspected by the Azure Firewall. You can perform this activity in an existing environment without a requirement of redeployment, but you have to author the necessary firewall rules to allow access.

If you configure only one side, either just the spoke subnets or the gateway subnets, then you have asynchronous routing that prevents connections from working.

### Why route network gateway traffic to the firewall?

A key element of Zero Trust is to not assume that just because something is in your environment, that it should have access to other resources in your environment. A default configuration often allows for routing between resources in Azure to your on-premises networks, controlled only by network security groups.

By routing the traffic to the firewall, you increase the level of inspection and increase the security of your environment. You're also alerted to suspicious activity and can take action.

### Configure gateway routing

There are two main ways to ensure that gateway traffic is being routed to the Azure firewall:

- Deploy the Azure Network Gateway (either for VPN or ExpressRoute connections) in a dedicated virtual network (often called a Transit or Gateway virtual network), peer it to the hub virtual network, and then create a broad routing rule that covers your planned Azure networking address spaces routing to the firewall.
- Deploy the Azure Network Gateway in the hub virtual network, configure routing on the gateway subnet, and then configure routing on the spoke virtual network subnets.

This guide details the second option because it's more compatible with the reference architecture.

Note

[Azure Virtual Network Manager](/en-us/azure/virtual-network-manager/overview) is a service that simplifies this process. When this service is Generally Available, used it to manage the routing.

### Configure gateway subnet routing

To configure the Gateway Subnet route table to forward internal traffic to the Azure Firewall, create and configure a new Route Table:

1. Navigate to **Create a Route Table** in the Microsoft Azure portal.
2. Place the Route Table in a resource group, select a region, and specify a name.
3. Select **Review + Create** and then **Create**.

    [![Screenshot of creating a route table.](media/hub/hub-create-route-table.png)](media/hub/hub-create-route-table.png#lightbox)
4. Navigate to the new route table, and select **Routes**.

    [![Screenshot of selecting a route table.](media/hub/hub-routes.png)](media/hub/hub-routes.png#lightbox)
5. Select **Add** and then add a route to one of the spoke VNets:

    1. In **Route name**, specify the name of the route field.
    2. Select **IP Addresses** in the **Address prefix destination** drop-down.
    3. Provide the spoke virtual network's address space in the **Destination IP addresses/CIDR ranges** field.
    4. Select **Virtual appliance** in the **Next hop type** drop-down box.
    5. Provide the Azure Firewall's private IP address in the **Next hop address** field.
    6. Select **Add**.

#### Associate the route table to the gateway subnet

1. Navigate to **Subnets**, and select **Associate**.
2. Select the Hub virtual network in the **Virtual network** drop-down list.
3. Select the GatewaySubnet in the **Subnet** drop-down.
4. Select **OK**.

Here's an example.

[![Screenshot of associating subnets.](media/hub/hub-associate-subnet.png)](media/hub/hub-associate-subnet.png#lightbox)

The gateway now forwards traffic intended for spoke VNets to the Azure Firewall.

### Configure spoke subnet routing

This process assumes that you already have a route table attached to your spoke virtual network subnets, with a default route to forward traffic to the Azure Firewall. This is most often accomplished by a rule that forwards traffic for CIDR range 0.0.0.0/0, often called a quad-zero route.

Here's an example.

[![Screenshot of configuring spoke subnet routing for default route traffic.](media/hub/hub-spoke-routing.png)](media/hub/hub-spoke-routing.png#lightbox)

This process disables the propagation of routes from the gateway, which enables the default route to take traffic intended to the on-premises networks.

Note

Resources, such as Application Gateways, that require internet access to function should not receive this route table. They should have their own route table to allow their necessary functions, such as what is outlined in the article [Zero-trust network for web applications with Azure Firewall and Application Gateway](/en-us/azure/architecture/example-scenario/gateway/application-gateway-before-azure-firewall).

To configure spoke subnet routing:

1. Navigate to the Route Table associated with your subnet, and select **Configuration**.
2. For **Propagate gateway routes**, select **No**.
3. Select **Save**.

[![Screenshot of setting Propagate gateway routes to No.](media/hub/hub-gateway-routes.png)](media/hub/hub-gateway-routes.png#lightbox)

Your default route now forwards traffic intended for the gateway to the Azure Firewall.

## Step 4: Configure threat protection

Microsoft Defender for Cloud can protect your hub virtual network built on Azure, just like other resources from your IT business environment running on Azure or on-premises.

Microsoft Defender for Cloud is a Cloud Security Posture Management (CSPM) and Cloud Workload Protection (CWP) that offers a secure score system to help your company build an IT environment with a better security posture. It also includes features to protect your network environment against threats.

This article won't cover Microsoft Defender for Cloud in detail. However, it's important to understand that Microsoft Defender for Cloud works based on Azure Policies and logs that it ingests in a Log Analytics workspace.

You write Azure Policies in JavaScript Object Notation (JSON) to hold different analysis of Azure resource properties, including network services and resources. That said, it's easy for Microsoft Defender for Cloud to check a property under a network resource and provide a recommendation to your subscription if you're protected or exposed to a threat.

### How to check all network recommendations available through Microsoft Defender for Cloud

To view all the Azure policies that provide network recommendations used by Microsoft Defender for Cloud:

[![Screenshot example of recommended Azure policies in Microsoft Defender for Cloud.](media/hub/azure-policies-mdc.jpg)](media/hub/azure-policies-mdc.jpg#lightbox)

1. Open **Microsoft Defender for Cloud**, by selecting the Microsoft Defender for Cloud icon in the left menu.
2. Select **Environment settings**.
3. Select **Security policy**.
4. If you select in the ASC Default, you'll be able to review all the policies available, including the policies that evaluate network resources.
5. Additionally, there are network resources evaluated by other regulatory compliance standards including PCI, ISO and the Microsoft cloud security benchmark. You can enable any of them and track for network recommendations.

### Network recommendations

Follow these steps to view some of the network recommendations, based on the Microsoft cloud security benchmark:

[![Screenshot example of network recommendations in Microsoft Defender for Cloud.](media/hub/network-rec-mdc.jpg)](media/hub/network-rec-mdc.jpg#lightbox)

1. Open **Microsoft Defender for Cloud**.
2. Select **Regulatory compliance**.
3. Select **Microsoft cloud security benchmark**.
4. Expand **NS. Network Security** to review the recommended network control.

It's important to understand that Microsoft Defender for Cloud provides other network recommendations for different Azure resources such as virtual machines and storage. You can review those recommendations in the left menu, under **Recommendations**.

On the left menu of the **Microsoft Defender for Cloud** portal, select **Security Alerts** to review alerts based on network resources so you might avoid some types of threats. Those alerts are generated automatically by Microsoft Defender for Cloud based on logs ingested in the **Log Analytics** workspace and monitored by Microsoft Defender for Cloud.

### Mapping and hardening your Azure network environment through Microsoft Defender for Cloud

You can also check options to get a better security posture by hardening your network environment in an effortless way by mapping your network environment for a better understanding of your network topology. Those recommendations are done through **Workload protection** option in the left menu, as show here.

[![Screenshot of an example mapping of Azure networking by Microsoft Defender for Cloud.](media/hub/mapping-mdc.jpg)](media/hub/mapping-mdc.jpg#lightbox)

### Managing Azure Firewall policies through Microsoft Defender for Cloud

Azure Firewall is recommended for a hub virtual network, as described in this article. Microsoft Defender for Cloud can manage multiple Azure Firewall policies centrally. In addition to Azure Firewall policies, you'll be able to manage other features related to Azure Firewall, as shown here.

![Screenshot example of managing Azure firewall policies through Microsoft Defender for Cloud.](media/hub/firewall-manager-mdc.jpg)

For more information about how Microsoft Defender for Cloud protects your network environment against threats, see [What is Microsoft Defender for Cloud?](/en-us/azure/defender-for-cloud/defender-for-cloud-introduction)

## Technical illustrations

These illustrations are replicas of the reference illustrations in these articles. Download and customize these for your own organization and customers. Replace the Contoso logo with your own.

| Item | Description |
| --- | --- |
| [![thumbnail picture 1](media/thumb-zero-trust-iaas-contoso.png)](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx)[Download Visio](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS** Use these illustrations with these articles:  - [Overview](azure-infrastructure-overview) - [Azure storage](azure-infrastructure-storage) - [Virtual machines](azure-infrastructure-virtual-machines) - [Azure spoke virtual networks](azure-infrastructure-iaas) - [Azure hub virtual networks](azure-infrastructure-networking) |
| [![thumbnail picture 2](media/thumb-zero-trust-iaas-contoso-poster.png)](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx)[Download Visio](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS — One page poster** A one-page overview of the process for [applying the principles of Zero Trust to Azure IaaS environments](azure-infrastructure-overview). |

For additional technical illustrations, see [Zero Trust illustrations for IT architects and implementers](zero-trust-tech-illus).

## Recommended training

- [Configure Azure Policy](/en-us/training/modules/configure-azure-policy/)
- [Design and implement network security](/en-us/training/modules/design-implement-network-security-monitoring/)
- [Configure Azure Firewall](/en-us/training/modules/configure-azure-firewall/)
- [Configure VPN Gateway](/en-us/training/modules/configure-vpn-gateway/)
- [Introduction to Azure DDoS Protection](/en-us/training/modules/introduction-azure-ddos-protection/)
- [Resolve security threats with Microsoft Defender for Cloud](/en-us/training/modules/resolve-threats-with-azure-security-center/)

For more training on security in Azure, see these resources in the Microsoft catalog:[Security in Azure | Microsoft Learn](/en-us/training/browse/?subjects=security&amp;products=azure)