---
layout: Conceptual
title: How do I protect AI apps and data? | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/security-for-ai/protect
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: guywild
author: guywi-ms
manager: orspodek
ms.service: security
ms.subservice: ''
description: How to use Microsoft capabilities to protect AI apps and data use in your environment.
ms.date: 2025-04-02T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: concept-article
ms.collection:
- msftsolution-security-for-ai
- msftsolution-scenario
- zerotrust-solution
- msec-ai-copilot
locale: en-us
document_id: 03ddf71c-e0fc-e53f-5f13-c2133877e104
document_version_independent_id: 03ddf71c-e0fc-e53f-5f13-c2133877e104
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/security-for-ai/protect.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: security-for-ai/protect
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/security-for-ai/protect.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/8e3fdb08-a059-4277-98f6-c0e21e940707
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/88291526-9c74-4f87-878c-de0a82134421
platformId: ede4cae8-20c7-7bee-c932-8ce26fe1c6f1
---

# How do I protect AI apps and data? | Microsoft Learn

This article describes how to use capabilities that are specific to protecting AI apps and the data these interact with.

- Safeguard your sensitive data in user prompts and AI-generated data
- Defend against emerging threats like prompt injections

This is the third article in a series. If you haven’t yet accomplished the tasks in [Prepare for AI security](prepare) and [Discover AI apps and data](discover), start with these articles to prepare your environment with capabilities prescribed in this article.

![Diagram that shows the Protect aspect of security for AI series.](media/security-for-ai-step-protect.svg)

Use this article together with this resource:

- Cloud Adoption Framework (CAF) for AI — [Process to secure AI](/en-us/azure/cloud-adoption-framework/scenarios/ai/secure)

Microsoft provides a broad set of capabilities for protecting AI apps and data. This article discusses these in two categories—data protection and threat protection.

[![Diagram that shows the capabilities for protecting AI apps and data.](media/capabilities-for-protecting-ai-apps.svg)](media/capabilities-for-protecting-ai-apps.svg#lightbox)

The following two tables describe the illustration and also walk through the steps of implementing these capabilities.

**Table 1—Data protection capabilities**

| Step | Task | Scope |
| --- | --- | --- |
| 1 | Apply SharePoint oversharing controls to quickly exempt sensitive sites and data from the scope of AI apps. | Sites and files across your Microsoft 365 environment. |
| 2 | Use Data Security Posture Management (DSPM) for AI to learn where oversharing is taking place and to find gaps in your policy coverage for sensitivity labels and DLP policies. | Copilots, agents, and other AI apps that use third-party large language modules (LLMs), including [Supported AI sites](/en-us/purview/ai-microsoft-purview-supported-sites). AI apps in other cloud providers through the Purview SDK. |
| 3 | Continue to make progress on sensitivity labels and data loss prevention (DLP) policies. | Sites, files, and devices across your Microsoft 365 environment.  SaaS apps when integrated with Defender for Cloud Apps.  AI apps in Azure and other cloud providers through the Purview SDK. |
| 4 | Within Insider Risk Management (IRM), apply the Risky AI template to identify risky behavior in AI apps. | Generative AI websites. Microsoft Copilot, Microsoft Copilot, Copilot Studio, Foundry Tools.  AI apps in other cloud providers through the Purview SDK. |
| 5 | Configure Adaptive Protection for Insider Risk Management to increase protection for data based on the risk of users | Sites, files, and devices across your Microsoft 365 environment. |

**Table 2—Threat protection capabilities**

| Step | Task | Scope |
| --- | --- | --- |
| 1 | Use Defender for Cloud Apps to alert you when new AI apps are being used, to calculate risk scores for AI apps, and to allow or block these apps in your environment. Defender for Cloud Apps provides extra protections for Microsoft Copilot. | SaaS AI apps |
| 2 | Defender for CloudDiscover deployed AI workloads in your environment and gain security insights with Microsoft Defender for Cloud | Custom-built Azure AI based AI applications |

## Protect AI data

These capabilities help you efficiently learn about and mitigate the top risks associated with data oversharing, sensitive data use, and risky behaviors of users. These capabilities are scoped to protections for AI apps and data in your environment.

### Step 1—Apply SharePoint oversharing controls

SharePoint oversharing controls include controls that are built into SharePoint, like scoped permissions, and add-on capabilities in SharePoint Advanced Management to bolster content governance for the Microsoft Copilot deployment journey. SharePoint oversharing controls help you:

- Temporarily limit Copilot search to a list of sites you specify (Restricted SharePoint Search).
- Quickly identify sites that potentially contain overshared data or sensitive content (data access governance reports).
- Flag sites so that users can't find them through Copilot or Org-wide search (Restricted Content Discovery in SharePoint Advanced Management).
- create inactive site policies to automatically manage and reduce inactive sites (SharePoint Advanced Management).
- Restrict access to SharePoint and OneDrive sites to users in a specific group (restricted access control policies in SharePoint Advanced Management).

To get started with oversharing controls, use the following resources.

| Task | Recommended resources |
| --- | --- |
| Review the illustration and description of oversharing controls you can use with Microsoft Copilot | [Microsoft Copilot data protection and auditing architecture](/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing) |
| Downloadable blueprint to prevent oversharing | [Microsoft Copilot blueprint for oversharing](/en-us/copilot/microsoft-365/microsoft-365-copilot-blueprint-oversharing) |
| Learn about SharePoint Advanced Management | [Microsoft SharePoint Premium - SharePoint Advanced Management overview](/en-us/sharepoint/advanced-management) |

### Step 2--Protect data through DSPM for AI

Use DSPM for AI to learn where oversharing is taking place and to find gaps in your policy coverage for sensitivity labels and DLP policies.

A great place to start is with the Assessment for the week report.

[![Screenshot of the data assessments from a week of November.](media/assessment-for-week-of-november.png)](media/assessment-for-week-of-november.png#lightbox)

You can drill into individual reports to learn more about where you have gaps in oversharing controls, labels, and DLP policies so you can quickly remediate these issues.

[![Screenshot that shows the top 5 SharePoint sites with unlabeled files in Copilot prompts.](media/sharepoint-sites-copilot-prompts.png)](media/sharepoint-sites-copilot-prompts.png#lightbox)

For each report, DSPM for AI provides recommendations to improve your data security. Use the **View all recommendations** link, or **Recommendations** from the navigation pane to see all the available recommendations for your tenant, and their status.

[![Screenshot that shows recommendations for tenant, and their status.](media/assessment-and-recommendations.svg)](media/assessment-and-recommendations.svg#lightbox)

Use the following resources to protect AI apps and data with DSPM for AI.

| Task | Recommended resources |
| --- | --- |
| Learn about DSPM for AI | [How to use DSPM for AI](/en-us/purview/dspm-for-ai) |
| Learn about prerequisites and how one-click policies and default policies work | [Considerations for DSPM for AI](/en-us/purview/dspm-for-ai-considerations) |
| For AI apps in other cloud providers, learn how to test integration with DSPM for AI by using the Purview SDK | [How to test an AI application integrated with Purview SDK](/en-us/purview/developer/how-to-test-an-ai-application-integrated-with-purview-sdk) |

### Step 3—Continue to identify gaps in sensitivity labels and DLP policies

In [Prepare for AI security](prepare), you used Microsoft Purview data security posture management tools, DSPM and DSPM for AI, to prioritize protection for your sensitive data. Continue to revisit these tools to identify gaps in your policy coverage and to discover where you need to continue to invest in applying sensitivity labels and DLP policies. Also, extend sensitivity labels and DLP policies to SaaS apps by using Defender for Cloud Apps.

Use the following resources to make progress with Microsoft Purview.

| Task | Recommended resources |
| --- | --- |
| Learn about recommended deployment strategies for information protection | [Deploy an information protection solution with Microsoft Purview](/en-us/purview/information-protection-solution?tabs=phase-one) |
| Extend sensitivity labels and DLP policies to SaaS apps by using Defender for Cloud Apps | [Deply information protection for SaaS apps](/en-us/security/zero-trust/deploy-information-protection-saas) |
| Define your sensitivity labels and policies that will protect your organization's data | [Get started with sensitivity labels](/en-us/purview/get-started-with-sensitivity-labels)[Create and configure sensitivity labels and their policies](/en-us/purview/create-sensitivity-labels)[Restrict access to content by using sensitivity labels to apply encryption](/en-us/purview/encryption-sensitivity-labels) |
| Label and protect data for Microsoft 365 apps and services | [Manage sensitivity labels in Office apps](/en-us/purview/sensitivity-labels-office-apps)[Enable sensitivity labels for files in SharePoint and OneDrive](/en-us/purview/sensitivity-labels-sharepoint-onedrive-files) |
| Tune your DLP policies | [Create and Deploy data loss prevention policies](/en-us/purview/dlp-create-deploy-policy) |
| For AI apps developed in Azure or other cloud providers, learn how to apply sensitivity labels and DLP policies by using the Purview SDK | [What is Purview SDK](/en-us/purview/developer/microsoft-purview-sdk-documentation-overview)[Use Microsoft Graph Purview APIs](/en-us/purview/developer/use-the-api)[How to test an AI application integrated with Purview SDK](/en-us/purview/developer/how-to-test-an-ai-application-integrated-with-purview-sdk) |

### Step 4—Apply the Risky AI template in Insider Risk Management (IRM)

Microsoft Purview Insider Risk Management (IRM) includes predefined policy templates you can apply to your environment, including Risky AI usage. IRM templates are predefined policy conditions that define the types of risk indicators and risk scoring model used by the policy.

The Risky AI usage policy can help detect and enable risk scoring for prompts and responses across AI tools in your organization. IRM helps you investigate and take action on risk activities related to AI.

Use the following resources to get started with Insider Risk Management and to apply the Risky AI usage policy template.

| Task | Recommended resources |
| --- | --- |
| Get started with Insider Risk Management and learn about top scenarios that benefit your organization | [Learn about insider risk management](/en-us/purview/insider-risk-management) |
| Apply the Risky AI template | [Learn about insider risk management policy templates | Microsoft Learn](/en-us/purview/insider-risk-management-policy-templates#risky-ai-usage-preview) |
| Learn about key scenarios for AI and view example reports | [Insider Risk Management empowering risky AI usage visibility and security investigations](https://techcommunity.microsoft.com/blog/microsoft-security-blog/insider-risk-management-empowering-risky-ai-usage-visibility-and-security-invest/4298246) |
| For AI apps developed with the Purview SDK, test Insider Risk Management integration | [How to test an AI application integrated with Purview SDK](/en-us/purview/developer/how-to-test-an-ai-application-integrated-with-purview-sdk) |

### Step 5—Configure Adaptive Protection for Insider Risk Management

Adaptive Protection in Microsoft Purview Insider Risk Management dynamically assigns a risk level to users and then applies policies you create to users with moderate or elevated risk. Policies can implement increased data loss prevention actions, preserve deleted content, or enforce higher conditional access requirements.

Use the following resources to get started with Adaptive Protection.

| Task | Recommended resources |
| --- | --- |
| Get started with Insider Risk Management and learn about top scenarios that benefit your organization | [Learn about insider risk management](/en-us/purview/insider-risk-management) |
| Learn about key scenarios for AI and view example reports | [Insider Risk Management empowering risky AI usage visibility and security investigations](https://techcommunity.microsoft.com/blog/microsoft-security-blog/insider-risk-management-empowering-risky-ai-usage-visibility-and-security-invest/4298246) |
| Apply the Risky AI template | [Learn about insider risk management policy templates](/en-us/purview/insider-risk-management-policy-templates#risky-ai-usage-preview) |
| Investigate and act on insider risk activities | [Investigate insider risk management activities](/en-us/purview/insider-risk-management-activities?tabs=purview-portal)[Take action on insider risk management cases](/en-us/purview/insider-risk-management-cases?tabs=purview-portal) |

## Get the most out of threat protection for AI

Defender for Cloud Apps and Defender for Cloud include capabilities to keep you informed of new AI app use and to apply appropriate controls.

### Step 1—Use Defender for Cloud Apps to triage and protect use of AI apps

The previous article in this series, [Discover AI Apps, and Data](discover), focused on using Defender for Cloud Apps to discover AI apps in your environment. This article encourages organizations to use Defender for Cloud Apps to stay on top of new AI app use by assessing the risk these poses to your environment, sanctioning or blocking these apps, and applying session controls to apps.

First, create a policy to automatically trigger an alert when a new Generative AI app is being used in your organization.

[![Screenshot that shows the Create app discovery policy page in Microsoft Defender.](media/create-app-discovery-policy.png)](media/create-app-discovery-policy.png#lightbox)

Next, assess the risk score for newly discovered apps. You can also customize the risk score. For example, highly regulated organizations might want to change the weight of specific attributes of the risk score. You can also override a risk score.

[![Screenshot showing the cloud app catalog.](media/cloud-app-catalog.png)](media/cloud-app-catalog.png#lightbox)

Decide whether to sanction or block each app. Organizations may choose to block the usage of apps for various reasons. Some are concerned that sensitive data will be unknowingly shared with applications and exposed later to an audience outside the organization. This could cause the organization to block the usage of all unmanaged AI apps. While other organizations need to ensure all the apps in use are compliant according to different standards, such as SOC2, or HIPAA.

Finally, for apps that you sanction, decide if you want to apply session policies for greater control and visibility. Session policies allow you to apply parameters to how cloud apps are used by your organization. For example, you can configure a session policy that allows only managed devices to access an AI app. A simpler example could be configuring a policy to monitor traffic from unmanaged devices so you can analyze the risk of this traffic before applying stricter policies.

[![A diagram that shows how cloud apps are accessed via session control policies with Defender for Cloud Apps.](media/m365-defender-mcas-architecture-d.svg)](media/m365-defender-mcas-architecture-d.svg#lightbox)

In this illustration:

- Access to sanctioned cloud apps from users and devices in your organization is routed through Defender for Cloud Apps where session policies can be applied to specific apps.
- Cloud apps that you haven't sanctioned or explicitly unsanctioned aren't affected.

Defender for Cloud Apps additionally provides dedicated detections for Microsoft Copilot. Security teams can detect a user’s suspicious interactions with Copilot and respond and mitigate the threat. For instance, when a user accesses sensitive data via Copilot from a risky IP address, Defender for Cloud Apps triggers an alert to flag this suspicious activity with important details including the MITRE attack technique, IP address, and other fields that security teams can use to investigate this alert further.

Use the following resources as next steps.

| Task | Recommended resources |
| --- | --- |
| Review steps 5-8 in this Defender for Cloud Apps deployment flow | [Discover and manage cloud apps](/en-us/defender-xdr/pilot-deploy-defender-cloud-apps#step-5-discover-and-manage-cloud-apps) |
| Review this video tutorial on managing apps | [Discover Which Generative AI Apps Are Used in Your Environment Using Defender for Cloud Apps - YouTube](https://www.youtube.com/watch?v=ZQI4A7W4E_4) |
| Create an app discovery policy | [Create cloud discovery policies](/en-us/defender-cloud-apps/cloud-discovery-policies) |
| Assess the risk score for newly discovered apps | [Cloud app catalog and risk scores](/en-us/defender-cloud-apps/risk-score) |
| Sanction or block new apps | [Govern discovered apps](/en-us/defender-cloud-apps/governance-discovery) |
| Apply session policies to AI apps for greater control and visibility | [Create session policies](/en-us/defender-cloud-apps/session-policy-aad) |
| Learn how to use threat protection for Microsoft Copilot | [New threat detections for Microsoft Copilot for Microsoft 365](/en-us/defender-cloud-apps/release-notes#new-threat-detections-for-microsoft-copilot-for-microsoft-365) |

### Step 2—Apply AI protections in Defender for Cloud

The previous article in this series, Discover AI Apps and data, focused on discovering generative AI workloads and models running in your environment. This article focuses on protection of GenAI applications throughout the application lifecycle, as you build and use your custom AI apps.

Organizations are choosing to develop new GenAI applications and embed AI into existing applications to increase business efficiency and productivity. Attackers are increasingly looking to exploit applications to alter the designed purpose of the AI model with new attacks like prompt injections, wallet attacks, model theft, and data poisoning, while increasing susceptibility to known risks such as data breaches and denial of service. Security teams need to be prepared and ensure they have the proper security controls for their AI applications and detections that address the new threat landscape.

Microsoft Defender for Cloud helps organizations secure their hybrid and multicloud environments from code-to-cloud. Defender for cloud includes security posture and threat protection capabilities to enable organizations to protect their enterprise-built GenAI applications throughout the entire application lifecycle:

- Continuously discover GenAI application components and AI-artifacts from code to cloud.
- Explore and remediate risks to GenAI applications with built-in recommendations to strengthen security posture.
- Identify and remediate toxic combinations in GenAI applications using attack path analysis.
- Detect on GenAI applications powered by [Azure AI Content Safety prompt shields,](/en-us/azure/ai-services/content-safety/concepts/jailbreak-detection) Microsoft threat intelligence signals, and contextual activity monitoring.
- Hunt and investigate attacks in GenAI apps with built-in integration with Microsoft Defender.

Start with AI security posture management capabilities in Defender Cloud Security Posture Management (CSPM). Defender CSPM automatically and continuously discovers deployed AI workloads with agentless and granular visibility into presence and configurations of AI models, SDKs, and technologies used across AI services such as Azure OpenAI Service, Azure Machine Learning, and Amazon Bedrock.

CSPM continuously surfaces contextualized security issues and suggests risk-based security recommendations tailored to prioritize critical gaps across your AI workloads. Relevant security recommendations also appear within the Azure OpenAI resource itself in Azure portal, providing developers or workload owners direct access to recommendations and helping remediate faster.

Attack path analysis capability can identify sophisticated risks to AI workloads including data security scenarios where grounding or fine-tuning data is exposed to the internet through lateral movement and is susceptible to data poisoning.

Next, Stay secure in runtime with threat protection for AI workloads. Defender for Cloud includes threat protection for AI workloads. Threat protection for AI uses native integration Azure OpenAI Service, Azure AI Content Safety prompt shields, and Microsoft threat intelligence to deliver contextual and actionable security alerts. Threat protection for AI workloads allows security teams to monitor their Azure OpenAI powered applications in runtime for malicious activity associated with direct and in-direct prompt injection attacks, sensitive data leaks and data poisoning, as well as wallet abuse or denial of service attacks.

Use the following resources for next steps.

| Task | Recommended resources |
| --- | --- |
| Review top scenarios described in this blog | [Secure Generative AI Applications with Microsoft Defender for Cloud](https://techcommunity.microsoft.com/blog/microsoftdefendercloudblog/secure-your-ai-applications-from-code-to-runtime-with-microsoft-defender-for-clo/4127665) |
| Use CSPM to gain visibility into AI risks in your environment | [Protect your resources with Defender CSPM](/en-us/azure/defender-for-cloud/tutorial-enable-cspm-plan)[Review the Data and AI security dashboard (Preview)](/en-us/azure/defender-for-cloud/data-aware-security-dashboard-overview) |
| Enable threat protection for AI workloads (preview) | Enable threat protection for AI workloads (preview) [Alerts for AI workloads (Preview)](/en-us/azure/defender-for-cloud/alerts-ai-workloads) |

## Next step for securing AI

After protecting AI apps and data in your organization, the next step is to govern AI apps to meet regulatory compliance requirements:

- Assess and strengthen your compliance posture against regulations.
- Implement controls to govern usage of AI apps and data.

See the next article in this series: [How do I govern AI for compliance?](govern)