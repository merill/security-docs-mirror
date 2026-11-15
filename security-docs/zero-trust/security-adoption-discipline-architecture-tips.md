---
layout: Conceptual
title: Foundational security laws | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-adoption-discipline-architecture-tips
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Use these foundational laws to make informed risk and security decisions across SAF.
ms.date: 2026-11-04T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 025879f0-5b2f-9590-804c-d1c92842daaa
document_version_independent_id: 025879f0-5b2f-9590-804c-d1c92842daaa
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-adoption-discipline-architecture-tips.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-adoption-discipline-architecture-tips
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-adoption-discipline-architecture-tips.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 428c8cbf-69e6-e319-010b-f9b0a0babcd0
---

# Foundational security laws | Microsoft Learn

This article provides 10 immutable laws of security and 10 laws of cybersecurity risk that capture durable realities about security controls, attackers, people, process, and technology.

These laws are part of the **Microsoft Security Adoption Framework (SAF)** and are used across strategy, governance, architecture, development, engineering, operations, and SecOps to test assumptions, understand recurring constraints and failure patterns, and make informed risk tradeoffs. Historically, these laws were commonly used in security architecture guidance, and architecture continues to apply them, but they are cross-cutting foundations for SAF rather than architecture-owned concepts.

## Review the immutable laws of security

Security work across SAF requires translating requirements into actionable guidance to reduce security risk, limit damage, and keep systems available over time. At the foundation of this work are the immutable laws of security.

These laws describe uncomfortable truths about security that help teams plan effective controls, avoid common misconceptions, and make better risk decisions.

| **Immutable law** | **Architecture impact** |
| --- | --- |
| **1. If a bad actor can persuade you to run their program, it’s not your computer** | Unauthorized code execution causes loss of control. Prevention alone is insufficient. |
| **2. If a bad actor can alter the operating system, it’s not your computer** | Control‑plane compromise is systemic risk. This applies whether the control plane is a local operating system, an identity management system, a security tool, or anything else with system/root level access. |
| **3. If a bad actor has unrestricted physical access, it’s not your computer** | Physical exposure must be assumed, not treated as an exception. |
| **4. If a bad actor can run active content on your website, it’s not your website** | Execution boundaries define trust boundaries. |
| **5. Weak passwords trump strong security** | Identity failures defeat layered controls. |
| **6. A computer is only as secure as its administrator** | Privileged access is a critically important security priority. |
| **7. Encrypted data is only as secure as its decryption key** | Cryptography without governance is fragile. |
| **8. An out‑of‑date antimalware scanner is marginally better than none** | Static defenses decay. |
| **9. Absolute anonymity isn’t achievable** | Visibility is unavoidable. |
| **10. Technology is not a panacea** | People and process failures must be assumed. |

## Apply the ten laws of cybersecurity risk

Even after understanding how security control is potentially lost, this isn't enough information to make effective decisions. Teams across SAF also need to understand:

- What are we optimizing for? - Where do we concentrate effort? - What tradeoffs are acceptable?

To answer these questions, we can apply 10 common laws of cybersecurity risk. Each set of laws addresses different aspects of cybersecurity.

| **Law** | **Risk implication across SAF** | **Decision guidance** |
| --- | --- | --- |
| **1. Security success is ruining the attacker's ROI** | Design architectures that increase attacker cost and reduce payoff, especially for high‑value assets. | - Concentrate controls around identity, privileged access, and sensitive data.- Reduce flat trust zones; segment systems so compromise doesn’t scale. - Prioritize protections that break common attacker chains, not special cases. |
| **2. Not keeping up is falling behind** | Static architectures fail. Architecture must assume continuous evolution. | - Security architecture is never done. It must be operationally sustainable and continuously improved.- Design for continuous update (patching, configuration, policy).- Prefer cloud‑native and managed services that evolve faster than on-premises or bespoke systems.- Ensure visibility and inventory are architectural requirements, not afterthoughts. |
| **3. Security is a business enabler (productivity always wins)** | If architecture creates friction, it's bypassed. | - Good security architecture enables productivity by default.- Favor identity‑based access over network complexity.- Integrate security controls into standard user and developer workflows.- Make secure paths the easiest paths. |
| **4. Attackers don't care** | Attackers use any available access path in the environment. Architecture must eliminate the cheapest paths, not defend only the obvious ones. | - Architecture must reflect real attacker behavior, not idealized beliefs in individual controls.- Assume compromise through phishing, misconfiguration, or legacy protocols.- Remove architectural single points of catastrophic failure. - Secure against the full attack lifecycle (lateral movement, execute on objectives), not just initial access. |
| **5. Ruthless prioritization is a survival skill** | You cannot secure everything. | - Architecture is about choosing what not to do.- Identify crown‑jewel assets and design “defense‑in‑depth” there.- Accept lower assurance where business impact is lower. - Use business scenarios to guide architectural investment. |
| **6. Cybersecurity is a team sport** | Architecture must integrate work across disciplines and teams. | - Architects design coordination, not just controls. - Align architecture with platform teams, developers, and operations. - Delegate controls to platforms that can do them better (cloud providers, identity systems). - Avoid custom solutions where shared services suffice. |
| **7. Your network isn't as trustworthy as you think it is** | Network trust must never be the primary or only control plane. | - This law underpins the move away from perimeter‑centric design. - Shift trust decisions to identity, device, and application context. - Design architectures that assume the network is observable and hostile. - Retain effective controls such as firewalls/web app firewalls (WAFs), but don't rely on them to detect/block everything. - Use Zero Trust access models consistently across environments. |
| **8. Isolated networks aren't automatically secure** | Isolation is effective only when rigorously designed and maintained. | - Retain network isolation that works well. Make sure you maintain it, and attackers can't easily work around it. - Architecture must account for people and process, not just topology.- Treat isolation as a system, not a network filtering rule. - Secure all bridging points (media, vendor access, admins). - Assume compromise and apply strong identity and operational controls, even in “air‑gapped” design. |
| **9. Encryption alone isn't a data protection solution** | Cryptology is only as secure as the keys that unlock it. | - Encryption is important, but is ineffective without secure implementation and operation. - Architect centralized key management and access governance. - Protect decryption paths as aggressively as encrypted storage. - Combine encryption with identity, monitoring, and policy enforcement. |
| **10. Technology doesn't solve people and process problems** | Architecture must assume imperfect humans and processes. | - Modernize security architecture to reduce the blast radius of human error. Don't let clicking on a single phishing email cause your security posture to fail. - Design systems that are resilient to error. - Automate guardrails where possible. - Avoid architectures that depend on flawless manual operation. |

## Apply both law sets in decision-making

Use these two tables as complementary lenses. One helps validate technical soundness and the other helps drive risk-based prioritization. When combined, they form a practical decision framework for security and risk decisions across SAF, including architecture design and modernization.

| **Laws** | **Aim** | **SAF decision use** | **Questions answered** |
| --- | --- | --- | --- |
| **Immutable laws of security** | Capture technical truths that always hold. | Ensure architectures don't violate technical reality.Test assumptionsValidate trust boundaries.Avoid false confidence. | *Is the architecture fundamentally sound*?*Does the design rely on something that can easily be bypassed*?*Are we assuming technology can make up for untrusted admins, weak passwords, or physical access methods*?*Are we mistaking encryption, isolation, or tools for actual control*? |
| **Laws of cybersecurity risk** | Decide what matters most. | Identify where to invest architecture effort.Shape modernization roadmaps.Justify tradeoffs to business leaders. | *Where do attackers get the biggest payoff for least effort*?*Which controls actually change attacker behavior*?*What work is no longer worth doing*? |

### Example

So if we take an example that applies both tables together.

| **Design decision** | **Immutable laws lens** | **Ten laws lens** |
| --- | --- | --- |
| Reduce dependency on network ACLs to identity‑based access | Networks aren’t trustworthy, identity matters. | Raises attacker cost and aligns with Zero Trust principles. |
| Prioritize MFA for admins before hardening edge firewalls. | Weak passwords trump strong security. | Cheapest way to break common attack chains. |
| Segment workloads instead of relying on “air gaps” | Isolation isn’t automatically secure. | Reduces blast radius when attackers get in. |
| Automate patching and config drift detection | Out‑of‑date defenses fail. | Not keeping up is falling behind |

Using both tables together leads to security architectures that:

- Assume compromise, focus on risk reduction and damage limitation, rather than promising absolute prevention.
- Focus on identity, privilege, and lateral movement, not just on perimeter defense.
- Assume continuous change and evolution, and not static diagrams.
- Balance business productivity with risk reduction. Align security controls to business value.
- Integrate people, processes, and technology.
- Reduce attacker ROI instead of chasing perfect security.
- Apply Zero Trust principles end-to-end.