---
layout: Conceptual
title: How do I apply Zero Trust principles to Azure virtual machines? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/azure-infrastructure-virtual-machines
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: How to apply Zero Trust principles to virtual machines in Azure.
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
document_id: dce6ab95-3326-fcf5-2c09-b6f0853595df
document_version_independent_id: dce6ab95-3326-fcf5-2c09-b6f0853595df
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/azure-infrastructure-virtual-machines.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/azure-infrastructure-virtual-machines
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/azure-infrastructure-virtual-machines.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2ed91286-6cf7-4b83-810d-75d0ee3b09dd
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/6735bd7e-4f7b-457d-b58c-29e6f0198677
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: f6e7af0d-18a3-eab5-ab49-60309a63f2bc
---

# How do I apply Zero Trust principles to Azure virtual machines? | Microsoft Learn

**Summary:** To apply Zero Trust principles to Azure virtual machines, you must configure logical isolation with dedicated resource groups, leverage Role Based Access Control (RBAC), secure virtual machine boot components, enable customer-managed keys and double encryption, control installed applications, configure secure access and maintenance of virtual machines, and enable advanced threat detection and protection.

This article provides steps to apply the [principles of Zero Trust](zero-trust-overview) to virtual machines in Azure:

| Zero Trust principle | Definition | Met by |
| --- | --- | --- |
| Verify explicitly | Always authenticate and authorize based on all available data points. | Use secure access. |
| Use least privileged access | Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection. | Leverage Role Based Access Control (RBAC) and control the applications running on virtual machines. |
| Assume breach | Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses. | Isolate virtual machines with resource groups, secure their components, use double encryption, and enable advanced threat detection and protection. |

This article is part of a series of articles that demonstrate how to apply the principles of Zero Trust across an environment in Azure that includes a spoke virtual network (VNet) hosting a virtual machine-based workload. For an overview, see [Apply Zero Trust principles to Azure infrastructure](azure-infrastructure-overview).

## Logical architecture for virtual machines

Zero Trust principles for virtual machines are applied across the logical architecture, from the tenant and directory level down to the data and application layer within each virtual machine.

The following diagram shows the logical architecture components.

[![Diagram of the logical architecture for applying Zero Trust to an Azure virtual machine showing a subscription, a resource group, and virtual machine components within a Microsoft Entra ID tenant.](media/vm/vm-security-configure.svg)](media/vm/vm-security-configure.svg#lightbox)

In this diagram:

- **A** is a set of virtual machines isolated within a dedicated resource group that resides within an Azure subscription.
- **B** is the logical architecture for a single virtual machine with the following components called out: applications, operating system, disks, boot loaders, OS Kernel, drivers, and the Trusted Platform Module (TPM) component.

This article walks through the steps to apply the principles of Zero Trust across this logical architecture, using these steps.

[![Diagram of the logical architecture for applying Zero Trust to an Azure virtual machine in the five steps of this article.](media/vm/azure-infra-vm-subscription-architecture-2.svg)](media/vm/azure-infra-vm-subscription-architecture-2.svg#lightbox)

| Step | Task | Zero Trust principles applied |
| --- | --- | --- |
| 1 | Configure logical isolation by deploying virtual machines to a dedicated resource group. | Assume breach |
| 2 | Leverage Role Based Access Control (RBAC). | Verify explicitly  Use least privileged access |
| 3 | Secure virtual machine boot components including boot loaders, OS kernels, and drivers. Securely protect keys, certificates, and secrets in the Trusted Platform Module (TPM). | Assume breach |
| 4 | Enable customer-managed keys and double encryption. | Assume breach |
| 5 | Control the applications that are installed on virtual machines. | Use least privileged access |
| 6 | Configure secure access (not shown on the logical architecture figure). | Verify explicitly  Use least privileged access  Assume breach |
| 7 | Set up secure maintenance of virtual machines (not shown on the logical architecture figure). | Assume breach |
| 8 | Enable advanced threat detection and protection (not shown on the logical architecture figure). | Assume breach |

## Step 1: Configure logical isolation for virtual machines

Begin by isolating virtual machines within a dedicated resource group. You can isolate virtual machines into different resource groups based on purpose, data classification, and governance requirements, such as the need to control permissions and monitoring.

Using dedicated resource groups allows you to set policies and permissions that apply to all the virtual machines within the resource group. You can then use role based access control (RBAC) to create least privileged access to the Azure resources contained in the resource group.

For more information on creating and managing resource groups, see [Manage Azure resource groups by using the Azure portal](/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal).

You assign a virtual machine to a resource group when you first create the virtual machine, as shown here.

[![Screenshot of assigning a virtual machine to a resource group.](media/vm/vm-create-vm-1.png)](media/vm/vm-create-vm-1.png#lightbox)

## Step 2: Leverage Role Based Access Control (RBAC)

Zero Trust requires configuring least privileged access. To do so, you need to limit user access with just-in-time and just-enough access (JIT/JEA) based on their role, workload, and data classification.

The following built-in roles are commonly used for virtual machine access:

- **Virtual Machine User Login:** View virtual machines in the portal and sign-in as a regular user.
- **Virtual Machine Administration Login:** View virtual machines in the portal and sign-in to virtual machines as an Administrator.
- **Virtual Machine Contributor:** Create and manage virtual machines, including reset root user's password and managed disks. Doesn't grant access to the management virtual network (VNet) or the ability to assign permissions to the resources.

To join a virtual machine to a VNet, you can use the custom permission **Microsoft.Network/virtualNetworks/subnets/join/action** to make a custom role.

When this custom role is used with Managed Identity and Conditional Access Policy, you can use device state, data classification, anomalies, location, and identity to force multifactor authentication and granularly allow access based on verified trust.

To extend your realm of control beyond the system and allow your Microsoft Entra ID tenant with Microsoft Intelligent Security Graph to support secure access, go to the **Management** blade of the virtual machine and turn on **System Assigned Managed Identity**, as shown here.

[![Screenshot of enabling system assigned managed identity.](media/vm/vm-create-vm-step2.png)](media/vm/vm-create-vm-step2.png#lightbox)

Note

This feature is only available for Azure Virtual Desktop, Windows Server 2019, Windows 10, and Linux Distros using certificate-based access.

## Step 3: Secure virtual machine boot components

Follow these steps:

- When you create the virtual machine, be sure you configure security for the boot components. Enhanced deployment of virtual machines allows you to select security type and use [Secure boot](/en-us/windows-hardware/design/device-experiences/oem-secure-boot) and [vTPM](/en-us/windows/security/information-protection/tpm/trusted-platform-module-overview).
- Securely deploy virtual machines with verified boot loaders, OS kernels, and drivers that are signed by trusted publishers to establish a "root ." If the image isn't signed by a trusted publisher, the virtual machine won't boot.
- Securely protect keys, certificates, and secrets in the virtual machines in a Trusted Platform Module.
- Gain insights and confidence of the entire boot chain's integrity.
- Ensure workloads are trusted and verifiable. The vTPM enables [attestation](/en-us/windows/security/information-protection/tpm/tpm-fundamentals#measured-boot-with-support-for-attestation) by measuring the entire boot chain of your virtual machine (UEFI, OS, system, and drivers).

Enhanced deployment of virtual machines allows you to select security type and use secure boot and vTPM when you create them, as shown here.

[![Screenshot of specifying security features for a virtual machine.](media/vm/vm-create-vm-step3.png)](media/vm/vm-create-vm-step3.png#lightbox)

## Step 4: Enable customer-managed keys and double encryption

Using customer-managed keys and double encryption ensures that if a disk is exported, it isn't readable or able to function. By ensuring that the keys are privately held and disks are double encrypted, you protect against breaches that attempt to extract disk information.

For information on how to configure a customer-managed encryption key with Azure Key Vault, see [Use the Azure portal to enable server-side encryption with customer-managed keys for managed disks](/en-us/azure/virtual-machines/disks-enable-customer-managed-keys-portal). There's an additional cost for using Azure Key Vault.

[Enable server-side encryption of Azure Disk Storage](/en-us/azure/virtual-machines/disk-encryption) for:

- FIPS 140-2 compliant transparent encryption with [AES 256 encryption](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard).
- Greater flexibility to manage controls.
- Hardware (HSM) or software-defined encryption.

[Enable server-side encryption](/en-us/azure/virtual-machines/disks-enable-host-based-encryption-portal#prerequisites) at the host for end-to-end encryption of your virtual machine data.

After completing these procedures, you use your customer-managed encryption key to encrypt the disks within your virtual machine.

You select the encryption type on the **Disks** blade for the virtual machine configuration. For **Encryption type**, select **Double encryption with platform-managed and customer-managed keys**, as shown here.

[![Screenshot for selecting the encryption type for a virtual machine.](media/vm/vm-create-vm-step4.png)](media/vm/vm-create-vm-step4.png#lightbox)

## Step 5: Control the applications installed on virtual machines

It's important to control the applications that are installed on your virtual machines:

- Browser extensions (APIs) are difficult to secure which can lead to malicious URL delivery.
- Unsanctioned apps can go unpatched as they're shadow IT objects (the IT teams aren't prepared or have no knowledge that these are installed).

You can use the Virtual Machine Applications feature to control the applications that are installed on virtual machines. With this feature, you select which virtual machine applications to install. This feature uses the Azure Compute Gallery to simplify management of applications for virtual machines. When used together with RBAC, you can ensure that only trusted applications are available for users.

You select the virtual machine applications on the **Advanced** blade for the virtual machine configuration, as show here.

[![Screenshot for configuring applications of a virtual machine.](media/vm/vm-create-vm-step5.png)](media/vm/vm-create-vm-step5.png#lightbox)

## Step 6: Configure secure access

To configure secure access:

- Configure secure communication within the Azure environment between components that are accessing virtual machines directly
- Set up multifactor authentication with conditional access
- Use privileged access workstations (PAWs)

[![Diagram of the logical architecture for configuring secure access to a virtual machine.](media/vm/azure-infra-vm-secure-access.svg)](media/vm/azure-infra-vm-secure-access.svg#lightbox)

In the diagram:

- multifactor authentication with conditional access is set up within Microsoft Entra ID and related portals.
- Admins use privileged access workstations (PAWs) to access virtual machines directly.

### Configure secure communication within the Azure environment for virtual machines

First, be sure that communication between the components in the Azure environment is secure.

In the reference architecture, [Azure Bastion](/en-us/azure/bastion/bastion-overview#key-features) provides secure connections to virtual machines. Azure Bastion acts as an RDP/SSH broker and doesn't interact with the RDP protocol of your physical system. This also enables you to reduce the number of public-facing IP addresses.

The following diagram shows the components of secure communications for virtual machines.

[![Diagram of the components of secure communications for virtual machines within the Azure IaaS reference architecture.](media/vm/azure-infra-vm-secure-comm.svg)](media/vm/azure-infra-vm-secure-comm.svg#lightbox)

### Set up multifactor authentication with conditional access

In Step 2. Leverage Role Based Access Control, you configured Microsoft Entra integration and managed identity. This allows you to set up [Azure multifactor authentication for Azure Virtual Desktop](/en-us/azure/virtual-desktop/set-up-mfa) or for servers running [Windows Server 2019 or newer](/en-us/azure/active-directory/devices/howto-vm-sign-in-azure-ad-windows). You can also [Log in to a Linux VM with Microsoft Entra credentials](/en-us/azure/active-directory/devices/howto-vm-sign-in-azure-ad-linux). The added benefit of this is the machine that connects to the virtual machine must also be registered to your Microsoft Entra ID tenant to be allowed to connect.

When configuring multifactor authentication with conditional access and related policies, use the recommended policy set for Zero Trust as a guide. This includes **Starting point** policies that don't require managing devices. Ideally, the devices accessing your virtual machines are managed and you can implement the **Enterprise** policies, which is recommended for Zero Trust. For more information, see [Common Zero Trust identity and device access policies](/en-us/microsoft-365/security/office-365-security/identity-access-policies).

The following diagram shows the recommended policies for Zero Trust.

[![Diagram of the Zero Trust identity and device access policies for three protection levels: Starting point, Enterprise, and Specialized security.](media/identity-device-access-policies-byplan.svg)](media/identity-device-access-policies-byplan.svg#lightbox)

Remember that usernames and passwords can be 100% compromised. Using multifactor authentication, you reduce your risk of compromise by 99.9%. This requires Microsoft Entra ID P1 licenses.

Note

You can use VPNs used to connect to virtual machines in Azure as well. However, you should be sure to use methods to verify explicitly. Creating a tunnel that is "trusted" regardless of how they are used can be riskier than having specific connections that are highly verified.

No amount of security at the Network, Transport, or Application layers matters if you aren't coming from a trusted, verified, and secure source.

### Use PAWs

Use [Privileged Access Workstations (PAWs)](/en-us/security/compass/privileged-access-devices) to ensure devices that access virtual machines are healthy. PAWs are configured specifically for privileged access so that admins use a device that has:

- Security controls and policies that restrict local administrative access.
- Productivity tools to minimize the attack surface to only what's absolutely required for performing sensitive administrative tasks.

For more information on deployment options, see [Privileged access deployment](/en-us/security/compass/privileged-access-deployment).

## Step 7: Set up secure maintenance of virtual machines

Secure maintenance of virtual machines includes:

- Using anti-malware
- Automating virtual machine updates

### Use anti-malware on virtual machines

Anti-malware helps protect your virtual machine from threats such as malicious files and adware, etc. You can use anti-malware software from an option of vendors such as Microsoft, Symantec, Trend Micro, and Kaspersky.

[Microsoft Antimalware](/en-us/azure/security/fundamentals/antimalware) is a no-cost resource that provides real-time protection capability to assist in detection, quarantining and eradicating malicious software, spyware, and viruses:

- Runs in the background with the need of user interaction
- Provides alerts when unwanted or malicious software is downloaded, installed, or run
- Offers secure-by-default configuration and anti-malware monitoring
- Scheduled scanning
- Signature updates
- Antimalware Engine and Platform updates
- Active Protection
- Samples reporting
- Exclusions
- Antimalware event collection

### Automate virtual machine updates

Automating updates to systems ensures they are protected from the latest malware and misconfiguration exploits. There's automatic updating with aid in the trusted platform verification process.

Concentrate on [Azure Virtual Machine Maintenance and Updates](/en-us/azure/virtual-machines/maintenance-and-updates) to ensure your systems are hardened against configuration insecurities:

- [Azure Automation Update Management](/en-us/azure/architecture/hybrid/azure-update-mgmt) can assist in the management of your update process. With this utility, you can check the update status of your systems, manage, schedule, and reboot servers.
- The Azure [Virtual Machine Agent](/en-us/azure/virtual-machines/extensions/agent-windows) is used to manage your virtual machines and gives you the ability to use extensions for management.

[Operating systems supported by Update Management](/en-us/azure/automation/update-management/operating-system-requirements) include the following:

- Each Windows virtual machine - Update Management does a scan twice a day for each machine.
- Each Linux virtual machine - Update Management does a scan every hour.

See this additional guidance:

- [Plan deployment for updating Windows VMs in Azure](/en-us/azure/architecture/example-scenario/wsus/)
- [Use Azure Private Link to securely connect networks to Azure Automation](/en-us/azure/automation/how-to/private-link-security) Ensures virtual machines connect in an isolated controlled fashion and not over the internet for updates.

## Step 8: Enable advanced threat detection and protection

Threat protection for Azure infrastructure is provided by Microsoft Defender for Cloud. This protection is extended to virtual machines when you provision [Microsoft Defender for Servers](/en-us/azure/defender-for-cloud/defender-for-servers-introduction), as shown in the following diagram.

[![Diagram of the logical architecture showing how Microsoft Defender for Cloud along Microsoft Defender for Servers provides threat detection and protection for virtual machines.](media/vm/azure-infra-vm-threat-protection.svg)](media/vm/azure-infra-vm-threat-protection.svg#lightbox)

In the diagram:

- As described in the [Apply Zero Trust principles to Azure IaaS overview](azure-infrastructure-overview) article, Defender for Cloud is enabled at the level of an Azure subscription or at the level of an Azure management group that includes multiple Azure subscriptions.
- In addition to enabling Defender for Cloud, Defender for Servers is provisioned.

Advanced threat protection verifies the activities occurring on virtual machines based on Microsoft's threat intelligence. It looks for specific configurations and activities that suggest that there could be a breach. It enables the **Verify explicitly** and **Assume breach** Zero Trust principles.

Microsoft Defender for Servers includes the following:

- Access to the [Microsoft Defender for Endpoint](https://www.microsoft.com/security/business/endpoint-security/microsoft-defender-endpoint?rtc=1) data that is related to vulnerabilities, installed software, and alerts for your endpoints for endpoint detection and response (EDR).
- [Defender for Cloud's integrated vulnerability assessment](/en-us/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management) scanner for servers.
- Discover vulnerabilities and misconfigurations in real time with Microsoft Defender for Endpoint, and without the need of other agents or periodic scans.
- [Defender for Cloud's integrated Qualys scanner for Azure and hybrid machines](/en-us/azure/defender-for-cloud/deploy-vulnerability-assessment-vm) allows you to use a leading tool in real-time vulnerability identification without the need of a Qualys license.
- Implement [Just-in-time virtual machine access in Defender for Cloud](/en-us/azure/defender-for-cloud/just-in-time-access-usage). This creates an explicit deny rule for RDP/SSH and gives you JIT access at the server level when you need it and allows you to limit the period of access.
- [File integrity monitoring in Defender for Cloud](/en-us/azure/defender-for-cloud/file-integrity-monitoring-overview) provides you to change monitoring of files and registries of the operations system, application software, and other changes that allow you to validate the integrity of your file systems.
- [Adaptive application controls in Defender for Cloud](/en-us/azure/defender-for-cloud/adaptive-application-controls) provides an automated solution for creating and defining allow list for known safe applications and generates security alerts if a new application runs other than those you define as safe for use.
- [Adaptive network hardening in Defender for Cloud](/en-us/azure/defender-for-cloud/adaptive-network-hardening?WT.mc_id=Portal-Microsoft_Azure_Security) uses machine learning algorithms that calculate your current traffic, threat intelligence, indicators of compromise, and known trusted configurations to provide recommendations for hardening your Network Security Groups.

## Technical illustrations

These illustrations are replicas of the reference illustrations in these articles. Download and customize these for your own organization and customers. Replace the Contoso logo with your own.

| Item | Description |
| --- | --- |
| [![thumbnail picture 1](media/thumb-zero-trust-iaas-contoso.png)](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx)[Download Visio](https://download.microsoft.com/download/2/d/e/2de84267-39d1-4845-8d31-83d97c9844a1/zero-trust-iaas-contoso.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS** Use these illustrations with these articles:  - [Overview](azure-infrastructure-overview) - [Azure storage](azure-infrastructure-storage) - [Virtual machines](azure-infrastructure-virtual-machines) - [Azure spoke virtual networks](azure-infrastructure-iaas) - [Azure hub virtual networks](azure-infrastructure-networking) |
| [![thumbnail picture 2](media/thumb-zero-trust-iaas-contoso-poster.png)](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx)[Download Visio](https://download.microsoft.com/download/b/6/b/b6b7207a-8b19-4a9a-a2c5-c6573e0f6685/zero-trust-iaas-contoso-poster.vsdx) Updated October 2024 | **Apply Zero Trust principles to Azure IaaS — One page poster** A one-page overview of the process for [applying the principles of Zero Trust to Azure IaaS environments](azure-infrastructure-overview). |

For additional technical illustrations, see [Zero Trust illustrations for IT architects and implementers](zero-trust-tech-illus).

## Recommended training

### Secure your Azure virtual machine disks

| Training | [Secure your Azure virtual machine disks](/en-us/training/modules/secure-your-azure-virtual-machine-disks) |
| --- | --- |
| ![](media/secure-your-azure-virtual-machine-disks.svg) | Learn how to use Azure Disk Encryption (ADE) to encrypt OS and data disks on existing and new virtual machines. In this module, you learn how to: - Determine which encryption method is best for your virtual machine.<br>- Encrypt existing virtual machine disks using the Azure portal.<br>- Encrypt existing virtual machine disks using PowerShell.<br>- Modify Azure Resource Manager templates to automate disk encryption on new virtual machines. |

For more training on Azure, see the entire Microsoft catalog:[Browse all - Training | Microsoft Learn](/en-us/training/browse)

### Implement virtual machine host security in Azure

| Training | [Implement virtual machine host security in Azure](/en-us/training/paths/implement-host-security) |
| --- | --- |
| ![](media/implement-host-security.svg) | In this learning path, learn how to protect and harden your virtual machines in Azure. |

For more training on virtual machines in Azure, see these resources in the Microsoft catalog:[Virtual machines in Azure | Microsoft Learn](/en-us/training/browse/?products=azure&amp;subjects=virtual-machine&amp;expanded=infrastructure)