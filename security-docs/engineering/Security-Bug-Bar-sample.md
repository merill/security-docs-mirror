---
layout: Conceptual
title: SDL Security Bug Bar (Sample) | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/security/engineering/security-bug-bar-sample
uhfHeaderId: MSDocsHeader-Security
breadcrumb_path: /security/breadcrumb/toc.json
feedback_system: Standard
feedback_help_link_type: ''
ms.author: raynew
author: rayne-wiselman
description: This document outlines the basic criteria to consider when creating security processes, and serves as an example of a security bug bar as recommended within the SDL practices information found at https://microsoft.com/sdl.
ms.date: 2025-03-12T00:00:00.0000000Z
ms.service: security
ms.topic: sample
locale: en-us
document_id: 6ebb06fd-fea2-1e18-c83f-b7209a897b76
document_version_independent_id: 6ebb06fd-fea2-1e18-c83f-b7209a897b76
original_content_git_url: https://github.com/MicrosoftDocs/security-pr/blob/live/security-docs/engineering/Security-Bug-Bar-sample.md
site_name: Docs
depot_name: MSDN.security-docs
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.security-docs/{branchName}{pdfName}
feedback_product_url: ''
feedback_help_link_url: ''
asset_id: engineering/security-bug-bar-sample
moniker_range_name: 
monikers: []
item_type: Content
source_path: security-docs/engineering/Security-Bug-Bar-sample.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/cbe4ca68-43ac-4375-aba5-5945a6394c20
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/ced846cc-6a3c-4c8f-9dfb-3de0e90e2742
platformId: 958ca8ee-07c0-b7ea-7d1b-e823e118de85
---

# SDL Security Bug Bar (Sample) | Microsoft Learn

**Note:** This sample document is for illustration purposes only. The content presented below outlines basic criteria to consider when creating security processes. It is not an exhaustive list of activities or criteria and should not be treated as such.

Please refer to the definitions of terms in this section.

## Server

| Server |
Please refer to the Denial of Service Matrix for a complete matrix of server DoS scenarios.

The server bar is usually not appropriate when user interaction is part of the exploitation process. If a Critical vulnerability exists only on server products, and is exploited in a way that requires user interaction and results in the compromise of the server, the severity may be reduced from Critical to Important in accordance with the NEAT/data definition of extensive user interaction presented at the start of the client severity pivot.
| --- |
| Critical | Server summary: Network worms or *unavoidable* cases where the server is “owned.”<br><br>- Elevation of privilege: The ability to either execute arbitrary code *or* obtain more privilege than authorized<br><br>    - Remote anonymous user<br><br>        - Examples:<br><br>            - Unauthorized file system access: arbitrary writing to the file system<br>            - Execution of arbitrary code<br>            - SQL injection (that allows code execution)<br>    - All write access violations (AV), exploitable read AVs, or integer overflows in remote anonymously callable code |
| Important | Server summary: Non-default critical scenarios or cases where mitigations exist that can help *prevent* critical scenarios.<br><br>- Denial of service: Must be "easy to exploit" by sending a small amount of data or be otherwise quickly induced<br><br>    - Anonymous<br><br>        - Persistent DoS<br><br>            - Examples:<br><br>                - Sending a single malicious TCP packet results in a Blue Screen of Death (BSoD)<br>                - Sending a small number of packets that causes a service failure<br>        - Temporary DoS with amplification<br><br>            - Examples:<br><br>                - Sending a small number of packets that causes the system to be unusable for a period of time<br>                - A web server (like IIS) being down for a minute or longer<br>                - A *single remote client* consuming all available resources (sessions, memory) on a server by establishing sessions and keeping them open<br>    - Authenticated<br><br>        - Persistent DoS ***against a high value asset***<br><br>            - Example:<br><br>                - Sending a small number of packets that causes a service failure for a ***high value asset*** in server roles (certificate server, Kerberos server, domain controller), such as when a domain-authenticated user can perform a DoS on a domain controller<br><br><br>- Elevation of privilege: The ability to either execute arbitrary code *or* to obtain more privilege than intended<br><br>    - Remote authenticated user<br>    - Local authenticated user (Terminal Server)<br><br>        - Examples:<br><br>            - Unauthorized file system access: arbitrary writing to the file system<br>            - Execution of arbitrary code<br>    - All write AVs, exploitable read AVs, or integer overflows in code that can be accessed by remote or local authenticated users that are not administrators (Administrator scenarios do not have security concerns by definition, but are still reliability issues.)<br>- Information disclosure (targeted)<br><br>    - Cases where the attacker can locate and read information *from anywhere* on the system, including system information that was not intended or designed to be exposed<br><br>        - Examples:<br><br>            - Personally identifiable information (PII) disclosure<br><br>                - Disclosure of PII (email addresses, phone numbers, credit card information)<br>                - Attacker can collect PII without user consent or in a covert fashion<br>- Spoofing<br><br>    - An entity (computer, server, user, process) is able to masquerade ***as a*****specific entity** (user or computer) of his/her choice.<br><br>        - Examples:<br><br>            - Web server uses client certificate authentication (SSL) improperly to allow an attacker to be identified as any user of his/her choice<br>            - New protocol is designed to provide remote client authentication, but flaw exists in the protocol that allows a malicious remote user to be seen as a different user of his or her choice<br>- Tampering<br><br>    - Modification of any ***“high value asset”*** data in ***a common or default scenario*** where the modification persists after restarting the affected software<br>    - Permanent or persistent modification of any user or system data used ***in a common or default scenario***<br><br>        - Examples:<br><br>            - Modification of application data files or databases in a common or default scenario, such as authenticated SQL injection<br>            - Proxy cache poisoning in a common or default scenario<br>            - Modification of OS or application settings without user consent in a common or default scenario<br>- Security features: Breaking or bypassing any security feature provided. Note that a vulnerability in a security feature is rated “Important” by default, but the rating may be adjusted based on other considerations as documented in the SDL bug bar.<br><br>    - Examples:<br><br>        - Disabling or bypassing a firewall without informing users or gaining consent<br>        - Reconfiguring a firewall and allowing connections to other processes |
| Moderate | - Denial of service<br><br>    - Anonymous<br><br>        - Temporary DoS without amplification in a default/common install.<br><br>            - Example:<br><br>                - ***Multiple remote clients*** consuming all available resources (sessions, memory) on a server by establishing sessions and keeping them open<br>    - Authenticated<br><br>        - Persistent DoS<br><br>            - Example:<br><br>                - Logged in Exchange user can send a specific mail message and crash the Exchange Server, and the crash is **not** due to a write AV, exploitable read AV, or integer overflow<br>        - Temporary DoS with amplification in a default/common install<br><br>            - Example:<br><br>                - Ordinary SQL Server user executes a stored procedure installed by some product and consumes 100% of the CPU for a few minutes<br>- Information disclosure (targeted)<br><br>    - Cases where the attacker can easily read information on the system *from **specific locations***, including system information, which was not intended/ designed to be exposed.<br><br>        - Example:<br><br>            - Targeted disclosure of anonymous data<br>            - Targeted disclosure of the existence of a file<br>            - Targeted disclosure of a file version number<br>- Spoofing<br><br>    - An entity (computer, server, user, process) is able to masquerade as a different, random entity that cannot be specifically selected.<br><br>        - Example:<br><br>            - Client properly authenticates to server, but server hands back a session from another random user who happens to be connected to the server at the same time<br>- Tampering<br><br>    - Permanent or persistent modification of any user or system data ***in a specific scenario***<br><br>        - Examples:<br><br>            - Modification of application data files or databases ***in a specific scenario***<br>            - Proxy cache poisoning ***in a specific scenario***<br>            - Modification of OS/application settings without user consent ***in a specific scenario***<br>    - Temporary modification of data in a common or default scenario that does not persist after restarting the OS/application-/session<br>- Security assurances:<br><br>    - A security assurance is either a security feature or another product feature/function that customers expect to offer security protection. Communications have messaged (explicitly or implicitly) that customers can rely on the integrity of the feature, and that’s what makes it a security assurance. Security bulletins will be released for a shortcoming in a security assurance that undermines the customer’s reliance or trust.<br><br>        - Examples:<br><br>            - Processes running with normal “user” privileges cannot gain “admin” privileges unless admin password/credentials have been provided via intentionally authorized methods.<br>            - Internet-based JavaScript running in Internet Explorer cannot control anything the host operating system unless the user has explicitly changed the default security settings. |
| Low | - Information disclosure (untargeted)<br><br>    - Runtime information<br><br>        - Example:<br><br>            - Leak of random heap memory<br>- Tampering<br><br>    - Temporary modification of data *in a specific scenario* that does not persist after restarting the OS/application |

## Client

| Client |Extensive user action is defined as:
- "User interaction" can only happen in client-driven scenario.
- Normal, simple user actions, like previewing mail, viewing local folders, or file shares, are not extensive user interaction.
- "Extensive" includes users manually navigating to a particular website (for example, typing in a URL) or by clicking through a yes/no decision.
- "Not extensive" includes users clicking through e-mail links.
- **NEAT** qualifier (*applies to warnings only*). Demonstrably, the UX is:

    - **N**ecessary (Does the user really need to be presented with the decision?)
    - **E**xplained (Does the UX present all the information the user needs to make this decision?)
    - **A**ctionable (Is there a set of steps users can take to make good decisions in both benign and malicious scenarios?)
    - **T**ested (Has the warning been reviewed by multiple people, to make sure people understand how to respond to the warning?)
- **Clarification:** Note that the effect of extensive user interaction is not one level reduction in severity, but is and has been a reduction in severity in certain circumstances where the phrase extensive user interaction appears in the bug bar. The intent is to help customers differentiate fast-spreading and wormable attacks from those, where because the user interacts, the attack is slowed down. This bug bar does not allow you to reduce the Elevation of Privilege below Important because of user interaction.
| --- |
| Critical | Client summary:<br><br>- Network Worms or *unavoidable* common browsing/use scenarios where the client is “owned” **without** warnings or prompts.<br>- Elevation of privilege (remote): The ability to either execute arbitrary code *or* to obtain more privilege than intended<br><br>    - Examples:<br><br>        - Unauthorized file system access: writing to the file system<br>        - Execution of arbitrary code without extensive user action<br>        - All write AVs, exploitable read AVs, stack overflows, or integer overflows in remotely callable code (***without*** extensive user action) |
| Important | Client summary:<br><br>- Common browsing/use scenarios where client is “owned” **with** warnings or prompts, or via extensive actions without prompts. Note that this does not discriminate over the quality/usability of a prompt and likelihood a user might click through the prompt, but just that a prompt of some form exists.<br>- Elevation of privilege (remote)<br><br>    - Execution of arbitrary code *with* extensive user action<br><br>        - All write AVs, exploitable read AVs, or integer overflows in ***remote*** callable code (***with*** extensive user action)<br>- Elevation of privilege (local)<br><br>    - Local low privilege user can elevate themselves to another user, administrator, or local system.<br><br>        - All write AVs, exploitable read AVs, or integer overflows in **local** callable code<br>- Information disclosure (targeted)<br><br>    - Cases where the attacker can locate and read information on the system, including system information that was not intended or designed to be exposed.<br>    - Example:<br><br>        - Unauthorized file system access: reading from the file system<br>        - Disclosure of PII<br><br>            - Disclosure of PII (email addresses, phone numbers)<br>        - Phone home scenarios<br>- Denial of service<br><br>    - System corruption DoS requires re-installation of system and/or components.<br><br>        - Example:<br><br>            - Visiting a web page causes registry corruption that makes the machine unbootable<br>    - Drive-by DoS<br><br>        - Criteria:<br><br>            - Un-authenticated System DoS<br>            - Default exposure<br>            - No default security features or boundary mitigations (firewalls)<br>            - No user interaction<br>            - No audit and punish trail<br>            - Example:<br><br>                - Drive-by Bluetooth system DoS or SMS in a mobile phone<br>- Spoofing<br><br>    - Ability for attacker to present a UI that is different from but visually identical to the UI that users *must rely on to make valid trust decisions* in a *default/common scenario*. A trust decision is defined as any time the user takes an action believing some information is being presented by a particular entity—either the system or some specific local or remote source.<br><br>        - Examples:<br><br>            - Displaying a different URL in the browser’s address bar from the URL of the site that the browser is actually displaying in a ***default/common scenario***<br>            - Displaying a window over the browser’s address bar that looks identical to an address bar but displays bogus data in a ***default/common scenario***<br>            - Displaying a different file name in a “Do you want to run this program?” dialog box than that of the file that will actually be loaded in a ***default/common scenario***<br>            - Display a “fake” login prompt to gather user or account credentials<br>- Tampering<br><br>    - Permanent modification of any user data or data used to make trust decisions in a common or default scenario that persists after restarting the OS/application.<br><br>        - Examples:<br><br>            - Web browser cache poisoning<br>            - Modification of significant OS/application settings without user consent<br>            - Modification of user data<br>- Security features: Breaking or bypassing any security feature provided<br><br>    - Examples:<br><br>        - Disabling or bypassing a firewall with informing user or gaining consent<br>        - Reconfiguring a firewall and allowing connection to other processes<br>        - Using weak encryption or keeping the keys stored in plain text<br>        - AccessCheck bypass<br>        - Bitlocker bypass; for example not encrypting part of the drive<br>        - Syskey bypass, a way to decode the syskey without the password |
| Moderate | - Denial of service<br><br>    - Permanent DoS requires cold reboot or causes Blue Screen/Bug Check.<br><br>        - Example:<br><br>            - Opening a Word document causes the machine to Blue Screen/Bug Check.<br>- Information disclosure (targeted)<br><br>    - Cases where the attacker can read information on the system *from known locations*, including system information that was not intended or designed to be exposed.<br><br>        - Examples:<br><br>            - Targeted existence of file<br>            - Targeted file version number<br>- Spoofing<br><br>    - Ability for attacker to present a UI that is different from but visually identical to the UI that users *are accustomed to trust* in *a specific scenario*. "Accustomed to trust" is defined as anything a user is commonly familiar with based on normal interaction with the operating system or application but does not typically think of as a "trust decision."<br><br>        - Examples:<br><br>            - Web browser cache poisoning<br>            - Modification of significant OS/application settings without user consent<br>            - Modification of user data |
| Low | - Denial of service<br><br>    - Temporary DoS requires restart of application.<br><br>        - Example:<br><br>            - Opening a HTML document causes Internet Explorer to crash<br>- Spoofing<br><br>    - Ability for attacker to present a UI that is different from but visually identical to the UI *that is a single part of a bigger attack scenario*.<br><br>        - Example:<br><br>            - User has to go a “malicious” web site, click on a button in spoofed dialog box, and is then susceptible to a vulnerability based on a different browser bug<br>- Tampering<br><br>    - Temporary modification of any data that does not persist after restarting the OS/application.<br>    - Information disclosure (untargeted)<br><br>        - Example:<br><br>            - Leak of random heap memory |

## Definition of Terms

**authenticated** Any attack which has to include authenticating by the network. This implies that logging of some type must be able to occur so that the attacker can be identified.

**anonymous** Any attack which does not need to authenticate to complete.

**client** Either software that runs locally on a single computer or software that accesses shared resources provided by a server over a network.

**default/common** Any features that are active out of the box or that reach more than 10 percent of users.

**scenario** Any features that require special customization or use cases to enable, reaching less than 10 percent of users.

**server** Computer that is configured to run software that awaits and fulfills requests from client processes that run on other computers.

**Critical** A security vulnerability that would be rated as having the highest potential for damage.

**Important** A security vulnerability that would be rated as having significant potential for damage, but less than Critical.

**Moderate** A security vulnerability that would be rated as having moderate potential for damage, but less than Important.

**Low** A security vulnerability that would be rated as having low potential for damage.

**targeted information disclosure** Ability to intentionally select (target) desired information.

**temporary DoS** A temporary DoS is a situation where the following criteria are met:

- The target cannot perform normal operations due to an attack.
- The response to an attack is roughly the same magnitude as the size of the attack.
- The target returns to the normal level of functionality shortly after the attack is finished. The exact definition of "shortly" should be evaluated for each product.

For example, a server is unresponsive while an attacker is constantly sending a stream of packets across a network, and the server returns to normal a few seconds after the packet stream stops.

**temporary DoS with amplification**

A temporary DoS with amplification is a situation where the following criteria are met:

- The target cannot perform normal operations due to an attack.
- The response to an attack is magnitudes beyond the size of the attack.
- The target returns to the normal level of functionality after the attack is finished, but it takes some time (perhaps a few minutes).

For example, if you can send a malicious 10-byte packet and cause a 2048k response on the network, you are DoSing the bandwidth by amplifying our attack effort.

**permanent DoS**

A permanent DoS is one that requires an administrator to start, restart, or reinstall all or parts of the system. Any vulnerability that automatically restarts the system is also a permanent DoS.

## Denial of Service (Server) Matrix

| **Authenticated vs. Anonymous attack** | **Default/Common vs. Scenario** | **Temporary DoS vs. Permanent** | **Rating** |
| --- | --- | --- | --- |
| Authenticated | Default/Common | Permanent | Moderate |
| Authenticated | Default/Common | Temporary DoS with amplification | Moderate |
| Authenticated | Default/Common | Temporary DoS | Low |
| Authenticated | Scenario | Permanent | Moderate |
| Authenticated | Scenario | Temporary DoS with amplification | Low |
| Authenticated | Scenario | Temporary DoS | Low |
| Anonymous | Default/Common | Permanent | Important |
| Anonymous | Default/Common | Temporary DoS with amplification | Important |
| Anonymous | Default/Common | Temporary DoS | Moderate |
| Anonymous | Scenario | Permanent | Important |
| Anonymous | Scenario | Temporary DoS with amplification | Important |
| Anonymous | Scenario | Temporary DoS | Low |

**Content Disclaimer**

| *This documentation is not an exhaustive reference on the SDL practices at Microsoft. Additional assurance work may be performed by product teams (but not necessarily documented) at their discretion. As a result, this example should not be considered as the exact process that Microsoft follows to secure all products. *<br><br>*This documentation is provided “as-is.” Information and views expressed in this document, including URL and other Internet website references, may change without notice. You bear the risk of using it. *<br><br>*This documentation does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes. *<br><br>*© 2018 Microsoft Corporation. All rights reserved.*<br><br>*Licensed under*[Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported](https://creativecommons.org/licenses/by-nc-sa/3.0/) |
| --- |