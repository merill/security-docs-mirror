---
layout: Conceptual
title: Zero Trust as a security foundation | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Get an overview of core Zero Trust principles and how to use them in security adoption and modernization.
ms.topic: article
ms.service: security
ms.subservice: zero-trust
ms.date: 2026-11-04T00:00:00.0000000Z
locale: en-us
document_id: 2c36a952-bd35-13b3-3cff-5af7b9676442
document_version_independent_id: 2c36a952-bd35-13b3-3cff-5af7b9676442
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/zero-trust-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/zero-trust-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/zero-trust-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 0c43e7b9-26e2-7503-431f-246fbea54935
---

# Zero Trust as a security foundation | Microsoft Learn

Zero Trust provides a modern security foundation for designing, implementing, and operating security across an organization. It helps organizations operate securely in complex environments where users, devices, applications, workloads, data, and infrastructure are distributed across organizational and technology boundaries.

Zero Trust is often summarized as **"never trust, always verify."** This phrase is a useful reminder not to grant access or assume something is safe solely because of its location, ownership, or previous trust. In practice, Zero Trust means making security decisions explicitly, using available context and risk information, limiting unnecessary privileges and dependencies, and designing for the possibility of compromise.

These ideas extend beyond individual access decisions. They influence how organizations design architectures, protect assets, operate security controls, monitor environments, respond to threats, and limit the impact when something is compromised.

## Zero Trust principles

Microsoft Zero Trust guidance uses three principles that shape sedcurity decisions across the organization and security controls across AI, identities, devices, applications, workloads, data, infrastructure, networks.

| **Principle** | **Application** |
| --- | --- |
| **Assume compromise***(previously referred to as assume breach)* | Design and operate on the expectation that attackers might gain access to part of the environment. Limit potential impact and support rapid detection, response, and recovery. |
| **Verify explicitly** | Make security and access decisions using relevant identity, device, resource, environmental, behavioral, and risk signals rather than relying on implicit trust. |
| **Use least privilege access** | Limit access and control relationships to what is required, for only as long as required, reducing unnecessary exposure and potential blast radius. |

Together, these principles help organizations make deliberate trust decisions rather than inheriting trust from network location, organizational boundaries, or previous interactions.

## Zero Trust outcomes

When applied consistently, Zero Trust leads to clear, consistent, and measurable security outcomes that replace traditional "trust-by-default" models with "trust-by-exception".

This produces several important security outcomes:

- **Trust decisions are explicit and context-aware**: Security decisions use relevant context and telemetry rather than relying on location or other implicit indicators of trust.
- **Access is conditional and temporary**: Permissions and control relationships are limited to what users, workloads, and systems need to perform their intended functions.
- **Privileges can adapt as conditions change**: Access and security decisions can be reassessed when identity, device, behavior, environment, or risk conditions change.
- **Potential blast radius is reduced**: Segmentation, least privilege, and constrained control relationships limit how far an attacker can move after compromise.
- **Security controls operate across environments**: Principles and controls apply across on-premises systems, cloud platforms, SaaS applications, operational environments, and AI workloads.
- **Detection, response, and recovery are part of the design**: Organizations monitor for compromise and prepare to contain, remediate, and recover when preventive controls don't stop an attack.

Zero Trust therefore isn't an expectation that compromise can always be prevented. It combines prevention with deliberate preparation for detecting and limiting compromise when it occurs.

## Zero Trust and security graph thinking

A graph is a model of entities (nodes) and their relationships. A security graph helps teams understand which entities can access or control other entities, such as users, devices, apps, identities, and resources.

[![Diagram of entities and control relationships in a security graph.](media/concepts/security-graph-entities-relationships.png)](media/concepts/security-graph-entities-relationships.png#lightbox)

Threat actors abuse these control relationships during attacks. In most attacks, adversaries move across existing relationships rather than breaking every control directly. If an upstream entity is compromised, downstream entities it controls can also be compromised.

[![Diagram showing attacker paths across a security graph.](media/concepts/security-graph-attack-paths.png)](media/concepts/security-graph-attack-paths.png#lightbox)

This dynamic is amplified by two realities:

- **Transitive control relationships**: If A controls B and B controls C, A effectively controls C.
- **Low-friction access for productivity**: Organizations intentionally enable broad access paths to support fast work, which can also increase attacker reach if not governed tightly.

[![Diagram showing expanded blast radius from transitive control relationships.](media/concepts/security-graph-transitive-impact.png)](media/concepts/security-graph-transitive-impact.png#lightbox)

The three Zero Trust principles reduce this risk by shaping both system-level strategy and per-relationship controls.

### Apply assume compromise and business enablement together

Organizations must achieve business outcomes while operating safely in environments where attacks and failures can occur. **Assume compromise** establishes this security reality as a design constraint, while **business enablement** ensures that security supports rather than unnecessarily obstructs the organization's mission.

Together, these ideas encourage organizations to design systems that enable necessary business activity while limiting the likelihood and impact of compromise.

[![Diagram showing business enablement and assume compromise principles across a security graph.](media/concepts/security-graph-assume-compromise.png)](media/concepts/security-graph-assume-compromise.png#lightbox)

### Apply verify explicitly and least privilege per relationship

The other two principles apply to each entity and its inbound and outbound control paths:

- **Verify explicitly** reduces attack surface by validating trust decisions with all relevant context and telemetry.
- **Least privilege** reduces blast radius by limiting standing access and unnecessary control relationships.

[![Diagram showing verify explicitly and least privilege applied to entity relationships.](media/concepts/security-graph-verify-least-privilege.png)](media/concepts/security-graph-verify-least-privilege.png#lightbox)

Depending on the technology and scenario, these principles can be implemented through approaches such as:

- Just-enough access (JEA) for role-scoped authorization.
- Just-in-time access (JIT) for time-bounded elevation.
- Risk-based policy enforcement and reassessment as conditions change.
- Segmentation and isolation that constrain potential attack paths.
- Monitoring and detection that identify unexpected or malicious behavior.

## Challenging traditional assumptions

Many traditional security approaches relied heavily on network boundaries and treated systems or activity inside a trusted perimeter differently from those outside it.

Those controls remain useful, but network location alone is no longer a sufficient basis for trust. Modern environments span cloud services, endpoints, identities, applications, data, infrastructure, operational technology, and AI workloads. Attackers can also use legitimate credentials, sessions, applications, tools, and administrative relationships to move through these environments.

Zero Trust challenges implicit trust by:

- **Making trust decisions explicitly instead of inheriting them from location or ownership.**
- **Using current context and risk to inform security decisions.**
- **Limiting privileges and control relationships to reduce attack paths and blast radius.**
- **Designing for detection, containment, response, and recovery when compromise occurs.**
- **Treating security as an organizational responsibility supported by technology, people, and processes.**

[![Diagram of Zero Trust security model highlighting the need to challenge traditional security assumptions.](media/zero-trust-assumptions.png)](media/zero-trust-assumptions.png#lightbox)

## Key shifts

Applying Zero Trust principles drives several broader shifts in how organizations approach security:

**Protection follows the asset and its relationships**

Assets aren't inherently protected because of where they reside. Protect them based on their value, sensitivity, exposure, dependencies, and relationships with other entities.

- **Trust is explicit and contextual**

    Don't assume that an identity, device, workload, network connection, or other entity should be trusted simply because of its location, ownership, or previous activity. Use relevant information to make security decisions.
- **Privilege and control relationships are constrained**

    Reduce unnecessary standing privilege and limit the paths through which compromise of one entity can affect others.
- **Compromise is anticipated**

    Prevent attacks where possible, while also designing controls and operations to detect, contain, respond to, and recover from compromise.
- **Security includes technology, people, and processes**

    Technical controls alone can't address every source of risk. Human behavior, operational practices, architecture, processes, and technology all influence security outcomes.
- **Security enables business outcomes**

    Zero Trust doesn't seek to eliminate access, connectivity, or collaboration. It enables organizations to provide the access and functionality the business needs while deliberately managing the associated security risk.

## Apply Zero Trust principles with SAF

Adopting Zero Trust is an incremental ongoing effort. Every organization starts from a different place based on its business priorities, risk profile, security maturity, technology environment, and existing investments.

The Microsoft Security Adoption Framework (SAF) uses Zero Trust as a foundational set of security principles rather than treating it as a single technology architecture or implementation project. SAF connects these principles with business priorities, security practices, and technical implementation.

SAF does this through three complementary components:

- **Business scenarios**

    Help leaders identify and prioritize important security outcomes based on business and security risk.
- **Security disciplines**

    Help teams build the strategy, architecture, processes, capabilities, and operational practices required to achieve those outcomes.
- **Technology pillars**

    Apply security principles to technology areas such as identity, endpoints, applications, data, infrastructure, networks, and AI workloads.

[![Diagram of Zero Trust principles applied to security adoption, showing connections between business scenarios, security disciplines, and technology pillars.](media/zero-trust-principles-adoption.png)](media/zero-trust-principles-adoption.png#lightbox)