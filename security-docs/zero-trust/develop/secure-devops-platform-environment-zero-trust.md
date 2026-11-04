---
layout: Conceptual
title: Secure the DevOps platform environment for Zero Trust | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/zero-trust/develop/secure-devops-platform-environment-zero-trust
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: jricketts
author: janicericketts
description: Learn best practices for secret and certificate management so that DevOps team members can secure their DevOps platform environments.
ms.subservice: zero-trust
ms.topic: best-practice
ms.service: security
ms.date: 2025-02-24T00:00:00.0000000Z
ms.collection:
- zerotrust-dev
ms.custom:
- template-concept
- sfi-image-nochange
locale: en-us
document_id: f48ef3c7-3ba5-ae09-e01d-3e52032606dc
document_version_independent_id: f48ef3c7-3ba5-ae09-e01d-3e52032606dc
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/zero-trust/develop/secure-devops-platform-environment-zero-trust.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: zero-trust/develop/secure-devops-platform-environment-zero-trust
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/zero-trust/develop/secure-devops-platform-environment-zero-trust.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9bdc1705-9b40-49d6-8377-caa0b71fda66
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/062d60c9-ee0f-402e-a046-b4e67c3572d6
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/686ed158-d915-41e9-9760-efa46ba88f6d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/17d3b3f6-a66e-4c69-9774-14a73c38e669
platformId: 39efe638-2781-348c-c99d-85edffd1f2ec
---

# Secure the DevOps platform environment for Zero Trust | Microsoft Learn

This article helps you, as a DevOps team member, to implement the [Zero Trust principle](../zero-trust-overview) of least privilege and secure the DevOps platform environment. It features content from our [Securing Enterprise DevOps Environments](https://aka.ms/SecureDevEnvironmentsEbook) eBook and highlights best practices for secret and certificate management.

Modern enterprises rely on DevOps platforms for deployment, including pipelines and production environments that developers require to be productive. In the past, application security methods didn't consider the increased attack surface that present day pipelines and production environments expose. As bad actors shift left and target upstream tools, you need innovative approaches to secure your DevOps platform environments.

In the following diagram, notice that the DevOps platform environment connects to the application environment and to [continuous integration and continuous delivery](/en-us/azure/devops/pipelines/get-started/key-pipelines-concepts) (CI/CD) pipeline extensions.

[![Diagram illustrates DevOps platform environments and security threats.](../media/develop/secure-devops-environments/diagram-devops-platform-environment-overview-inline.png)](../media/develop/secure-devops-environments/diagram-devops-platform-environment-overview-expanded.png#lightbox)

CI/CD pipeline extensions present bad actors with opportunities to engage in privilege escalations from the application environment. Extensions and integrations increase attack surface vulnerabilities. It's critical to defend against malware intrusion threats.

## How and why bad actors target pipelines

Pipelines and production environments might be independent of standard application security practices and processes. They typically require high-level access credentials that can provide deep and meaningful access to bad actors.

While bad actors find new ways to compromise systems, the most common vulnerabilities for pipelines include:

- Extracting runtime variables and argument injection.
- Scripts that retrieve service principles or credentials from pipelines.
- Misconfigured personal access tokens that allow anyone with the key to access the DevOps platform environment.
- Vulnerabilities and misconfigurations in integrated tools that require access to the code (often read-only, but sometimes write access). Integrated tools can include test frameworks, static application security testing (SAST), and dynamic application security testing (DAST).

## Best practices for secret and certificate management

Avoiding a catastrophic breach can be as simple as effective secret management. The following diagram illustrates an example of effective secret, password, access token, and certificate management.

[![Diagram illustrates secret and certificate management.](../media/develop/secure-devops-environments/diagram-secret-management-example-inline.png)](../media/develop/secure-devops-environments/diagram-secret-management-example-expanded.png#lightbox)

As shown in the previous diagram, the developer starts a build for a customer request. GitHub then starts a runner with a Vault App Role's role ID and secret ID. The Trusted Entity periodically requests a new secret ID from the Vault and gets the GitHub Secret secret ID from GitHub. The Vault uses the GitHub Secrets role ID and secret ID to sign in and get code-signing assets. The Runner customizes and code-signs the mobile app.

The following best practices help you to build a secure setup that minimizes secret and parameter exposure.

- **Provide secure storage for secrets and certificates at each application lifecycle stage.** Always develop as if it's an open-source project. Ensure that teams are storing secrets in key vaults rather than in the code or on team environments. Use the [Azure Key Vault](/en-us/azure/key-vault/general/basic-concepts) cloud service for securely storing and accessing secrets.
- **Configure Azure to trust GitHub's OIDC as a federated identity.** OpenID Connect (OIDC) allows your GitHub Actions workflows to [access resources in Azure](https://docs.github.com/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-azure) without needing to store the Azure credentials as long-lived GitHub secrets.

## More best practices for DevOps environment security

To help defend against security incidents, review the following best practices to fortify your DevOps platform environments. Find a detailed discussion of these recommendations in our [Securing Enterprise DevOps Environments](https://aka.ms/SecureDevEnvironmentsEbook) eBook.

- **Equip every DevOps platform environment with audit trails.**[Review audit logs to track](https://docs.github.com/enterprise-cloud@latest/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization) who gained access, what change occurred, and the date/time for any active system. Specifically include DevOps platforms with CI/CD pipelines that flow into production. Audit trails for DevOps tools provide robust ways to remediate threats quicker, find, and alert on suspicious activities to possible breaches or vulnerabilities, and find potential data or privilege misuse. Ensure granular control and audit trails are available across each environment.
- **Secure the software supply chain.** With every library you bring into your codebase, you expand the software supply chain and inherit dependencies from each open-source project or tool. With caution, remove unnecessary libraries and open-source components to reduce the attack surface of your software supply chain.
- **Automate Infrastructure-as-Code (IaC) template scans.** With [IaC environments](/en-us/azure/cloud-adoption-framework/ready/considerations/infrastructure-as-code), it's easy to scan for misconfigurations, compliance audits, and policies issues. Implementing compliance checks and access controls raises the security posture of your entire infrastructure. Verify the security of tool integrations that fulfill automation system requirements.
- **Automate approval workflows.** For any approval workflow to push code into production, certain automatic or manual checks must confirm security, business value, status, and quality of each request. These checks function as a gate between development and production to prevent denial-of-service attacks and bad actors injecting code into production environments without flagging or triggering an alert.
- **Allow only verified DevOps tool integrations.** As in developer environments, DevOps tools come with extensions and integrations to make the DevOps team efficient and secure. Confirm that verified integrations require the least privilege possible to execute their work. Implement least privilege access when possible and ensure the right level of read/write permissions. Learn how to [disable or limit GitHub Actions for your organization.](https://docs.github.com/organizations/managing-organization-settings/disabling-or-limiting-github-actions-for-your-organization)