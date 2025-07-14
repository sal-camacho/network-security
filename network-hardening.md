# Activity Overview

Following a major data breach, a social media organization has uncovered four critical network vulnerabilities. This report analyzes those issues and proposes key hardening tools and methods to strengthen the organization’s security posture and prevent future incidents.

You are a security analyst working for a social media organization. The organization recently experienced a major data breach, which compromised the safety of their customers’ personal information, such as names and addresses. Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future. 

After inspecting the organization’s network, you discover four major vulnerabilities. The four vulnerabilities are as follows:

The organization’s employees' share passwords.

The admin password for the database is set to the default.

The firewalls do not have rules in place to filter traffic coming in and out of the network.

Multifactor authentication (MFA) is not used. 

If no action is taken to address these vulnerabilities, the organization is at risk of experiencing another data breach or other attacks in the future. 

In this activity, you will write a security risk assessment to analyze the incident and explain what methods can be used to further secure the network.

---
## My Contributions
### Part 1: Recommended Hardening Tools & Methods

#### Tools
- **Multi-Factor Authentication (MFA):**  
  Requires two or more verification methods (e.g., passwords, fingerprints, OTPs), adding depth to identity validation.

- **Password Policies:**  
  Enforce complexity, uniqueness, rotation schedules (e.g., every 90 days), and lockout thresholds to deter brute force attacks.

- **Firewall Maintenance:**  
  Regular rule reviews and traffic filtering prevent unauthorized access and block suspicious activity.

#### Methods
- **Security Information and Event Management (SIEM):**  
  Monitors network-wide activity for anomalies and supports incident response. Enables daily inspection and analysis of logs.

- **Operating System (OS) Hardening:**  
  Applies secure configuration settings, reduces attack surfaces, and enforces access control across hosts.

- **Network Hardening:**  
  Includes port filtering, encryption standards, and access privilege management to secure traffic and limit unauthorized exposure.

### Part 2: Justification of Recommendations

- **MFA** reduces attack surface by requiring more than just a password, which helps block brute force and minimizes internal misuse.
- **Password Policies** address multiple vulnerabilities: shared credentials, default passwords, and weak login behavior. Regular updates (every 90 days) support secure access.
- **Firewall Maintenance** ensures rules are aligned with evolving threats. Daily monitoring allows the team to act swiftly when network behavior deviates.
- **SIEM tools** give visibility into unusual patterns, allowing analysts to inspect incidents in real time and trace breach timelines.
- **OS Hardening** builds a foundation of security by eliminating default settings and tightening administrative controls.
- **Network Hardening** reinforces perimeter defense by restricting traffic and protecting encrypted channels.

---

## Screenshot — Home Asset Inventory Overview
![Home Asset Inventory](images/home-asset-inventory
