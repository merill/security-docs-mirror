---
layout: Conceptual
title: Safe Secrets Standard with Microsoft Entra ID and Azure Key Vault | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/sfi/safe-secrets-standard
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: v-cjwoodling
author: cjwoodling6
description: Eliminate credential-based risk by removing all unmanaged service-to-service secrets and replacing them with identity-based authentication.
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.date: 2026-09-25T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1028
ms.collection:
- highpri
- zerotrust
- sfi-zerotrust
ai-usage: ai-generated
locale: en-us
document_id: 48671606-6c85-78f3-e8e7-e78f0fae65bc
document_version_independent_id: 48671606-6c85-78f3-e8e7-e78f0fae65bc
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/sfi/safe-secrets-standard.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/sfi/safe-secrets-standard
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/sfi/safe-secrets-standard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/f488294d-f483-456e-94e3-755f933b811b
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/02662057-0b9b-40f4-a3c7-537125b6d283
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 57e4e275-6792-5938-bb64-3caa5fadf3f1
---

# Safe Secrets Standard with Microsoft Entra ID and Azure Key Vault | Microsoft Learn

**Pillar name: Protect identities and secrets** **Practice name: Eliminate unmanaged service-to-service secrets**

Manual handling of service-to-service (S2S) secrets has been a recurring source of security incidents and reliability issues across the industry. To address this risk internally, Microsoft established the Safe Secrets Standard, an internal security standard under the Secure Future Initiative (SFI).

## Context and problem

S2S is a process by which one application, service, or system verifies the identity of another so they can communicate securely without involving human users across cloud and hybrid environments. The Safe Secrets Standard is designed to eliminate credential‑based risk by removing unmanaged secrets from S2S authentication. The goal is to make secrets invisible by replacing unmanaged credentials with identity‑based access control wherever possible.

Organizations adopting the Safe Secrets Standard often encounter similar challenges. The following scenarios strongly indicate the need for managed identity:

- Hard‑coded credentials in code, configuration files, or repositories
- Lack of visibility into where secrets exist or how they're used
- Third‑party access that's difficult to grant, audit, or revoke
- Continuous integration/continuous delivery (CI/CD) pipelines requiring manual credential injection
- Manual certificate or secret rotation processes

In each of these cases, identity‑based authentication replaces insecure practices and brittle processes with platform‑enforced standards and security.

## Solution

The Safe Secrets Standard removes all unmanaged S2S credentials primarily by adopting managed identities in Microsoft Entra ID. In scenarios where managed identity or native Entra authentication isn't yet supported, store secrets in protected environments like Azure Key Vault and set up automatic rotation.

The key principles of the Safe Secrets Standard include:

- Use Microsoft Entra ID authentication instead of local or shared credentials.
- Use managed identity for Azure workloads when supported.
- Eliminate hard‑coded, manually distributed, or long‑lived secrets.

Microsoft developed this standard to protect critical infrastructure and resources that threat actors frequently target. Microsoft now uses this standard for all internally managed S2S secrets.

## Guidance

| **Use case** | **Recommended action** | **Resource** |
| --- | --- | --- |
| **Inventory secrets (code + pipeline + runtime) and prioritize by blast radius and exposure** | Inventory passwords, API keys, connection strings, certificates, and other credentials across application code, CI/CD pipelines, runtime environments, and supporting infrastructure. Prioritize remediation for secrets that are externally exposed, long-lived, broadly shared, or grant access to production systems and high-value data. Treat discovered hard-coded or embedded secrets as compromised, replace them, and remove them from code or configuration. Use separate Key Vaults by application, environment, and region to reduce blast radius and simplify operational boundaries. | [Secure your Azure Key Vault](/en-us/azure/key-vault/general/secure-key-vault) |
| **Replace with managed identity / workload identity** | Use managed identities for Azure-hosted workloads wherever supported to eliminate application secrets and passwords. Where an Entra application is required, use workload identity federation to reduce or eliminate stored credentials. For application code, use Azure Identity or MSAL patterns to connect to Azure resources such as Key Vault, Storage, and SQL by using token-based access rather than stored credentials. Where a target resource doesn't yet support token-based authentication, retrieve the credential from Key Vault rather than embedding it in code or configuration. | [Managed identities for Azure resources](/en-us/entra/identity/managed-identities-azure-resources/managed-identities-faq)[Connecting from your application to resources without handling credentials](/en-us/entra/identity/managed-identities-azure-resources/overview-for-developers?tabs=dotnet) |
| **Consolidate remaining secrets into Key Vault** | Store remaining application credentials, access keys, passwords, and connection strings in Azure Key Vault rather than in code or configuration. Use managed identities for application and service connections to Key Vault. Use Azure RBAC for Key Vault instead of legacy access policies for critical workloads and assign roles at the vault scope except in limited exception scenarios. Enable foundational protections such as soft delete and purge protection, and consider Managed HSM for highly sensitive key scenarios. | [Secure your Azure Key Vault](/en-us/azure/key-vault/general/secure-key-vault)[Provide access to Key Vault keys, certificates, and secrets with Azure role-based access control](/en-us/azure/key-vault/general/rbac-guide?tabs=azure-cli)[Best practices for protecting secrets](/en-us/azure/security/fundamentals/secrets-best-practices)[Secure your Azure Key Vault secrets](/en-us/azure/key-vault/secrets/secure-secrets) |
| **Automate rotation + app refresh** | For keys, configure Key Vault rotation policies and use versionless URIs so dependent services can use the latest key version with minimal change. For secrets, use Event Grid and Azure Functions to automate rotation and application refresh. For resources with one credential set, plan for a brief update window while the target system is refreshed. For resources with two credential sets, alternate the inactive credential to support lower-disruption or zero-downtime rotation patterns. In application code, cache secrets in memory and refresh cached values when secrets rotate. | [Understanding autorotation in Azure Key Vault](/en-us/azure/key-vault/general/autorotation)[Configure key autorotation in Azure Managed HSM](/en-us/azure/key-vault/managed-hsm/key-rotation?tabs=azure-portal)[Automate the rotation of a secret for resources that use one set of authentication credentials](/en-us/azure/key-vault/secrets/tutorial-rotation)[Automate the rotation of a secret for resources that have two sets of authentication credentials](/en-us/azure/key-vault/secrets/tutorial-rotation-dual?tabs=azure-cli)[Configure cryptographic key auto-rotation in Azure Key Vault](/en-us/azure/key-vault/keys/how-to-configure-key-rotation) |
| **Monitor and governance** | Use Azure RBAC for Key Vault and avoid legacy access policies for critical workloads. Use Privileged Identity Management (PIM) to provide eligible, just-in-time access for Key Vault administrators and operators. Use Azure Policy to enforce secure Key Vault configuration. Enable audit logging, Defender for Key Vault, Azure Monitor alerts, and lifecycle notifications to track access and rotation outcomes. Regularly review privileged access and remove unnecessary permissions. | [What is managed identities for Azure resources?](/en-us/entra/identity/managed-identities-azure-resources/overview)[Understanding autorotation in Azure Key Vault](/en-us/azure/key-vault/general/autorotation)[Configure cryptographic key auto-rotation in Azure Key Vault](/en-us/azure/key-vault/keys/how-to-configure-key-rotation)[Best practices for protecting secrets](/en-us/azure/security/fundamentals/secrets-best-practices) |

In an emergency, services should be able to rotate secrets within a 24-hour period without manual action. Even in an emergency, the expedited distribution mechanism is the same one used for a planned rotation. In other words, whether it’s a routine rotation or an urgent fix, services should use the same vetted and highly secure mechanism to obtain and apply new secrets automatically, without manual intervention and the risks that it introduces.

In edge cases, there can be other guidance that doesn't include managed identity. Due to the nature of and complexity that often comes with enterprises, these edge cases require case-by-case assessment.

Additionally, Microsoft urges that customers prioritize identifying and deleting unused S2S secrets, but that they proceed cautiously to prevent the disruption of normal business operations.

## Outcomes

### Benefits

- Eliminate all unmanaged S2S secrets.
- Safeguard sensitive data against unauthorized access across various services and applications.
- Prioritize the protection of sensitive and frequently used resources.

### Trade-offs

- Engineer training: Developers and other engineers need training on how to use tools like [GitHub Advanced Security](https://docs.github.com/en/code-security/concepts/secret-security/about-secret-scanning) to scan for secrets in source code and block their upload to source code repositories.
- Cost of implementation: Remediating all unmanaged S2S secrets across an enterprise codebase requires centralized management and prioritization by managers who can assess risk from a business and technical point of view.

## Key success factors

You achieve the Safe Secrets Standard when you eliminate all unmanaged service-to-service (S2S) secrets.

In practical terms, success means:

- Fully disabling local authentication for Azure resources
- Using Microsoft Entra ID as the primary authentication system
- Using managed identities for all supported Azure workloads
- Using automated secret rotation only where identity isn't yet available
- Blocking plaintext secrets from being uploaded to source code repositories

For Microsoft services, this approach means that applications authenticate by using tokens issued by Microsoft Entra ID rather than storing or transmitting shared secrets.

## Summary

Eliminate credential-based risk by removing all unmanaged service-to-service secrets and replacing them with identity-based authentication. Prioritize managed identities in Microsoft Entra ID, move any remaining secrets into protected stores like Azure Key Vault, and automate rotation to minimize exposure. Drive consistency by treating secret-based authentication as a temporary exception and enforcing token-based access across all services. Measure success by fully disabling local authentication, adopting Entra ID as the primary control plane, and ensuring no unmanaged secrets remain in your environment.