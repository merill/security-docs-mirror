---
layout: Conceptual
title: Microsoft security platform technologies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-platform
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about the products and services in the Microsoft security platform
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: edcbeeba-990f-bd80-cf68-f7b7a06870f4
document_version_independent_id: edcbeeba-990f-bd80-cf68-f7b7a06870f4
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-platform.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-platform
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-platform.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 58c66ac8-6631-7c5b-4bce-f4f9face7de1
---

# Microsoft security platform technologies | Microsoft Learn

This article describes Microsoft security services and how they work together as a unified system to deliver protection across [technology pillars](deploy/overview) that include identities, devices, applications, data, AI, and infrastructure.

Modern enterprise security shifted from perimeter-based protection to an identity-driven, cloud-integrated model. Organizations must secure users, devices, applications, and data across hybrid and multicloud environments while continuously adapting to evolving threats.

Microsoft provides an integrated set of cloud-based services that work together to share signals, apply consistent policies, enforce controls, and coordinate detection and response across the environment.

## Security outcomes

Integrated Microsoft security delivers the following outcomes:

- **Unified signal visibility**: Telemetry is continuously collected and centralized across identities, devices, applications, data, and infrastructure, and converted into centralized, actionable signals.
- **Identity-driven decision making**: Access and enforcement decisions are based on identity, device state, risk signals, and session context.
- **Consistent enforcement**: Zero Trust controls are applied across endpoints, cloud services, and applications at access time and during use.
- **Integrated detection and response**: Signals and alerts are correlated across domains to detect and respond to threats as unified operations.
- **Continuous validation and improvement**: Detection and risk signals feed back into policy decisions to strengthen protection over time.

## Core security services

Core security services span multiple technology pillars, each contributing signals, context, and enforcement across the platform.

| **PillarPrimary service** | **Protection** | **Primary portal** |
| --- | --- | --- |
| **Identity and access**Microsoft EntraMicrosoft Defender for Identity. | Microsoft Entra controls access for users, workloads, and applications. It evaluates identity, device, and session signals to make access decisions.Defender for Identity monitors hybrid identity infrastructure to detect attacks. | [Microsoft Entra admin center](https://entra.microsoft.com/)[Microsoft Defender portal](https://sip.security.microsoft.com/) |
| **Devices/endpoints**Microsoft Defender for EndpointMicrosoft Intune | Defender for Endpoint collects endpoint telemetry and detects threats.Microsoft Intune assesses device compliance and enforces policy. | [Microsoft Defender portal](https://sip.security.microsoft.com/)[Microsoft Intune admin center](https://intune.microsoft.com/) |
| **Email and collaboration**Defender for Office 365 | Protects Exchange and collaboration services (Microsoft Teams, SharePoint, OneDrive) from malware, malicious links/attachments, and business email compromise. | [Microsoft Defender portal](https://sip.security.microsoft.com/) |
| **Data**Microsoft Purview | Enforces data protection and data loss prevention (DLP) policies across endpoints and cloud services. | [Microsoft Purview portal](https://sip.purview.microsoft.com/) |
| **Infrastructure/cloud workloads**Microsoft Defender for Cloud | Improves security posture and provides threat detection across cloud and hybrid workloads. | [Microsoft Azure portal](https://ms.portal.azure.com/)[Microsoft Defender portal](https://sip.security.microsoft.com/) |
| **Networks**Azure networking services | Segment and protect networks. | [Microsoft Azure portal](https://ms.portal.azure.com/) |
| **SaaS/cloud apps**Microsoft Defender for Cloud Apps | Provides visibility into cloud app usage and monitors user activity to detect risky behavior. | [Microsoft Defender portal](https://sip.security.microsoft.com/) |
| **Posture/risk**Microsoft Security Exposure Management | Identifies, prioritizes, and reduces exposure across identities, devices, cloud resources, and applications. | [Microsoft Defender portal](https://sip.security.microsoft.com/) |
| **Threat detection/response**Microsoft Defender XDR | Correlates signals across Defender services and produces unified incidents for investigation and response. | Microsoft Defender portal |
| **Security operations**Microsoft Sentinel | Aggregates telemetry from Microsoft and third-party sources for centralized analysis, investigation, and response. | [Microsoft Azure portal](https://ms.portal.azure.com/)[Microsoft Defender portal](https://sip.security.microsoft.com/) |
| **Developer/app security**Defender for DevOps (in Defender for Cloud)GitHub Advanced Security | Secures code, dependencies, and build pipelines, and enforces security governance across DevOps workflows. | [Microsoft Defender portal](https://sip.security.microsoft.com/)GitHub interface |

## Network protection services

The table summarizes Azure networking capabilities and how they directly integrate with other security services. Services are configured in the [Microsoft Azure portal](https://ms.portal.azure.com/).

| **Service** | **Protection** | **Integration** |
| --- | --- | --- |
| **Azure Firewall** | Enforces IP, port, and application rules to control inbound and outbound traffic across subnets, internet, and on-premises networks. Uses Microsoft threat intelligence to block known malicious traffic. | Defender for Cloud evaluates configuration posture.Diagnostic logs are ingested into Azure Monitor/Log Analytics and analyzed by Microsoft Sentinel for detection and correlation. |
| **Azure DDoS Protection** | Mitigates volumetric, protocol, and application-layer attacks. Protects internet-facing resources in virtual networks (VNets) from large-scale flooding attacks. | Metrics and attack telemetry are ingested into Azure Monitor/Log Analytics and can be analyzed in Microsoft Sentinel.Defender for Cloud provides posture recommendations. |
| **Azure VNet** | Provides network isolation, segmentation, and private IP addressing for Azure resources. Enables controlled connectivity between services. | Defender for Cloud evaluates configuration state, including exposure such as public access paths. |
| **Network Security Groups (NSGs)** | Filters traffic at the subnet and network interface level using allow/deny rules. Restricts unwanted traffic to resources. | NSG flow logs (via Azure Monitor) can be analyzed in Microsoft Sentinel for traffic visibility and detection.Defender for Cloud evaluates NSG rule configuration. |
| **Azure Web Application Firewall (WAF)** | Protects HTTP/HTTPS applications using OWASP rule sets. Helps prevent common web attacks such as SQL injection and cross-site scripting (XSS). | WAF logs are ingested into Azure Monitor/Log Analytics and analyzed by Microsoft Sentinel.Defender for Cloud evaluates WAF configuration posture. |
| **Azure Front Door** | Provides a global entry point for web applications with routing, acceleration, and edge security capabilities. Integrates with WAF for application protection. | Diagnostic logs (Front Door/WAF) are ingested into Log Analytics and analyzed by Microsoft Sentinel.Defender for Cloud evaluates configuration posture. |
| **Azure Application Gateway** | Provides regional load balancing with built-in web application firewall capabilities to protect and route application traffic. | Access and WAF logs are ingested into Log Analytics and analyzed by Microsoft Sentinel.Defender for Cloud evaluates configuration posture and exposure settings. |
| **Azure VPN Gateway** | Provides encrypted IPsec/IKE connectivity between on-premises environments and Azure VNets. Protects data in transit over public networks. | Connection and tunnel logs are ingested into Log Analytics and can be analyzed in Microsoft Sentinel.Defender for Cloud evaluates configuration posture, including encryption settings. |
| **Azure ExpressRoute** | Provides private, dedicated connectivity between on-premises environments and Azure over the Microsoft backbone, avoiding the public internet. | Operational telemetry (such as BGP, circuit status) is available through Azure Monitor and can be analyzed in Microsoft Sentinel.Defender for Cloud evaluates high-level configuration posture. |
| **Azure Bastion** | Provides secure RDP and SSH access to virtual machines through a browser, eliminating the need for public IP exposure. | Diagnostic logs are ingested into Log Analytics and analyzed by Microsoft Sentinel.Defender for Cloud evaluates reduced VM, but not Azure Bastion configuration directly. |
| **Azure Private Link** | Provides private connectivity to Azure PaaS services and customer services using private IP addresses, eliminating public exposure. | Service-level logs (for services accessed via Private Link such as Storage, SQL, Key Vault) are ingested into Log Analytics and analyzed by Microsoft Sentinel.Defender for Cloud evaluates whether private links are used to reduce exposure. |
| **Azure Network Watcher** | Provides network diagnostics, monitoring, and flow-level visibility across Azure resources. | NSG flow logs and diagnostics are ingested into Log Analytics and can be analyzed in Microsoft Sentinel.Defender for Cloud evaluates underlying resource configuration state such as NSG settings, rather than Network Watcher directly. |

## Security workflow

Security services operate as a continuous pipeline. Signals are continuously collected, evaluated, enforced, and used to drive detection and response.

| **Pipeline** | **Action** | **Key activity** |
| --- | --- | --- |
| **Stage 1: Signal collection** | Security services generate telemetry across identities, devices, applications, and infrastructure. | - Defender for Endpoint collects device telemetry.- Microsoft Intune evaluates device compliance.- Defender for Identity monitors on-premises identity activity.- Defender for Cloud Apps monitors SaaS activity.- Defender for Cloud monitors infrastructure/workload configuration and activity. |
| **Stage 2: Policy decisions** | Signals are evaluated to determine access conditions and control actions. | Microsoft Entra Conditional Access evaluates identity risk, device trust, location, and session context. |
| **Stage 3: Control enforcement** | Security controls are applied across identity, device, session, data, and network layers. | Enforcement points include:- Conditional Access (MFA/restrictions)- Intune (device compliance)-Defender for Cloud Apps (session control)- Microsoft Purview (DLP)- Azure networking (connectivity restrictions). |
| **Stage 4: Detection and response** | Signals and alerts are correlated to detect, investigate, and remediate threats. | Microsoft Defender XDR correlates signals from all Defender products into unified incidents.Microsoft Sentinel centralizes logs, incidents, hunting, and security orchestration, automation, and response (SOAR) across the entire environment—including third-party sources. |
| **Feedback loop** | Detection outcomes feed back into policy decisions to continuously improve protection. | Risk and threat signals inform real-time policy updates, enabling adaptive and automated protection. |

## Security service integration

Microsoft security services integrate through multiple flows operating as a cohesive pipeline, forming a continuous system of protection.

- **Signals (telemetry)** capture activity across identities, devices, applications, and other resources.
- **Context (identity, device posture, and data classification)** enriches signals to improve accuracy and decision-making.
- **Policy** defines what access is allowed or blocked based on evaluated conditions.
- **Actions** enforce decisions through automated controls and response.

As signals move through the platform, they're enriched, evaluated against policy, and acted on, creating a continuous cycle of protection and response.

### How services integrate

The table summarizes how security services consume signals and context from each out, and what they output and action.

| **Service** | **Consumes** | **Outputs** |
| --- | --- | --- |
| **Microsoft Entra ID** | **Signals**: Authentication activity (sign-ins, risk events). Device compliance status from Microsoft Intune.**Context**: Device context for access decisions from Defender for Endpoint. Session context for access decisions from Defender for Cloud Apps. | **Actions**: Conditional Access decisions (allow, block, restrict, require controls). |
| **Microsoft Intune** | **Signals**: Managed devices inventory, health, compliance state. **Context**: Identity association from Microsoft Entra ID. | **Outputs**: Device compliance posture to Microsoft Entra ID. Device audit logs to Microsoft Sentinel. |
| **Microsoft Purview** | **Signals**: Enterprise data across Microsoft 365, SaaS apps, and on-premises systems.**Context**: Data classification (sensitivity labels, content inspection, user activity). | **Outputs**: Insider risk and data loss protection (DLP) alerts to Defender XDR. Compliance and audit logs to Microsoft Sentinel.**Actions**: DLP enforcement across endpoints (Defender for Endpoint), and sessions (Defender for Cloud Apps). |
| **Defender for Endpoint** | **Signals**: Endpoint telemetry (process, file, network activity).**Context**: Microsoft Entra ID (identity context). Microsoft Intune (device posture). Microsoft Purview (DLP policies). | **Outputs**: Endpoint alerts and telemetry to Defender XDR and Microsoft Sentinel.**Actions**: Endpoint enforcement (device isolation, blocking, remediation). |
| **Defender for Identity** | **Signals**: Active Directory identity signals. | **Output**: Identity threat alerts to Defender XDR and Microsoft Sentinel. |
| **Defender for Cloud Apps** | **Signals**: SaaS app activity (cloud usage). Network and shadow IT telemetry from Defender for Endpoint.**Context**: Session and authentication context from Microsoft Entra ID. DLP policies from Microsoft Purview. | **Outputs**: Cloud app alerts to Defender XDR and Microsoft Sentinel.**Actions**: Session enforcement (block, monitor, restrict access). |
| **Defender for Cloud** | **Signals**: Resource operation information from Azure. Server/workload telemetry from Defender for Endpoint.**Context**: Resource configuration and posture. | **Outputs**: Security alerts and posture insights to Defender XDR and Microsoft Sentinel. |
| **Microsoft Security Exposure Management** | **Signals**: Device risk scores from Defender for Endpoint. Cloud resource inventory, posture, exposure, and attack surface findings from Defender for Cloud. Identity inventory and risk signals from Microsoft Entra. SaaS app inventory, risk, and usage context from Defender for Cloud Apps.**Context**: Unified exposure and risk correlation. | **Outputs**: Exposure insights and risk correlations to Microsoft XDR and Microsoft Sentinel. |
| **Defender XDR** | **Signals**: Alerts from Defender for Endpoint (devices), Defender for Identity (identity signals), Defender for Office 365 (email and collaboration), Defender for Cloud Apps (SaaS/app activity). Extra signals from Microsoft Purview (DLP, insider risk, data classification), Microsoft Entra ID Protection (identity risk signals), and Defender for Cloud (workload/cloud posture). | **Outputs**: Correlated alerts, incidents to Microsoft Sentinel.**Actions**: Automated cross-domain response. |
| **Microsoft Sentinel** | **Signals**: Alerts, logs, telemetry from Defender XDR, Microsoft Purview, cloud services, and other first-party/third-party sources. | **Outputs**: Analytics, investigations, and incidents.**Actions**: Automated response using playbooks. |
| **Microsoft Security Copilot** | **Signals**: Incidents and alerts from Microsoft Sentinel and Defender XDR.**Context**: Sensitive data and insider risk context from Microsoft Purview. Exposure context from Microsoft Security Exposure Management. | **Outputs**: Investigation summaries, recommendations, AI-driven insights.**Actions**: Guided response actions routed through Microsoft Sentinel and Defender XDR workflows. |