---
layout: Conceptual
title: 'AI Security Training: Case Studies and Tools for Generative AI | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/security/ai-red-team/training
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: None
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Secure generative AI systems with Microsoft's AI Red Teaming 101 series. Learn vulnerabilities, attack techniques, and defense strategies. Gain hands-on experience.
ms.service: security
ms.subservice: ai-red-team
ms.topic: how-to
ms.date: 2025-07-09T00:00:00.0000000Z
ms.reviewer: sayoung
ms.custom:
- ai-gen-docs-bap
- ai-gen-title
- ai-seo-date:07/03/2025
- ai-gen-description
locale: en-us
document_id: 7af9f7c9-8726-db0d-dea9-adffa1d144cc
document_version_independent_id: 7af9f7c9-8726-db0d-dea9-adffa1d144cc
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/ai-red-team/training.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: ai-red-team/training
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/ai-red-team/training.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 854bef90-35f9-cef3-9cd5-d5a3354e8889
---

# AI Security Training: Case Studies and Tools for Generative AI | Microsoft Learn

Microsoft's **AI Red Teaming 101 training series** helps professionals secure generative AI systems against emerging threats. This series dives into vulnerabilities, attack techniques, and defense strategies, providing actionable insights and hands-on experience. Whether you're a security expert, machine learning engineer, or business leader, you'll gain practical knowledge through real-world case studies, modular episodes, and automated testing tools. Explore topics like prompt injection attacks, multi-turn adversarial techniques, and scalable defense methods to enhance your AI security expertise.

## Why watch this training series

Get actionable advice to help identify, exploit, and defend against critical vulnerabilities in generative AI systems. Learn best practices, techniques, and guidance based on real-world lessons from Microsoft’s AI Red Team.

## Who should watch this training series

The training series is useful for security teams, ML engineers, AI practitioners, and business leaders working with AI. It primarily focuses on:

- Security professionals: learn about AI-specific attack vectors and defense strategies.
- ML practitioners and AI engineers: add security testing to AI development workflows.
- Enterprise and security architects: create secure AI systems and explore emerging threats.

Tip

The AI Red Teaming 101 videos are modular, so you can jump to any section of interest or start at the beginning and watch them all. [Download the slides](https://download.microsoft.com/download/5b4d1684-798f-4040-ae80-eb8e1a1b3411/AI-Red-Teaming-101.pptx), and follow along at your own pace.

## What's in the training series

The training series gives guidance on understanding generative AI vulnerabilities, executing attack techniques, and implementing defensive measures. The workshop includes hands-on demonstrations, real-world case studies, and automated testing tools based on Microsoft's production AI security practices.

Tip

All episodes include [hands-on demonstrations and access to Microsoft's red teaming labs](https://aka.ms/AIRTlabs) to gain practical experience.

### Introduction and Fundamentals

**Episode 1: What is AI red teaming?** - Introduction to AI red teaming fundamentals, key risks in generative AI, and the mission of Microsoft's AI red team

**Episode 2: How Generative AI Models Work** - Understanding model architecture, training stages, and why these models create unique security risks

### Part A - Core Attack Techniques

**Episode 3: Direct prompt injection explained** - How attackers manipulate model behavior by injecting malicious instructions, including real-world case studies such as the $1 SUV chatbot attack

**Episode 4: Indirect Prompt Injection Explained** - Stealthy attacks where malicious instructions are hidden in external data sources like emails, websites, or databases

**Episode 5: Single-Turn Attacks** - Advanced prompt engineering techniques including persona hacking, emotional manipulation, and filter evasion with encoding tricks

**Episode 6: Multi-Turn Attacks** - techniques like Skeleton Key and Crescendo that gradually steer models toward bypassing safety protections

### Part B - Defense and Mitigation

**Episode 7: Defending against attacks** - Mitigation strategies and guardrail techniques, including Microsoft's spotlighting defense methods (delimiting, data marking, and encoding)

### Part C - Automation and Scale

**Episode 8: Automating AI red teaming with PyRIT** - Introduction to Microsoft's open-source tool for automating and scaling adversarial testing of generative AI systems, the Python Risk Identification Tool (PyRIT)

**Episode 9: Automating Single-Turn Attacks** - Hands-on demonstration of configuring datasets, targets, and scoring logic to send many prompts at once using PyRIT

**Episode 10: Automating Multi-Turn Attacks** - Advanced automation techniques for multi-turn conversations, including adversarial model conversations and testing both text and image generation systems

## What you learn

After completing this training series, you'll understand:

- Fundamentals of AI red teaming versus traditional red teaming approaches
- Core vulnerabilities in generative AI systems, like prompt injection and model misalignment
- Attack techniques, from simple prompt manipulation to sophisticated multi-turn adversarial strategies
- Defense strategies, including proven mitigation techniques like Microsoft's Spotlighting methods
- Automation tools for scaling red teaming efforts using PyRIT and other open-source tools
- Real-world applications with hands-on labs and case studies from Microsoft's production AI security work