---
layout: Conceptual
title: AI security in the Security Adoption Framework | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/foundations/ai-security-governance
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Understand how AI changes security and use the Microsoft Security Adoption Framework (SAF) to coordinate business, security, and technology responses.
ms.date: 2026-11-08T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: af425108-7d92-acf0-3c7e-6f8369bbc78e
document_version_independent_id: af425108-7d92-acf0-3c7e-6f8369bbc78e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/foundations/ai-security-governance.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/foundations/ai-security-governance
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/foundations/ai-security-governance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d6f38669-3d05-40f2-afd8-e49f7dd20884
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/55265cca-de9b-48dc-a77a-9047cc39a575
platformId: 586efcad-76f4-ea71-8cef-5dfbdc4c49ac
---

# AI security in the Security Adoption Framework | Microsoft Learn

Artificial intelligence (AI) has a transformational effect on security, driving large and small changes across business scenarios, security disciplines, technologies, and security operations.

Organizations need to manage several changes at the same time: attackers are using AI to improve and accelerate attacks, businesses are rapidly adopting AI to drive growth and efficiency, AI technology introduces new security risks and control requirements, and security teams can use AI to improve the speed and effectiveness of security work.

The Microsoft Security Adoption Framework (SAF) helps organizations address these changes as part of the existing security program rather than creating a separate AI security program. Use this page to understand how AI changes security and find the SAF business scenarios, technologies, workshops, disciplines, and other guidance that can help you manage those changes.

## How AI changes security

AI affects security in four connected ways:

- **Attackers use AI** - Threat actors adopt new technologies quickly because they aren't constrained by the legal, regulatory, moral, and organizational considerations that legitimate organizations face. Attackers use AI to enhance and accelerate existing techniques, including social engineering, phishing, deepfakes, analysis of stolen data, and attack automation. SAF helps organizations strengthen the strategy, architecture, controls, and operational capabilities needed to manage this increased speed, scale, and quality of attacks.
- **Businesses embrace AI to drive growth and efficiency** - Business leaders are rapidly adopting AI technology to improve existing activities and create new capabilities. Security must enable these opportunities while identifying and managing the additional business risk they introduce. Use the [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) business scenario to coordinate the security changes needed across the organization.
- **AI technology must be secured** - Protect AI-enabled applications and agents against abuse by external threat actors and insiders, including inadvertent errors and malicious use. AI applications, models, agents, identities, data, tools, and infrastructure become part of the technology estate that organizations need to protect. Generative AI is different from classic deterministic computing, and autonomous agents create additional considerations because they can perform actions without a human overseeing every step.
- **AI enhances security technology and processes** - AI can automate or improve security work that previously required significant human effort, including posture analysis, vulnerability prioritization, detection, investigation, and response. Organizations should use this capability to increase security speed and effectiveness while preserving human judgment, expertise, accountability, and oversight for consequential decisions.

Note

Most AI systems also contain conventional applications, infrastructure, identities, data, and deterministic code. AI security considerations are added to existing security considerations rather than replacing them.

## Understand the AI technology you are securing

AI includes several technologies with different functions, security characteristics, and risks.

### Machine learning

Machine learning (ML) uses algorithms and data to make decisions or predictions without being explicitly programmed for every task. ML helps scale human expertise over datasets that would be difficult or impossible to analyze manually or by using static queries.

The two main types of machine learning are:

- **Supervised ML** - Analysis is performed on a representative dataset, and the model is trained to make decisions or predictions based on data labeled by human subject-matter experts. The trained model can then apply that expertise at scale to large datasets and real-time streams such as telemetry, logs, pictures, audio, and video.
- **Unsupervised ML** - Analysis finds patterns and anomalies in unlabeled data, including clusters, repeating patterns, and deviations from normal behavior. Human experts can then assess whether the results are benign, malicious, interesting, or actionable.

[![Diagram comparing supervised and unsupervised machine learning.](../media/concepts/ai-ml-types.png)](../media/concepts/ai-ml-types.png#lightbox)

For all machine learning, validate the quality and security integrity of the data. Errors, bias, manipulation, or malicious data poisoning can produce incorrect results at scale. Supervised machine learning also depends on the quality of the labels and the expertise of the people performing the labeling.

Both supervised and unsupervised machine learning are commonly used in security products to analyze large volumes of telemetry, identify vulnerabilities, detect attacks, find anomalies, and prioritize action.

### Generative AI

Generative AI builds on machine learning to provide more advanced data analysis and generate new data that resembles its training and grounding data. This technology includes large language models (LLMs), small language models (SLMs), and other model types.

**Generative AI is dynamic.** Most classic computing is deterministic: it produces the same output when provided the same input and state. Generative AI produces outputs dynamically based on models, prompts, context, data, parameters, and other inputs.

This changes how humans interact with computers and enables software to perform tasks that previously required human interpretation or judgment. It also creates security considerations such as prompt injection, unsafe output, sensitive-data disclosure, manipulation of model behavior, and misuse of connected tools and services.

### AI agents

AI agents combine generative AI with deterministic components, identities, data, applications, and tools to perform tasks with varying degrees of autonomy.

The defining security consideration is **autonomy**: an agent can take actions without a human supervising every step. Organizations must carefully manage what agents are authorized to do, what information and systems they can access, and how their actions are monitored.

[![Diagram showing generative AI components, deterministic code, and access to systems and data as parts of an AI agent.](../media/concepts/ai-genai-agents.png)](../media/concepts/ai-genai-agents.png#lightbox)

Organizations should expect to be accountable for the actions and decisions of AI agents operating on their behalf. Apply least privilege, constrain authorized use cases, establish clear ownership, and monitor agent behavior so autonomy doesn't amplify risk beyond acceptable levels.

## Securing AI technology

Generative AI and autonomous agents introduce additional security considerations beyond classic security:

- **Classic code** requires integrating security during the design, implementation, and operation of software.
- **Generative AI** adds dynamic software execution, dependence on data integrity and classification, and risk from social trickery and manipulation through inputs.
- **Autonomous agents** add risk from autonomous execution, requiring careful scoping of authority, strict application of least privilege, monitoring, and intervention capabilities.

[![Diagram showing how security responsibilities expand from classic software to generative AI and autonomous agents.](../media/concepts/ai-security-evolution-agents.png)](../media/concepts/ai-security-evolution-agents.png#lightbox)

Use the [AI technology guidance](/en-us/security/saf/technologies/ai/overview) for detailed guidance on AI applications and systems, models, agents and agent identities, prompts and context, grounding and training data, tools and connectors, communications, hosting infrastructure, and other AI dependencies.

## Use SAF to manage AI security

AI security isn't a single technical control or security discipline. It requires coordinated work across business decisions, security disciplines, technology controls, and operations.

SAF provides several ways into this work depending on the problem you're trying to solve.

### Start with your business outcome

Use the [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) business scenario when your organization is introducing AI and needs to balance business opportunity, adoption speed, and security risk.

The scenario helps business, security, and technology stakeholders understand the outcome they are trying to achieve and coordinate the changes required across security disciplines and technologies.

Other SAF business scenarios remain relevant because AI depends on and interacts with the existing technology estate. Organizations still need to protect critical business assets, minimize damage from security incidents, and continuously improve security posture as AI adoption expands.

### Secure AI as a technology

Use the [AI technology guidance](/en-us/security/saf/technologies/ai/overview) when you need to determine what must be protected in AI systems and where security controls need to apply.

AI security also depends on other SAF technology areas, including identity, applications, data, endpoints, infrastructure, and network.

### Coordinate security work across disciplines

AI creates work across many [SAF security disciplines](/en-us/security/zero-trust/security-adoption-discipline-overview) rather than becoming a separate discipline.

For example:

- **Strategy, integration, and governance** establishes priorities, accountability, policy, risk decisions, and measures of success.
- **Security architecture** establishes trust boundaries and end-to-end control patterns for AI and classic systems.
- **Access and identity** governs human, workload, and agent identities and applies least privilege.
- **Data security** discovers, classifies, protects, and governs information used by people, applications, models, and agents.
- **Development security** integrates threat modeling, secure engineering, testing, and release controls into AI-enabled applications.
- **Security posture management** discovers AI assets and exposure, prioritizes risk, and measures improvement.
- **Security operations (SecOps)** detects attacks and misuse involving AI while using AI itself to improve detection, investigation, and response.

These disciplines help organizations integrate AI security into the operating model they already use to manage security risk.

### Use the Zero Trust Workshop for detailed AI security planning

Use the [AI security guidance in the Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security) when you need a structured technical planning exercise for securing AI implementations.

The workshop helps teams examine areas such as AI risk and posture, agent lifecycle governance, authentication and access, data protection, network and service access, secure development, and detection and response.

The workshop complements SAF rather than creating a separate framework: SAF organizes the broader security outcomes and work, while the workshop provides a focused way to plan AI security controls and implementation.

## AI security transformation

AI is changing both what organizations need to secure and how security work gets done. Microsoft describes several current [AI security transformation themes](/en-us/security/saf/scenarios/ai-security/overview) that can help leaders communicate and prioritize these changes:

- **Secure your foundations** - Reduce preventable exposure across posture, identity, secrets, data, development, infrastructure, and governance so AI adoption doesn't amplify existing weaknesses.
- **Defend with agents** - Use AI and agents to increase defensive speed and quality across posture management, detection, investigation, and response while preserving appropriate human judgment and oversight.
- **Secure your agentic insider** - Treat autonomous agents as powerful actors inside the environment. Constrain their identities, privileges, data access, tools, actions, and autonomy so their behavior remains within policy and risk boundaries.

These themes are a useful strategic lens, but they don't create a separate security framework or permanent taxonomy. Use SAF to translate them into durable business outcomes, security work, technology controls, and implementation priorities.

## Where to go next

Use the path that best matches the question you're trying to answer:

- **How do we adopt AI rapidly without introducing unacceptable business risk?** Start with the [Adopt and secure AI](/en-us/security/zero-trust/security-adoption-scenario-secure-ai) business scenario.
- **What AI systems, agents, data, identities, and dependencies do we need to protect?** Use the [AI technology guidance](/en-us/security/saf/technologies/ai/overview).
- **How do we plan detailed security controls for AI?** Use the [AI security guidance in the Microsoft Zero Trust Workshop](/en-us/security/zero-trust/workshop-zero-trust-ai-security).
- **How does AI change our existing security program?** Use the relevant [SAF security disciplines](/en-us/security/zero-trust/security-adoption-discipline-overview) and the [AI security transformation themes](/en-us/security/saf/scenarios/ai-security/overview).
- **How do we implement the controls?** Follow the [technical solutions](/en-us/security/zero-trust/implement-overview) and Microsoft product guidance linked from the relevant SAF technology and discipline pages.
- **How do SFI lessons relate to this work?** Use the [SAF mapping of Secure Future Initiative lessons](/en-us/security/saf/foundations/sfi/saf-mapping) to connect Microsoft's internal security transformation experience with customer security adoption.