---
layout: Conceptual
title: Microsoft Zero Trust Workshop - Devices | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/workshop-zero-trust-devices
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Learn about the Devices pillar in the Microsoft Zero Trust Workshop
ms.date: 2026-11-12T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: d1045259-ac6d-8681-fe99-837111c5e69f
document_version_independent_id: d1045259-ac6d-8681-fe99-837111c5e69f
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/workshop-zero-trust-devices.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/workshop-zero-trust-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/workshop-zero-trust-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 5a644632-ff43-3243-a9a6-439c65d3d800
---

# Microsoft Zero Trust Workshop - Devices | Microsoft Learn

In a Zero Trust model, devices are a critical part of the trust evaluation. Even when a user's identity is validated, access decisions also depend on the security health, configuration, and risk state of the device. The Devices workshop pillar focuses on managing and protecting devices, assessing their security posture, and protecting organizational data accessed from unmanaged devices.

Devices workshop pillar guidance focuses on managing device lifecycle and enrollment, enforcing compliance and configuration standards, protecting endpoints from threats, reducing attack surface, and integrating device risk into access and security operations.

The Devices workshop pillar corresponds to the Endpoints technology defined in the [Microsoft Security Adoption Framework (SAF)](deploy/overview).

## Workshop implementation

The Devices workshop covers the implementation areas summarized in the table.

Available capabilities and prerequisites vary by operating system, device enrollment state, supported app, and licensing. Select the controls that apply to your device and access scenarios.

| **Area** | **Details** |
| --- | --- |
| **Manage device enrollment and lifecycle** | Enroll and provision devices using modern management (such as Microsoft Intune and Windows Autopilot).Standardize device onboarding and configuration to establish a known security baseline and keep devices consistently managed throughout their lifecycle.Define retirement and offboarding procedures, including removal of organizational data and appropriate wipe actions based on device ownership and platform support. |
| **Define and enforce device compliance posture** | Define device compliance policies based on supported security requirements, such as minimum OS version, encryption, and device risk level.Reassess device compliance as devices check in and supported state-change evaluations occur. Define actions for noncompliance and any applicable grace periods.When using compliance-based Conditional Access, configure devices with no assigned compliance policy to be marked as noncompliant. |
| **Enforce posture-based access with Conditional Access** | Use Microsoft Entra Conditional Access to require compliant devices for resources that need device-level assurance. Integrate Microsoft Defender for Endpoint device risk with Intune compliance policies so that risk contributes to the compliance status evaluated by Conditional Access.Apply differentiated access controls for managed, unmanaged, and high-risk devices. Where organizational policy permits unmanaged-device access, use supported app protection or restricted browser sessions instead of requiring full device enrollment. |
| **Secure device configuration and baseline standards** | Apply security baselines and configuration policies to enforce consistent hardening across devices.Standardize settings for operating systems, security controls, and management configurations to reduce misconfigurations. |
| **Reduce device attack surface and restrict risky behaviors** | Implement controls such as Attack Surface Reduction (ASR) rules, exploit protection, and application control (for example, App Control for Business (formerly Windows Defender Application Control)) to limit exploitable behaviors and restrict untrusted or unauthorized code execution. |
| **Protect endpoints with threat detection and response** | Deploy endpoint protection and detection capabilities to identify, investigate, and remediate threats on devices.Generate risk signals from endpoint protection systems and use them to drive remediation and inform access decisions. |
| **Implement least-privilege and administrative control** | Minimize local administrator access and enforce least privilege on devices.Apply role-based access control and administrative segmentation to ensure only authorized personnel can manage device configurations and management policies. |
| **Secure access for unmanaged and BYOD** | Enable secure access from personally owned (bring your own device, or BYOD) and other unmanaged devices using Intune app protection policies, a mobile application management (MAM) capability, browser-based controls, or virtualization solutions.Protect organizational data in supported apps without requiring full device enrollment. Use the Microsoft Entra Conditional Access Require app protection policy grant control for supported apps and platforms.For supported browser-access scenarios, use application-enforced restrictions or Microsoft Defender for Cloud Apps session controls to restrict actions such as downloading organizational data. |
| **Keep devices up-to-date** | Regularly apply operating system and application updates to ensure devices are protected against known vulnerabilities.Enforce update compliance and automate patching processes to maintain a consistent and secure device baseline across the environment. |
| **Support secure access for diverse device scenarios** | Enable secure use of personally owned, shared, and frontline devices.Apply appropriate controls such as app protection policies, shared device modes, or session-based protections according to platform, app support, ownership, and user-sharing requirements. Use device management where appropriate, and select supported app or session protections for scenarios where full device management is not feasible. |
| **Integrate device signals into security operations (SecOps)** | Stream device health, compliance, and threat signals into centralized monitoring and response workflows.Correlate these signals with identity, data, and network telemetry to detect and respond to device-based threats. |

## Assess device posture

The Zero Trust Assessment tool can assess your tenant's device-management and security configuration against supported best-practice checks. For assessment scope and capabilities, see the Zero Trust Assessment [overview](/en-us/security/zero-trust/assessment/overview).