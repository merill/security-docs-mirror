---
layout: Conceptual
title: Establish an Infrastructure and Networking discipline | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-infrastructure
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Use the Microsoft security adoption model to secure cloud infrastructure, including networks, based on Zero Trust principles.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: dfe14e3f-f132-1c31-1726-d21ffbbb1214
document_version_independent_id: dfe14e3f-f132-1c31-1726-d21ffbbb1214
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-infrastructure.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-infrastructure
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-infrastructure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: f8bea2ab-a1d5-79f0-5d75-7225a59bd326
---

# Establish an Infrastructure and Networking discipline | Microsoft Learn

This article helps security and technology teams establish and modernize an Infrastructure Security discipline. This discipline focuses on protecting the foundational systems and platforms that underpin the security of systems and data across the organization, including the systems used to define, create, change, and govern it.

This guidance is part of the **Microsoft Security Adoption Framework (SAF)**, a broader body of guidance for planning, prioritizing, and implementing end-to-end security modernization. SAF connects business scenarios, security disciplines, and technical implementation so that strategy, architecture, operations, and controls work together rather than as isolated recommendations.

Within SAF, Infrastructure Security is a technical strategy discipline focused on secure-by-design operation of foundational platforms and connectivity.

## Why this discipline?

The Infrastructure Security discipline helps organizations reduce risk from large‑scale compromise by preventing and limiting damage to datacenters, servers, containers, networks, storage, cloud services, and other resources that store and process sensitive data and workloads.

It's a key strategic priority frequently targeted by threat actors because compromise allows them access to many systems at once. A modern, disciplined approach to infrastructure security limits blast radius, improves resilience, and enables secure operations at scale.

Infrastructure underpins every security outcome. If the cloud, containers, virtualization or other infrastructure platforms are compromised, attackers can rapidly access workloads, data, and identities across the organization.

Without effective infrastructure and networking security, organizations might experience:

- Ransomware and extortion attacks
- Large‑scale data breaches
- Regulatory noncompliance
- Operational outages and service disruption

These impacts translate directly into financial loss, reputational damage, and harm to customers and critical services. Infrastructure security is therefore a strategic priority, not just a technical concern.

## Mission and outcomes

The mission of the Infrastructure Security discipline is to safeguard the foundational systems that support workloads and data across on‑premises, hybrid, and multicloud environments. Outcomes of the mission include:

- Reduced blast radius from infrastructure compromise
- Consistent security controls across environments
- Improved resilience against ransomware and service outages
- Stronger protection for sensitive workloads and data
- Alignment of infrastructure security with business risk

Infrastructure security reduces risk by preventing, detecting, and limiting damage to datacenters, servers, containers, networks, storage, and cloud services throughout their lifecycle.

## How to apply this discipline

To apply the Infrastructure and Networking Security discipline effectively, focus on establishing a consistent approach to securing the platforms and connectivity that support your organization:

1. **Define an infrastructure security strategy aligned to business risk** Establish a clear approach for securing platforms, workloads, and network environments in a way that protects critical systems and reduces the most significant risks.
2. **Ensure consistent protection across hybrid and multicloud environments** Apply a unified approach to securing infrastructure across on-premises, cloud, and edge environments to reduce gaps and inconsistencies.
3. **Establish standardized security configurations and practices** Provide clear guidance, reusable secure infrastructure patterns, templates, and modules to ensure that infrastructure and network controls are implemented consistently across environments and workloads. Embed security requirements into these reusable components so that secure configurations are applied by default.
4. **Align infrastructure security with business-critical services and scenarios** Prioritize protections for the systems and services that support critical business operations and key scenarios such as secure remote work and protection of critical assets.
5. **Automate infrastructure configuration and policy enforcement** Use infrastructure as code (IaC), policy as code, and automated governance to define, deploy, and maintain secure infrastructure configurations consistently at scale. Integrate security validation and policy enforcement into deployment pipelines so that insecure or noncompliant configurations can be identified or prevented before reaching production.
6. **Continuously monitor and improve infrastructure security posture** Use insights from vulnerabilities, misconfigurations, configuration drift, and operational signals to strengthen protections and reduce risk over time.

## Manage change

The Infrastructure Security Technology Strategy defines how an organization applies modern tools and architectures to protect its foundational systems where critical data resides.

- Strategy focuses on implementing Zero Trust principles, advanced threat protection, automated patching, and continuous monitoring to ensure confidentiality, integrity, and availability of data across hybrid environments.
- Strategy aligns technology investments with risk reduction goals, enabling secure connectivity, resilience against cyberattacks, and compliance with regulatory standards.
- Without a clear strategy, organizations face fragmented security controls, increased vulnerabilities, and higher risks of data breaches, service outages, and regulatory penalties.

Modernization of this discipline is focused on:

- Continuously improving infrastructure security throughout the lifecycle of govern, identify, protect, detect, respond, and recover.
- Implementing security controls through infrastructure as code (IaC), automated policy enforcement, automated patching, and continuous monitoring to consistently deploy secure configurations, prevent or detect configuration drift, and address evolving threats and compliance requirements.
- Integrating security into infrastructure engineering and deployment pipelines so that infrastructure definitions, configuration changes, and policy changes can be reviewed, tested, validated, and deployed through controlled and repeatable processes.

These efforts ensure confidentiality, integrity, and availability of data by reducing attack surfaces, preventing unauthorized access, and maintaining resilience against disruptions.

Technology infrastructure is highly complex, has many moving parts, is constantly evolving, and must stay secure against persistent and evolving threats. This means that effective infrastructure security must be:

- **Comprehensive** - Controls must address the various technical elements of infrastructure including networks, endpoints (servers, containers, and more), data, apps, and more to avoid providing threat actors an unguarded access path they can exploit. This requires using a combination of well-know security techniques and the integration of advanced automation and technology as it becomes available.
- **Consistent and Rigorous** - Security controls must be applied consistently and rigorously across all instances of each technology to avoid providing threat actors an opportunity to exploit vulnerabilities in overlooked or undiscovered resources.
- **Automated and Repeatable** - Infrastructure security should use infrastructure as code, reusable secure configurations, automated security testing, and automated policy enforcement wherever practical. Automation helps organizations apply security controls consistently at scale while reducing manual configuration errors and configuration drift.
- **Continuously Improved** - Both the infrastructure itself and the threat actors are constantly evolving, so all aspects of security must continuously evolve as well including threat models, security architectures and controls, how security is integrated into infrastructure management and automation, and more.

Tip

Infrastructure automation systems, including source repositories, infrastructure as code, CI/CD pipelines, deployment identities, reusable modules, and associated secrets and credentials should be protected as security-sensitive infrastructure because their compromise can enable changes to infrastructure at scale.

Change management is critical. Infrastructure operators must be involved early and consistently— security controls that ignore operational reality fail or are bypassed.

## Discipline roles and collaborators

The Infrastructure Security discipline typically requires close collaboration between technical and security teams. These roles must:

- Work together to ensure that security controls are embedded across infrastructure layers to maintain confidentiality, integrity, and availability of data.
- Are responsible for planning, designing, and operating secure foundational systems (networks, compute, storage, and cloud platforms) where critical data resides.

In larger organizations, dedicated specialists typically own infrastructure security responsibilities. In smaller organizations, roles might be combined with other technical roles.

Primary Roles:

- **Security Architect** – Designs secure architectures for on-premises and cloud infrastructure, applying Zero Trust principles and integrating identity, network, and platform security.
- **Infrastructure Engineering and Operations** – Implements and operates secure infrastructure using standardized configurations, automation, patching, monitoring, and policy enforcement. Maintains secure configurations and compliance across infrastructure components.
- **Network Engineer** – Focuses on secure connectivity, segmentation, and protection of data in transit across hybrid environments.

Key internal collaborators include:

- **Enterprise and Solution Architects** – Ensure security requirements are integrated into infrastructure designs and modernization initiatives.
- **Security Strategy, Integration, and Governance** – Provides governance and oversight for security controls, aligning infrastructure security with organizational risk management. Helps prioritize projects and vulnerabilities based on organizational risk and impact.
- **Developers and Application Teams** – Collaborate to ensure infrastructure supports secure application deployment and data protection.
- **Development Security** - Secures infrastructure code, deployment pipelines, reusable modules, and other software-defined infrastructure artifacts.
- **CISO and Security Leadership** – Define strategic priorities, risk tolerance, and compliance objectives for infrastructure security.

Infrastructure architects must understand how identity, network, and platform security intersect to protect workloads effectively.

## Alignment with other disciplines

Infrastructure and Networking security works in concert with other SAF disciplines:

- **Access and Identities** – Secures privileged human access and the workload, service, automation, and deployment identities used to manage infrastructure.
- **Security Operations (SecOps)** – Detects and responds to infrastructure‑based attacks.
- **Data Security** – Protects sensitive data hosted and processed on infrastructure.
- **Security Architecture and Governance** – Aligns controls with risk and business priorities.

This alignment ensures infrastructure security supports end‑to‑end security outcomes rather than operating as an isolated silo.

## Alignment with technology pillars

You must apply Infrastructure Security work across the technology estate. Technology pillars organize the different types of technology assets to protect and the technology controls used to protect them.

[![Infrastructure Security - mapping to technology pillars](media/security-adoption-discipline-infrastructure.png)](media/security-adoption-discipline-infrastructure.png#lightbox)

Infrastructure Security applies to these technology pillars in the following ways:

- **Identities**: Protect the identities and access mechanisms used to administer and operate infrastructure, including privileged users, workload identities, service accounts, automation, deployment pipelines, and AI agents. Apply least privilege, strong authentication, credential and secret protection, and monitoring appropriate to the level of access and authority granted.
- **Endpoints**: Protect administrative workstations and other endpoint devices used to access, administer, and operate infrastructure. Apply secure configuration, vulnerability and patch management, endpoint protection, strong access controls, and monitoring, with particular attention to endpoints with privileged access to infrastructure.
- **Infrastructure**: Protect cloud platforms and control planes, servers, virtualization platforms, containers and orchestration platforms, storage, compute, management systems, and other foundational infrastructure. Apply standardized secure configurations, infrastructure as code (IaC), reusable secure patterns, automated security testing, policy enforcement, vulnerability management, monitoring, and configuration drift detection to maintain security consistently at scale.
- **Apps**: Protect infrastructure components that host, connect, or provide platform services to applications. Apply infrastructure security requirements to application hosting environments, platform services, deployment environments, secrets and certificates, and supporting infrastructure. Coordinate infrastructure changes with application owners when those changes can affect application security, availability, or functionality.
- **Data**: Protect the infrastructure used to store, process, transmit, back up, and recover data. Apply infrastructure controls such as secure configuration, access restrictions, encryption, isolation, resilient architecture, and secure backup and recovery according to the sensitivity, business importance, and security requirements of the data.
- **Networking**: Protect network infrastructure and connectivity across on-premises, cloud, multicloud, edge, and remote environments. Apply segmentation, filtering, secure connectivity, encryption, threat protection, denial-of-service protections, monitoring, and other network controls to limit unauthorized access and movement while maintaining required business connectivity.
- **AI**: Protect the infrastructure and platform services used to develop, host, connect, and operate AI applications and agents. Apply infrastructure security controls to AI compute, platform services, network connectivity, data access paths, management interfaces, and the identities used by AI workloads and agents. Apply appropriate controls to AI-enabled automation that can make or initiate infrastructure changes.

## Microsoft resources

### Workshop

Microsoft Unified offers expert-led workshops to help organizations modernize their Infrastructure Security strategy, architecture, and technology. These workshops include:

- **Architecture and strategy workshops** - The *Security Adoption Framework (SAF) - Architecture Design Session: Infrastructure and Development Security* workshop focuses on accelerating development security modernization and integration with infrastructure security. This workshop is available as a less than four-hour summary/discussion focused on key learnings and best practices.
- **Technology adoption workshops** - Microsoft Unified has workshops to help organizations learn about, plan, implement, and optimize the use of Microsoft infrastructure and networking technologies including Microsoft Entra and Microsoft Intune.

### Technology

Microsoft offers technology solutions that enable and accelerate modernization of infrastructure security.

| **Technology** | **Details** |
| --- | --- |
| **Microsoft Defender for Cloud** | Provides extended detection and response (XDR) and posture management capabilities to monitor and secure your 'hybrid of everything' infrastructure across Azure, AWS, GCP, and on-premises resources (including VMs, Networks, Kubernetes/Containers, SQL, Storage, IoT/OT, & more). Key capabilities within Microsoft Defender for Cloud include: - [*Defender for Servers*](/en-us/azure/defender-for-cloud/defender-for-servers-overview) - provides recommendations to improve and remediate security posture, protects machines against real-time security threats and attacks with Defender for Endpoint integration, and offers agentless scanning for vulnerabilities. - [*Defender For Containers*](/en-us/azure/defender-for-cloud/defender-for-containers-introduction) - cloud-native solution to enhance, monitor, and maintain the security of your containerized assets (Kubernetes clusters, nodes, workloads, registries, images, and more) and their applications across multicloud and on-premises environments.- [*Defender for SQL*](/en-us/azure/defender-for-cloud/defender-for-sql-introduction) - helps discover and mitigate potential database vulnerabilities with vulnerability assessment and alerts on anomalous activities that might indicate threats to your databases.- [*Defender for Storage*](/en-us/azure/defender-for-cloud/defender-for-storage-introduction) - detects potential threats to storage accounts with malware scanning and sensitive data threat detection across Azure Blob Storage, Azure Files, and Azure Data Lake Storage.- [*Defender for Databases*](/en-us/azure/defender-for-cloud/defender-for-databases-overview) - helps protect database estates from threats and vulnerabilities with threat protection and security management for Azure SQL, open-source databases, and Cosmos DB.- [*AI Security Posture Management*](/en-us/azure/defender-for-cloud/ai-security-posture) - discovers generative AI applications, identifies vulnerabilities, and reduces risks with built-in recommendations and attack path analysis for AI workloads. |
| [**Microsoft Sentinel**](/en-us/azure/sentinel/overview) | Cloud native SIEM + SOAR + Data Lake solution that includes detection and response for infrastructure components. |
| [**Azure Arc**](/en-us/azure/azure-arc/overview) | Enables unified governance and management across on-premises data centers, multiple clouds, and edge components by projecting your existing non-Azure and/or on-premises resources into Azure Resource Manager. |
| [**Microsoft Entra**](/en-us/entra/fundamentals/whatis) | Supports strong identities for developers as well as identities for the application and avoiding roll your own identities and crypto |
| [**Microsoft Intune**](/en-us/intune/intune-service/fundamentals/what-is-intune) | Supports with cloud-based endpoint management solution for securing developer workstations with mobile device management (MDM) and mobile application management (MAM) |
| [**Microsoft Defender XDR**](/en-us/defender-xdr/microsoft-365-defender) | Supports with detection and response capabilities for developer workstations, CI/CD systems, servers, containers, and more that are required for a secure development environment. |
| **Microsoft Azure** | Supports with security capabilities in the cloud infrastructure that should be leveraged for software design and implementation including [Azure Firewall](/en-us/azure/firewall/overview), [Azure WAF](/en-us/azure/web-application-firewall/overview), [DDoS Protection](/en-us/azure/ddos-protection/ddos-protection-overview), [Azure Key Vault](/en-us/azure/key-vault/general/overview), [Azure Bastion](/en-us/azure/bastion/bastion-overview), [Azure Lighthouse](/en-us/azure/lighthouse/overview), and [Azure Backup](/en-us/azure/backup/backup-overview). |

Next steps

[Learn how](security-adoption-discipline-iot) OT/IoT security integrates into the Infrastructure and Networking discipline.