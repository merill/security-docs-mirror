---
layout: Conceptual
title: Prepare for ransomware attacks with a backup and recovery plan | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/ransomware/protect-against-ransomware-phase1
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: pauloliveria
author: poliveria
manager: orspodek
ms.service: security
ms.subservice: ''
keywords: ransomware, human-operated ransomware, human operated ransomware, HumOR, extortion attack, ransomware attack, encryption, cryptovirology, extortionware, malicious encryption
ms.date: 2024-10-16T00:00:00.0000000Z
ms.topic: best-practice
ms.collection:
- msftsolution-ransomware
ms.custom: cx-rw
description: Prepare your organization so that you can recover from cybercriminal ransomware attacks without having to pay the ransom.
locale: en-us
document_id: babe4cad-5226-1215-f92e-8ee6c9de4dbd
document_version_independent_id: babe4cad-5226-1215-f92e-8ee6c9de4dbd
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/ransomware/protect-against-ransomware-phase1.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: ransomware/protect-against-ransomware-phase1
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/ransomware/protect-against-ransomware-phase1.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/aebdc4a3-c54b-4eea-94e3-663d5e166f57
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1baec8e6-ab38-4b56-bb59-f6282d94f311
platformId: ad8ed88f-02e7-b492-1c8c-312b29197735
---

# Prepare for ransomware attacks with a backup and recovery plan | Microsoft Learn

*Always* prepare a ransomware attack recovery plan, starting with an alternative to ransom payment to help avoid losing access to your data.

Important

**Read the whole ransomware prevention series, and make your organization *hard to ransomware attack*.**

- [Have a recovery plan](protect-against-ransomware-phase1)
- [A plan to limit the harm done](protect-against-ransomware-phase2)
- [Make it hard to get in](protect-against-ransomware-phase3)

Ransomware actors in control of your organization have many ways to pressure you into paying. The demands primarily focus on two categories:

- **Pay a ransom to regain access**

    Threat actors demand payment under the threat that they *won’t give you back access to your systems and data*. This is usually done by encrypting your systems and data and demanding payment for the decryption key.

    Important

    Paying the ransom won't guarantee restored access to your data.

> 
> Financially motivated cybercriminals (and often relatively amateur operators who are using a toolkit provided by someone else), might keep both the payment locked files. There is no legal guarantee that they will provide a key that decrypts 100% of your systems and data, or even provide a key at all. The process to decrypt these systems uses homegrown attack tools, an often clumsy and manual process.

- **Pay to avoid disclosure**

    Threat actors demand payment in exchange for not releasing sensitive or embarrassing data to the dark web (other criminals) or the general public.

To avoid being forced into payment (the profitable situation for threat actors), the most immediate and effective action you can take is to make sure your organization can restore your entire enterprise from immutable storage, which neither the cybercriminal nor you can modify.

Identifying the most sensitive assets and protecting them at a higher level of assurance is also critically important but is a longer and more challenging process to execute. We don’t want you to hold up other areas in phases 1 or 2, but we recommend you get the process started by bringing together business, IT, and security stakeholders to ask and answer questions like:

- What business assets would be the most damaging if compromised? For example, for which assets would our business leadership be willing to pay an extortion demand if cybercriminals controlled them?
- How do these business assets translate to IT assets (such as files, applications, databases, servers, and control systems)?
- How can we protect or isolate these assets so that threat actors with access to the general IT environment can’t access them?

## Secure backups

You must ensure that critical systems and their data are backed up and backups are protected against deliberate erasure or encryption by a threat actor.

Attacks on your backups focus on crippling your organization’s ability to respond without paying, frequently targeting backups and key documentation required for recovery to force you into paying extortion demands.

Most organizations don’t protect backup and restoration procedures against this level of intentional targeting.

[Backup and restore plan to protect against ransomware](/en-us/azure/security/fundamentals/backup-plan-to-protect-against-ransomware) addresses what to do before an attack to protect your critical business systems and during an attack to ensure a rapid recovery of your business operations.

Learn how to [restore your OneDrive files](https://support.microsoft.com/office/ransomware-detection-and-recovering-your-files-0d90ec50-6bfd-40f4-acc7-b8c12c73637f) in the event of a ransomware attack.

### Program and project member accountabilities

This table describes the overall protection of your data from ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Operations or CIO |  | Executive sponsorship |
| Program lead from [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) infrastructure |  | Drive results and cross-team collaboration |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Infrastructure/Backup | Enable Infrastructure backup |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Productivity / End User | Enable OneDrive Backup |
|  | [Security Architecture](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) | Advise on configuration and standards |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |
|  |  |  |

### Implementation checklist

Apply these best practices to secure your backup infrastructure.

| Done | Task | Description |
| --- | --- | --- |
|  | Backup all critical data automatically on a regular schedule. | Allows you to recover data up to the last backup. |
|  | Regularly exercise your business continuity/disaster recovery (BC/DR) plan. | Ensures rapid recovery of business operations by treating a ransomware or extortion attack with the same importance as a natural disaster. |
|  | Protect backups against deliberate erasure and encryption:  - Strong Protection – Require out of band steps (MFA or PIN) before modifying online backups (such as [Azure Backup](/en-us/azure/backup/backup-azure-security-feature#prevent-attacks)).  - Strongest Protection – Store backups in online immutable storage (such as [Azure Blob](/en-us/azure/storage/blobs/storage-blob-immutable-storage)) and/or fully offline or off-site. | Backups accessible by cybercriminals can be rendered unusable for business recovery. Implement stronger security to access backups and the inability to change the data stored in backups. |
|  | Protect supporting documents required for recovery such as restoration procedure documents, your configuration management database (CMDB), and network diagrams. | Threat actors deliberately target these resources because it impacts your ability to recover. Make sure they survive a ransomware attack. |

### Implementation results and timelines

Within 30 days, ensure that Mean Time to Recover (MTTR) meets your BC/DR goal, as measured during simulations and real-world operations.

## Data protection

You must implement data protection to ensure rapid and reliable recovery from a ransomware attack and to block some attack techniques.

Ransomware extortion and destructive attacks only work when all legitimate access to data and systems is lost. Ensuring that threat actors cannot remove your ability to resume operations without payment will protect your business and undermine the monetary incentive for attacking your organization.

### Program and project member accountabilities

This table describes the overall protection of your organization data from ransomware in terms of a sponsorship/program management/project management hierarchy to determine and drive results.

| Lead | Implementor | Accountability |
| --- | --- | --- |
| [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Operations or CIO |  | Executive sponsorship |
| Program lead from [Data Security](/en-us/azure/cloud-adoption-framework/organize/cloud-security-data-security) |  | Drive results and cross-team collaboration |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Productivity / End User | Implement changes to Microsoft 365 tenant for OneDrive and Protected Folders |
|  | [Central IT](/en-us/azure/cloud-adoption-framework/organize/central-it) Infrastructure/Backup | Enable Infrastructure backup |
|  | Business / Application | Identify critical business assets |
|  | [Security Architecture](/en-us/azure/cloud-adoption-framework/organize/cloud-security-architecture) | Advise on configuration and standards |
|  | [Security Policy and Standards](/en-us/azure/cloud-adoption-framework/organize/cloud-security-policy-standards) | Update standards and policy documents |
|  | [Security Compliance Management](/en-us/azure/cloud-adoption-framework/organize/cloud-security-compliance-management) | Monitor to ensure compliance |
|  | User Education Team | Ensure guidance for users reflects policy updates |
|  |  |  |

### Implementation checklist

Apply these best practices to protect your organization data.

| Done | Task | Description |
| --- | --- | --- |
|  | Migrate your organization to the cloud:  - Move user data to cloud solutions like OneDrive/SharePoint to take advantage of [versioning and recycle bin capabilities](/en-us/microsoft-365/enterprise/microsoft-365-malware-and-ransomware-protection#sharepoint-online-and-onedrive-for-business-protection-against-ransomware).  - Educate users on how to [recover their files](https://support.microsoft.com/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15) by themselves to reduce delays and cost of recovery. | User data in the Microsoft cloud can be protected by built-in security and data management features. |
|  | Designate [Protected Folders](/en-us/windows/security/threat-protection/microsoft-defender-atp/controlled-folders). | Makes it more difficult for unauthorized applications to modify the data in these folders. |
|  | Review your permissions:  - Discover broad write/delete permissions on file shares, SharePoint, and other solutions. Broad is defined as many users having write/delete permissions for business-critical data.  - Reduce broad permissions for critical data locations while meeting business collaboration requirements.  - Audit and monitor critical data locations to ensure broad permissions don’t reappear. | Reduces risk from ransomware activities that rely on broad access. |
|  |  |  |