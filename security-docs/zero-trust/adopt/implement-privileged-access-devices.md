---
layout: Conceptual
title: Secure devices and workstations | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/adopt/implement-privileged-access-devices
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Learn how to secure devices and workstations in a privileged access architecture
ms.date: 2025-05-25T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
ms.custom: sfi-image-nochange
locale: en-us
document_id: 2b7b45aa-f494-f573-9987-7405fa6bdd37
document_version_independent_id: 2b7b45aa-f494-f573-9987-7405fa6bdd37
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/adopt/implement-privileged-access-devices.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/adopt/implement-privileged-access-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/adopt/implement-privileged-access-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 0dfdfdb1-9dee-e9ec-85ed-840d9a5bc9c0
---

# Secure devices and workstations | Microsoft Learn

This article is part of the [Implement a privileged access architecture](implement-privileged-access) solution guide.

Privileged access presents a critical security risk in most organizations because it enables direct control over identity systems, cloud control planes, and business‑critical assets.

Learn how a [secure privileged access architecture](../security-adoption-scenario-privileged-access) plays a critical role in your business scenario - *[Protect critical business assets](../security-adoption-scenario-secure-assets)* - by reducing this risk and strengthening control over sensitive systems.

This article describes Phase 2 of the solution. It deploys and hardens Privileged Access Workstations (PAWs) so privileged activity originates only from trusted devices. It builds on Phase 1 and produces the device trust signals (Intune compliance and Microsoft Defender for Endpoint risk) used for enforcement in Phase 3.

## Protection goals

Phase 2 ensures that privileged access:

- Originates only from trusted, hardened devices.
- Is isolated from high‑risk productivity activities.
- Produces a clean, reliable device signal for later enforcement.
- Reduces credential theft, token replay, and session hijacking risk.
- Limits blast radius if a device is compromised.

## Protection scope

Privileged access is only as trustworthy as the device from which it originates. Identity protections—such as MFA, approvals, and role activation—can't compensate for a compromised workstation. If an attacker controls the device used for privileged access, they can:

- Steal authentication tokens after MFA is completed.
- Inject malicious processes into administrative sessions.
- Replay credentials or tokens from memory.
- Bypass approval workflows by operating as the legitimate user.

For privileged roles, a single compromised workstation can enable rapid escalation to tenant‑wide or enterprise‑wide control. As a result, device security defines the upper bound of trust for privileged access. Privileged access policies therefore assume that administrative sessions originate from devices that meet the highest security bar. These devices form the trust boundary for privileged operations.

### Privileged access workstations (PAWs)

A PAW is a hardened, managed Windows workstation designed exclusively for privileged tasks. PAWs define the device trust boundary for privileged access, and are isolated from common attack vectors.

- Are isolated from email, general web browsing, and productivity workloads.
- Are enrolled and managed via Microsoft Intune.
- Use Microsoft Entra ID for identity integration.
- Are monitored by Microsoft Defender for Endpoint.
- Provide a strong hardware-based root of trust.

Here's how PAWs fit in from a security level/profile perspective.

| **Security level** | **Device profile** |
| --- | --- |
| Enterprise users | Standard managed device |
| Specialized operators | Hardened managed device |
| Privileged (control plane administrators) | PAW |

## Risks mitigated

| **Risk** | **Why it matters** | **Phase 1 mitigation** |
| --- | --- | --- |
| **Attacker steals authentication tokens after MFA** | MFA protects authentication, not the execution environment. If a workstation is compromised, attackers can steal tokens post‑authentication and reuse them to impersonate privileged users. | PAWs isolate privileged work on hardened devices with reduced attack surface, credential protection (Credential Guard), and continuous monitoring, preventing token theft from compromised productivity devices. |
| **Malicious process injection into administrative sessions** | Attackers can inject code into admin tools or browser sessions on compromised devices, gaining control of privileged operations even when identities are protected. | Application control, removal of local admin rights, and restricted application execution on PAWs prevent unauthorized code execution during administrative sessions. |
| **Credential replay from memory** | Attackers can extract credentials or tokens from memory on compromised workstations and replay them to escalate privileges or move laterally. | PAWs enforce credential isolation using virtualization‑based security and hardened OS configurations, reducing exposure of credentials in memory and limiting replay opportunities. |
| **Approval workflows bypassed from compromised devices** | Even with approval‑based role activation, attackers controlling a workstation can hijack approved sessions and rapidly escalate privileges. | Device trust becomes a prerequisite for privileged work. PAWs ensure approvals and administrative actions occur only from devices designed to resist compromise. |
| **Rapid escalation from compromised workstation** | A single compromised admin workstation can allow attackers to pivot quickly to identity systems, control planes, and enterprise‑wide administration. | Device security sets an upper bound on trust. PAWs provide the highest security bar, reducing the likelihood that a compromised endpoint can be used to escalate into privileged roles. |

## Phase outcomes

After completing Phase 2:

- One or more dedicated PAW devices are set up.
- Privileged administrative work originates only from PAWs.
- PAWs are isolated from productivity usage.
- Devices are centrally managed, monitored, and recoverable.
- Device trust assumptions are explicit and enforceable.
- Later phases can safely apply Conditional Access and monitoring.

## Prerequisites

Before configuring procedures in this article:

- Make sure that [Phase 1 instructions](implement-privileged-access-identity) are complete.
- Learn about [device security in the privileged access story](../security-concept-privileged-access).
- The following services should be available:
    - Microsoft Entra ID as the identity provider.
    - Microsoft Intune for device management.
    - Microsoft Defender for Endpoint for threat protection.
- You need at least one supported Windows device per administrator, with modern Windows hardware that supports:
    - TPM 2.0
    - UEFI Secure Boot
    - BitLocker
    - Virtualization-based security (VBS/HVCI)
    - Firmware and drivers serviced through Windows Update.

Devices that don't meet this bar must not be used for privileged access.

## Step 1: Define PAW provisioning/lifecycle

Define which devices are PAWs, how they are created, enrolled, managed, and prevented from being used before they are ready.

### Create a PAW device group

This group will contain PAW devices, and is used for:

- Enrollment targeting
- Hardening profiles
- Compliance evaluation
- Conditional Access enforcement in a later phase.

Create as follows:

1. In the [Microsoft Entra Admin Center](https://entra.microsoft.com), navigate to **Microsoft Entra ID** &gt; **Groups** &gt; **New group**.
2. Configure the group settings, and then select **Create**.

    - **Group type**: Security
    - **Group name**: Secure Workstation Devices
    - **Membership type**: Dynamic Devices
3. Select **Add dynamic query** and add a rule with this syntax: *device.devicePhysicalIds -any \_ -contains "[OrderID]: PAW"*
4. Select **Save** &gt; **Create**.

Devices enrolled with the PAW Autopilot group tag are identified by the PAW dynamic device rule and treated as privileged access workstations.

### Control who can create PAWs

Ensure PAWs are enrolled intentionally and securely.

- Restrict who can join devices to Microsoft Entra ID.
- Require MFA to join devices.
- Remove automatic local administrator rights on join.

1. In the Entra Admin Center, navigate to **Devices** &gt; **Device settings**.
2. In **Users may join devices to Microsoft Entra ID** &gt; **Selected**, select **Secure Workstation Users**.
3. In **Require Multi-Factor Auth to join devices**, select **Yes**.
4. In **Additional local administrator on Microsoft Entra joined devices**, select **None**.
5. Save the settings.

With this in place, only PAW users can enroll PAWs, MFA is required, and no PAW user becomes a local administrator by default.

### Manage PAWs from first boot

PAWs must be managed from first boot. Unmanaged devices cannot be trusted for privileged access.

- Configure Microsoft Entra ID to automatically enroll devices into Intune.
- Ensure all PAWs are MDM‑managed immediately after join.
- Restrict device enrollment to approved platforms.

1. Open **Microsoft Entra ID** &gt; **Mobility (MDM and MAM)** &gt; **Microsoft Intune**.
2. Set **MDM user scope** to **All** and save.
3. Configure **Enrollment restrictions**:
    - Allow Windows device enrollment.
    - Block or restrict personally owned devices.

PAWs are always managed, never unmanaged.

### Provision PAWs consistently

Use Windows Autopilot to enforce consistent, repeatable PAW provisioning that ensures PAWs start in a known-good state.

Create a dedicated Autopilot deployment profile, and assign it to the PAW device group.

1. In the Microsoft Intune Admin Center, go to **Devices** &gt; **Windows** &gt; **Windows enrollment** &gt; **Deployment profiles**.
2. Select **Create profile**and create a profile with the following settings:
    - **Name**: Secure workstation deployment profile
    - **Convert all targeted devices to Autopilot**: Yes
    - **Deployment mode**: Self‑deploying
    - **User account type**: Standard
3. Select **Create**.

### Prevent PAWs from use before hardening

Prevent PAWs from being used before they’re fully hardened. This prevents early exposure during setup.

- Configure an Enrollment Status Page (ESP)
- Block device use until all required profiles and applications install
- Assign ESP to PAW devices

1. In the Microsoft Intune Admin Center, go to **Devices** &gt; **Windows** &gt; **Windows enrollment** &gt; **Enrollment status**.
2. Select **Create profile** and create a profile with the following settings:

    - **Show app and profile installation progress**: Yes
    - **Block device use until all apps and profiles are installed**: Yes
3. Assign to **Secure Workstation Devices** and select **Create**.

### Ongoing lifecycle operations

1. To recover and rebuild PAWs:

    - Reset / reprovision PAWs via Autopilot when compromised.
    - Treat PAWs as replaceable, not manually repaired.
2. To identity and track PAWs use:

    - Device group membership
    - Autopilot registration

With these processes in place, PAWs are explicitly identifiable, centrally managed devices that can be inventoried, reviewed, and safely wiped and re‑provisioned through Autopilot if compromised.

## Step 2: Harden PAWs

Harden Privileged Access Workstations (PAWs) to present a clean, low‑risk device signal. Hardening controls include reducing the attack surface, enforcing patching, and producing Defender risk/compliance signals.

Conditional Access and monitoring controls rely on this posture to enforce privileged access decisions.

These controls assume PAWs meet the required hardware security prerequisites defined earlier.

### Configure Windows Update rings

PAWs must be patched quickly and predictably. Delays or user‑controlled deferrals undermine device trust.

1. In the Microsoft Intune Admin Center, go to **Devices** &gt; **Windows** &gt; **Software updates** &gt; **Windows Update rings**.
2. Select **Create profile**.
3. Configure the following settings:

    - Name: PAW – Windows Update Ring
    - Quality update deferral (days): 3
    - Feature update deferral (days): 3
    - Automatic update behavior: Auto install and reboot without end‑user control
    - Block user from pausing updates: Block
    - Set deadline for pending restarts: 3 days
4. In **Assignments**, assign to secure workstation devices.
5. Create the profile.

After you complete this procedure, PAWs stay patched with minimal exposure window and no user bypass.

### Onboard to Defender for Endpoint

Conditional Access and compliance depend on Defender risk signals. Without Defender for Endpoint, device trust is incomplete.

1. In the Microsoft Intune Admin Center, go to **Endpoint security** &gt; **Microsoft Defender for Endpoint**.
2. Set **Connect Microsoft Defender for Endpoint to Intune** to **On**.
3. Select **Save**.
4. Refresh in Intune to confirm the connection.

### Create an onboarding profile

1. In the Microsoft Intune Admin Center, go to **Endpoint security** &gt; **Endpoint detection and response**.
2. Select **Create profile** and configure the following settings:

    - Platform: Windows 10 and later
    - Profile type: Endpoint detection and response
    - Name: PAW - Defender for Endpoint
3. In **Configuration settings** enable **Sample sharing for all files**.
4. Assign to the **Secure Workstation Devices** group.
5. Create the profile.

After you configure the procedure, PAWs emit device risk, malware, and EDR telemetry used by Conditional Access and SecOps.

### Enforce firewall and network restrictions

Most PAW compromise paths are outbound. Restricting egress is critical.

1. In the Microsoft Intune Admin Center, go to **Endpoint security** &gt; **Firewall**.
2. Create an **Endpoint protection** profile.
3. Configure outbound firewall rules to allow only required services such as DNS, DHCP, NTP, and approved administrative and management endpoints. Block unnecessary outbound traffic by default.
4. Assign to**Secure Workstation Devices**.

After you configure the procedure, PAWs can reach only administrative endpoints required for management tasks.