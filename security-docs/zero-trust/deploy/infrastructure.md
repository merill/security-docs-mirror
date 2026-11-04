---
layout: Conceptual
title: Securing infrastructure with Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/deploy/infrastructure
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Infrastructure represents a critical threat vector. A Zero Trust strategy makes it easier for you to develop, test, deliver, monitor, control, and support IT services.
ms.date: 2024-04-30T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: best-practice
ms.collection:
- zerotrust-pillar
locale: en-us
document_id: 80d81697-3ade-f1da-c79e-7de6277a2c2a
document_version_independent_id: d6b9f71d-c0ae-6768-fc47-37baa4f78b63
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/deploy/infrastructure.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/deploy/infrastructure
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/deploy/infrastructure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/8e3fdb08-a059-4277-98f6-c0e21e940707
- https://authoring-docs-microsoft.poolparty.biz/devrel/eea02214-631d-404a-92d1-5a3357c32a26
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/88291526-9c74-4f87-878c-de0a82134421
- https://authoring-docs-microsoft.poolparty.biz/devrel/f42c31d7-eed9-43b7-9757-54caffb53cdc
platformId: 6b9a5d7b-1823-7600-c838-9ce5a529c3dd
---

# Securing infrastructure with Zero Trust | Microsoft Learn

![](../media/icon-infrastructure-medium.png)

Infrastructure represents a critical threat vector. IT Infrastructure, whether on-premises or multicloud, is defined as all the hardware (physical, virtual, containerized), software (open source, first- and third-party, PaaS, SaaS), micro-services (functions, APIs), networking infrastructure, facilities, and so on, that is required to develop, test, deliver, monitor, control, or support IT services. It's an area where Microsoft has invested tremendous resources to develop a comprehensive set of capabilities to secure your future cloud and on-premises infrastructure.

Modern security with an end-to-end Zero Trust strategy makes it easier for you to:

- Assess for version.
- Perform configuration management.
- Employ Just-In-Time and Just-Enough-Access (JIT/JEA) administrative privileges to harden defenses.
- Use telemetry to detect attacks and anomalies.
- Automatically block and flag risky behavior and take protective actions.

Just as importantly, Microsoft Azure Blueprints and related capabilities ensure that resources are designed, implemented, and sustained in ways that conform to an organization's policies, standards, and requirements.

Azure Blueprints, Azure Policies, Microsoft Defender for Cloud, Microsoft Sentinel, and Azure Sphere can greatly contribute to improving the security of your deployed infrastructure. Together, they enable a different approach to defining, designing, provisioning, deploying, and monitoring your infrastructure.

![A repeating circular diagram of five elements: Assess compliance, Observe gaps, Author, Test, and Deploy.](../media/diagram-infrastructure-5-elements-white-background.png)

## Infrastructure Zero Trust deployment objectives

Tip

Before most organizations start the Zero Trust journey, their approach to infrastructure security is characterized by the following:

- Permissions are managed manually across environments.
- Configuration management of VMs and servers on which workloads are running.

| When implementing an end-to-end Zero Trust framework for managing and monitoring your infrastructure, we recommend you focus first on these **initial deployment objectives**: |
| --- |
| ![List icon with one checkmark.](../media/icon-initial-deployment-small.png) | **I.**Workloads are monitored and alerted to abnormal behavior.<br><br>**II.**Every workload is assigned an app identity—and configured and deployed consistently.<br><br>**III.**Human access to resources requires Just-In-Time. |
| After the initial objectives are completed, focus on these **additional deployment objectives**: |
| ![List icon with two checkmarks.](../media/icon-additional-deployment-small.png) | **IV.**Unauthorized deployments are blocked, and alert is triggered.<br><br>**V.**Granular visibility and access control are available across workloads.<br><br>**VI.**User and resource access segmented for each workload. |

## Infrastructure Zero Trust deployment guide

This guide walks you through the steps required to secure your infrastructure following the principles of a Zero Trust security framework.

Before you get started, ensure you've met these baseline infrastructure deployment objectives.

**Setting the Microsoft Tenant Baseline**

A prioritized baseline should be set for how your Infrastructure is managed. Applying industry guidance such as NIST 800-53, you can derive a set of requirements for managing your infrastructure. At Microsoft, we have set a minimal baseline to the following list of requirements:

- Access to data, networks, services, utilities, tools, and applications must be controlled by authentication and authorization mechanisms.
- Data must be encrypted in transit and at rest.
- Restrict network traffic flows.
- Security team visibility into all assets.
- Monitoring and auditing must be enabled and correctly configured according to prescribed organizational guidance.
- Anti-malware must be up to date and running.
- Vulnerability scans must be performed, and vulnerabilities remediated, according to prescribed organizational guidance.

In order to measure and drive compliance to this minimal—or our expanded—baseline, we start with getting visibility at the Tenant level, and across your on-premises environments, by applying a Security Reader role across the Azure Tenant. With the Security Reader role in place, it can gain further visibility through Microsoft Defender for Cloud and Azure Policies that can be used to apply industry baselines (for example, Azure CIS, PCI, ISO 27001) or a custom baseline that your organization has defined.

### Permissions are managed manually across environments

From the tenant level down to the individual resources within each resource group ad subscription, appropriate role-based access controls must be applied.

Tip

[Learn about implementing an end-to-end identity Zero Trust strategy](https://aka.ms/ZTIdentity).

#### Configuration management of VMS and servers on which workloads are running

Just as we've managed our on-prem data center environment, we must also ensure that we're effectively managing our cloud resources. The benefit of leveraging Azure is the ability to manage all your VMs from one platform using [Azure Arc](https://azure.microsoft.com/services/azure-arc/) (preview). Using Azure Arc, you can extend your Security Baselines from [Azure Policy](/en-us/azure/governance/policy/overview), your [Microsoft Defender for Cloud](https://azure.microsoft.com/services/security-center) policies, and Secure Score evaluations, as well as logging and monitoring all your resources in one place. Below are some actions for getting started.

##### Implement [Azure Arc (preview)](https://azure.microsoft.com/services/azure-arc/)

[Azure Arc](https://azure.microsoft.com/services/azure-arc/) allows organizations to extend the familiar security controls of Azure to on-premises and the edge of the organization's infrastructure. Administrators have several options for connecting on-premises resources to Azure Arc. These include Azure portal, PowerShell, and Windows Installation with Service Principal scripting.

[Learn more about these techniques](/en-us/azure/azure-arc/).

##### Apply security baselines through Azure Policy, including application of in-guest policies

By enabling [Defender for Cloud](/en-us/azure/security-center/security-center-get-started), you'll be able to incorporate a set of baseline controls through [Azure Policy's built-in policy definitions for Microsoft Defender for Cloud](/en-us/azure/security-center/policy-samples). The set of baseline policies will be reflected in the [Defender for Cloud secure score](/en-us/azure/security-center/security-center-secure-score), where you can measure your compliance with those policies.

You can extend your coverage of policies beyond the Defender for Cloud set and create custom policies if a built-in isn't available. You can also incorporate [Guest Configuration policies](/en-us/azure/governance/policy/how-to/guest-configuration-create), which measure compliance inside your guest VMs within your subscriptions.

##### Apply Defender for Cloud Endpoint Protection and Vulnerability Management controls

Endpoint protection is essential to ensuring infrastructure remains secure and available. As part of any strategy for endpoint protection and vulnerability management, you'll be able to measure compliance centrally to ensure malware protection is enabled and configured through the [Endpoint protection assessment and recommendations in Microsoft Defender for Cloud](/en-us/azure/security-center/security-center-endpoint-protection).

**Centralized visibility of your baseline across multiple subscriptions**

By applying the tenant reader roll, you can get visibility across your tenant of the status of each of the policies that are being evaluated as part of the Defender for Cloud secure score, Azure Policy, and Guest Config policies. You funnel that to your organizational compliance dashboard for central reporting of the state of your tenant.

Additionally, as part of Defender for Servers, you can use the policy [Enable the built-in vulnerability assessment solution on virtual machines (powered by Qualys)](/en-us/azure/security-center/built-in-vulnerability-assessment) to scan your VMs for vulnerabilities, and have those reflected directly in Defender for Cloud. If you already have a Vulnerability scanning solution deployed in your enterprise, you can use the alternate policy Vulnerability assessment solution, which should be installed on your virtual machines for [Deploying a partner vulnerability scanning solution](/en-us/azure/security-center/partner-vulnerability-assessment).

Tip

[Learn about implementing an end-to-end Zero Trust strategy for endpoints](https://aka.ms/ZTEndpoints).

| ![Checklist icon with one checkmark.](../media/icon-initial-deployment.png) | Initial deployment objectives |
| --- | --- |

Once you've met the baseline infrastructure objectives, you can focus on implementing a modern infrastructure with an end-to-end Zero Trust strategy.

### I. Workloads are monitored and alerted to abnormal behavior

When you create new infrastructure, you need to ensure that you also establish rules for monitoring and raising alerts. This is key for identifying when a resource is displaying unexpected behavior.

We recommend **enabling Microsoft Defender for Cloud and its [plans to protect the supported resource types](/en-us/azure/defender-for-cloud/defender-for-cloud-introduction)**, including [Defender for Servers](/en-us/azure/defender-for-cloud/plan-defender-for-servers-select-plan), [Defender for Storage](/en-us/azure/defender-for-cloud/defender-for-storage-introduction), [Defender for Containers](/en-us/azure/defender-for-cloud/defender-for-containers-introduction), [Defender for SQL](/en-us/azure/defender-for-cloud/quickstart-enable-database-protections), etc.

For monitoring identities, we recommend **enabling [Microsoft Defender for Identity](/en-us/defender-for-identity/what-is) and [Advanced Threat Analytics](/en-us/advanced-threat-analytics/what-is-ata)** in order to enable signal collection to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.

Integrating these signals from Defender for Cloud, Defender for Identity, Advanced Threat Analytics, and other monitoring and auditing systems with [Microsoft Sentinel](/en-us/azure/sentinel/overview), a cloud-native, security information event management (SIEM) and security orchestration automated response (SOAR) solution, will allow your Security Operations Center (SOC) to work from a single pane of glass to monitor security events across your enterprise.

Tip

[Learn about implementing an end-to-end identity Zero Trust strategy](https://aka.ms/ZTIdentity).

### II. Every workload is assigned an app identity—and configured and deployed consistently

We recommend you use a [policy](/en-us/azure/governance/policy/tutorials/create-and-manage) that is assigned and enforced when creating resources/workloads. Policies can require tags be to applied to a resource upon creation, mandate resource group assignment, and restrict/direct technical characteristics, such as regions allowed, VM specifications (for example, VM type, disks, network policies applied).

Tip

[Learn about implementing an end-to-end Zero Trust strategy for applications](https://aka.ms/ZTApplications).

### III. Human access to resources requires Just-In-Time

Personnel should use administrative access sparingly. When administrative functions are required, users should receive temporary administrative access.

Organizations should establish a [Protect the Administrator](https://www.microsoft.com/itshowcase/protecting-high-risk-environments-with-secure-admin-workstations) program. Characteristics of these programs include:

- Targeted reduction in the number of users with administrative permissions.
- Auditing elevated permission accounts and roles.
- Creating special High-Value Asset (HVA) infrastructure zones to reduce surface area.
- Giving administrators special Secure Admin Workstations (SAWs) to reduce the likelihood of credential theft.

All of these items help an organization become more aware of how administrative permissions are being used, where these permissions are still necessary, and provide a roadmap for how to operate more securely.

| ![Checklist icon with two checkmarks.](../media/icon-additional-deployment.png) | Additional deployment objectives |
| --- | --- |

Once you've accomplished your initial three objectives, you can focus on additional objectives such as blocking unauthorized deployments.

### IV. Unauthorized deployments are blocked, and alert is triggered

When organizations move to the cloud, the possibilities are limitless. That's not always a good thing. For various reasons, organizations need to be able to block unauthorized deployments and trigger alerts to make leaders and managers aware of the issues.

Microsoft Azure offers [Azure Blueprints](/en-us/azure/governance/blueprints/overview) to govern how resources are deployed, ensuring that only approved resources (for example, ARM templates) can be deployed. Blueprints can ensure that resources which do not meet the Blueprint's policies or other rules are blocked from deployment. Actual or attempted Blueprint violation can raise alerts as needed and make notifications, activate webhooks or automation runbooks, or even create service management tickets.

### V. Granular visibility and access control are available across workloads

Microsoft Azure offers a variety of methods to achieve resource [visibility](https://aka.ms/ZTCrossPillars). From the Azure portal, resource owners can set up many metric and log collection and analysis capabilities. This visibility can be used not only to feed security operations but can also to support computing efficiency and organizational objectives. These include capabilities like [Virtual Machine Scale Sets](/en-us/azure/virtual-machine-scale-sets/overview), which allow for the secure and efficient scaling out and scaling in of resources based on metrics.

On the access control side, [Role-Based Access Control (RBAC)](/en-us/azure/role-based-access-control/overview) can be employed to assign permissions to resources. This allows permissions to be assigned and revoked uniformly at the individual and group levels by using a variety of built-in or custom roles.

### VI. User and resource access segmented for each workload

Microsoft Azure offers many ways to segment workloads to manage user and resource access. [Network segmentation](/en-us/azure/architecture/reference-architectures/hybrid-networking/network-level-segmentation) is the overall approach, and, within Azure, resources can be isolated at the subscription level with Virtual networks (VNets), VNet peering rules, Network Security Groups (NSGs), Application Security Groups (ASGs), and Azure Firewalls. There are several design patterns to determine the best approach to segmenting workloads.

Tip

[Learn about implementing an end-to-end Zero Trust strategy for your network](https://aka.ms/ZTNetwork).

## Products covered in this guide

**Microsoft Azure**

[Azure Blueprints](https://azure.microsoft.com/services/blueprints/)

[Azure Policy](/en-us/azure/governance/policy/overview)

[Azure Arc](https://azure.microsoft.com/services/azure-arc)

[Microsoft Defender for Cloud](https://azure.microsoft.com/products/defender-for-cloud/)

[Microsoft Sentinel](https://azure.microsoft.com/services/azure-sentinel/)

[Azure Resource Manager (ARM) templates](/en-us/azure/azure-resource-manager/templates/overview)

## Conclusion

Infrastructure is central to a successful Zero Trust strategy. For further information or help with implementation, please contact your Customer Success team, or continue to read through the other chapters of this guide, which spans all Zero Trust pillars.

**The Zero Trust deployment guide series**

[![Icon for the introduction](../media/icon-introduction-navbar.png)](https://aka.ms/ZTDeploymentGuideIntroduction)

[![Icon for identity](../media/icon-identity-navbar.png)](https://aka.ms/ZTIdentity)

[![Icon for endpoints](../media/icon-endpoints-navbar.png)](https://aka.ms/ZTDevices)

[![Icon for applications](../media/icon-applications-navbar.png)](https://aka.ms/ZTApplications)

[![Icon for data](../media/icon-data-navbar.png)](https://aka.ms/ZTData)

[![Icon for infrastructure](../media/icon-infrastructure-navbar.png)](https://aka.ms/ZTInfrastructure)

[![Icon for networks](../media/icon-networks-navbar.png)](https://aka.ms/ZTNetwork)

[![Icon for visibility, automation, orchestration](../media/icon-visibility-automation-orchestration-navbar.png)](https://aka.ms/ZTCrossPillars)