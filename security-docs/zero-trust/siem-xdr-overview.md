---
layout: Conceptual
title: Incident Response with XDR and Integrated SIEM | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/siem-xdr-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: bagol
author: batamig
description: Learn how to integrate Microsoft Sentinel and Defender XDR to quickly respond to incidents and improve Zero Trust security.
ms.subservice: zero-trust
manager: raynemw
ms.date: 2025-02-12T00:00:00.0000000Z
ms.topic: concept-article
ms.service: security
ms.collection:
- zerotrust-solution
- msftsolution-secops
- msftsolution-overview
- zerotrust-azure
- usx-security
ms.localizationpriority: medium
locale: en-us
document_id: d2006b65-7595-77b9-2afb-1d5089f066a9
document_version_independent_id: d2006b65-7595-77b9-2afb-1d5089f066a9
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/siem-xdr-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/siem-xdr-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/siem-xdr-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8a94907f-2511-4271-b5ca-ec7f2e75067c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1577a46d-8446-40bd-bfae-0578362f4d94
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bffa8e88-f633-409d-a24d-083bdbc68872
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/cdf3f22d-5420-4d59-a2bf-66d6b3d9c828
platformId: 69be2dcf-cf2a-09b2-f789-ac0b15f8e538
---

# Incident Response with XDR and Integrated SIEM | Microsoft Learn

This solution guide shows you how to set up Microsoft extended detection and response (XDR) tools and how to integrate these with Microsoft Sentinel so your organization can respond to and remediate cybersecurity attacks faster.

Microsoft Defender XDR is an XDR solution that automatically collects, correlates, and analyzes signal, threat, and alert data from across your Microsoft 365 environment.

Microsoft Sentinel is a cloud-native solution that provides security information and event management (SIEM) and security orchestration, automation, and response (SOAR) capabilities. Together, Microsoft Sentinel and Microsoft Defender XDR provide a comprehensive solution to help organizations defend against modern attacks.

This guidance helps you improve your Zero Trust architecture by mapping the principles of Zero Trust in the following ways:

| Zero Trust Principle | Met by |
| --- | --- |
| Verify explicitly | Microsoft Sentinel collects data from across the environment and analyzes threats and anomalies so your organization and any automation can act on verified data. Microsoft Defender XDR provides extended detection and response across users, identities, devices, apps, and emails. Configure Microsoft Sentinel automation to use risk-based signals captured by Microsoft Defender XDR to take action, such as blocking or authorizing traffic based on risk. |
| Use least privileged access | Microsoft Sentinel detects anomalous activity through its UEBA engine. As security scenarios change rapidly, its threat intelligence imports data from Microsoft and third-party providers to detect and contextualize emerging threats. Microsoft Defender XDR includes Microsoft Entra ID Protection to block users based on identity risk. Feed related data into Microsoft Sentinel for further analysis and automation. |
| Assume breach | Microsoft Defender XDR continuously scans the environment for threats and vulnerabilities. Microsoft Sentinel analyzes collected data and behavioral trends to detect suspicious activity, anomalies, and multistage threats across the enterprise.Both Microsoft Defender XDR and Microsoft Sentinel implement automated remediation tasks, including investigations, device isolation, and data quarantine. Use device risk as a signal for Microsoft Entra Conditional Access. |

## Getting started with Microsoft Defender XDR

Deploying Microsoft Defender XDR is a great starting point for building incident detection and response abilities within your organization. Defender XDR is included with Microsoft 365 E5 and you can even get started by using [Microsoft 365 E5 trial licenses](/en-us/defender-xdr/pilot-deploy-overview#using-microsoft-365-e5-trial-licenses). Defender XDR can be integrated with Microsoft Sentinel or with a [generic SIEM tool](/en-us/defender-cloud-apps/siem).

For more information, see [Pilot and deploy Microsoft Defender XDR](/en-us/defender-xdr/pilot-deploy-overview?toc=%2Fsecurity%2Fzero-trust%2Ftoc.json&amp;bc=%2Fsecurity%2Fbreadcrumb%2Ftoc.json).

[![Diagram of the process to evaluate and deploy Microsoft Defender XDR components.](media/copilot/defender-xdr-pilot-deploy-flow.svg)](media/copilot/defender-xdr-pilot-deploy-flow.svg#lightbox)

## Microsoft Sentinel and XDR architecture

Microsoft Sentinel customers can use one of these methods to integrate Microsoft Sentinel with Microsoft Defender XDR services:

- Onboard Microsoft Sentinel to the Defender portal to use it together with Microsoft Defender XDR for unified security operations. View Microsoft Sentinel data directly in the Defender portal alongside your Defender incidents, alerts, vulnerabilities, and security data.
- Use Microsoft Sentinel data connectors to ingest Microsoft Defender XDR service data into Microsoft Sentinel. View Microsoft Sentinel data in the Azure portal.

This guidance center provides information for both methods. If you've onboarded your workspace to the Defender portal, use it; if not, use the Azure portal unless otherwise indicated.

# [Defender portal](#tab/defender-portal)
The following illustration shows how Microsoft's XDR solution integrates with Microsoft Sentinel in the Defender portal.

[![Diagram of a Microsoft Sentinel and Microsoft Defender XDR architecture with the SecOps operations platform.](media/sentinel-xdr-unified-security-experience.png)](media/sentinel-xdr-unified-security-experience.png#lightbox)

In this diagram:

- Insights from signals across your entire organization feed into Microsoft Defender XDR and Microsoft Defender for Cloud.
- Microsoft Sentinel provides support for multicloud environments and integrates with third-party apps and partners.
- Microsoft Sentinel data is ingested together with your organization's data into the Microsoft Defender portal.
- SecOps teams can analyze and respond to threats identified by Microsoft Sentinel and Microsoft Defender XDR in the Microsoft Defender portal.

# [Azure portal](#tab/azure-portal)
This illustration shows how Microsoft's XDR solution integrates with Microsoft Sentinel in the Azure portal.

[![Diagram that shows the integration of Microsoft Sentinel and Microsoft XDR.](media/sentinel-xdr.png)](media/sentinel-xdr.png#lightbox)

In this diagram:

- Insights from signals across your entire organization feed into Microsoft Defender XDR and Microsoft Defender for Cloud.
- Microsoft Defender XDR and Microsoft Defender for Cloud send SIEM log data through Microsoft Sentinel connectors.
- SecOps teams analyze and respond to threats identified in Microsoft Sentinel and Microsoft Defender XDR.
- Microsoft Sentinel supports multicloud environments and integrates with third-party apps and partners.

---

## Key capabilities

Implement a Zero Trust approach for managing incidents using Microsoft Sentinel and Defender XDR features. For workspaces onboarded to the Defender portal, use Microsoft Sentinel in the Defender portal.

| Capability or feature | Description | Product |
| --- | --- | --- |
| [Automated Investigation & Response (AIR)](/en-us/microsoft-365/security/defender-endpoint/automated-investigations) | AIR capabilities are designed to examine alerts and take immediate action to resolve breaches. AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives. | Microsoft Defender XDR |
| [Advanced hunting](/en-us/microsoft-365/security/defender/advanced-hunting-overview) | Advanced hunting is a query-based threat hunting tool that lets you explore up to 30 days of raw data. You can proactively inspect events on your network to locate threat indicators and entities. The flexible access to data enables unconstrained hunting for both known and potential threats. | Microsoft Defender XDR |
| [Custom file indicators](/en-us/microsoft-365/security/defender-endpoint/indicator-file) | Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware. | Microsoft Defender XDR |
| [Cloud discovery](/en-us/defender-cloud-apps/set-up-cloud-discovery) | Cloud Discovery analyzes traffic logs collected by Defender for Endpoint and assesses identified apps against the cloud app catalog to provide compliance and security information. | Microsoft Defender for Cloud Apps |
| [Custom network indicators](/en-us/microsoft-365/security/defender-endpoint/indicator-ip-domain) | By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence. | Microsoft Defender XDR |
| [Endpoint detection and response (EDR) Block](/en-us/microsoft-365/security/defender-endpoint/edr-in-block-mode) | Provides added protection from malicious artifacts when Microsoft Defender Antivirus (MDAV) isn't the primary antivirus product and is running in passive mode. EDR in block mode works behind the scenes to remediate malicious artifacts that were detected by EDR capabilities. | Microsoft Defender XDR |
| [Device response capabilities](/en-us/microsoft-365/security/defender-endpoint/respond-machine-alerts) | Quickly respond to detected attacks by isolating devices or collecting an investigation package | Microsoft Defender XDR |
| [Live response](/en-us/microsoft-365/security/defender-endpoint/live-response) | Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection. This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats in real time. | Microsoft Defender XDR |
| [Secure cloud applications](/en-us/azure/defender-for-cloud/defender-for-cloud-introduction#secure-cloud-applications) | A development security operations (DevSecOps) solution that unifies security management at the code level across multicloud and multiple-pipeline environments. | Microsoft Defender for Cloud |
| [Improve your security posture](/en-us/azure/defender-for-cloud/defender-for-cloud-introduction#improve-your-security-posture) | A cloud security posture management (CSPM) solution that surfaces actions that you can take to prevent breaches. | Microsoft Defender for Cloud |
| [Protect cloud workloads](/en-us/azure/defender-for-cloud/defender-for-cloud-introduction#protect-cloud-workloads) | A cloud workload protection platform (CWPP) with specific protections for servers, containers, storage, databases, and other workloads. | Microsoft Defender for Cloud |
| [User and Entity Behavioral Analytics (UEBA)](/en-us/azure/sentinel/enable-entity-behavior-analytics) | Analyzes behavior of organization entities such as users, hosts, IP addresses, and applications | Microsoft Sentinel |
| [Fusion](/en-us/azure/sentinel/configure-fusion-rules) | A correlation engine based on scalable machine learning algorithms. Automatically detects multistage attacks also known as advanced persistent threats (APT) by identifying combinations of anomalous behaviors and suspicious activities that are observed at various stages of the "kill chain". | Microsoft Sentinel |
| [Threat Intelligence](/en-us/azure/sentinel/threat-intelligence-integration) | Use Microsoft third-party providers to enrich data to provide extra context around activities, alerts, and logs in your environment. | Microsoft Sentinel |
| [Automation](/en-us/azure/sentinel/automation) | Automation rules are a way to centrally manage automation with Microsoft Sentinel, by allowing you to define and coordinate a small set of rules that can apply across different scenarios. | Microsoft Sentinel |
| [Anomaly rules](/en-us/azure/sentinel/work-with-anomaly-rules) | Anomaly rule templates use machine learning to detect specific types of anomalous behavior. | Microsoft Sentinel |
| [Scheduled queries](/en-us/azure/sentinel/detect-threats-custom) | Built-in rules written by Microsoft security experts that search through logs collected by Microsoft Sentinel for suspicious activity chains, known threats. | Microsoft Sentinel |
| [Near-real-time (NRT) rules](/en-us/azure/sentinel/create-nrt-rules) | NRT rules are limited set of scheduled rules, designed to run once every minute, in order to supply you with information as up-to-the-minute as possible. | Microsoft Sentinel |
| [Hunting](/en-us/azure/sentinel/hunting) | To help security analysts look proactively for new anomalies that weren't detected by your security apps or even by your scheduled analytics rules, Microsoft Sentinel's built-in hunting queries guide you into asking the right questions to find issues in the data you already have on your network. | Microsoft Sentinel For workspaces onboarded to the Defender portal, use the Microsoft Defender portal advanced hunting functionality. |
| [Microsoft Defender XDR Connector](/en-us/azure/sentinel/connect-microsoft-365-defender) | The Microsoft Defender XDR connector synchronizes logs and incidents to Microsoft Sentinel. | Microsoft Defender XDR and Microsoft Sentinel |
| [Data connectors](/en-us/azure/sentinel/connect-data-sources) | Allow for the ingestion of data for analysis in Microsoft Sentinel. | Microsoft Sentinel |
| [Content hub solution -Zero Trust (TIC 3.0)](/en-us/azure/sentinel/sentinel-solution) | Zero Trust (TIC 3.0) includes a workbook, analytics rules, and a playbook, which provide an automated visualization of Zero Trust principles, cross-walked to the Trust Internet Connections framework, helping organizations to monitor configurations over time. | Microsoft Sentinel |
| [Security orchestration, automation, and response (SOAR)](/en-us/azure/sentinel/sentinel-soar-content) | Using automation rules and playbooks in response to security threats increases your SOC's effectiveness and saves you time and resources. | Microsoft Sentinel |
| [SOC optimizations](/en-us/azure/sentinel/soc-optimization/soc-optimization-access) | Close coverage gaps against specific threats and tighten your ingestion rates against data that doesn't provide security value. | Microsoft Sentinel For workspaces onboarded to the Defender portal, use SOC optimization in the Microsoft Defender portal. |

## What's in this solution

This solution helps your security operations team remediate incidents using a Zero Trust approach by guiding you through Microsoft Sentinel and Microsoft Defender XDR implementation. The implementation includes these phases:

| Phase | Description |
| --- | --- |
| 1. [Pilot and deploy Microsoft Defender XDR services](/en-us/defender-xdr/pilot-deploy-overview?bc=/security/breadcrumb/toc.json&amp;toc=/security/zero-trust/toc.json) | Start by piloting Microsoft Defender XDR services so you can evaluate their features and capabilities before you complete the deployment across your organization. |
| 2. [Plan your deployment](/en-us/unified-secops-platform/overview-plan?bc=/security/breadcrumb/toc.json&amp;toc=/security/zero-trust/toc.json) | Then, plan your full SIEM and XDR deployment, including the XDR services and the workspace for Microsoft Sentinel. |
| 3. [Set up XDR tools and architect your workspace](/en-us/unified-secops-platform/overview-deploy?bc=/security/breadcrumb/toc.json&amp;toc=/security/zero-trust/toc.json) | In this phase, deploy the XDR services you decided to use across your environment, deploy Microsoft Sentinel and other services to support your SIEM and XDR solution.  If you plan to work from the Azure portal, skip the step to [connect Microsoft Sentinel to the Microsoft Defender portal](/en-us/defender-xdr/microsoft-sentinel-onboard?bc=/security/breadcrumb/toc.json&amp;toc=/security/zero-trust/toc.json). This step is only relevant if you want to use Microsoft Sentinel Defender portal, and is not relevant if you want to respond to incidents in the Azure portal. |
| 4. Respond to incidents | Finally, respond to incidents based on whether you onboarded to the Defender portal:  - [Respond to an incident from the Defender portal](respond-incident-defender) - [Respond to an incident from the Azure portal](respond-incident-azure) |