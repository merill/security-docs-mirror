---
layout: Conceptual
title: Adopting Microsoft Secure Future Initiative (SFI) best practices | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/secure-future-initiative-adoption
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn about adopting Microsoft's Secure Future Initiative (SFI) best practice patterns.
ms.date: 2026-01-19T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: best-practice
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/f488294d-f483-456e-94e3-755f933b811b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/02662057-0b9b-40f4-a3c7-537125b6d283
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 435daaa6-a27f-a12f-5dad-c862f38594c3
---

# Adopting Microsoft Secure Future Initiative (SFI) best practices | Microsoft Learn

Microsoft's Secure Future Initiative (SFI) launched as a multiyear effort to further secure the way that Microsoft designs, builds, tests, and operates its infrastructure, products, and services.

This article shows how your organization might consider and adopt some of these SFI best practices.

Note

- We're continuously working on content that details each best practice pattern within pillars. Links to these best practices are included where available and we're planning to publish more over time.
- Before you start, [get an overview of SFI](secure-future-initiative-overview).

## Protect identities and secrets

Initiatives under this pillar aim to reduce the risk of unauthorized access by implementing and enforcing standards to control user/app authentication and authorization, and to harden the identity and secrets infrastructure. The Microsoft SFI initiative work focuses on:

- Passwordless, phishing-resistant multifactor authentication (MFA) (FIDO2 passkeys, certificate-based auth) for all users.
- Deprecation of passwords, SMS OTP, etc.
- Replacement of static credentials with managed identities and Microsoft Entra Workload ID.
- Storage of secrets in Azure Key Vault, key protection with Managed Hardware Security Module (HSM) with role-based access control (RBAC), network isolation, and access logs.
- Automated key rotation and HSM-backed token signing.
- Adoption of standard SDKs with supported identity libraries (MSAL, Microsoft.Identity.Web), and avoiding custom Json Web Token (JWT) validation.
- Periodic scanning of code pipelines, and repos for leaked secrets.

### Adopt best practices

Key adoption best practices for identity and secrets protection are summarized in the following table.

| **Best practice** | **Zero Trust** | **Adoption considerations** | **Detailed guidance** |
| --- | --- | --- | --- |
| Implement and enforce phishing-resistant MFA across privileged accounts and admins.Deprecate legacy MFA methods that aren't phishing-resistant or sufficiently secure.Eliminate static credentials and enable dynamic short-lived tokens for workloads.Centralize credentials in in centralized, monitored vaults.Automate secret rotation and signing key lifecycle. Use standardized, Microsoft-supported SDKs, avoid custom JwT identification.Continuously scan, detect, and remediate credential vulnerabilities. | **Verify explicitly**: Continuous, adaptive authentication based on risk and context.**Use least privilege**: Use Just-In-Time/Just-Enough Access controls.**Assume breach**: Credential misuse triggers automatic revocation and access reviews. | Might require modernization of older applications to support managed identities. User enablement and hardware are required for some MFA methods. Operational overhead for auditing and rotation policies. | [Adopt phishing-resistant MFA](/en-us/security/zero-trust/sfi/phishing-resistant-mfa).[Adopt standard SDKs for identity](/en-us/security/zero-trust/sfi/adopt-standard-sdk-identity). |

## Protect tenants and isolate systems

Initiatives under this pillar aim to independently secure and isolate tenants and environments to eliminate implicit trust and reduce blast radius. The Microsoft SFI initiative focuses on:

- Strong tenant isolation and configuration governance across production tenants.
- Restriction of cross-tenant access and privileged delegation.
- Implementation of privileged access workstations (PAWs) and isolated admin tools.
- Application of tenant baselines and resource isolation.
- Segmentation of management and customer data paths, with no implicit trust between engineering, customer, and operational tenants.

### Adopt best practices

Key adoption best practices for identity and secrets protection are summarized in the following table.

| **Best practice** | **Zero Trust** | **Adoption considerations** | **Detailed guidance** |
| --- | --- | --- | --- |
| Create isolated environments for production, test, and partner tenants. Limit or eliminate cross-tenant roles, and enforce conditional access. Require hardening devices for administration.Define and enforce tenant baselines and resource isolation using consistent policies and controls.Enforce strict data path separation across environments. | **Verify explicitly**: Cross-tenant and inter-environment trust always reauthenticated and logged.**Use least privilege**: Access boundaries defined per tenant, workload, and admin role.**Assume breach**: Tenant isolation used as a hard boundary to prevent lateral movement. | Requires good tenant inventory and centralized governance.Multitenant orgs may need federated identity strategies or cross-tenant access policies.Initial increase in admin complexity to configure PIM and conditional access rules. | [Eliminate identity lateral movement](/en-us/security/zero-trust/sfi/eliminate-identity-lateral-movement)[Remove legacy systems](/en-us/security/zero-trust/sfi/remove-legacy-systems-that-risk-security)[Increase security for Microsoft Entra ID apps](/en-us/security/zero-trust/sfi/higher-security-microsoft-entra-id-apps)[Secure all tenants and resources](/en-us/security/zero-trust/sfi/secure-all-tenants-resources). |

## Protect networks

Initiatives under this pillar aim to limit lateral movements and enforce explicit validation for all connectivity through network segmentation. The Microsoft SFI initiative focuses on:

- Network segmentation and isolation between production, engineering, and corporate environments.
- Identity-based access layered on top of network segmentation.
- Private access for management interfaces.
- Continuous access evaluation (CAE) for network sessions.
- No implicit trust across network resources.
- Use of network-level threat-intelligence-enabled firewalls, strict egress control, and telemetry logging.

### Adopt best practices

Key adoption best practices for identity and secrets protection are summarized in the following table.

| **Best practice** | **Zero Trust** | **Adoption considerations** | **Detailed guidance** |
| --- | --- | --- | --- |
| Implement of macro and microsegmentation across networks and subnets, separating production, admin, and PaaS service boundaries. Restrict admin access via Private Link, Azure Bastion, and just-in-time admin access.Implement session validation tied to identity state.Use Secure Access Service Edge (SASE) and Zero Trust network access (ZTNA) instead of VPNs. Enable and tune Microsoft Defender for network telemetry. | **Verify explicitly**: Every connection is authenticated, authorized, and encrypted.**Use least privilege**: Access granted only to required services or segments.**Assume breach**: Network segmentation and monitoring detect and contain lateral movement. | Deep understanding of existing traffic flows; segmentation can disrupt legacy integrations.Retraining users used to VPN-based access on ZTNA rollout.Additional cost and storage overhead of network telemetry in SIEM. | [Isolate networks](/en-us/security/zero-trust/sfi/network-isolation). |

## Protect engineering systems

Initiatives under this pillar aim to secure the entire software engineering and delivery process. The Microsoft SFI initiative focuses on:

- Isolation of build environments from internet and production.
- Code signing using trusted pipelines.
- Adoption of two-person integrity for sensitive operations.
- Software Bill of Materials (SBOM) tracking
- Pipeline scanning for leaked credentials or malicious code.
- Standardization of SDKs, developer security tooling, and dependency verification.

### Adopt best practices

Key adoption best practices for identity and secrets protection are summarized in the following table.

| **Best practice** | **Zero Trust** | **Adoption considerations** | **Detailed guidance** |
| --- | --- | --- | --- |
| Run builds in secure isolated environments.Require verified build provenance and signed artifacts.Require code or release approval from multiple trusted approvers. Maintain software component inventories/SBOM tracking for all builds.Integrate secrets scanning and SAST/DAST tools into CI/CD pipelines for code scanning.Enforce trusted package sources and signed dependencies. | **Verify explicitly**: Authenticate all code commits, build actions, and releases.**Use least privilege**: Developers, pipelines, and service principals only access what they need.**Assume breach**: Treat build and repo systems as potential targets. Isolate and monitor them. | High load of upfront work to modernize pipelines and dependency tracking.Handling legacy build tools that might not support signing or SBOM formats.Added build-time complexity for artifact signing that significantly improves traceability. | [Standardize secure development pipelines](/en-us/security/zero-trust/sfi/standardize-secure-development-pipelines)[Apply Zero Trust principles for source code access](/en-us/security/zero-trust/sfi/zero-trust-source-code-access)[Protect the software supply chain](/en-us/security/zero-trust/sfi/protect-software-supply-chain). |

## Monitor and detect cyberthreats

Initiatives under this pillar aim to unify telemetry across identity, endpoint, network, and engineering systems for proactive, contextualized threat detection, and fast, effective investigation and response. The Microsoft SFI initiative focuses on:

- Unified telemetry ingestion from identity, endpoint, network, and engineering systems.
- Development of threat correlation models and AI-driven detection.
- Shared detection rules across tenants.
- Centralized dashboards for rapid triage.
- Threat intelligence integration from MSTIC and global sources.

### Adopt best practices

Key adoption best practices for identity and secrets protection are summarized in the following table.

| **Best practice** | **Zero Trust** | **Adoption considerations** | **Detailed guidance** |
| --- | --- | --- | --- |
| Centralize logs (identity, Key Vault, network, endpoint, etc.) into Microsoft Sentinel or another security information and event management (SIEM) solution. Use analytics and ML-based threat detection for abnormal behaviorStandardize detection templates and automationConsolidate visibility across assets and incidentsUse threat feeds to enrich detection and alerting | **Verify explicitly**: Continuous validation of behavior and state against normal baselines.**Use least privilege**: Detections inform adaptive policies that restrict access automatically.**Assume breach**: Assume that attackers might already have access, and detect attack movement quickly. | Ongoing tuning to avoid alert fatigue. Costs for licensing and ingestion volume for Sentinel/SIEM. Continuous refinement and analyst training for detection logic. | [Inventory production infrastructure](/en-us/security/zero-trust/sfi/complete-production-infrastructure-inventory)[Set security log retention standards](/en-us/security/zero-trust/sfi/security-log-retention-standards)[Detect and respond to anomalies](/en-us/security/zero-trust/sfi/rapid-anomaly-detection-response)[Centralize access to security logs](/en-us/security/zero-trust/sfi/centralize-access-to-security-logs). |

## Accelerate response and remediation

Initiatives under this pillar aim to minimize the duration and impact of security incidents through automation, orchestration, and systemic learning. The Microsoft SFI initiative focuses on:

- Rapid coordinated incident response and patching, with automation of common mitigations.
- Systematic post-incident learning, and "secure-by-default” changes integrated into products and services.
- Continuous improvement loops and cross-team incident-response playbooks.

### Adopt best practices

Key adoption best practices for identity and secrets protection are summarized in the following table.

| **Key practices** | **Zero Trust** | **Adoption considerations** | **Detailed guidance** |
| --- | --- | --- | --- |
| Develop and test incident response playbooks for common attack types. Automate token revocation, key rotation, and account disablement workflows. Tie vulnerability management processes to business risk and exposure. Adopt post-incident learning loops, and integrate lessons into policy and code baselines. Design communication plans (legal, PR, technical, etc.) for significant breaches. Run regular tabletop exercises with leadership and technical teams. | **Verify explicitly**: Continuously reassess and revoke trust as needed after a security event.**Use least privilege**: Automate containment by restricting or removing access rapidly.**Assume breach**: Treat every incident as a catalyst for architectural and procedural hardening. | Disciplined coordination is needed between the security operations center (SOC), engineering, and leadership. Automation of remediation actions must balance speed and risk of disruption. Time and learning can result from tabletop exercises that might expose procedural gaps, but deliver large maturity gains. | [Accelerate vulnerability mitigation](/en-us/security/zero-trust/sfi/accelerate-vulnerability-mitigation). |