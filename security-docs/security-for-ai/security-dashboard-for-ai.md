---
layout: Conceptual
title: Assess your organization's AI risk with Microsoft Security Dashboard for AI | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/security-for-ai/security-dashboard-for-ai
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: guywild
author: guywi-ms
manager: orspodek
ms.service: security
ms.subservice: ''
description: Use the Microsoft Security Dashboard for AI dashboard to discover, assess, and mitigate AI risks across your organization.
ms.date: 2026-04-28T00:00:00.0000000Z
ms.update-cycle: 90-days
ms.topic: concept-article
ms.collection:
- msftsolution-security-for-ai
- msftsolution-overview
- zerotrust-solution
- msec-ai-copilot
ai-usage: ai-assisted
locale: en-us
document_id: b98d10af-f1d5-511f-39a6-e2c53cd3eb9b
document_version_independent_id: b98d10af-f1d5-511f-39a6-e2c53cd3eb9b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/security-for-ai/security-dashboard-for-ai.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: security-for-ai/security-dashboard-for-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/security-for-ai/security-dashboard-for-ai.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c671beaa-a830-4c9f-aceb-97379ee031ca
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/8921374c-4dbe-4ed0-b011-a39e18bfbd98
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
platformId: 75e98eeb-011f-cc4f-b85a-708c7cca2255
---

# Assess your organization's AI risk with Microsoft Security Dashboard for AI | Microsoft Learn

[Microsoft Security Dashboard for AI](https://ai.security.microsoft.com) is a unified security dashboard that helps security leaders understand and address the AI risk in their organization. The dashboard equips leadership with a governance tool that provides clear and comprehensive AI security insights and answers the most pressing questions about AI risk, including:

- Which AI assets exist in our environment?
- What’s their current security posture?
- Where must we take action?

This article explains the core capabilities of the Security Dashboard for AI and how to use the dashboard to manage AI security across your enterprise.

## End-to-end AI security visibility and management

Security Dashboard for AI provides a real-time view of AI security posture and risk across Microsoft Security solutions - including Microsoft Entra, Microsoft Purview, and Microsoft Defender - enabling proactive governance and reactive threat protection. This lets security teams keep using the tools they trust while empowering security leaders to govern and collaborate seamlessly.

The dashboard provides:

- **Real-time visibility of AI risk**: Aggregated insights across Microsoft Entra, Defender, and Purview.
- **Comprehensive inventory of AI assets**: The dashboard covers Microsoft AI solutions - including Microsoft Copilot, Microsoft Copilot Studio agents, and Microsoft Foundry apps and agents - as well as third-party AI models, applications, and agents such as Google Gemini, OpenAI ChatGPT, and MCP servers.
- **Recommendations and remediation paths**: Direct integration with Microsoft productivity tools and practitioner portals.
- **AI-powered insights**: Microsoft Security Copilot provides suggested prompts that help you drill down to key insights, and quickly access intelligent risk assessments, summaries, and recommendations.
- **Executive reporting**: Board-ready analytics and compliance insights.

[![A screenshot showing the Overview page of the Security Dashboard for AI.](media/security-dashboard-for-ai/security-for-ai-dashboard-overview.png)](media/security-dashboard-for-ai/security-for-ai-dashboard-overview.png#lightbox)

## How Security Dashboard for AI works

Microsoft Security and partner services provide the sensors and signals the dashboard uses. If you haven't deployed a required service, the dashboard guides you on which capabilities are missing and how to strengthen your AI security.

**Supported products:**

| **Product** | **Key capabilities and dashboard insights** |
| --- | --- |
| **Microsoft Entra** | - **Identity management**: Centralized user and application identity governance<br>- **Conditional access**: Risk-based access controls for AI applications<br>- **Privileged identity management**: Elevated access monitoring and control<br><br> For more information, see [What is Microsoft agent identity platform](/en-us/entra/agent-id/identity-platform/what-is-agent-id-platform). |
| **Microsoft Defender** | - **Threat detection**: Continuous monitoring and observability of AI agents and workloads<br>- **Real-time protection**: Blocking of dangerous actions initiated by AI agents, for supported agents<br>- **Cloud security posture**: Infrastructure vulnerability assessment<br>- **App security**: SaaS AI application risk evaluation<br><br> For more information, see [Protect AI assets from emerging threats and vulnerabilities using Microsoft Defender](/en-us/defender-xdr/security-for-ai/defender-security-for-ai). |
| **Microsoft Purview** | - **Data classification**: Automated labeling and protection of AI-accessible data<br>- **Data loss prevention**: Prevent sensitive information exposure through AI<br>- **Insider risk management**: Detect anomalous AI usage patterns<br><br> For more information, see [Microsoft Purview data security and compliance protections for generative AI apps](/en-us/purview/ai-microsoft-purview). |
| **Microsoft Security Copilot** | - **Prompt-based exploration**: Explore AI risks, agent activity, and security recommendations via prompts<br>- **Enhanced AI risk insights**: Aggregate signals across Microsoft and partner security solutions for deeper analysis<br>- **Enhanced agent discovery and categorization**: Improve identification of managed, unmanaged, and shadow AI agents to strengthen your AI security posture<br><br> For more information, see [What is Microsoft Security Copilot?](/en-us/copilot/security/microsoft-security-copilot) |

## Permissions

The tables in this section outline the data access levels for Microsoft Entra built-in roles. For more information about Microsoft Entra roles, see [Microsoft Entra built-in roles](/en-us/entra/identity/role-based-access-control/permissions-reference).

Important

**Security Reader** is the minimum Microsoft Entra role required to view all Security Dashboard for AI data and assign security recommendations. This role is recommended for CISOs and security leaders who need full visibility into AI security posture without requiring tenant-level administrative permissions, such as editing policies. 

**Overview page permissions**

These roles can view data on the summary cards on the **Overview** page.

| Summary card | Security Reader | AI Administrator | Compliance Administrator | Security Administrator | Global Reader | Agent ID Administrator | Agent Registry Administrator |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **AI inventory** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **AI risk: Misconfigurations and attack paths** | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| **AI risk: Agents with sensitive interactions** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |

These roles can all view instructions and assign tasks on the **Overview** page, as described in Review and assign security recommendations, but cannot view the status of the recommendation unless specified below:

| Recommendation category | Security Reader | AI Administrator | Compliance Administrator | Security Administrator | Global Reader | Agent ID Administrator | Agent Registry Administrator |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Prevent agent sprawl and unauthorized access** (Microsoft Entra) | ✅ | ✅ | ✅ | ✅ Except *Configure global collection in Entra agent registry* | ✅ | ❌ | ❌ |
| **Prevent data leaks and oversharing** (Microsoft Purview) | ✅ | ✅ Except *Enable Microsoft Purview audit* | ✅ | ✅ Except *Enable Microsoft Purview audit* | ✅ | ✅ Only *Turn on Communication Compliance, Insider Risk Management, and Data Lifecycle Management* | ✅ Only *Turn on Communication Compliance, Insider Risk Management, and Data Lifecycle Management* |
| **Address AI risk and vulnerability** (Microsoft Defender) | ✅ | ✅ | ✅ | ✅ Except *Enable app governance* | ✅ | ❌ | ❌ |

**AI inventory page permissions**

These roles can view data on the **AI inventory** page, as described in Explore AI assets and manage asset security risks.

| Asset type | Security Reader | AI Administrator | Compliance Administrator | Security Administrator | Global Reader | Agent ID Administrator | Agent Registry Administrator |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **AI agents** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **AI models** | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| **MCP servers** | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Other AI apps** | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |

**AI risk page permissions**

These roles can view data on the **AI risk** page, as described in View and prioritize AI security risks across your organization.

| Risk category | Security Reader | AI Administrator | Compliance Administrator | Security Administrator | Global Reader | Agent ID Administrator | Agent Registry Administrator |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Identity and access risk** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Data security risk** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Cloud security risk** | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Misconfigurations and attack paths** | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| **Agents with sensitive interactions** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |

## Review and assign security recommendations

The **Overview** page of the dashboard provides key insights about your AI assets and related security risks. It also assesses your organization's implementation of Microsoft security for AI capabilities and provides recommendations for improving your organization's AI security posture.

Each recommendation shows its current status, such as **Not started** or **Completed**, and belongs to a recommendation category associated with a Microsoft Security product (Microsoft Entra, Microsoft Purview, or Microsoft Defender). Select a recommendation category to expand it and view individual recommendations.

### Assign a recommendation

To assign the implementation of a recommendation to a specific user or group:

1. Select a recommendation on the **Overview** page.

    [![A screenshot showing the Overview page with one of the security recommendations highlighted.](media/security-dashboard-for-ai/security-dashboard-for-ai-delegate-recommendation.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-delegate-recommendation.png#lightbox)
2. On the recommendation details page, select **Assign**.

    [![A screenshot showing the recommendation details page with the Assign button highlighted.](media/security-dashboard-for-ai/security-dashboard-for-ai-recommendation-details.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-recommendation-details.png#lightbox)
3. On the **Assignment details** page, configure the following:

    - **Assign to**: Select **Assign to user or group** to choose an assignee.
    - **Due date**: Set a due date for the recommendation. The dashboard displays a countdown showing the number of days remaining.
    - **Create a notification**: Choose how to notify the assignee — **Teams**, **Email**, or **Don't create a notification**. When you save the assignment, this creates a pre-populated notification you can edit and send.

    [![Screenshot of Assignment details dialog with assignee, due date, notification options, and Save assignment button highlighted.](media/security-dashboard-for-ai/assignment-details-save-assignment.png)](media/security-dashboard-for-ai/assignment-details-save-assignment.png#lightbox)
4. Select **Save assignment**. The recommendation details page now shows a **Delegated to** card with the assignee, the due date countdown, and assignment details. To update or remove the assignment, select **Manage assignment**.

    [![Screenshot of Assignment details dialog showing assignee selection, due date, notification options, and Manage assignment button.](media/security-dashboard-for-ai/assignment-summary.png)](media/security-dashboard-for-ai/assignment-summary.png#lightbox)

Assigned recommendations display an **Assigned** indicator on the **Overview** page.

### Skip a recommendation

If a recommendation isn't relevant to your organization, you can skip it to keep the dashboard focused on actionable items:

1. On the recommendation details page, select the ellipsis (**...**) next to the **Assign** button.

    [![Screenshot of recommendation details dialog with Turn on Data Loss Prevention steps, Assign button, ellipsis menu, and Skip this recommendation highlighted.](media/security-dashboard-for-ai/skip-recommendation.png)](media/security-dashboard-for-ai/skip-recommendation.png#lightbox)
2. Select **Skip this recommendation**.

Skipped recommendations are hidden from the default view. To view or restore skipped recommendations, select **Show skipped recommendations** on the **Overview** page.

## Explore AI assets and manage asset security risks

The **AI inventory** page of the dashboard provides detailed views to help you discover AI assets, assess risks, and implement remediation actions across the AI agents registered in [Microsoft Agent 365](/en-us/microsoft-agent-365/overview), as well as the AI models, MCP servers, and AI applications in your organization.

### What's included in the AI inventory

The dashboard inventories AI assets surfaced by the underlying Microsoft services. Coverage and terminology are defined by those source services — the following table summarizes what each asset type means in the dashboard and what's in scope.

| Asset type | What it means in the dashboard | Coverage source | Learn more |
| --- | --- | --- | --- |
| **AI agents** | Software entities that perform tasks on behalf of users, typically using AI models and tools. | Agents registered in Microsoft Agent 365. | [What is Microsoft Agent 365?](/en-us/microsoft-agent-365/overview) |
| **AI models** | Generative AI and other models deployed in your environment, including those that power your AI agents and applications. | Models discovered by Microsoft Defender. | [Protect AI assets using Microsoft Defender](/en-us/defender-xdr/security-for-ai/defender-security-for-ai) |
| **MCP servers and other AI applications** | SaaS AI applications and Model Context Protocol (MCP) servers used in your organization. | Apps and servers discovered by Microsoft Defender. | [Protect AI assets using Microsoft Defender](/en-us/defender-xdr/security-for-ai/defender-security-for-ai) |

Assets that aren't registered in Microsoft Agent 365 or aren't visible to Microsoft Defender don't appear in the inventory. To expand coverage, register additional agents in Agent 365 and ensure Microsoft Defender is deployed across your environment.

To discover and manage AI asset security risks:

1. Select **AI Inventory** to review the discovered AI assets in your organization.
2. Apply filters to focus on specific asset types or risk levels.
3. Select any AI asset to view detailed information, review security configuration and compliance status, and analyze user access patterns and data interactions.
4. Select **Export** to export filtered views for targeted analysis and reporting.

### AI agents

The **AI agents** tab of the **AI inventory** page presents AI agents that are registered in Microsoft Agent 365, and provides key insights from the [Microsoft Entra Agent Registry](/en-us/entra/agent-id/identity-platform/what-is-agent-registry) and [Microsoft Purview Data Security Posture Management (DSPM) for AI](/en-us/purview/data-security-posture-management-learn-about).

[![A screenshot showing the Agents tab of the AI inventory page of Security Dashboard for AI.](media/security-dashboard-for-ai/security-dashboard-for-ai-inventory.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-inventory.png#lightbox)

Select an AI agent to view agent details and activities. Select **View all activities** to open the [Activity Explorer in DSPM for AI](/en-us/purview/data-security-posture-management-considerations#activity-explorer-events-in-data-security-posture-management) and review agent activity related to content that contains sensitive information or has labels applied.

[![A screenshot showing the Agent Overview page of Security Dashboard for AI.](media/security-dashboard-for-ai/security-dashboard-for-ai-agent-overview.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-agent-overview.png#lightbox)

### AI models

The **AI models** tab of the **AI inventory** page presents AI models discovered by [Microsoft Defender](/en-us/defender-xdr/security-for-ai/defender-security-for-ai) across your environment. Select **Show more in Defender** to open the [Microsoft Defender cloud asset inventory](/en-us/azure/defender-for-cloud/asset-inventory?pivots=defender-portal) for detailed information and risk mitigation.

[![A screenshot showing the AI models page of Security Dashboard for AI.](media/security-dashboard-for-ai/security-dashboard-for-ai-models.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-models.png#lightbox)

### MCP servers and other AI applications

View and manage the security of MCP servers and other AI applications discovered by [Microsoft Defender](/en-us/defender-xdr/security-for-ai/defender-security-for-ai) across your environment. Select **Show more in Defender** to open the [Microsoft Defender for Cloud Apps applications inventory](/en-us/defender-cloud-apps/applications-inventory) for detailed information and risk mitigation.

[![A screenshot showing the Other AI apps page of Security Dashboard for AI.](media/security-dashboard-for-ai/security-dashboard-for-ai-mcp-and-other-ai-apps.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-mcp-and-other-ai-apps.png#lightbox)

## View and prioritize AI security risks across your organization

The **AI risk** page of the dashboard provides a consolidated view of AI-related security risks — including identity and access risks, data security risks, and cloud security risks — enabling you to prioritize and address threats effectively. Each risk category links directly to the relevant Microsoft Security product for remediation.

To investigate and remediate AI security risks:

1. Review risk summary cards for immediate priorities, examine trend charts to identify emerging threats, and use Microsoft Security Copilot's suggested prompts to explore complex risk scenarios.
2. Select **View in Microsoft Purview**, **View in Microsoft Defender**, or **View details in Entra** to navigate to the relevant Microsoft Security product for detailed risk analysis and remediation.

[![A screenshot showing the AI risk page of the Security Dashboard for AI.](media/security-dashboard-for-ai/security-dashboard-for-ai-risks.png)](media/security-dashboard-for-ai/security-dashboard-for-ai-risks.png#lightbox)