---
layout: Conceptual
title: How do I apply Zero Trust principles to storage in Azure? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-infrastructure-storage
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: How to apply Zero Trust principles to Azure storage.
ms.date: 2025-05-20T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: best-practice
ms.collection:
- msftsolution-azureiaas
- msftsolution-scenario
- zerotrust-solution
- zerotrust-azure
locale: en-us
document_id: b0636fa6-c28e-e894-5e70-ddf0a7348de0
document_version_independent_id: b0636fa6-c28e-e894-5e70-ddf0a7348de0
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-infrastructure-storage.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-infrastructure-storage
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-infrastructure-storage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/de8ce683-cbe1-461b-bae7-77db0888ec6d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/a06cf482-4ca9-4582-a142-bcf842258d42
platformId: 7153d4c2-7ad1-f258-d7d3-b0c4a917c5dd
---

# How do I apply Zero Trust principles to storage in Azure? | Microsoft Learn

**Summary:** To apply Zero Trust principles to Azure storage, you must protect data (at rest, in transit, and in use), verify users and control access, separate or segregate critical data with network controls, and use Defender for Storage for automated threat detection and protection.

This article provides steps to apply the [principles of Zero Trust](zero-trust-overview) to Azure Storage:

| Zero Trust principle | Definition | Met by |
| --- | --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. | Verify user credentials and access. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. | Control access to storage data with least privileges. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses. | Protect data at rest, data in transit, and data in use. Separate critical data with network controls. Use Defender for Storage for automated threat detection and protection. |

This article is part of a series of articles that demonstrate how to apply the principles of Zero Trust across an environment in Azure that includes Azure Storage services to support an IaaS workload. For an overview, see [Apply Zero Trust principles to Azure infrastructure](azure-infrastructure-overview).

## Storage architecture in Azure

You apply Zero Trust principles for Azure Storage across the architecture, from the tenant and directory level down to the storage container at the data layer.

The following diagram shows the logical architecture components.

[![Diagram of the logical architecture for applying Zero Trust to Azure storage showing subscriptions, resource groups, and storage accounts within a Microsoft Entra ID tenant.](media/secure-storage/azure-infra-storage-subscription-architecture-1.svg)](media/secure-storage/azure-infra-storage-subscription-architecture-1.svg#lightbox)

In the diagram:

- The storage account for the reference architecture is contained in a dedicated resource group. You can isolate each storage account in a different resource group for more granular role-based access controls (RBAC). You can assign RBAC permissions to manage the storage account at the resource group or resource group level and audit these with Microsoft Entra ID logging and tools such as Privileged Identity Management (PIM). If you're running multiple applications or workloads with multiple corresponding storage accounts in one Azure subscription, it is important to limit each storage account's RBAC permissions to its corresponding owners, data custodians, controllers, etc.
- Azure storage services for this diagram are contained within a dedicated storage account. You can have one storage account for each type of storage workload.
- For a broader look at the reference architecture, see the [Apply Zero Trust principles to Azure IaaS overview](azure-infrastructure-overview).

The diagram doesn't include Azure Queues and Azure Tables. Use the same guidance in this article to secure these resources.

## What's in this article?

This article walks through the steps to apply the principles of Zero Trust across the reference architecture.

| Step | Task | Zero Trust principle(s) applied |
| --- | --- | --- |
| 1 | Protect data in all three modes: data at rest, data in transit, data in use. | Assume breach |
| 2 | Verify users and control access to storage data with least privileges. | Verify explicitly  Use least privileged access |
| 3 | Logically separate or segregate critical data with network controls. | Assume breach |
| 4 | Use Defender for Storage for automated threat detection and protection. | Assume breach |

## Step 1: Protect data in all three modes: data at rest, data in transit, data in use

You configure most of the settings for protecting data at rest, in transit, and in use, when you create the storage account. Use the following recommendations to be sure you configure these protections. Also consider enabling Microsoft Defender for Cloud to automatically evaluate your storage accounts against the [Microsoft cloud security benchmark](/en-us/security/benchmark/azure/introduction) that outlines a security baseline for each Azure service.

For more information on these storage security controls, see [here](/en-us/security/benchmark/azure/baselines/storage-security-baseline).

### Use encryption in transit

Keep your data secure by enabling transport-level security between Azure and the client. Always use HTTPS to secure communication over the public internet. When you call the REST APIs to access objects in storage accounts, you can enforce the use of HTTPS by requiring [Secure Transfer Required](/en-us/azure/storage/common/storage-require-secure-transfer) for the storage account. Any request originating from an insecure connection is rejected.

This configuration is enabled by default when you deploy a new Azure Storage Account (Secure by Default).

Consider applying a policy to deny the deployment of insecure connections for Azure Storage (Secure by Design).

This configuration also requires SMB 3.0 with Encryption.

### Prevent anonymous public read access

By default, public blob access is prohibited, but a user with the proper permissions can configure an accessible resource. To prevent data breaches from anonymous access, you should specify who has access to your data. Preventing this at the storage account level prevents a user from enabling this access at the container or blob level.

For more information, see [Prevent anonymous public read access to containers and blobs](/en-us/azure/storage/blobs/anonymous-read-access-prevent).

### Prevent shared key authorization

This configuration forces the storage account to reject all requests made with a shared key and require Microsoft Entra authorization instead. Microsoft Entra ID is a more secure choice as you can use risk-based access mechanisms to harden access to data tiers. For more information, see [Prevent Shared Key authorization for an Azure Storage account](/en-us/azure/storage/common/shared-key-authorization-prevent?tabs=portal).

You configure data protection for all three modes from the configuration settings of a storage account, as shown here.

[![Screenshot of configuring data protection for all three modes for a storage account.](media/secure-storage/storage-1.png)](media/secure-storage/storage-1.png#lightbox)

These settings can't be changed after you create the storage account.

### Enforce a minimum required version of transport layer security (TLS)

The highest version Azure Storage currently supports is TLS 1.2. Enforcing a minimum TLS version rejects requests from clients using older versions. For more information, see [Enforce a minimum required version of TLS for requests to a storage account](/en-us/azure/storage/common/transport-layer-security-configure-minimum-version).

### Define the scope for copy operations

Define the scope for copy operations to restrict copy operations to only those from source storage accounts that are within the same Microsoft Entra tenant or that have a [Private Link](/en-us/azure/storage/common/storage-network-security) to the same virtual network (VNet) as the destination storage account.

Limiting copy operations to source storage accounts with private endpoints is the most restrictive option and requires that the source storage account has private endpoints enabled.

You configure a scope for copy operations from the configuration settings of a storage account, as shown here.

[![Screenshot of defining the scope for copy operations for a storage account.](media/secure-storage/storage-2.png)](media/secure-storage/storage-2.png#lightbox)

### Understand how encryption at rest works

All data written to Azure Storage is automatically encrypted by [Storage Service Encryption (SSE)](/en-us/azure/security/fundamentals/encryption-atrest) with a 256-bit Advanced Encryption Standard (AES) cipher. SSE automatically encrypts data when writing it to Azure Storage. When you read data from Azure Storage, Azure Storage decrypts the data before returning it. This process incurs no additional charges and doesn't degrade performance. Using customer-managed keys (CMK) provides additional capabilities to control rotation of the key encryption key or cryptographically erase data.

You enable CMK from the **Encryption** blade when creating a storage account, as shown here.

[![Screenshot of enabling CMK for a storage account.](media/secure-storage/storage-3.png)](media/secure-storage/storage-3.png#lightbox)

You can also enable infrastructure encryption, which provides double encryption at both the service and infrastructure levels. This setting can't be changed after you create the storage account.

Note

In order to utilize a customer-managed key for storage account encryption, you must enable it during account creation and you should have a Key Vault with Key and Managed Identity with appropriate permissions already provisioned. Optionally, 256-bit AES encryption at the Azure Storage infrastructure level can also be enabled.

## Step 2: Verify users and control access to storage data with the least privileges

First, use Microsoft Entra ID to govern access to storage accounts. Using [Role-based Access Control with Storage Accounts](/en-us/azure/storage/blobs/authorize-access-azure-active-directory) allows you to granularly define access based job function using OAuth 2.0. You can align your granular access to your Conditional Access Policy.

It is important to note that roles for storage accounts must be assigned at either the management or data level. Thus, if you're using Microsoft Entra ID as the authentication and authorization method, a user should be assigned the appropriate combination of roles to give them the least amount of privilege necessary to complete their job function.

For a list of Storage Account Roles for granular access see [Azure built-in roles for Storage](/en-us/azure/role-based-access-control/built-in-roles#storage). RBAC assignments are done through the Access Control option on the Storage Account and can be assigned at various scopes.

You configure access control from the **Access Control (IAM)** settings of a storage account, as shown here.

[![Screenshot of configuring access control for a storage account.](media/secure-storage/storage-4.png)](media/secure-storage/storage-4.png#lightbox)

You can check the access levels of users, groups, service principals, or managed identities and add a role assignment.

Another way to provide permissions that are time-bound is through Shared Access Signatures (SAS). [Best Practices when using SAS](/en-us/azure/storage/common/storage-sas-overview#best-practices-when-using-sas) at a high level are the following:

- Always use HTTPS. If you have deployed the [suggested Azure Policies for Azure landing zones](https://github.com/Azure/Enterprise-Scale/wiki/ALZ-Policies), secure transfer via HTTPS will be audited.
- Have a revocation plan.
- Configure SAS expiration policies.
- Validate permissions.
- Use a user delegation SAS wherever possible. This SAS is signed with Microsoft Entra ID credentials.

## Step 3: Logically separate or segregate critical data with network controls

In this step, you use the recommended controls to protect the network connections to and from Azure Storage services.

The following diagram highlights the network connections to the Azure Storage services in the reference architecture.

[![Diagram of the reference architecture for applying Zero Trust to Azure storage that highlights the network connections to Azure Storage services within the Azure IaaS reference architecture.](media/secure-storage/azure-infra-storage-network-2.svg)](media/secure-storage/azure-infra-storage-network-2.svg#lightbox)

| Task | Description |
| --- | --- |
| Prevent public access, create network segmentation with [Private Endpoint](/en-us/azure/private-link/private-endpoint-overview) and Private Link. | Private endpoint allows you to connect to services with the use of a single private IP address on the VNet using Azure Private Link.  Enabling private endpoints allows the Azure platform to validate network connections and allow only the connection with explicit access to the private-link resource to gain access to subsequent resources.  You'll need a separate private endpoint for each service on the Azure Storage Account. |
| Use [Azure Private Link](/en-us/azure/private-link/private-link-overview) | Use Azure Private Link to access Azure Storage over a private endpoint in your VNet. Use the [approval workflow](/en-us/azure/private-link/private-endpoint-overview) to automatically approve or manually request, as appropriate. |
| Prevent public access to your data sources using [Service Endpoints](/en-us/azure/virtual-network/virtual-network-service-endpoints-overview) | You can do network segmentation using Service Endpoints by enabling private IP addresses in a VNet to reach an endpoint without using public IP addresses. |

You configure private endpoints from the **Networking** settings of a storage account, as shown here.

[![Screenshot of configuring a private endpoint for a storage account.](media/secure-storage/storage-5.png)](media/secure-storage/storage-5.png#lightbox)

## Step 4: Use Defender for Storage for automated threat detection and protection

[Microsoft Defender for Storage](/en-us/azure/storage/common/azure-defender-storage-configure?tabs=azure-security-center) provides that additional level of intelligence that detects unusual and potentially harmful attempts to exploit your storage services. Microsoft Defender for Storage is built into Microsoft Defender for Cloud.

Defender for Storage detects anomalous access pattern alerts such as:

- Access from unusual locations
- Application Anomaly
- Anonymous access
- Anomalous extract/upload alerts
- Data Exfiltration
- Unexpected delete
- Upload Azure Cloud Service package
- Suspicious storage activities alerts
- Access permission change
- Access Inspection
- Data Exploration

For more information about threat protection across the reference architecture, see the [Apply Zero Trust principles to Azure IaaS overview](azure-infrastructure-overview).

Once enabled, Defender for Storage notifies you of security alerts and recommendations for improving the security posture of your Azure storage accounts.

Here's an example security alert for a storage account with a description of the alert and prevention measures highlighted.

[![Screenshot of an example security alert for a storage account.](media/secure-storage/storage-6.png)](media/secure-storage/storage-6.png#lightbox)

## Technical illustrations

These illustrations are replicas of the reference illustrations in these articles. Download and customize these for your own organization and customers. Replace the Contoso logo with your own.

| Item | Description |
| --- | --- |
| [![thumbnail picture 1](media/thumb-zero-trust-iaas-contoso.png)](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx)[Download Visio](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS** Use these illustrations with these articles:  - [Overview](azure-infrastructure-overview) - [Azure storage](azure-infrastructure-storage) - [Virtual machines](azure-infrastructure-virtual-machines) - [Azure spoke virtual networks](azure-infrastructure-iaas) - [Azure hub virtual networks](azure-infrastructure-networking) |
| [![thumbnail picture 2](media/thumb-zero-trust-iaas-contoso-poster.png)](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx)[Download Visio](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS — One page poster** A one-page overview of the process for [applying the principles of Zero Trust to Azure IaaS environments](azure-infrastructure-overview). |

For additional technical illustrations, see [Zero Trust illustrations for IT architects and implementers](zero-trust-tech-illus).

## Recommended training

### Configure Storage security

| Training | [Configure Storage security](/en-us/training/modules/configure-storage-security/) |
| --- | --- |
| ![](media/storage-security-configure.png) | Learn how to configure common Azure Storage security features like storage access signatures. In this module, you learn how to: - Configure a shared access signature (SAS), including the uniform resource identifier (URI) and SAS parameters.<br>- Configure Azure Storage encryption.<br>- Implement customer-managed keys.<br>- Recommend opportunities to improve Azure Storage security. |

For more training on security in Azure, see these resources in the Microsoft catalog:[Security in Azure | Microsoft Learn](/en-us/training/browse/?subjects=security&amp;products=azure)