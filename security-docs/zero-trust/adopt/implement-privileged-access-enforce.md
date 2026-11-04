---
layout: Conceptual
title: Phase 3-Enforce privileged access policies | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/adopt/implement-privileged-access-enforce
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to configure Conditional Access to control privileged access
ms.date: 2025-05-18T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.custom: sfi-image-nochange
locale: en-us
document_id: be604505-84d5-9151-7be7-d169b0aca839
document_version_independent_id: be604505-84d5-9151-7be7-d169b0aca839
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/adopt/implement-privileged-access-enforce.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/adopt/implement-privileged-access-enforce
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/adopt/implement-privileged-access-enforce.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/8b9ae643-2e85-42b8-beb2-eef4bae8c4bc
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e047e27d-b5f3-43a8-b4b0-4f6dca95e7c9
platformId: 357b4f6f-72e3-cd0e-2b60-5f1e7559c5f8
---

# Phase 3-Enforce privileged access policies | Microsoft Learn

This article is part of the [Implement a privileged access architecture](implement-privileged-access) solution guide.

Privileged access presents a critical security risk in most organizations because it enables direct control over identity systems, cloud control planes, and business‑critical assets.

Learn how a [secure privileged access architecture](../security-adoption-scenario-privileged-access) plays a critical role in your business scenario - *[Protect critical business assets](../security-adoption-scenario-secure-assets)* - by reducing this risk and strengthening control over sensitive systems.

This article describes Phase 3 of the implementation. It enforces privileged access policies to restrict where privileged identities can be used.

Using the trusted device signals established in Phase 2, you configure Conditional Access so privileged roles, portals, and management interfaces can be used only from approved, low-risk privileged access workstations (PAWs).

## Protection goals

Phase 3 enforces the following protection goals:

- Ensure privileged credentials can't be used from non-PAW devices.
- Admin portals and interfaces are only reachable from compliant, low-risk devices.
- Privileged access requires strong user authentication and verified device trust.
- Restrict access to administrative interfaces (portals, APIs, PowerShell) to approved PAWs.
- Stolen credentials can't be reused from standard or unmanaged endpoints.
- Privileged access paths are explicit, auditable, and enforceable.

## Protection scope

Phase 3 protects privileged access interfaces and workflows through which privileged actions occur, including:

- Cloud management portals (Azure portal, Microsoft Entra admin center, Microsoft 365 admin center)
- Security management portals (Microsoft Defender portals)
- Privileged role usage and activation (including PIM-controlled roles)
- Administrative browser sessions
- Network egress paths used by privileged devices

Phase 3 doesn't reconfigure devices or identities. It enforces policy using the outputs of Phases 1 and 2.

## Risks mitigated

| **Risk** | **Why it matters** | **Phase 3 mitigation** |
| --- | --- | --- |
| **Privileged credentials reused from non‑PAW devices** | MFA and approvals do not prevent attackers from reusing stolen tokens or credentials on compromised standard workstations. | Conditional Access requires privileged roles to authenticate from compliant, low‑risk PAWs only. |
| **Privileged access from high‑risk or unpatched devices** | A vulnerable device allows attackers to immediately exercise administrative control. | Access decisions evaluate Intune compliance and Microsoft Defender for Endpoint risk level before granting privileged access. |
| **Administrative portals accessible** from unmanaged or BYOD devices | Cloud control planes become reachable from devices outside organizational control. | Conditional Access restricts administrative portals to PAWs, blocking access from non‑PAW devices. |
| **Bypass of protected portals using alternate interfaces** | Attackers can avoid controls by using PowerShell, APIs, or alternative admin endpoints. | Enforcement applies consistently across administrative interfaces, not just primary portals. |
| **Privileged role activation from compromised workstations** | Approval workflows can be hijacked if role activation occurs on an unsafe device. | PIM role activation and role usage are enforced through the same Conditional Access device trust requirements. |
| **Credentials alone grant privileged access** | Identity‑only protections assume a trustworthy execution environment. | Phase 3 binds identity, device, and interface conditions so credentials alone are insufficient. |
| **Lack of visibility into enforcement** | Without policy enforcement, it’s difficult to prove privileged access is constrained. | Conditional Access decisions and Defender telemetry provide auditable, observable enforcement evidence. |
| **Rapid escalation after workstation compromise** | Attackers pivot quickly from a compromised device to enterprise‑wide control. | Phase 3 ensures stolen credentials are unusable outside PAWs, breaking common escalation paths. |

## Phase outcomes

After completing Phase 3:

- Privileged roles and admin portals are only accessible from compliant, low‑risk PAWs.
- Conditional Access blocks privileged access from non‑PAW devices.
- Device compliance and Microsoft Defender for Endpoint risk signals are required inputs to access decisions.
- Privileged access is enforced across identity, device, and interface layers.
- Access attempts are logged, observable, and auditable.

## Prerequisites

Before configuring procedures in this article:

- Complete [Phase 1 instructions](implement-privileged-access-identity) to secure the identity control plane.
- Complete [Phase 2](implement-privileged-access-devices) to deploy and harden PAWs.
- Make sure that device compliance and Defender for Endpoint integration is active.

## Step 1 — Require MFA and device trust for privileged access

Ensure privileged access requires strong user authentication and trusted devices.

1. In the [Microsoft Entra Admin Center](https://entra.microsoft.com), navigate to **Protection** &gt; **Conditional Access** &gt; **Policies**.
2. Select **Create new policy**.
3. In **Assignments** &gt; **Users**configure these settings:
    - Include privileged directory roles such as Global Administrator, Security Administrator.
    - Exclude the emergency break glass group.
4. In **Assignments** &gt; **Cloud apps** include cloud management applications such as the Azure portal, Microsoft Entra admin center, Microsoft 365 admin center, and Defender portals.
5. In **Access controls**, grant access with these settings:
    - Require multifactor authentication
    - Require device to be marked as compliant
    - Require Microsoft Defender for Endpoint device risk = Low
6. Enable the policy.

## Step 2 - Restrict administrative portals to PAWs

Ensure that administrative portals are reachable only from compliant PAWs.

1. In the [Microsoft Entra Admin Center](https://entra.microsoft.com), navigate to **Protection** &gt; **Conditional Access** &gt; **Policies**.
2. Select **Create new policy** to create an additional policy.
3. In **Assignments** &gt; **Users**configure these settings:
    - Include privileged directory roles such as Global Administrator, Security Administrator.
    - Exclude the emergency break glass group.
4. In **Assignments** &gt; **Cloud apps** include the administrative applications used for privileged access in your environment.
5. In **Access controls**, grant access with these settings:
    - Require device to be marked as compliant
    - Require Microsoft Defender for Endpoint device risk = Low
6. Enable the policy.

## Step 3 - Block privileged access from non-PAW devices

Ensure that privileged access to administrative portals is blocked from non‑PAW devices, even if those devices meet general compliance requirements.

1. In the [Microsoft Entra Admin Center](https://entra.microsoft.com), navigate to **Protection** &gt; **Conditional Access** &gt; **Policies**.
2. Select **Create new policy** to create a third policy.
3. In **Assignments** &gt; **Users**configure these settings:
    - Include privileged directory roles such as Global Administrator, Security Administrator.
    - Exclude designated emergency access accounts.
4. In **Assignments** &gt; **Cloud apps** include the same administrative portals.
5. Under **Conditions**, select **Filter for devices**.
6. Configure the device filter to target non‑PAW devices:
    - Select **Include filtered devices**:
    - Configure a device filter that identifies non-PAW devices based on the attribute or rule your organization uses to distinguish PAWs. Make sure this matches the identification method established in [Phase 2](implement-privileged-access-devices).
7. Select **Done** to apply the device filter condition.
8. Under **Access controls**, select **Block access**.
9. Select **Create** to enable the policy.

## Step 4 - Restrict PAW network access

Limit PAW network access to only required administrative and management endpoints. This configuration relies on explicit firewall rules to allow required endpoints, rather than broad protocol-based allowances.

1. In the Microsoft Intune admin center, navigate to **Endpoint security** &gt; **Firewall**.
2. Select **Create Policy**.
3. Configure the policy: - **Platform**: Windows 10 and later. 1. Configure the firewall profile settings:

    - **Inbound connections**: Block
    - **Outbound connections**: Allow (default, controlled by rules below)
4. Under **Settings**, configure **Firewall** rules. Use firewall rules to define the traffic required for privileged administration.
5. Create **outbound allow rules** for required services, such as:

    - DNS
    - DHCP
    - NTP
    - Required Microsoft cloud management endpoints such as Intune and Microsoft Entra ID.
    - Required administrative endpoints.

    Each rule should:

    - Specify **Direction**: **Outbound**.
    - Specify **Action**: **Allow**
    - Define **destination endpoints** (IP ranges, FQDNs, or service tags where supported)
6. Ensure no broad allow rules such as unrestricted HTTP/HTTPS are configured.
7. Assign the policy to **Secure Workstation Devices (PAWs)**.
8. Select **Create** to deploy the policy.

This completes the privileged access enforcement layer. The next article can build on this to cover measurement, monitoring, and success criteria.