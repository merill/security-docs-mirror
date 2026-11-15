---
layout: Conceptual
title: Map CIS Controls and CIS Benchmarks to SAF | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/saf/framework-mappings/cis-controls-benchmarks
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: mas
author: MarkSimos
description: Use CIS Controls v8.1 and CIS Benchmarks with Microsoft Security Adoption Framework roles, disciplines, technologies, and implementation guidance.
ms.date: 2026-11-09T00:00:00.0000000Z
ms.service: security
ms.subservice: zero-trust
ms.topic: concept-article
locale: en-us
document_id: ef93d960-afdb-4e5d-a922-224f732952ae
document_version_independent_id: ef93d960-afdb-4e5d-a922-224f732952ae
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/saf/framework-mappings/cis-controls-benchmarks.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: ../../zero-trust/toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: saf/framework-mappings/cis-controls-benchmarks
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/saf/framework-mappings/cis-controls-benchmarks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: f75d7a00-c9a5-b605-c6de-be84ef02f9cf
---

# Map CIS Controls and CIS Benchmarks to SAF | Microsoft Learn

The Center for Internet Security (CIS) publishes two related but different forms of guidance:

- **CIS Controls v8.1** provide a prioritized set of cybersecurity practices and 153 Safeguards. They help organizations decide **what security work to perform**.
- **CIS Benchmarks** provide prescriptive, consensus-based configuration recommendations for specific technologies and product families. They help technology owners decide **how to configure an in-scope technology securely**.

The Microsoft Security Adoption Framework (SAF) helps organizations assign the work to appropriate roles and disciplines, apply it across technologies, and connect it to architecture and implementation guidance.

Important

CIS remains the authoritative source for CIS Controls, Safeguards, Implementation Groups, and Benchmarks. This mapping doesn't replace CIS guidance, certify a configuration, or demonstrate that a CIS outcome has been achieved.

## Use CIS Controls and Benchmarks for different decisions

| Guidance | Primary question | Unit of work | SAF use |
| --- | --- | --- | --- |
| **CIS Controls v8.1** | Which cybersecurity practices and Safeguards should the organization implement and prioritize? | Organization-level Controls and Safeguards | Connect outcomes to business context, security disciplines, accountable and responsible roles, technologies, and measurable improvement work. |
| **CIS Benchmarks** | How should a particular technology or service be securely configured? | Technology-specific configuration recommendations | Establish an approved security baseline, assign implementation to technology owners, validate compatibility, manage exceptions, and monitor configuration drift. |

## Map the 18 CIS Controls to SAF work and role actions

Role names follow [Security roles and responsibilities in SAF](/en-us/security/zero-trust/security-adoption-roles).

| CIS Control v8.1 | Primary SAF work | Typical role actions |
| --- | --- | --- |
| **1. Inventory and Control of Enterprise Assets** | Security Posture Management; Infrastructure Security; OT/IoT Security | Product Owners identify business ownership and criticality. Infrastructure/Platform, User Endpoint, Network, and OT/ICS roles maintain inventories and lifecycle state. Security Posture Management measures coverage, unmanaged assets, and remediation. |
| **2. Inventory and Control of Software Assets** | Security Posture Management; Infrastructure Security; Development Security | Technical engineering and operations roles maintain authorized software inventories and enforcement. Software/Application Architects and development roles identify required software and dependencies. Security Posture Management identifies unauthorized or unsupported software and tracks remediation. |
| **3. Data Protection** | Data Security; Access and Identity; Security Architecture | Data Officer/Data Governance and Product Owners identify data value, use, and obligations. Data Architects and Access Architects define classification, access, protection, retention, and handling patterns. Data and Identity roles implement them; Security Posture Management measures coverage. |
| **4. Secure Configuration of Enterprise Assets and Software** | Security Architecture; Infrastructure Security; Development Security; Security Posture Management | Architects establish approved baselines. Technology owners test, implement, and operate configurations. Automation Engineers scale enforcement. Security Posture Management measures conformance, drift, exceptions, and risk. |
| **5. Account Management** | Access and Identity; Security Posture Management | Access Architects define account lifecycle patterns. Identity roles and application/platform owners implement provisioning, review, and deprovisioning. Product Owners validate business need. Posture roles measure stale, shared, and unmanaged accounts. |
| **6. Access Control Management** | Access and Identity; Security Architecture | Accountable business and technology owners approve access requirements. Access Architects define policy patterns. Identity, Network, Application, Data, and Infrastructure roles enforce least privilege and separation of duties. Posture and audit roles validate effectiveness. |
| **7. Continuous Vulnerability Management** | Security Posture Management; Infrastructure Security; Development Security | Security Posture Management prioritizes vulnerability and attack-path risk. Infrastructure/Platform, User Endpoint, Software Security Engineering, and development roles remediate. Product Owners make authorized tradeoffs and fund durable fixes. |
| **8. Audit Log Management** | SecOps/SOC; Security Architecture; technical engineering and operations | Security Architects and Detection Engineers define telemetry requirements. Technology owners enable and protect logs. SecOps Platform and Data Engineers collect, normalize, retain, and monitor data. Triage and Investigation Analysts use it during operations. |
| **9. Email and Web Browser Protections** | Infrastructure Security; Access and Identity; SecOps/SOC | User Productivity and Support, User Endpoint, Identity, and Security Engineer roles implement protections. Detection Engineers and analysts monitor abuse and tune detections. Security Education and Engagement reduces human-targeted risk. |
| **10. Malware Defenses** | Infrastructure Security; SecOps/SOC | User Endpoint, Infrastructure/Platform, and Security Engineer roles deploy and maintain prevention controls. Detection Engineers tune detections. Triage, Investigation, Threat Hunting, and Reverse Engineering roles investigate and respond. |
| **11. Data Recovery** | Business Management and Operations; Infrastructure Security; Data Security; SecOps/SOC | Product Line Managers/Directors and Product Owners set recovery priorities and acceptable service impact. Infrastructure/Platform and Data roles implement protected recovery capabilities and test restoration. SecOps/SOC coordinates recovery after attacks. |
| **12. Network Infrastructure Management** | Infrastructure Security; Access and Identity; Security Architecture | Network and Infrastructure roles maintain supported assets and secure configurations. Access and Infrastructure Architects define segmentation, management, and administrative-access patterns. Posture roles measure exposure and drift. |
| **13. Network Monitoring and Defense** | SecOps/SOC; Infrastructure Security | Network roles provide enforceable control points and telemetry. SecOps Platform and Data Engineers integrate signals. Detection Engineers, Threat Hunters, Triage, and Investigation Analysts detect and respond to threats. |
| **14. Security Awareness and Skills Training** | Strategy, Integration, and Governance | Security Education and Engagement designs role-specific learning. Human Resources and Organizational Readiness/Training integrate it into workforce processes. Leaders reinforce expected behavior and accountability. Managers verify that people have the skills required for assigned responsibilities. |
| **15. Service Provider Management** | Strategy, Integration, and Governance; Security Architecture | Cyber Supply Chain Risk Management, Procurement and Acquisition, Legal, Product Owners, and architects identify requirements, evaluate providers, establish contract and assurance expectations, and monitor material provider risk. |
| **16. Application Software Security** | Development Security; Security Architecture | Software/Application Architects and Software Security Engineers define secure design and engineering requirements. Developers, Software Testers, Software Testing/Quality Managers, and DevOps Leads implement and verify them throughout the lifecycle. |
| **17. Incident Response Management** | SecOps/SOC; Strategy, Integration, and Governance; cross-functional disciplines | Incident Coordination and Management maintains plans and coordinates response. Analysts, hunters, forensics, reverse engineering, and technical owners investigate and contain. Business leaders, Legal, Communications/Public Relations, Human Resources, and other partners execute authorized business actions. |
| **18. Penetration Testing** | SecOps/SOC; Security Architecture; Security Posture Management | Attack Simulation roles plan and conduct authorized testing. Architects and technology owners interpret findings and remediate systemic issues. Security Posture Management tracks risk reduction and recurrence. Accountable owners approve scope and risk treatment. |

This table identifies the primary SAF work and role actions. Use the applicable CIS Safeguards as the authoritative requirements and assign local accountability through SAF roles.

## Map CIS Benchmark work to SAF roles

Use the applicable CIS Benchmark as the configuration source. SAF helps assign configuration work across the roles responsible for the technology and its security. Security and technology architects establish the baseline, Product Owners and other accountable leaders provide business context and approve risk decisions, and engineering and operations roles implement and maintain the configuration. Security Posture Management measures conformance and drift, SecOps/SOC roles investigate related security events, and compliance and audit roles validate applicable obligations and evidence.