---
title: "When the Cloud Fails: Inside Microsoft's Azure Outage and Its Far-Reaching Impact"
date: 2024-07-19T20:39:12+05:30
draft: false
cover:
    image: /cyber-security/microsoft-global-outage/blue_screen.jpeg
    alt: "Blue Screen of Death"
tags: ["Microsoft","Outage","Incident Response"]
categories: ["Technology"]
showTOC: false
author: "Sai Kiran Reddy Appidi"
---
***

[//]: # (# When the Cloud Fails: Inside Microsoft's Azure Outage and Its Far-Reaching Impact)


## Unraveling the Incident

On July 18, 2024, at 9:56 PM UTC, Microsoft Azure, one of the world's leading cloud computing platforms, experienced a significant outage. This disruption had widespread effects on Microsoft 365 apps and services, leaving users around the globe struggling to access essential tools like Microsoft Teams, PowerBI, and the Microsoft 365 admin center.

## Root Cause Analysis

In their official statement, Microsoft acknowledged the issue and attributed it to a configuration change in Azure's backend workloads. This change disrupted the connectivity between storage and compute resources in the Central US region. This resulted in the compute resources automatically restarting when connectivity was lost to virtual disks hosted on impacted storage resources leading to connectivity failures and service interruptions across various Microsoft 365 services.

## CrowdStrike's Role

CrowdStrike’s software, Falcon, caused a major disruption due to a faulty update. This update led to widespread IT system failures, impacting banks, airlines, and other industries globally. CrowdStrike quickly identified the issue, rolled back the update, and provided steps for affected Windows users to delete the problematic file and restore their systems. This incident highlighted the deep system access required by security software and the potential impact of faulty updates.  **The update conflicted with Microsoft’s Azure cloud services, particularly affecting Windows Virtual Machines (VMs) running the CrowdStrike Falcon agent.**

## The Impact: A Global Ripple Effect

The ripple effect of the Azure outage was felt across continents, affecting a diverse range of industries. Here's a detailed look at how it impacted specific sectors:

### Airlines

1. **United Airlines:**
    - **Grounded Flights:** The outage caused significant disruptions to United Airlines' flight operations. Many flights were grounded due to system failures, leading to widespread passenger inconvenience and operational delays.

2. **American Airlines:**
    - **Flight Delays and Cancellations:** American Airlines faced numerous delays and cancellations. The disruption affected their scheduling systems, causing a flight backlog and a surge in passenger queries and complaints.

3. **Delta Airlines:**
    - **Operational Disruptions:** Delta Airlines experienced similar issues with flight operations. The IT outage hindered their ability to manage flight schedules and passenger information systems effectively.

4. **Ryanair (UK):**
    - **Advisory for Early Arrivals:** Ryanair advised passengers to arrive early at airports due to potential delays caused by the IT outage. The airline's check-in and boarding systems were significantly impacted, causing long queues and frustrated travelers.

_And here is a tweet from IndiGo, an Indian airline, addressing the flight cancellations due to the worldwide travel system outage:_
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Flights are cancelled due to the cascading effect of the worldwide travel system outage, beyond our control. The option to rebook/claim a refund is temporarily unavailable. To check the cancelled flights, visit <a href="https://t.co/D1sAKR5Hhl">https://t.co/D1sAKR5Hhl</a>. We truly appreciate your patience &amp; support.</p>&mdash; IndiGo (@IndiGo6E) <a href="https://twitter.com/IndiGo6E/status/1814245981254189260?ref_src=twsrc%5Etfw">July 19, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

_And another tweet from a passenger sharing their experience with handwritten boarding passes due to the outage:_
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">The Microsoft / CrowdStrike outage has taken down most airports in India. I got my first hand-written boarding pass today 😅 <a href="https://t.co/xsdnq1Pgjr">pic.twitter.com/xsdnq1Pgjr</a></p>&mdash; Akshay Kothari (@akothari) <a href="https://twitter.com/akothari/status/1814202068531552666?ref_src=twsrc%5Etfw">July 19, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### Banks and Financial Institutions

1. **Australian Banks:**
    - **Offline Services:** Several Australian banks reported that their online services went offline. This disruption affected online banking, ATMs, and self-service kiosks, causing inconvenience to customers and operational challenges for the banks.

2. **New Zealand Banks:**
    - **Similar Issues:** Banks in New Zealand faced comparable disruptions. Customers experienced difficulties accessing online banking services, leading to increased traffic at physical branches and heightened frustration.

### Media Broadcasters

1. **Sky News (UK):**
    - **Broadcasting Struggles:** Sky News faced significant challenges in broadcasting. The IT issues disrupted their ability to deliver news updates and live broadcasts, impacting their viewership and operational efficiency.

### Indian Offices

- **Operational Impact:** Numerous offices in India experienced disruptions. The outage affected business operations, with employees unable to access essential tools and services, leading to delays in project timelines and decreased productivity.

### Telecommunications Providers

- **Widespread Disruptions:** Telecommunications companies across various regions reported service interruptions. Customers faced difficulties accessing mobile networks, internet services, and customer support, highlighting the outage's extensive impact on communication infrastructure.

### Visa and ADT Security

1. **Visa:**
    - **Service Outages:** Visa, a global payment processing giant, experienced outages that affected transaction processing and cardholder services. This disruption cascaded effect on merchants and consumers relying on Visa's network.

2. **ADT Security:**
    - **Operational Challenges:** ADT Security, a provider of security solutions, faced operational challenges due to the outage. The disruption impacted their monitoring and response systems, affecting their ability to provide timely security services.

### Amazon

- **Operational Challenges:** Even Amazon, a leader in e-commerce and cloud computing, faced significant challenges. The outage affected their cloud services and e-commerce platforms, causing delays in order processing, inventory management, and customer service operations.

## Impacted Services

The outage impacted several critical services, including:
- **PowerBI**: Transitioned to read-only mode.
- **Microsoft Fabric**: Also switched to read-only mode.
- **Microsoft Teams**: Users faced issues with presence, group chats, and user registration.
- **Microsoft 365 Admin Center**: Admins encountered intermittent access issues, delaying actions.

However, some services like Microsoft Defender, OneDrive for Business, SharePoint Online, and Windows 365 recovered more swiftly and were reported stable post-incident.


## Microsoft's Response

Microsoft's immediate response involved:
- **Mitigation Actions**: Swift actions to reroute affected traffic and restore connectivity.
- **Monitoring and Updates**: Continuous monitoring of telemetry data to ensure service recovery and stability.
- **Communication**: Regular updates to users and administrators about the status of the recovery efforts.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">We&#39;re aware of an issue with Windows 365 Cloud PCs caused by a recent update to CrowdStrike Falcon Sensor software. This is being communicated under WP821561 in the admin center. (Cont...)</p>&mdash; Microsoft 365 Status (@MSFT365Status) <a href="https://twitter.com/MSFT365Status/status/1814250844319060219?ref_src=twsrc%5Etfw">July 19, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## What Happened with CrowdStrike? and The Solution

### The Incident

- **Faulty Update:** On July 19, 2024, a fault with an update issued by cybersecurity company CrowdStrike led to a cascade effect among global IT systems, affecting industries from banking to airlines.
- **Global Impact:** Banks, healthcare providers, TV broadcasters, and airlines faced disruptions. Planes were grounded, services were delayed, and businesses grappled with the ongoing outage.
- **Blue Screen of Death:** Users worldwide encountered the "blue screen of death" due to an update from CrowdStrike's Falcon product, designed to stop cyber breaches using cloud technology.

### CrowdStrike's Response

- **Identifying the Problem:** CrowdStrike’s engineering team quickly identified that the recent content deployment was responsible for the issues.
- **Reverting Changes:** CrowdStrike reverted the problematic update globally. Reverting involves rolling back to a previous state before the new deployment, effectively undoing the changes that caused the disruption.

_Here is a tweet from CrowdStrike CEO George Kurtz addressing the incident:_
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Today was not a security or cyber incident. Our customers remain fully protected.<br><br>We understand the gravity of the situation and are deeply sorry for the inconvenience and disruption. We are working with all impacted customers to ensure that systems are back up and they can…</p>&mdash; George Kurtz (@George_Kurtz) <a href="https://twitter.com/George_Kurtz/status/1814316045185822981?ref_src=twsrc%5Etfw">July 19, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### What is CrowdStrike and What Does it Do?

- **Endpoint Security:** CrowdStrike is a cybersecurity vendor that develops software to help companies detect and block hacks. It is used by many Fortune 500 companies, including major global banks, healthcare, and energy companies.
- **Cloud Technology:** CrowdStrike uses cloud technology to apply cyber protections to devices connected to the internet, differing from other approaches that protect back-end server systems.
- **Deep System Access:** CrowdStrike’s software requires deep access to a computer’s operating system to scan for threats.

### Resolution Steps for Users

For affected Windows users, CrowdStrike provided clear and actionable steps to resolve the issue:

1. **Boot into Safe Mode:** Users were instructed to boot their Windows systems into Safe Mode, a diagnostic mode that starts the computer with minimal drivers and services.
2. **Navigate to CrowdStrike Directory:** In Safe Mode, users need to navigate to the directory where CrowdStrike files are stored.
3. **Delete the Problematic File:** Users were advised to delete the file identified as causing the issue.
4. **Boot Normally:** After deleting the problematic file, users can reboot their systems normally.

### Further Explanation and Challenges

- **Privileged Access:** Security software like CrowdStrike needs privileged access to machines to protect organizations, which can lead to significant issues when updates go wrong.
- **Microsoft's Statement:** Microsoft confirmed the problem was with the CrowdStrike update, not Windows itself. They advised customers to reach out to CrowdStrike for additional assistance.
- **CEO’s Update:** CrowdStrike CEO George Kurtz emphasized it was not a security incident or cyberattack. The issue was identified, and isolated, and a fix was deployed.

### Complex Recovery Process

Implementing the fix involves:

- **Manual Intervention:** Engineers must go into each data center running Windows, login, navigate to the CrowdStrike file, delete it, and reboot the system.
- **Encryption Challenges:** For machines with complex encryption, keys need to be entered manually, making the recovery process more challenging.
## Current Status

### Updated as of July 19, 2024

- **03:41 UTC on 19 July 2024:** Microsoft confirmed mitigation efforts for computing resources.
- **03:41 - 12:15 UTC on 19 July 2024:** Services affected by the outage began to recover progressively. Engineers from the respective teams intervened to perform manual recovery where necessary.
- **Post 12:15 UTC:** Following an extended monitoring period, Microsoft determined that impacted services had returned to their expected availability levels. The company continues to closely monitor the situation to prevent any further disruptions.

## Financial Impact

CrowdStrike’s shares dropped by nearly 16.8%, falling to ``$285.49`` in pre-market trading. Microsoft’s stock also slipped around 2.3%, declining to ``$430.28``. The outage not only impacted Microsoft's direct revenue streams from Azure and Microsoft 365 services but also had a significant ripple effect on the businesses and industries dependent on these platforms.

## Conclusion

The July 2024 Microsoft Azure outage serves as a stark reminder of the vulnerabilities inherent in our interconnected digital infrastructure. However, it also highlights the importance of robust crisis management and the resilience of cloud service providers in addressing and mitigating such issues. As Microsoft works towards full recovery, this incident will undoubtedly prompt a reevaluation of best practices and safeguards to prevent future occurrences.

---

## Author:

<div id="authorCard" style="display: flex;align-items: center">
    <img src="/authors/saikiran_appidi.jpeg" alt="Author Image" style="float: left; width: 100px; height: 100px;margin-right: 10px">
    <a href="https://www.linkedin.com/in/saikiranreddyappidi/" target="_blank" style="margin-left: 5%; display: block;">Sai Kiran Reddy Appidi</a>
</div>

---