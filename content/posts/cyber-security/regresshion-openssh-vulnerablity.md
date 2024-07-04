---
title: "regreSSHion: A Critical Vulnerability in OpenSSH (CVE-2024-6387)"
date: 2024-07-04T22:13:16+05:30
draft: false
cover:
    image: /cyber-security/regreSSHion-openssh-vulnerability/regresshion-vulnerablity-1.png
    alt: "RegreSSHion-OpenSSH Vulnerability-cover image"
tags: ["OpenSSH","regreSSHion","Vulnerability"]
categories: ["Cyber security","Learn","Technology"]
showTOC: false
author: "Lokesh Koppineedi"
---
***

## What is CVE-2024-6387?

CVE-2024-6387, dubbed "regreSSHion," is a severe vulnerability in OpenSSH that allows remote code execution with root privileges. This vulnerability is a regression of CVE-2006-5051, reintroduced in OpenSSH 8.5p1 and present until 9.7p1.

## Status and Discovery
<div style="position: relative;width: 100%;padding-top: 56.25%;margin-bottom: 5%">
  <img src="/cyber-security/regreSSHion-openssh-vulnerability/regresshion-vulnerablity-2.jpg" alt="RegreSSHion-OpenSSH Vulnerability" style="position:absolute;top: 0;left: 0;width: 100%;height: 100%;object-fit: cover">
</div>
Discovered by Qualys Threat Research Unit (TRU) and disclosed on July 1, 2024, CVE-2024-6387 was highlighted by the Ubuntu Security Team due to incorrect signal management handling in OpenSSH.

## Impact and Risk Assessment

The severity of CVE-2024-6387 lies in its potential to:
- **Compromise Entire Systems**: Attackers can install malware, steal data, and disrupt services.
- **Bypass Authentication**: Unauthorized access to systems is possible.
- **Remote Code Execution**: Attackers can execute arbitrary code with root privileges.

## Affected Versions and Operating Systems

- **OpenSSH Versions**: 8.5p1 to 9.7p1
- **Operating Systems**: Unix-like systems, including Ubuntu, Debian, Fedora, CentOS, and BSD variants.

## Exploitation Scenario
<img src="/cyber-security/regreSSHion-openssh-vulnerability/Command-and-Control-Communication.png">

<span ><center>_Figure: Command and Control (C2) Communication_
</center></span>

### Overview
An attacker can remotely exploit a vulnerability in OpenSSH by sending specially crafted packets to the server. This exploitation is possible without any authentication, making it highly risky as it allows for remote code execution with root access.

### Steps in the Exploitation

1. **Identification**:
    - The attacker identifies a target system running a vulnerable version of OpenSSH.

2. **Crafting Malicious Packets**:
    - The attacker crafts specific packets designed to exploit the race condition in the OpenSSH signal handler.

3. **Sending Packets**:
    - The attacker sends these crafted packets to the OpenSSH server. These packets are designed to manipulate the timing of the signal handler, causing it to mishandle memory or other resources.

4. **Triggering the Vulnerability**:
    - By repeatedly sending these crafted packets, the attacker triggers the race condition, leading to memory corruption or other unexpected behaviors in the OpenSSH process.

5. **Gaining Access**:
    - Successful exploitation of the vulnerability allows the attacker to execute arbitrary code on the server. Since the vulnerability permits unauthenticated access, the attacker can gain root privileges.

6. **Post-Exploitation**:
    - With root access, the attacker can perform various malicious actions, such as installing backdoors, stealing sensitive data, or further compromising the network.

## Mitigation

1. **Update OpenSSH**: Apply the latest patches from OpenSSH.
2. **Configure SSHD**: Set `LoginGraceTime` to 0 in `/etc/ssh/sshd_config` to mitigate the vulnerability (at the cost of potential denial-of-service from MaxStartups exhaustion).
3. **Network Security**: Use firewalls and intrusion detection systems.

### Detailed Steps for Applying SSHD Configuration

1. **Open a terminal and execute the following command**:
   ```sh
   echo "LoginGraceTime 0" | sudo tee /etc/ssh/sshd_config.d/cve-2024-6387.conf
   ```

2. **Reload the SSH service to apply the changes**:
   ```sh
   sudo systemctl reload ssh.service
   ```
## Additional Context and Developments

### Rigorous Security Process

[//]: # (OpenSSH is developed with the same rigorous security process that the OpenBSD group is famous for. To report a security issue, contact the private developers list at <openssh@openssh.com>. More information is available on the [OpenBSD security page]&#40;https://www.openbsd.org/security.html&#41;.)

OpenSSH is developed with the same rigorous security process that the OpenBSD group is famous for. To report a security issue, contact the private developers list at <openssh@openssh.com>. More information is available on the <a href="https://www.openbsd.org/security.html" target="_blank">OpenBSD security page</a>.

### Race Condition in SIGALRM Handling Code

The issue stems from a race condition in the `sshd(8)` signal management code. This can lead to remote code execution on non-OpenBSD systems. Disabling the login grace timeout (`LoginGraceTime=0` in `sshd_config`) can prevent this attack but makes denial-of-service attacks easier.

### Logic Error in ObscureKeystrokeTiming Option

Another related issue affects OpenSSH versions 9.5p1 to 9.7p1, where a logic error in the `ObscureKeystrokeTiming` option exposes limited keystroke timing information. Disabling this feature (`ObscureKeystrokeTiming=no`) can avoid this issue.

### Key Takeaways

- **Critical Threat**: Unauthenticated remote code execution with root privileges.
- **Wide Impact**: Affects numerous Unix-like operating systems.
- **Urgent Mitigation**: Update OpenSSH and configure security settings.

## Conclusion

[//]: # (CVE-2024-6387 is a critical vulnerability that underscores the importance of keeping systems updated and implementing robust security measures. Immediate action to update OpenSSH and enhance network security is crucial to protect against this threat. For more detailed information, refer to the [Ubuntu Security Notice]&#40;https://ubuntu.com/security/notices/USN-6859-1&#41; and other relevant resources.)
CVE-2024-6387 is a critical vulnerability that underscores the importance of keeping systems updated and implementing robust security measures. Immediate action to update OpenSSH and enhance network security is crucial to protect against this threat. For more detailed information, refer to the <a href="https://ubuntu.com/security/notices/USN-6859-1" target="_blank">Ubuntu Security Notice</a> and other relevant resources.

[//]: # (- Stay informed and proactive to defend against threats like CVE-2024-6387. For more details, refer to the [Qualys Security Advisory]&#40;https://www.qualys.com/2024/07/01/cve-2024-6387/regresshion.txt&#41; and the official [CVE Record]&#40;https://www.cve.org/CVERecord?id=CVE-2024-6387&#41;.)
- Stay informed and proactive to defend against threats like CVE-2024-6387. For more details, refer to the <a href="https://www.qualys.com/2024/07/01/cve-2024-6387/regresshion.txt" target="_blank">Qualys Security Advisory</a> and the official <a href="https://www.cve.org/CVERecord?id=CVE-2024-6387" target="_blank">CVE Record</a>.

---

## Author:

<div id="authorCard" style="display: flex;align-items: center">
    <img src="/authors/lokesh_koppineedi.JPG" alt="Author Image" style="float: left; width: 100px; height: 100px;margin-right: 10px">
    <a href="https://www.linkedin.com/in/k-lokesh-7716ab233/" target="_blank" style="margin-left: 5%; display: block;">Lokesh Koppineedi</a>
</div>

---