---
layout: Conceptual
title: Embed Zero Trust security into your developer workflow | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/embed-zero-trust-dev-workflow
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn how to develop your apps using Zero Trust principles so that you can innovate quickly and securely.
ms.subservice: zero-trust
ms.topic: best-practice
ms.service: security
ms.date: 2025-04-18T00:00:00.0000000Z
ms.custom: template-concept
ms.collection:
- zerotrust-dev
locale: en-us
document_id: 7d6c1886-8c5b-0be2-ab9c-0fa5e5e2369e
document_version_independent_id: 7d6c1886-8c5b-0be2-ab9c-0fa5e5e2369e
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/embed-zero-trust-dev-workflow.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/embed-zero-trust-dev-workflow
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/embed-zero-trust-dev-workflow.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9bdc1705-9b40-49d6-8377-caa0b71fda66
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/686ed158-d915-41e9-9760-efa46ba88f6d
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f887ecbe-ff50-9f49-b37d-0791b03064d8
---

# Embed Zero Trust security into your developer workflow | Microsoft Learn

As a developer, you need to feel confident and secure to move at speed. The need for security starts as soon as you clone your code. In this article, you learn how to [develop using Zero Trust principles](overview) so that you can innovate quickly and securely. The [Zero Trust security strategy](../zero-trust-overview) and approach for designing and implementing applications comprises these principles:

- **Verify explicitly**. Always authenticate and authorize based on all available data points.
- **Use least privilege access.** Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection.
- **Assume breach.** Minimize blast radius and segment access. Verify end-to-end encryption and use analytics to get visibility, drive threat detection, and improve defenses.

Embedding security into your workflow helps you to:

- Pinpoint security vulnerabilities more quickly.
- Provide more secure developer tooling.
- Create connections to improve collaboration between security and development teams.

## Innovate and secure your workflow as you create code

Microsoft's unified solution, illustrated in the following diagram, bridges across DevOps and SecOps teams to help you accelerate and secure code-to-cloud development.

[!\[Diagram shows the technologies that comprise the unified code-to-cloud development solution.\](../media/develop/embed-zero-trust-dev-workflow/diagram-code-to-cloud-dev-solution-inline.png)
 Diagram title: Microsoft provides a unified solution. Diagram subtitle: to help you accelerate and secure code-to-cloud development. Listed technologies: Visual Studio Code, GitHub Codespaces, Visual Studio, Microsoft DevBox, GitHub Advanced Security, Azure Pipelines, GitHub Actions, Microsoft Entra ID, Azure.](../media/develop/embed-zero-trust-dev-workflow/diagram-code-to-cloud-dev-solution-expanded.png#lightbox)

Our solution to safeguard DevOps relies on two main components: providing developers with tooling to power innovation and securing the developer workflow as developers create code. Watch the [Accelerate and secure your code to cloud development](https://mybuild.microsoft.com/sessions/84ff7d8d-64da-4a5e-9c84-92f7b6387225) session from [Microsoft Build 2022](https://mybuild.microsoft.com/) to learn how these components can secure your development environment.

Implement the following best practices that work together in Azure and GitHub to secure your development solution.

- Because security starts when developers clone code, [enable DevSecOps with Azure and GitHub](/en-us/devops/devsecops/enable-devsecops-azure-github) to bridge across DevOps and SecOps teams and secure your development environments.
- Provide flexible and powerful developer tools for any developer, language, and stack with [Visual Studio](/en-us/visualstudio/) and [Visual Studio Code](https://code.visualstudio.com/docs).
- Simplify new developer onboarding and collaboration with an entire development lifecycle tool in the cloud using [GitHub Codespaces](https://docs.github.com/codespaces) and [Microsoft Dev Box](/en-us/azure/dev-box/).
- Include built-in intellectual property protection for code that you no longer disperse into multiple locations. Help your teams collaborate, develop, automate, and deploy code wherever they want with [GitHub Actions](https://docs.github.com/actions) and [Azure Pipelines](/en-us/azure/devops/pipelines/security/overview).
- Get security guidance and continuous security feedback within the developer workflow with code scanning, secret scanning, and dependency review using [GitHub Advanced Security](https://docs.github.com/get-started/learning-about-github/about-github-advanced-security).
- Instill zero-trust security throughout your organization using [identity management services](/en-us/entra/workload-id/workload-identity-federation) in Microsoft Entra ID.

## Fit Zero Trust security into your development lifecycle

From precommit to commit through deploy then operate and monitor, you need security solutions in place throughout all of your development lifecycle stages.

### Precommit stage

- Threat modeling
- IDE security plug-in
- Precommit hooks
- Secure coding standards
- Peer review

Eighty-five percent of code defects appear during the development precommitment phase, mostly due to human error. Focus on security before you commit your code by writing your code in Visual Studio Code, Visual Studio, or GitHub Codespaces to identify vulnerabilities and secure code. Use peer reviews to encourage secure coding practices.

### Commit (CI) stage

- Static code analysis
- Security unit tests
- Dependency management
- Credential scanning

During the commit stage, use extensive security methods to review your code (including static code analysis) and scan your code as you check it into your source control. Use credential scanning (also known as secret scanning or token scanning) to expose credentials that you might inadvertently introduce into the codebase. Catch insecure dependencies before you introduce them to your environment with dependency review.

### Deploy (CD) stage

- Infrastructure as code (IaC) scanning
- Dynamic security scanning
- Cloud configuration checks
- Security acceptance tests

During the deploy stage, look at the overall health of your codebase and perform high-level security scanning to identify risks. Perform cloud configuration checks, infrastructures code checks, and security acceptance tests to ensure alignment with organizational security goals.

### Operate and monitor stage

- Continuous monitoring
- Threat intelligence
- Blameless postmortems

During the operate and monitor phase, use continuous monitoring and threat intelligence to mitigate overall dependency vulnerabilities that you might inherit over time. Perform postmortems to take away lessons learned and continue iterating through your DevOps cycle.

## Implement dependency, code, and secret scanning

To make securing code easier for developers, use native and automated capabilities to provide continuous feedback with continuous security features throughout your development lifecycle. Provide overall security to developers and communities with GitHub Advanced Security dependency scanning, code scanning, and secret scanning.

### Dependency scanning

- Integrated review of dependencies
- Alerts and security updates

Get risk levels of dependencies and automated fixes to vulnerable dependencies in your codebase with continuous [dependency scanning](https://docs.github.com/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review). As a continuous process, it nudges your developers in the right direction in a friendly and nonobtrusive way.

### Code scanning

- Extensible framework for code scanning
- Integrated within the developer workflow
- Backed by industry leading CodeQL engine

Implement [code scanning](https://docs.github.com/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning) as you generate code with no other steps to run at separate locations. Ease fixes early in your development lifecycle by viewing scanning results in your familiar GitHub user experience.

### Secret scanning

- Scan for leaked secrets in public and private repos
- Partnership with 40+ providers
- Push protection
    - Move from remediation to prevention
    - Check for high-confidence secrets
    - Enable protection with one select

Scan your code for hardcoded credentials and tokens with [secret scanning](https://docs.github.com/code-security/secret-scanning/about-secret-scanning). Push protection scans for secrets and tokens before you push to your codebase. Check for high-confidence secrets as developers push code, blocking the push when GitHub identifies a secret.

## Manage and secure workload identities

- Lifecycle management
- Access governance
- Secure adaptive access

Get visibility into the activity of your [workload identities](/en-us/entra/workload-id/workload-identities-overview) and enable periodic cleanup. Determine who owns workload identities and how you keep this information up to date across organization changes. Track when you have last used workload identities, when you last issued tokens and when tokens expire.

To mitigate the potential for leaked secrets and credentials, periodically conduct access reviews. Require users to review their workload identities and remove unnecessary access privileges. Have users report overprivileged and underutilized access privileges. Discuss how you protect workload identities from breach. Enable conditional access to ensure that access is originating from expected resources.

## Secure identities with GitHub OIDC and Microsoft Entra Workload ID Federation

To further secure your organization, use [GitHub OpenID Connect](https://docs.github.com/actions/deployment/security-hardening-your-deployments/about-security-hardening-with-openid-connect) (OIDC) with Microsoft Entra [Workload Identity Federation](/en-us/entra/workload-id/workload-identity-federation) and minimize the need to store and access secrets. Securely manage Azure server principal secrets and other long-lived cloud credentials resources to minimize service downtime due to expired credentials. Integrate with developer platforms, like GitHub Actions, to securely build your apps.

Our recommended Workload Identity Federation workflow, illustrated in the following diagram, comprises six steps.

[![Diagram illustrates Workload Identity Federation workflow steps.](../media/develop/embed-zero-trust-dev-workflow/diagram-workload-identity-federation-inline.png)](../media/develop/embed-zero-trust-dev-workflow/diagram-workload-identity-federation-expanded.png#lightbox)

1. Set up trust in Microsoft Entra ID and request a token.
2. Configure the GitHub workflow to allow actions to get the token.
3. GitHub workflow sends a request to Azure ID.
4. Microsoft Entra ID validates the trust on the application and fetches the keys to validate the token.
5. Microsoft Entra ID accesses and issues the token.
6. The deploy action uses the Microsoft Entra access token to deploy to resources in Azure.

Watch April Edwards, Senior Cloud Advocate and DevOps Practice Lead, demo the Workload Identity Federation workflow. The demonstration begins at the 19:14 mark in the Microsoft Build 2022 session, [Accelerate and secure your code to cloud development](https://www.youtube.com/watch?v=1fMdA3pSBaY&amp;t=1154s).