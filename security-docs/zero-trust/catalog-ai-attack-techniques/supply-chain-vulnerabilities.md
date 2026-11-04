---
layout: Conceptual
title: 6. Supply Chain Vulnerabilities (OSS) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/catalog-ai-attack-techniques/supply-chain-vulnerabilities
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: ridive
author: richarddiver-ms
description: Covers how poisoned open-source models, libraries, or packages can introduce backdoors into AI systems, and the vetting controls needed to mitigate them.
ms.date: 2026-07-28T00:00:00.0000000Z
ms.custom: msecd-doc-authoring-1012
ms.topic: concept-article
ms.service: security
ms.subservice: zero-trust
locale: en-us
document_id: 5d408af0-db80-24ad-4216-bb67209257a6
document_version_independent_id: 5d408af0-db80-24ad-4216-bb67209257a6
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/catalog-ai-attack-techniques/supply-chain-vulnerabilities.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/catalog-ai-attack-techniques/supply-chain-vulnerabilities
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/catalog-ai-attack-techniques/supply-chain-vulnerabilities.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2624a017-7337-44fa-9494-a407bb0e59fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a438284e-c3c3-4c36-ab0b-aa7c244b912c
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6bcb9b77-20a6-64fb-7e86-a80f623daccd
---

# 6. Supply Chain Vulnerabilities (OSS) | Microsoft Learn

One notable case in 2023 was the **Mithril Security demo**: researchers uploaded a slightly modified LLM to a public repository (Hugging Face) that appeared normal but was **trained to output a specific falsehood when asked about a target phrase**. This poisoned model, if adopted by an unsuspecting organization, would deliver that misinformation convincingly while otherwise behaving normally – a supply chain backdoor.

In another case, a cybersecurity firm demonstrated how a popular open-source ML library could be altered to exfiltrate environment variables (like API keys) during model training – a risk if organizations update to the compromised version. These scenarios mirror classic software supply-chain attacks (like **typosquatting** or malicious npm/PyPI packages) but for AI: for example, a fake “torch++” Python package could quietly install a spyware along with purported AI functionality.

The prevalence of open-source in AI—models, tools, libraries, datasets, and fine-tuning assets—means enterprises must treat AI components with the same caution as any code or data from external sources. This section should also be read alongside “4. Training Data Poisoning,” which is another form of AI supply-chain attack: instead of compromising a library or model package, the adversary compromises the data used to train, fine-tune, evaluate, or ground the model.

## What happens in this scenario

*Supply chain attacks* in AI target the **third-party components that an LLM or AI system relies on**, rather than the core model itself. Modern AI applications often incorporate open-source models, libraries, pre-trained weights, and external datasets. In a supply chain attack:

1. An adversary compromises one of these dependencies *before it’s integrated* into your system.
2. For instance, an enterprise data science team might download a pre-trained model from a public repository to fine-tune for internal use – if an attacker had tampered with that model (e.g. inserted malicious weights or backdoors), the enterprise AI comes pre-infected.
3. Similarly, an attacker could contribute malicious code to an open-source LLM library or a data preprocessing package; when the enterprise updates to the new version, a hidden payload might exfiltrate data or subtly alter the AI’s decisions.

> 
> Essentially, the attacker targets the *less-guarded upstream components*, knowing that once they’re within the AI system, they operate with trust.

## Why this technique is effective

It leverages the fact that organizations often **trust external components** and may not scrutinize them as closely as in-house software. LLMs and AI workflows often depend on:

- **Pre-trained models** (from model hubs or vendors)
- **Open-source libraries** (for data handling, model building, etc.)
- **Third-party datasets** (for training or evaluation) Attackers can insert exploits at any of these points. For example, a poisoned model on a public model hub might function normally for most queries but trigger malicious behavior for a specific input (as in a backdoored LLM scenario). If an enterprise downloads this model, the backdoor is now inside their firewall. Because these components are complex and often treated as “trusted,” typical security scans might miss issues (a malicious model won’t flag an antivirus the way a typical virus would). The effectiveness is amplified by the difficulty in interpreting model internals – a model isn’t code that can be easily inspected; you can’t easily “read” weights to spot a backdoor. Thus, a poisoned or malicious dependency can slip through traditional security review.

## Recommended controls

- **Pin and verify versions**: Treat models and datasets as critical artifacts. Download them from official or reputable sources and verify checksums or digital signatures (if provided) to ensure they haven’t been tampered with. Avoid unsourced model files or data from unknown origins.
- **Supplier security diligence**: Just as you vet software vendors, scrutinize the security of model providers. Prefer providers who offer transparency (e.g., model cards detailing training data and known limitations) and provide signed model files. If using open-source, check that the project is active and community-vetted.
- **Isolate and scan new models**: When incorporating a third-party model, test it in a sandbox environment first. Perform extensive validation: Does it behave as expected across a range of inputs? (For example, test both normal queries and some adversarial ones to see if they exhibit strange outputs.) Use tools to scan for embedded malicious content – e.g., *transformer interpretability* methods might detect if a model is unexpectedly biased toward a certain output.
- **Monitor model behavior in production**: Even after deployment, keep an eye on model outputs. Use canaries or periodic checks for known triggers. If a model suddenly starts behaving oddly (e.g., providing a specific unexpected answer when a certain query is used), that could indicate hidden manipulation. Be prepared to roll back to a previous trusted model version.
- **Secure model repositories**: If your organization maintains a private model store or a fork of an open model, protect it like you would source code. Restrict who can push updates, require code reviews for changes (in the case of code-based model definitions), and use integrity scanning for model files.

## Technologies to consider

- **Model and data repositories**: Utilize enterprise-grade artifact storage (e.g., **Azure Artifacts** or **Azure Machine Learning Model Registry**) which supports versioning and checksum verification for models and datasets.
- **Dependency scanning**: Apply software composition analysis tools (like **GitHub Dependabot**, **Azure Defender for open-source packages**) to your AI project environment. These can alert on known vulnerabilities in libraries (although they might not catch a poisoned model, they can catch malicious code in dependencies or outdated packages).
- **AI security frameworks**: Keep abreast of projects like **MITRE ATLAS** (Adversarial Threat Landscape for AI) and **NIST’s AI Risk Management Framework**, which provide guidelines for securing the AI supply chain. Tools that implement these frameworks can be integrated into your governance.
- **Controlled environment for third-party AI**: Consider using containerization or dedicated cloud endpoints for third-party models. For example, **Azure Container Instances** or **Kubernetes** can run external models in isolation from core data, limiting damage if a model is later found to be malicious.

## OWASP Top 10 mapping

[OWASP Top 10 for LLM and Generative AI](https://genai.owasp.org/llm-top-10/) (2025)

This scenario maps to **LLM01: Prompt Injection**, where attackers exploit weaknesses in upstream open‑source components to introduce malicious instructions the model later consumes; **LLM03: Supply Chain**, since compromised packages, libraries, datasets, or plugins allow adversaries to insert harmful behavior deep within the AI pipeline; and **LLM04: Data and Model Poisoning**, as tampered dependencies can silently modify training data or model artifacts, enabling hidden backdoors or corrupted outputs.

## MITRE ATLAS mapping

This scenario maps broadly to MITRE ATLAS behaviors around supply-chain compromise, dependency risk, and malicious or back-doored AI components.

**[MITRE ATLAS Techniques](https://atlas.mitre.org/techniques) (Attack):** The attack primarily reflects supply-chain compromise: untrusted models, libraries, datasets, or plugins introduce malicious behavior or hidden dependencies into the AI system.

- AML.T0010 AI Supply Chain Compromise (.001 AI Software, .002 Data, .003 Model, .005 AI Agent Tool)
- AML.T0011 User Execution
- AML.T0016 Obtain Capabilities

**[MITRE ATLAS Mitigations](https://atlas.mitre.org/mitigations) (Defense):** Prioritize SBOMs, component vetting, version pinning, signature verification, sandboxing, and incident response playbooks.

- AML.M0011 Restrict Library Loading
- AML.M0013 Code Signing
- AML.M0014 Verify AI Artifacts
- AML.M0016 Vulnerability Scanning
- AML.M0023 AI Bill of Materials