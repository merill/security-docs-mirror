---
layout: Conceptual
title: AI/ML Pivots to the Security Development Lifecycle Bug Bar | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/engineering/bug-bar-aiml
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: Machine Learning Bug Triage Guidance
ms.date: 2024-09-25T00:00:00.0000000Z
ms.topic: best-practice
ms.service: security
locale: en-us
document_id: 7679c932-33a9-af81-9140-4ddf60adc218
document_version_independent_id: 7679c932-33a9-af81-9140-4ddf60adc218
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/engineering/Bug-Bar-aiml.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: engineering/bug-bar-aiml
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/engineering/Bug-Bar-aiml.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d6f38669-3d05-40f2-afd8-e49f7dd20884
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/55265cca-de9b-48dc-a77a-9047cc39a575
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
2PlusCloud:
- Power
- Azure
- M365
__autotagging_hash:
- F20922A5A0F3C65B3592F13C44D2AC6ED421B960A4B0A9E25EC2A0CAA8CC5125
platformId: e47e2bf5-49f4-dfd2-52de-d456cc43c92d
---

# AI/ML Pivots to the Security Development Lifecycle Bug Bar | Microsoft Learn

By Andrew Marshall, Jugal Parikh, Emre Kiciman, and Ram Shankar Siva Kumar

November 2019

This article is a deliverable of the Microsoft AETHER Engineering Practices for AI Working Group. This article functions as a supplement to the existing SDL bug bar used to triage traditional security vulnerabilities. It's intended to be used as a reference for the triage of AI/ML-related security issues. The [Vulnerability Severity Classification](https://www.microsoft.com/msrc/aibugbar) for AI Systems (published by Microsoft Security Response Center), defines common vulnerability types and severity levels for systems involving AI.

This guidance is organized around the Adversarial Machine Learning Threat Taxonomy, created by Ram Shankar Siva Kumar, David O'Brien, Kendra Albert, Salome Viljoen, and Jeffrey Snover, and titled [Failure Modes in Machine Learning](/en-us/security/failure-modes-in-machine-learning). While the research this content is based on addresses both intentional/malicious and accidental behaviors in ML failure modes, this bug bar supplement focuses entirely on intentional/malicious behaviors that would result in a security incident and/or deployment of a fix.

| Threat | Description/Business Risks/Examples |
| --- | --- |
| Data Poisoning | Corrupting the training data - The end goal of the attacker is to contaminate the machine model generated *in the training phase*, so that predictions on new data are modified in the testing phase.<br><br>In targeted poisoning attacks, the attacker wants to misclassify specific examples to cause specific actions to be taken or omitted.<br><br>Submitting AV software as malware to force its misclassification as malicious and eliminate the use of targeted AV software on client systems. <br><br>A company scrapes a well-known and trusted website for futures data to train their models. The data provider's website is then compromised via SQL Injection attack. The attacker can poison the dataset at-will and the model being trained has no notion that the data is tainted. |
| Model Stealing | Recreation of the underlying model by legitimately querying it. The functionality of the new model is same as that of the underlying model. Once the model is recreated, it can be inverted to recover feature information or make inferences on training data. <br><br>Equation solving – For a model that returns class probabilities via API output, an attacker can craft queries to determine unknown variables in a model.<br><br>Path Finding – an attack that exploits API particularities to extract the "decisions" taken by a tree when classifying an input.<br><br>Transferability attack - An adversary can train a local model—possibly by issuing prediction queries to the targeted model - and use it to craft adversarial examples that transfer to the target model. If your model is extracted and discovered vulnerable to a type of adversarial input, new attacks against your production-deployed model can be developed entirely offline by the attacker who extracted a copy of your model.<br><br>In settings where an ML model serves to detect adversarial behavior, such as identification of spam, malware classification, and network anomaly detection, model extraction can facilitate evasion attacks |
| Model Inversion | The private features used in machine learning models can be recovered. This includes reconstructing private training data that the attacker doesn't have access to. This is accomplished by finding the input which maximizes the confidence level returned, subject to the classification matching the target.<br><br>Example: Reconstruction of facial recognition data from guessed or known names and API access to query the model. |
| Adversarial Example in Physical Domain | These examples can manifest in the physical domain, like a self-driving car tricked into running a stop sign because of a certain color of light (the adversarial input) being shone on the stop sign, forcing the image recognition system to no longer see the stop sign as a stop sign. |
| Attack ML Supply Chain | Owing to large resources (data + computation) required to train algorithms, the current practice is to reuse models trained by large corporations and modify them slightly for task at hand (e.g: ResNet is a popular image recognition model from Microsoft).<br><br>These models are curated in a Model Zoo (Caffe hosts popular image recognition models).<br><br>In this attack, the adversary attacks the models hosted in Caffe, thereby poisoning the well for anyone else. |
| Backdoored Algorithm from Malicious ML Provider | Compromising the underlying algorithm<br><br>A malicious ML-as-a-Service provider presents a backdoored algorithm, wherein the private training data is recovered. This provides the attacker with the ability to reconstruct sensitive data such as faces and texts, given only the model. |
| Neural Net Reprogramming | With a specially crafted query from an attacker, ML systems can be reprogrammed to a task that deviates from the creator's original intent<br><br>Weak access controls on a facial recognition API enabling 3^rd^ parties to incorporate into apps designed to harm users, such as a deep fakes generator.<br><br>This is an abuse/account takedown scenario |
| Adversarial Perturbation | In perturbation-style attacks, the attacker stealthily modifies the query to get a desired response from a *production-deployed model*. This is a breach of model input integrity which leads to fuzzing-style attacks where the end result isn't necessarily an access violation or EOP. Instead it compromises the model's classification performance.<br><br>This can be manifested by trolls using certain target words in a way that the AI bans them, effectively denying service to legitimate users with a name matching a "banned" word.<br><br>Forcing benign emails to be classified as spam or causing a malicious example to go undetected. These are also known as model evasion or mimicry attacks.<br><br>Attacker can craft inputs to reduce the confidence level of correct classification, especially in high-consequence scenarios. This can also take the form of a large number of false positives meant to overwhelm administrators or monitoring systems with fraudulent alerts indistinguishable from legitimate alerts. |
| Membership Inference | Infer individual membership in a group used to train a model<br><br>Ex: prediction of surgical procedures based on age/gender/hospital |