---
layout: Conceptual
title: Monitor and detect cyberthreats in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-threat-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn the security outcomes, priorities, and lessons from the cyberthreat monitoring pillar in Microsoft's Secure Future Initiative.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: 753b50eb-a8d3-79ee-46bb-5daee4d7788a
document_version_independent_id: 753b50eb-a8d3-79ee-46bb-5daee4d7788a
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-threat-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-threat-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-threat-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: db3f3fe0-0e22-a9c2-629c-b838c3884582
---

# Monitor and detect cyberthreats in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

This pillar focuses on improving detection quality and speed through better telemetry coverage, correlation, and operational visibility.

## Security outcome Microsoft prioritized

Microsoft prioritized earlier detection of high-impact threats and faster, coordinated investigation across identity, infrastructure, network, and engineering systems.

## What Microsoft prioritized

- Better inventory and telemetry coverage for production systems
- Durable security log retention and availability standards
- Centralized access patterns for security telemetry
- Faster anomaly detection and response workflows
- Cross-domain visibility that supports threat correlation

## Lessons from SFI implementation

- Detection quality depends on data quality, consistency, and governance.
- Shared telemetry standards improve cross-team response speed.
- Monitoring maturity improves when inventory, retention, and detection engineering are managed together.

## Zero Trust and NIST CSF alignment

This pillar primarily applies **Verify explicitly** and **Assume breach**.

Representative NIST CSF mappings:

- **Identify (ID)** for inventory and prioritization of monitored assets
- **Protect (PR)** for telemetry-enabling controls
- **Detect (DE)** for threat analysis and anomaly detection
- **Respond (RS)** for coordinated response activation

## Use canonical implementation guidance

Use these resources for implementation details:

- [SIEM and XDR overview](../siem-xdr-overview)
- [Microsoft Sentinel documentation](/en-us/azure/sentinel/)
- [Microsoft Defender XDR documentation](/en-us/defender-xdr/)
- [Azure security benchmark logging and monitoring](/en-us/security/benchmark/azure/)

## Related SFI and AI security guidance

- [Manage memory safety in agentic systems](manage-agentic-memory-safety)
- [Complete AI threat modeling](threat-modeling-ai)
- [Implement AI observability](observability-ai-systems)
- [Identify risk for autonomous agentic AI](manage-agentic-risk)
- [Secure autonomous agentic AI systems](secure-agentic-systems)
- [Defend against indirect prompt injection attacks](defend-indirect-prompt-injection)
- [Complete production infrastructure inventory](complete-production-infrastructure-inventory)
- [Security log retention standards](security-log-retention-standards)
- [Rapid anomaly detection and response](rapid-anomaly-detection-response)
- [Centralize access to security logs](centralize-access-to-security-logs)
- [Combating insider threats](combat-insider-threats)
- [Reinforcing a secure-first mindset](education-awareness)