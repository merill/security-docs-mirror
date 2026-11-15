---
layout: Conceptual
title: Apply Microsoft Secure Future Initiative (SFI) lessons | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-adoption
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Apply lessons from Microsoft's Secure Future Initiative by mapping SFI priorities to Zero Trust, SAF, and canonical Microsoft implementation guidance.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 59ceeb21-3e2f-e6ca-ef13-cb921235e784
document_version_independent_id: 59ceeb21-3e2f-e6ca-ef13-cb921235e784
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-adoption.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-adoption
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-adoption.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 435daaa6-a27f-a12f-5dad-c862f38594c3
---

# Apply Microsoft Secure Future Initiative (SFI) lessons | Microsoft Learn

Microsoft's Secure Future Initiative provides lessons that organizations can use to strengthen their own security programs. Many of the security practices implemented through SFI are established security practices already covered by Microsoft Zero Trust, architecture, operational, and product guidance.

SFI adds value by showing which practices Microsoft prioritized, why they became priorities, what Microsoft changed, and what organizations can learn from Microsoft's experience. Use the existing Microsoft security guidance linked from this section to plan and implement these practices in your environment.

## How to use this guidance

Use SFI to inform prioritization and program sequencing, not as a separate implementation framework.

- Start with the [SFI overview](secure-future-initiative-overview) for context and boundaries.
- Use [SAF](/en-us/security/zero-trust/security-adoption-model) to organize your modernization journey.
- Use [Zero Trust guidance](../zero-trust-overview) to align principles and architecture.
- Use product and architecture documentation for implementation details.

## Pillar 1: Protect identities and secrets

**Security outcome Microsoft prioritized:** Reduce unauthorized access risk from weak authentication, overprivilege, exposed secrets, and long-lived credentials.

**SFI priorities:** phishing-resistant authentication, managed identities, centralized secrets protection, automated rotation, supported identity SDKs, and exposed-secret detection.

**Implementation insights from SFI:** credential misuse and token abuse create high-impact attack paths; reducing standing credential risk and standardizing identity controls improves resilience.

**Zero Trust alignment:** Verify explicitly, Use least privilege, Assume breach.

**Canonical implementation guidance:**

- [Secure identity with Zero Trust](/en-us/security/zero-trust/deploy/identity)
- [Microsoft Entra architecture](/en-us/entra/architecture/)
- [Workload identities](/en-us/entra/workload-id/workload-identities-overview)
- [Privileged access strategy](/en-us/entra/identity/role-based-access-control/security-planning)
- [Azure Key Vault security baseline](/en-us/security/benchmark/azure/baselines/key-vault-security-baseline)

**SFI pattern pages retained for SFI-specific context:**

- [Phishing-resistant MFA](phishing-resistant-mfa)
- [Adopt standard SDKs for identity](adopt-standard-sdk-identity)
- [Safe Secrets Standard](safe-secrets-standard)
- [Secure identity to get ready for AI](secure-identity-to-get-ready-for-ai)

## Pillar 2: Protect tenants and isolate systems

**Security outcome Microsoft prioritized:** Limit blast radius and identity-based lateral movement across tenants, environments, and administrative boundaries.

**SFI priorities:** tenant isolation, hardened cross-tenant access controls, safer administrative workstations, and stronger controls for app identities and tenant configurations.

**Implementation insights from SFI:** explicit boundary design and consistent governance reduce systemic risk from complex multi-tenant operations.

**Zero Trust alignment:** Verify explicitly, Use least privilege, Assume breach.

**Canonical implementation guidance:**

- [Deploy tenant restrictions](/en-us/entra/external-id/tenant-restrictions-v2)
- [Cross-tenant access settings](/en-us/entra/external-id/cross-tenant-access-overview)
- [Privileged access strategy](/en-us/security/zero-trust/security-adoption-discipline-identity-access-privileged-strategy)
- [Security baselines and governance](/en-us/security/benchmark/azure/)

**SFI pattern pages retained for SFI-specific context:**

- [Eliminate identity lateral movement](eliminate-identity-lateral-movement)
- [Remove legacy systems that risk security](remove-legacy-systems-that-risk-security)
- [Higher security for Microsoft Entra ID apps](higher-security-microsoft-entra-id-apps)
- [Secure all tenants and their resources](secure-all-tenants-resources)
- [Secure Admin Workstations (SAW) devices and how they are used](saw-devices)

## Pillar 3: Protect networks

**Security outcome Microsoft prioritized:** Reduce lateral movement and unauthorized connectivity across internal and production networks.

**SFI priorities:** stronger segmentation, identity-aware controls, isolation boundaries, and tighter controls for privileged network paths.

**Implementation insights from SFI:** practical segmentation sequencing and boundary hardening are essential for reducing high-consequence network pivot paths.

**Zero Trust alignment:** Verify explicitly, Use least privilege, Assume breach.

**Canonical implementation guidance:**

- [Secure networks with Zero Trust](/en-us/security/zero-trust/deploy/networks)
- [Azure network security architecture](/en-us/azure/architecture/reference-architectures/hybrid-networking/)
- [Azure landing zone network topology and connectivity](/en-us/azure/cloud-adoption-framework/ready/landing-zone/design-area/network-topology-and-connectivity)

**SFI pattern pages retained for SFI-specific context:**

- [Network isolation](network-isolation)
- [Teams end-to-end encryption](teams-end-to-end-encryption)

## Pillar 4: Protect engineering systems

**Security outcome Microsoft prioritized:** Improve trust in software supply chains, source code systems, build pipelines, and engineering operations.

**SFI priorities:** secure build pipelines, stronger source code access controls, software supply chain governance, and engineering security standards.

**Implementation insights from SFI:** reducing systemic engineering risk requires combined controls across identity, workflow governance, and pipeline integrity.

**Zero Trust alignment:** Verify explicitly, Use least privilege, Assume breach.

**Canonical implementation guidance:**

- [Secure development imperatives in SAF](/en-us/security/zero-trust/security-adoption-discipline-development-imperatives)
- [GitHub security hardening](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)
- [Defender for DevOps](/en-us/azure/defender-for-cloud/defender-for-devops-introduction)
- [NIST SSDF (SP 800-218)](https://csrc.nist.gov/pubs/sp/800/218/final)

**SFI pattern pages retained for SFI-specific context:**

- [Standardize secure development pipelines](standardize-secure-development-pipelines)
- [Zero Trust for source code access](zero-trust-source-code-access)
- [Protect the software supply chain](protect-software-supply-chain)
- [Governed pipeline templates](governed-pipeline-templates)
- [Securing source code with GitHub Advanced Security](secure-source-code-github-advanced-security)

## Pillar 5: Monitor and detect cyberthreats

**Security outcome Microsoft prioritized:** Improve detection speed and quality by increasing telemetry coverage, correlation, and operational visibility.

**SFI priorities:** infrastructure inventory, log retention standards, centralized access to security telemetry, and faster anomaly detection.

**Implementation insights from SFI:** durable detection improvements require consistent data quality, shared telemetry standards, and governance across teams.

**Zero Trust alignment:** Verify explicitly, Assume breach.

**Canonical implementation guidance:**

- [SIEM and XDR overview](../siem-xdr-overview)
- [Microsoft Sentinel architecture and best practices](/en-us/azure/sentinel/)
- [Defender XDR operations](/en-us/defender-xdr/)
- [Cloud security posture and inventory guidance](/en-us/security/benchmark/azure/)

**SFI pattern pages retained for SFI-specific context:**

- [Complete production infrastructure inventory](complete-production-infrastructure-inventory)
- [Security log retention standards](security-log-retention-standards)
- [Rapid anomaly detection and response](rapid-anomaly-detection-response)
- [Centralize access to security logs](centralize-access-to-security-logs)

## Pillar 6: Accelerate response and remediation

**Security outcome Microsoft prioritized:** Reduce incident impact and duration through coordinated response, automation, and feedback loops into engineering.

**SFI priorities:** faster vulnerability mitigation, stronger response orchestration, and improved communication and recovery discipline.

**Implementation insights from SFI:** response maturity improves when remediation workflows, ownership models, and post-incident learning are integrated into engineering and operations.

**Zero Trust alignment:** Verify explicitly, Use least privilege, Assume breach.

**Canonical implementation guidance:**

- [Plan incident response with SAF](/en-us/security/zero-trust/security-adoption-discipline-security-operations-incidents)
- [Prepare for incident response with SAF](/en-us/security/zero-trust/security-operations-incident-response-readiness)
- [Microsoft incident response playbooks](/en-us/security/zero-trust/security-operations-incident-response-playbooks)
- [Defender XDR incident response](/en-us/defender-xdr/incident-response-overview)

**SFI pattern pages retained for SFI-specific context:**

- [Accelerate vulnerability mitigation](accelerate-vulnerability-mitigation)
- [Accelerating vulnerability response](accelerate-vulnerability-response)
- [Respond to incidents in AI systems](incident-response-ai-systems)

## Relationship to SAF

The Microsoft Secure Future Initiative is Microsoft's multiyear security transformation program. The Security Adoption Framework incorporates relevant lessons and practices from SFI while connecting organizations to established Microsoft architecture, operational, and technology guidance for implementation.