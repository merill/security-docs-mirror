---
layout: Conceptual
title: Secure DevOps environments for Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/secure-devops-environments-zero-trust
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn best practices to secure DevOps environments and prevent compromise of developer boxes, release pipelines, and production data.
ms.subservice: zero-trust
ms.topic: best-practice
ms.date: 2025-02-24T00:00:00.0000000Z
ms.custom: template-concept
ms.service: security
ms.collection:
- zerotrust-dev
locale: en-us
document_id: e87e34ed-dd76-370e-c962-f677ad630994
document_version_independent_id: e87e34ed-dd76-370e-c962-f677ad630994
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/secure-devops-environments-zero-trust.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/secure-devops-environments-zero-trust
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/secure-devops-environments-zero-trust.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43093068-2dda-408b-b3fe-dfd705c84f78
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e453d60d-ba7e-43bc-8028-ec38e6b62512
platformId: 57f30165-68c2-a7d0-9306-ef496c6e99c4
---

# Secure DevOps environments for Zero Trust | Microsoft Learn

Securing DevOps environments is no longer a choice for developers. Bad actors are shifting left so you must implement [Zero Trust principles](../zero-trust-overview) that include verify explicitly, use least privilege access, and assume breach in DevOps environments.

This article describes best practices for securing your DevOps environments with a Zero Trust approach for preventing bad actors from compromising developer boxes, infecting release pipelines with malicious scripts, and gaining access to production data via test environments.

Our [Securing Enterprise DevOps Environments](https://aka.ms/SecureDevEnvironmentsEbook) eBook features the following visualization of the developer, DevOps platform, and application environments along with the potential security threats for each.

[![Diagram illustrates DevOps environments and security threats.](../media/develop/secure-devops-environments/diagram-enterprise-devops-overview-inline.png)](../media/develop/secure-devops-environments/diagram-enterprise-devops-overview-expanded.png#lightbox)

Notice in the previous diagram how connections between environments and to external integrations expand the threat landscape. These connections can increase opportunities for bad actors to compromise the system.

Bad actors stretch across enterprises to compromise DevOps environments, gain access, and unlock new dangers. Attacks go beyond the typical breadth of cybersecurity breaches to inject malicious code, assume powerful developer identities, and steal production code.

As companies transition to ubiquitous, work-from-anywhere scenarios, they must strengthen device security. Cybersecurity offices might lack consistent understanding of where and how developers secure and build code. Bad actors take advantage of these weaknesses with remote connection hacks and developer identity thefts.

DevOps tools are key entry points for bad actors, from pipeline automation to code validation and code repositories. If bad actors infect code before it reaches production systems, in most cases, it can pass through cybersecurity checkpoints. To prevent compromise, ensure that your development teams are engaged with peer reviews, security checks with IDE security plugins, secure coding standards, and branch review.

Cybersecurity teams aim to prevent bad actors from sieging production environments. However, environments now include supply chain tools and products. Open source tool breach can heighten global cybersecurity risks.

Learn more about developer-specific articles with the following **DevSecOps** articles in the [Developer guidance](overview) section of the [Zero Trust Guidance Center](../):

- [Secure the DevOps platform environment](secure-devops-platform-environment-zero-trust) helps you to implement Zero Trust principles in your DevOps platform environment and highlights best practices for secret and certificate management.
- [Secure the developer environment](secure-dev-environment-zero-trust) helps you to implement Zero Trust principles in your development environments with best practices for least privilege, branch security, and trusting tools, extensions, and integrations.
- [Embed Zero Trust security into your developer workflow](embed-zero-trust-dev-workflow) helps you to innovate quickly and securely.