---
layout: Conceptual
title: Privileged access | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-concept-privileged-access
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Get a primer overview of privileged access
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: ae528416-b5da-ec38-951d-c6b654de401d
document_version_independent_id: ae528416-b5da-ec38-951d-c6b654de401d
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-concept-privileged-access.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-concept-privileged-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-concept-privileged-access.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 1203f8b6-d16a-1194-f526-a2c3d256c2b6
---

# Privileged access | Microsoft Learn

Privileged access sits across the [enterprise access model](security-adoption-discipline-identity-access-enterprise-model) and provides the only administrative path to the control plane. It defines who can configure systems, manage identities, enforce security, and ultimately shape the organization’s technology environment.

In modern enterprises, a relatively small number of identities - administrators, service accounts, and control plane roles have power and access to most business assets. These identities can:

- Modify access controls
- Change system configurations
- Access sensitive data
- Disable or bypass security protections

Attackers recognize this. Rather than attacking every system individually, they focus on:

- Stealing credentials.
- Escalating privileges.
- Moving laterally toward high-value roles.

Once privileged access is obtained, the attacker can operate with speed and scale.

This is why modern security models treat privileged access differently:

- **It must be explicitly controlled**. For example, define privileged roles and onboarding through identity governance and privileged identity management (PIM), requiring approval and time-bound elevation instead of permanent role assignments.
- **It must be isolated from normal activity**. For example, use separate administrative accounts and dedicated privileged access devices (PAWs) so privileged actions never occur from standard user sessions or unmanaged devices.
- **It must be continuously monitored**. For example, send privileged sign-ins, role activations, and policy changes to monitoring tools like Microsoft Sentinel to detect unusual usage patterns and trigger alerts or automated response.
- **It must be agreed that privileged access is a primary target of compromise**. For example, protect all privileged accounts with strong multifactor authentication (MFA), no standing access, and break-glass account controls, assuming attackers attempt credential theft and privilege escalation.

Protecting privileged access requires looking beyond just roles and accounts to understanding all components that have privileged access. This includes:

- The identity control plane.
- Privileged devices, apps, and interfaces.
- Intermediary systems such as VPNs, PIM, and privileged access management (PAM) systems.

Together, these define how control is exercised—and how it must be protected.

The following graphic illustrates the potential attack surface for privileged access compromise.

[![Diagram showing the potential attack surface for privileged access.](media/security-adoption-discipline-privileged-access-attack.png)](media/security-adoption-discipline-privileged-access-attack.png#lightbox)

## Identity control plane

The identity control plane is the layer that defines and governs who can hold privileged roles and how those privileges are assigned, elevated, and revoked across the organization. In a privileged access context, it includes privileged identities, role assignments, and approved elevation paths, forming the foundation that all other controls depend on.

Securing the identity control plane ensures that privilege is explicit, time-bound, strongly authenticated, and auditable, preventing unauthorized or uncontrolled access to the systems that ultimately control the entire environment.

The following diagram show that the control plane is centrally managed in cloud services (Microsoft Entra ID, Intune, Defender for Endpoint) and can only be accessed through a privileged access workstation (PAW), enforcing isolation, control, and secure administration of all privileged operations.

[![Diagram showing Microsoft technologies that protect the identity control plane.](media/security-adoption-discipline-access-privileged-control.png)](media/security-adoption-discipline-access-privileged-control.png#lightbox)

### Control plane roles

Microsoft Entra ID has roles and permissions that are identified as privileged.

These roles and permissions can be used to delegate management of directory resources to other users, modify credentials, authentication or authorization policies, or access restricted data. Privileged role assignments can lead to elevation of privilege if not used in a secure and intended manner.

- Review [privileged Microsoft Entra roles](/en-us/entra/identity/role-based-access-control/permissions-reference).
- [Learn more](/en-us/entra/identity/role-based-access-control/privileged-roles-permissions) about viewing and using privileged roles.

## Privileged access workstations

A Privileged Access Workstation (PAW) is a dedicated, hardened device used only for performing administrative tasks. It's separate from regular user devices and is tightly secured to reduce the risk of credential theft, malware, or lateral movement. PAWs enforce key protections such as:

- Strong authentication (for example, Windows Hello for Business)
- Device hardening (Credential Guard, Device Guard, Exploit Guard, AppLocker)
- Restricted usage (no general browsing or productivity activity)

The goal is to ensure that privileged credentials and actions are never exposed to untrusted environments.

The following diagram shows how the PAW in the only trusted access point into the control plane.

[![Diagram showing Microsoft technologies that protect privileged devices.](media/security-adoption-discipline-access-enterprise-privileged-device.png)](media/security-adoption-discipline-access-enterprise-privileged-device.png#lightbox)

As shown in the diagram, all administrative actions flow through the PAW and are controlled as summarized in the table.

| **Control** | **Implementation** |
| --- | --- |
| **Explicitly controlled** | Administrative access is granted only through policy-based identity controls, requiring strong authentication and approved, time-bound elevation. Device state must also meet compliance requirements before access is allowed. |
| **Isolated from normal activity** | Privileged operations are restricted to a dedicated PAW device with tightly controlled usage and connectivity. The PAW isn't used for general productivity, with restricted internet access and secure remote connectivity to sensitive systems. |
| **Continuously monitored** | All identity activity, device state, and endpoint behavior are continuously collected and analyzed, enabling detection of abnormal privileged activity and rapid response. |
| **Assumed to be targeted** | The environment is hardened and continuously validated, assuming attackers target privileged access. Devices are kept up to date, secure bootstrapping is enforced. |