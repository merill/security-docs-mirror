---
layout: Conceptual
title: Get started quickly configuring ransomware prevention so you can stop ransomware cybercriminals from targeting your organization. | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/ransomware/protect-against-ransomware
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: pauloliveria
author: poliveria
manager: orspodek
ms.service: security
ms.subservice: ''
ms.date: 2024-10-13T00:00:00.0000000Z
ms.topic: best-practice
ms.collection:
- msftsolution-ransomware
ms.custom: cx-rw
ms.localizationpriority: medium
description: Learn how to protect against ransomware cybercriminals by quickly configuring ransomware prevention for your organization. Get started today!
locale: en-us
document_id: f35fa6ab-c338-8707-bfb9-21e9ac99b44b
document_version_independent_id: f35fa6ab-c338-8707-bfb9-21e9ac99b44b
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/ransomware/protect-against-ransomware.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: ransomware/protect-against-ransomware
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/ransomware/protect-against-ransomware.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/aebdc4a3-c54b-4eea-94e3-663d5e166f57
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/1baec8e6-ab38-4b56-bb59-f6282d94f311
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: ee88b5c5-665c-97f6-2761-708dd742f99d
---

# Get started quickly configuring ransomware prevention so you can stop ransomware cybercriminals from targeting your organization. | Microsoft Learn

Ransomware is a cyber attack type that cybercriminals use to extort organizations large and small.

Understanding how to protect against ransomware attacks and minimized damage is an important part of safeguarding your company. This article gives you practical guidance for how to quickly configure ransomware protection.

The guidance is organized into steps, starting with the most urgent actions to take.

Bookmark this page as your starting point for the steps.

Important

**Read the ransomware prevention series, and make your organization hard to cyber attack.**

- [Have a recovery plan](protect-against-ransomware-phase1)
- [A plan to limit the harm done](protect-against-ransomware-phase2)
- [Make it hard to get in](protect-against-ransomware-phase3)

Note

What is ransomware? See the ransomware definition [here](/en-us/security/ransomware/human-operated-ransomware).

## Important information about this article

Note

The order of these steps is designed to ensure you reduce risk *as fast as possible*, and built on an assumption of great urgency that overrides normal security and IT priorities, in order to avoid or mitigate devastating attacks.

![The three steps to protecting against ransomware attacks](media/protect-against-ransomware/protect-against-ransomware-phases.png)

**It is important to note** this ransomware prevention guidance is structured as steps you should follow in the order shown. To best adapt this guidance to your situation:

1. **Stick with the recommended priorities**

    Use the steps as a starting plan for what to do first, next, and later, so you get the most impactful elements first. These recommendations are prioritized using the [Zero Trust](https://www.microsoft.com/security/business/zero-trust) principle of *assuming a breach*. This forces you to focus on minimizing business risk by assuming the attackers can successfully gain access to your environment through one or more methods.
2. **Be proactive and flexible (but *don’t skip important tasks*)**

    Scan through the implementation checklists for all sections of all three steps to see if there are any areas and tasks that you can quickly *complete earlier*. In other words, things you can do faster because you already have access to a cloud service that hasn’t been used but could be quickly and easily configured. As you look over the whole plan, be careful that *these later areas and tasks don’t delay completion* of critically important areas like backups and privileged access!
3. **Do some items in parallel**

    Trying to do everything at once can be overwhelming, but some items can naturally be done in parallel. Staff on different teams can be working on tasks at the same time (for example, backup team, endpoint team, identity team), while also driving for completion of the steps in priority order.

The items in the implementation checklists are in the recommended order of prioritization, not a technical dependency order.

Use the checklists to confirm and modify your existing configuration as needed and in a way that works in your organization. For example, in the most important backup element, you back up some systems, but they might not be offline or immutable, you might not test the full enterprise restore procedures, or you might not have backups of critical business systems or critical IT systems like Active Directory Domain Services (AD DS) domain controllers.

Note

See the [3 steps to prevent and recover from ransomware (September 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/) Microsoft security blog post for an additional summary of this process.

## Set up your system to prevent ransomware right now

The steps are:

### Step 1. Prepare your ransomware recovery plan

This step is designed to [minimize the monetary incentive from ransomware attackers](protect-against-ransomware-phase1) by making it:

- Much harder to access and disrupt systems or encrypt or damage key organization data.
- Easier for your organization to recover from an attack without paying the ransom.

Note

While restoring many or all enterprise systems is a difficult endeavor, the alternative of paying an attacker for a recovery key they might not deliver, and using tools written by the attackers to try to recover systems and data.

### Step 2. Limit the scope of ransomware damage

Make the attackers work a lot harder to [gain access to multiple business critical systems through privileged access roles](protect-against-ransomware-phase2). Limiting the attacker’s ability to get privileged access makes it much harder to profit off of an attack on your organization, making it more likely they'll give up and go elsewhere.

### Step 3. Make it hard for cybercriminals to get in

This last set of tasks is important to raise friction for entry but will take time to complete as part of a larger security journey. The goal of this step is to make the attackers' work *much* harder as they try to [obtain access to your on-premises or cloud infrastructures](protect-against-ransomware-phase3) at the various common points of entry. There are many tasks, so it's important to prioritize your work here based on how fast you can accomplish these with your current resources.

While many of these will be familiar and easy to quickly accomplish, it's critically important that ***your work on step 3 should not slow down your progress on steps 1 and 2***.

Tip

For Azure-specific guidance on preparing for, detecting, and responding to ransomware attacks in cloud environments, see [Ransomware protection in Azure](/en-us/azure/security/fundamentals/ransomware-protection).

## Ransomware protection at a glance

You can also see an overview of the steps and their implementation checklists as levels of protection against ransomware attackers with the [Protect your organization from ransomware poster](https://download.microsoft.com/download/5/e/3/5e37cbff-9a7a-45b2-8b95-6d3cc5426301/protect-your-organization-from-ransomware.pdf).

[![The &quot;Protect your organization from ransomware&quot; poster](media/human-operated-ransomware/ransomware-poster-thumbnail.png#lightbox)](https://download.microsoft.com/download/5/e/3/5e37cbff-9a7a-45b2-8b95-6d3cc5426301/protect-your-organization-from-ransomware.pdf)

Prioritize ransomware mitigation at the macro level. [Configure your organization's environment to protect against ransomware](protect-against-ransomware).