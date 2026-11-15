---
layout: Conceptual
title: Protect identities and secrets in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-identity-overview
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn the security outcomes, priorities, and lessons from the identity and secrets pillar in Microsoft's Secure Future Initiative.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: overview
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
locale: en-us
document_id: b9c99b90-dc61-65e8-5017-d4fe3398db57
document_version_independent_id: b9c99b90-dc61-65e8-5017-d4fe3398db57
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/secure-future-initiative-identity-overview.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/secure-future-initiative-identity-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/secure-future-initiative-identity-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: ebd32cb0-166c-005f-8fa2-c77628b83de9
---

# Protect identities and secrets in the Microsoft Secure Future Initiative (SFI) | Microsoft Learn

This pillar focuses on reducing unauthorized access risk from identity compromise, token abuse, and exposed secrets.

## Security outcome Microsoft prioritized

Microsoft prioritized stronger identity assurance and lower credential risk by reducing dependence on long-lived credentials and tightening controls for privileged access, workload identity, and key management.

## What Microsoft prioritized

- Phishing-resistant authentication for high-impact access paths
- Reduced use of static credentials
- Increased use of managed identities and centralized secrets protection
- Automated key and secret lifecycle controls
- Standardized, supported identity SDK usage
- Faster detection and remediation of exposed credentials

## Lessons from SFI implementation

- Identity and credential controls are foundational risk reducers across all engineering and operations domains.
- Standardization and automation are necessary to reduce systemic identity risk at scale.
- Reducing standing access and long-lived credentials materially lowers blast radius.

## Zero Trust and NIST CSF alignment

This pillar primarily applies **Verify explicitly**, **Use least privilege access**, and **Assume breach**.

Representative NIST CSF mappings:

- **Protect (PR)** for authentication, authorization, and secrets controls
- **Detect (DE)** for credential misuse and token abuse detection

## Use canonical implementation guidance

Use these resources for implementation details:

- [Secure identity with Zero Trust](/en-us/security/zero-trust/deploy/identity)
- [Microsoft Entra architecture](/en-us/entra/architecture/)
- [Workload identities](/en-us/entra/workload-id/workload-identities-overview)
- [Privileged access strategy](/en-us/security/zero-trust/security-adoption-discipline-identity-access-privileged-strategy)
- [Azure Key Vault security baseline](/en-us/security/benchmark/azure/baselines/key-vault-security-baseline)

## Related SFI pattern pages

- [Phishing-resistant MFA](phishing-resistant-mfa)
- [Adopt standard SDKs for identity](adopt-standard-sdk-identity)
- [Least privilege for AI agents](least-privilege-for-ai-agents)
- [Modernizing identity governance with Microsoft Entra ID Governance](migrate-identity-governance)
- [Safe Secrets Standard](safe-secrets-standard)