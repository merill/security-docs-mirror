---
layout: Conceptual
title: Phishing investigation playbook | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/security-operations-playbook-phishing
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Understand how to use a phishing investigation playbook.
ms.date: 2026-05-24T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: 363383a6-852c-5d2d-126b-6e23b8800dbf
document_version_independent_id: 363383a6-852c-5d2d-126b-6e23b8800dbf
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/security-operations-playbook-phishing.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/security-operations-playbook-phishing
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/security-operations-playbook-phishing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: 339ba37c-0523-f7ce-ba6b-d7a80b1a9f22
---

# Phishing investigation playbook | Microsoft Learn

This article demonstrates a phishing investigation playbook. It is part of the incident response guidance for the Security Operations (SecOps) discipline in the **Microsoft Security Adoption Framework (SAF)**.

This playbook is intended for all roles responsible for building or executing incident response playbooks, including SecOps analysts, incident responders, identity administrators, and IT operations staff.

Phishing attacks are one of the most common initial access techniques used by adversaries. A successful phishing attack can lead to credential compromise, malware execution, data exfiltration, and lateral movement across identity, email, and endpoint environments.

The guidance in this article describes what to investigate and why. Product‑specific examples (such as Microsoft Defender XDR or Microsoft Sentinel) are provided as reference implementations.

## Before you start

Before starting a phishing investigation, ensure that the following baseline readiness requirements are in place. These prerequisites should be completed before an incident occurs as part of incident response planning.

| **Area** | **Requirement** | **Details** |
| --- | --- | --- |
| **Account information** | Have at least one identifier for the suspected target user | Identifiers can be: user principal name (UPN), email address, or username/alias.This information is required to correlate email activity, sign‑ins, and downstream actions. |
| **Microsoft 365 audit/logging** | Mailbox auditing should be enabled organization‑wide to ensure that mailbox access and actions are recorded. | Verify that mailbox auditing on by default is enabled by running the following command in Exchange Online PowerShell: *Get-OrganizationConfig | Format-List AuditDisable*/. A value of False indicates that mailbox auditing is enabled for all mailboxes. |
| **Microsoft 365 audit/logging** | Message trace logs are required to identify the original phishing message, deliver status, all recipients, message routing details. | Message trace is available in [Exchange Admin Center](https://admin.exchange.microsoft.com/#/messagetrace), Microsoft Defender portal (Email & collaboration &gt; Exchange message trace).To work effectively with message trace data, investigators must be able to retrieve and interpret Message‑ID values, which are obtained from raw email headers. |
| **Microsoft 365 audit/logging** | Unified audit logs are required to review user and administrative activity across Microsoft 365 workloads. | Ensure investigators can search the unified audit log to review actions such as mailbox access, mail item actions, administrative changes, and sign‑in–related events. |
| **Microsoft Entra logs** | Microsoft Entra ID sign‑in and audit logs are retained for a limited period (30 or 90 days, depending on licensing). | To support investigations, historical analysis, and post‑incident review, export logs to a long‑term repository such as Microsoft Sentinel, Azure Monitor, or a third-party SIEM. |
| **Permissions** | Ensure investigators have sufficient permissions to access required data without over‑privileging accounts. | Microsoft Entra ID: minimum recommended role is Security Reader.Defender portal and Microsoft Compliance portal: Security Reader.These roles provide read‑only access to email, alerts, and audit data. |
| **Endpoint visibility** | Microsoft Defender for Endpoint | If Defender for Endpoint is installed, use it to:- Validate whether users interacted with phishing content.- Identify payload execution.- Correlate endpoint activity with email events. |
| **Hardware** | A system capable of running PowerShell. |  |
| **Software** | These PowerShell modules are commonly used during phishing investigations | Microsoft Graph PowerShell SDKExchange Online PowerShell moduleMicrosoft Entra Incident Response PowerShell module.Ensure all modules are installed and kept up to date. |

## Workflow

The phishing investigation workflow follows these high‑level stages:

1. Identify and confirm the phishing message.
2. Scope the impact and affected users.
3. Assess user interaction and credential exposure.
4. Identify downstream activity.
5. Contain the threat and prevent recurrence

This workflow helps responders move from detection to containment without skipping critical validation steps.

## What to check

Use this checklist as a quality gate during the investigation.

- Identify the phishing email and original Message‑ID
- Determine all recipients and delivery status
- Identify whether users interacted with the message
- Assess credential compromise or malware execution
- Identify lateral or follow‑on activity
- Remove malicious messages from mailboxes
- Reset or secure impacted accounts
- Improve detections and prevention controls

## Investigation steps

### Step 1: Identify the phishing message

1. Obtain the suspected phishing email.
2. Extract the Message‑ID from the email headers.
3. Use message trace to determine:

    - When the message was received
    - Which users received it
    - Whether it was delivered, blocked, or quarantined

### Step 2: Scope affected users

1. Identify all recipients of the message
2. Confirm whether the message bypassed filters
3. Determine whether similar messages were sent using variants of the same campaign

### Step 3: Assess user interaction

1. For each affected user, determine whether they:

    - Opened the email
    - Clicked links
    - Opened attachments
    - Submitted credentials

    Correlate email activity with:

    - Microsoft Entra sign‑in logs
    - Audit logs
    - Endpoint activity (if available)

### Step 4: Identify follow‑on activity

1. If credentials may have been exposed, investigate for:

    - Suspicious sign‑ins
    - Password spray or brute force activity
    - OAuth consent grants
    - Token abuse
    - Unusual mailbox or collaboration activity
2. If attachments were opened, validate whether any malware executed on endpoints.

### Step 5: Contain and remediate

Based on findings:

1. Remove phishing messages from all mailboxesDisable or reset.
2. compromised accounts.
3. Revoke active sessions and tokens.
4. Block malicious senders, domains, and URLs.
5. Isolate or remediate impacted endpoints.

### Step 6: Recovery

After containment, focus on restoring normal operations and reducing recurrence risk.

Recovery actions may include:

- Enforcing credential resets and multifactor authentication
- Reviewing mailbox rules and forwarding settings
- Improving email filtering and anti‑phishing policies
- Updating detections and alerts
- Updating or refining phishing response playbooks